---
Title: 902-1-8 Caching
Creation date: 14.03.2023 18:13
Modification date: Tuesday 14th March 2023 18:13:53
Author: MKraus
Tags: 
- spring
- moc 
- schulung
- caching
Type:
---
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]

- [[#902-1-8 Caching|902-1-8 Caching]]
		- [[#Spring Caching|Spring Caching]]
		- [[#Weitere SpEL Variablen|Weitere SpEL Variablen]]
		- [[#Cachable + unless|Cachable + unless]]
		- [[#KeyGenerator|KeyGenerator]]
		- [[#CacheConfig|CacheConfig]]
		- [[#Cache in Test abschalten|Cache in Test abschalten]]


# 902-1-8 Caching 

Wann immer wir Dinge beziehen die "teuer" sind. 
Es muss aber sichergestellt werden das Werte auch cachable sind. (Idempotenz).

```ad-caution
title: Vorbedingung
Für jeden Eintrag muss ein Key vorhanden sein, der eindeutig ist. (z.B. `SimpleKeyGenerator`)

Unter einem Cache kann man sich so was wie eine `ConcurrentHashMap` Vorstellen ,

```


Z.B. Bilder

```ad-danger
title: Muss man wissen:
Wenn in einer Klasse mehrere Methoden mit @Cachable vorhanden sind, die sich gegenseitig aufrufen, wird **kein** neuer Proxy / Cache erzeugt.

Der Proxy wird nur aufgebaut, wenn man von ausserhalb der Klasse die Methoden aufruft. 

!! Das gilt auch für andere Proxies.

```



> [!Hinweis] Caching Enablen
> Das wird mit `@EnableCaching` gemacht.
> Dann wird ein `Proxy` von Spring erzeugt. siehe [[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-7 Proxys|902-1-7 Proxys]] 


Man kann sich dann gut vorstellen, das `@Scheduler` dann z.B. eine Cache nach einer bestimmten Zeit **löschen**.

### Spring Caching 

Spring bietet eine Abstraktion mit den folgenden Annotations:
- `@EnableCaching`
- `@Cachable`
- `@CacheEvict`
- `@CachePut`
- `@CacheRemove`
- `@Caching`
- `@CacheConfig`

```ad-hint
title: Hint: Usage
Automatisch wird ein Cache nichts machen, alles wird über Methoden gesteuert die mit Annotationen versehen werden. Dabei wird dann geschaut ob ein Result gecached ist oder noch nicht. Im letzteren Fall wird dann die Daten geladen und in den Cache geschoben.

Das bedeutet aber auch , das wenn die die Klasse mit dem Cache nutzen, wird nicht die Klasse sondern ein Proxy bereitgestellt. (Siehe dann in Debug (CGLIB) :-))
`log.info(classInstance.getClass().getName());`

```


```ad-attention
title: Attention: SpEL
Hint: SpEL ist auch möglich..

z.B. 
```java
// Wobei dann das Objekt im Parameter analysiert wird. Hier `List<Long>` (.size())
@Cachable(cacheNames="some.cache", condition = "#ids.size() > 10"
public String hotAsYaml(List<Long> ids)
```

```


### Sample Code

```java
@Component
class HotProfileToYamlConverter {
	private final Logger log = LoggerFactory.getLogger(getClass());

	@Cacheable("some.name") (1) (2)
	// @CacheEvict(cacheNames = "some.name") (3)
	public String hotAsYaml(List<Long> ids) {  (4)
		log.info("Generating YAML for list {}", ids);
		return new Yaml().dump(Map.of("trendy", ids));
	}
}
```

(1) = Sollen Methodenergebnisse im Cache landen, bzw aus dem Cache kommen, wird die Methode mit `@Cacheable` annotiert.
(2) = Jeder Cache hat einen Namen. Wird keiner genommen so wird wie in Spring üblich der Methodenname verwendet.
(3) = Annotationsattribut `value` und `cacheNames` sind `Alias`
(4) = Die Methoden müssen (standardmäßig) `public` sein, das gilt auch für andere `Proxys`

### Weitere SpEL Variablen

- `#root.method`, `#root.target`,  `#root.caches`
- `#root,methodName`, `#root.targetClass`
- `#root.args[0]`, `#p0`, `#a0` oder einfach `#Parametername`

siehe [Spring Doc](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/cache/annotation/Cacheable.html#condition--)


### Cachable + unless

Mit `unless` kann man eine Bedingung angeben, die wenn erfüllt sicher stellt, das das Ergebnis  **nicht**  in den Cache aufgenommen wird.

Code:
```java
// Hier ist die Bedingung nicht erfüllt, also aufnehmen in den Cache
@Cacheable(cacheNames = "some.cache",
			unless = "false")
			
```

### KeyGenerator

Es wie immer in Spring möglich einen Key selber zu erzeugen, siehe `KeyGenerator`


```java
/**  
 * Sample custom key generator. */public class CustomKeyGenerator implements KeyGenerator {  
  
  
    @Override  
    public Object generate(Object target, Method method, Object... params) {  
        //if (params.length == 0) {
	    //    return SimpleKey.EMPTY;
        //}
        
        return target.getClass().getSimpleName() + "_" + method.getName() + "_"  
                + StringUtils.arrayToDelimitedString(params, "_");  
    }  
}
```

Man kann aber auch das folgende nutzen. 

```java
 @Cachable(cacheNames = "some.cache", key = "#prof.id")
 Object method(Profile prof)
```

Damit wird dann auch ein Key erzeugt.. 
z.B. ISBN Nummer bei einem Buch :-) 

### CacheConfig

Mit einer `@CacheConfig` kann an einer Klasse z.B. ein CacheName bereitstellen. Das kann dann an der jeweiligen Methode überschrieben werden.

### Cache in Test abschalten

Optionen:
- `spring.cache.type=NONE`
- `@Bean public CacheManager cacheManager() {return new NoOpCacheManager();}`
- Mit Profiles arbeiten
- Im Test properties bereitstellen `@SpringBootTest(properties={"spring.cache.type=none"}`

siehe auch [Baeldung override properties in Test](https://www.baeldung.com/spring-tests-override-properties)

