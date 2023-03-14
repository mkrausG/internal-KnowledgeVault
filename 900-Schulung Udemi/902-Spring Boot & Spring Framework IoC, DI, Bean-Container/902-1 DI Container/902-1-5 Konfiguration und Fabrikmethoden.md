---
Title: 902-1-5 Konfiguration und Fabrikmethoden
Creation date: 14.02.2023 18:29
Modification date: Tuesday 14th February 2023 18:29:38
Author: MKraus
Tags: 
- spring
- moc 
- schulung
- configuration
Type:
---

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]

# 902-1-5 Konfiguration und Fabrikmethoden

# Toc

- [[#Was '@Component' nicht kann|Was '@Component' nicht kann]]
	- [[#Was '@Component' nicht kann#Lösung|Lösung]]
- [[#'@Configuration' and '@Bean'|'@Configuration' and '@Bean']]
- [[#Diverse Typen als Bean erlaubt|Diverse Typen als Bean erlaubt]]
- [[#InjectionPoint|InjectionPoint]]
	- [[#InjectionPoint#Beispiel "Random" für CryptoAnnotation sicher bereitstellen|Beispiel "Random" für CryptoAnnotation sicher bereitstellen]]
		- [[#Beispiel "Random" für CryptoAnnotation sicher bereitstellen#Eine eigene Annotation CryptographicallyStrong bereitstellen|Eine eigene Annotation CryptographicallyStrong bereitstellen]]
		- [[#Beispiel "Random" für CryptoAnnotation sicher bereitstellen#Injezierungstellen|Injezierungstellen]]
			- [[#Injezierungstellen#Vor einer Variable|Vor einer Variable]]
			- [[#Injezierungstellen#Über einer Methode|Über einer Methode]]
			- [[#Injezierungstellen#Vor einem Parameter|Vor einem Parameter]]
		- [[#Beispiel "Random" für CryptoAnnotation sicher bereitstellen#Beispiel wie nun InjectionPoint genutzt wird|Beispiel wie nun InjectionPoint genutzt wird]]
- [[#Import , Import-Selektor|Import , Import-Selektor]]
	- [[#Import , Import-Selektor#ImportSelector|ImportSelector]]
- [[#Abstraktion / Qualifizierung / Namen|Abstraktion / Qualifizierung / Namen]]
	- [[#Abstraktion / Qualifizierung / Namen#Injizierung auf Basis des Typs|Injizierung auf Basis des Typs]]
		- [[#Injizierung auf Basis des Typs#Lösung wenn mehrere Beans mit einem Interface bereitgestellt werden.|Lösung wenn mehrere Beans mit einem Interface bereitgestellt werden.]]
	- [[#Abstraktion / Qualifizierung / Namen#`@Resources`|`@Resources`]]
	- [[#Abstraktion / Qualifizierung / Namen#`ObjectProvider`|`ObjectProvider`]]
	- [[#Abstraktion / Qualifizierung / Namen#@Order / @AutoconfigurationOrder|@Order / @AutoconfigurationOrder]]
	- [[#Abstraktion / Qualifizierung / Namen#@Bean Methoden|@Bean Methoden]]
	- [[#Abstraktion / Qualifizierung / Namen#Annotation @Inherited|Annotation @Inherited]]
- [[#Lebenszyklus der Beans|Lebenszyklus der Beans]]
	- [[#Lebenszyklus der Beans#Annotations im Lebenszyklus|Annotations im Lebenszyklus]]
	- [[#Lebenszyklus der Beans#Callback Methoden alternative (BeanPostProcessor )|Callback Methoden alternative (BeanPostProcessor )]]
- [[#Autokonfiguration (Magic :-))|Autokonfiguration (Magic :-))]]
	- [[#Autokonfiguration (Magic :-))#ProxyBeanMethods|ProxyBeanMethods]]
	- [[#Autokonfiguration (Magic :-))#Interfaces|Interfaces]]
	- [[#Autokonfiguration (Magic :-))#Autokonfiguration ausschließen|Autokonfiguration ausschließen]]
	- [[#Autokonfiguration (Magic :-))#Ausschalten Konfiguration|Ausschalten Konfiguration]]
	- [[#Autokonfiguration (Magic :-))#Individuelle Konfiguration|Individuelle Konfiguration]]
- [[#Spring Startzeiten reduzieren|Spring Startzeiten reduzieren]]
	- [[#Spring Startzeiten reduzieren#Component Index|Component Index]]
	- [[#Spring Startzeiten reduzieren#Functional Bean Definition|Functional Bean Definition]]
- [[#Externe Konfigurationen  / Application Properties / Property Sources|Externe Konfigurationen  / Application Properties / Property Sources]]
	- [[#Externe Konfigurationen  / Application Properties / Property Sources#PropertyResolver|PropertyResolver]]
	- [[#Externe Konfigurationen  / Application Properties / Property Sources#Statische Werte über @Value injizieren|Statische Werte über @Value injizieren]]
	- [[#Externe Konfigurationen  / Application Properties / Property Sources#Dynamische Werte über @Value injizieren|Dynamische Werte über @Value injizieren]]
	- [[#Externe Konfigurationen  / Application Properties / Property Sources#Configuration-Properties|Configuration-Properties]]
	- [[#Externe Konfigurationen  / Application Properties / Property Sources#Relaxed Binding (Namenskonvertierungen der Properties)|Relaxed Binding (Namenskonvertierungen der Properties)]]
	- [[#Externe Konfigurationen  / Application Properties / Property Sources#Profile|Profile]]
- [[#Events|Events]]
	- [[#Events#Spring events|Spring events]]
		- [[#Spring events#ApplicationListener:|ApplicationListener:]]
		- [[#Spring events#EventListener:|EventListener:]]
		- [[#Spring events#Publishing Events|Publishing Events]]
		- [[#Spring events#Subscribe to events|Subscribe to events]]
		- [[#Spring events#Generische Events|Generische Events]]
	- [[#Events#Resource|Resource]]
		- [[#Resource#Laden|Laden]]
- [[#Konverter (Typ-)|Konverter (Typ-)]]
	- [[#Konverter (Typ-)#Beispielkonvertierungen|Beispielkonvertierungen]]
	- [[#Konverter (Typ-)#Lokalisierte Übersetzung|Lokalisierte Übersetzung]]
- [[#Hilfsklassen|Hilfsklassen]]
	- [[#Hilfsklassen#Packet: `org.springframework.util`|Packet: `org.springframework.util`]]
	- [[#Hilfsklassen#Paket:  `org.springframework.data.util`|Paket:  `org.springframework.data.util`]]



## Was '@Component' nicht kann

- Abhängig von Zuständen Beans erzeugen.
- Instanzen von Klassen, die nicht mit @Component annotiert sind.

### Lösung
* Fabrikmethoden nutzen (== Java Annotation und  @Bean)

## '@Configuration' and '@Bean' 

```java
@Configuration 
public class MyOwnBeanFactory {
	@Bean
	Foo bean_name_is_method_name() {return ...}
	@Bean
	Bar another_factory_method() {return ...}
}
```

> [!info]
> 
> '@SpringBootApplication' ist eine '@Configuration'

## Diverse Typen als Bean erlaubt
Es sind nicht nur komplexe Objekte (Klassen) die verwaltet, bzw. in den Context gebracht werden können-

> [!tip]
> 
Naming von Beans beachten...
und natürlich '@Lazy'

Hier ein Beispiel wie man Strings, Arrays, und Listen bereitstellen kann.

```java
 @Bean String name() {
	 return "Fillmore";
 }

@Bean String[] names() {
	return new String[] {"Fillmore","juicyLucy"};
}

@Bean List<String> namesList() {
	return List.op("fillmore","juicyLucy");
}

@Bean UUID appUUid() {
	UUID uuid = UUID.randomUUID();
	log.info("uuid -> {}", uuid);
	return uuid;
}

// Instanziieren

@Autowired String name;
@Autowired String[] names;
@Autowired List<String> namesList;
@Autowired UUID appUUId;
```

## InjectionPoint

Das ist ein Typ den man als Parameter (z.B. Constructor  in einer @Bean factory method) übergeben kann. 
Über den `InjectionPoint` kann dann die Factory Methode erfahren wer, also welcher `InjectionPoint` jetzt vorhanden ist und kann dann entscheiden wie die Bean ggf aufgebaut / initialisiert werden.

> [!caution]
> 
Das bedeutet das wir `Reflection` informationen über den Aufrufer bekommen

![[Resources/InjectionPoint PackageOverview.png]]

### Beispiel "Random" für CryptoAnnotation sicher bereitstellen 
Hinweis: Wir wollen eine Bean "Random" bereitstellen die für die Annotation `CryptographicallyStrong` ein besonderen Random Typ `CryptoStrongRandom` bereitstellen .

1. [[#Eine eigene Annotation CryptographicallyStrong bereitstellen]]
2. Überlegen, welche Injezierungstellen wir unterstützen 
	1. [[#Injezierungstellen#Vor einer Variable]]
	2. [[#Injezierungstellen#Über einer Methode]]
	3. [[#Injezierungstellen#Vor einem Parameter]]
3. [[#Beispiel wie nun InjectionPoint genutzt wird]]

#### Eine eigene Annotation CryptographicallyStrong bereitstellen 

```java
@Retention (RetentionPolicy.RUNTIME)
@interface CryptographicallyStrong {}
```

#### Injezierungstellen 

##### Vor einer Variable 

```java
@Autowired 
CryptographicallyStrong Random random;
```

##### Über einer Methode

```java
@Autowired
@CryptographicallyStrong
void setRnd(Random random) {...}
```

##### Vor einem Parameter 

```java
@Autowired 
void setRnd(@CryptographicallyStrong Random random)
```



#### Beispiel wie nun InjectionPoint genutzt wird
Hier ein Beispiel wie man nnu den InjectionPoint nutzt um die Annotation zu analysieren und ggf einen speziellen Random Typ erzeugen 

```java
@Bean @Scope (ConfigurableBeanFactory.SCOPE_PROTOTYPE)
public Random random (InjectionPoint injectionPoint ) {
  return nonNull(injectionPoint.getAnnotation(CryptographicallyStrong.class))
      || (InjectionPoint.getMember() instanceOf AnnotatedElement member 
	      && member.isAnnotationPresent(CryptographicallyStrong.class))
	      ? new SecureRandom()
	      : new Random();
}
```

> [!tip]
> 
Die Prüfung kann noch besser geschrieben werden. 
So was wie `boolean isCryptoAnnotationNull = nonNull(InjectionPoint.getAnn....` 

## Import , Import-Selektor

Mit `@Import` kann man andere Konfigurationen wie `@Configurationen` oder `@Component` einbinden.

> [!note]
> 
Import wird eigentlich nicht in Spring benötigt, da ClassPathScanning das automatisch bereitstellt. Eine Außnahme wäre Test / Sliced Tests
ABER
Wenn die Beans in anderen Paketen / Namespaces als in dem eigenen Namespace liegen muss entweder `@Import` oder `ClassPathScanning` angepasst werden :-)

### ImportSelector

Mit einem `ImportSelector` kann man eine Möglichkeit zur Verfügung stellen, das **unterschieden** wird welche Bean dann bereitgestellt wird.
D.h. wir haben ein interface das 2 **unterschiedliche** Implementierungen bereitstellen.
Mit dem `ImportSelector` wird dann unterschieden welche Implementierung bereitgestellt wird.

> [!tip]
> 
Es wird immer ein `String[]` , also "Name" der Klasse zurück gegeben.

```java
static class CoffeeBeansImportSelcetor implements ImportSelector {
  @Override
  public String[] selectImports (AnnotationsMetadata __) {
	  if (Math.random() > 0.5)
		  return new String[] {JavaCoffeeBeansConfig.class.getName()};
	  else
		  return new String[] {BrazilianCoffeeBeansConfig.class.getName()};
  }
}

// Dann
@Configuration 
@Import(CoffeeBeansImportSelector.class)
static class CoffeeDrinker {}
```

## Abstraktion / Qualifizierung / Namen

Jede Bean hat einen Namen und einen weiteren optionalen Namen (**Alias**) 

Hier die Regeln für die Namensgebung:

| Regel             | Namensgebung                                                            |
| ----------------- | ----------------------------------------------------------------------- |
| ohne Namensgebung | kleingeschriebender **ComponentName** oder Name der @Bean-Fabrikmethode |
|                   |                                                                         |

> [!important]
> 
Bei `@Component` gibt es einen Parameter 'value' mit Standart "". Wird ein Value angegeben wird das als `@Bean` Name genutzt.

Beispiel wie man mit DI Container und Naming vorgehen sollte:

> [!important]+ Important YAGNI beachten
> Dabei aber YAGNI beachten. Es kann auch eine Direkte Implementierung (also ohne Interface) verwendet werden, wenn nur eine Implementierung dafür geplant ist :-) Aber besser wäre es mit Interfaces zu arbeiten, da ein Austauschen einfacher wäre. == Inversion of Control
> 

![[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/Name Steps Diagram.svg]]

### Injizierung auf Basis des Typs

Es ist auch möglich generische `@Beans` in einer Factorymethode bereit zu stellen.

```Java
// Bereitstellung von Beans
@Configuration
class SupplierConfiguration() {
	@Bean Supplier<FileSystem> fileSytem() {...
}

...

@Component
class PhotoServiceSupplier implements Supplier<PhotoService>{
	@Override
	public PhotoService get() {...}
}

// Bereitstellung von Beans Done...

...

// Injizierung
@Autowired Supplier<FileSystem> fs;
```

#### Lösung wenn mehrere Beans mit einem Interface bereitgestellt werden.

1. `@Autowired @Qualifier` nutzen .d.h. Namen bereitstellen mit `@Service(value ="dd")` und dan
2. Eigene Annotationstypen bereitstellen
3. `@Primary` bereitstellen
4. Alle Beans in einer Datenstruktur
5. Nach Namen gehen (d.h. variable so benennen wie Komponenten Namen nur starting lowercase) (! ist aber nicht so sauber und schwer zu erkennen im Code) 

Beispiel Code `Eigene AnnotationsTypen bereitstellen`:

```Java
// 1. Neuer Annotationstype mit Kriterium
@Target( {ElementType.FIELD, ElementType.METHOD, ElementType.TYPE,
		  ElementType.PARAMETER, ElementType.ANNOTATION_TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Qualifier
public interface ThumbnailRendering {
	enum RenderingQuality  {FAST, QUALITY}
	RenderingQuality value(); // Parameter
}

// 2. Markieren der Komponenten d.h die Implementierung markieren
// d.h. welchen `Typ` stellt diese Komponente dar .. !!
// d.h. in unserem Fall gäbe es 2 Komponenten ..
@Service
@ThumbnailRendering(ThumbnailRendering.RenderingQuality.FAST)
class AwtNearestNeighborThumbnail implements Thumbnail

// 3. Auswählen, also welche Implmentierung wird hier erwartet.
@Autowired
@ThumbnailRendering( ThumbnailRendering.RenderingQuality.FAST)
Thumbnail thumbnail;
```

Beispiel Code `Alle Beans in einer Datenstruktur`:

```Java
	// 1.ter Service
	@Service
	class AwtBicubicThumbnail implements Thumbnail 
	
	// 2.ter Service
	@Service
	class AwtNearestNeighborThumbnail  implements Thumbnail 

	// Verwendung
	@Service
	class WhatEver {

		@Autowired
		// !! @Qualifier möglich 
		List<Thumbnail> thumbnails // !!!!! Hier wären dann beide o.g. Services bereitgestellt.
		// kann auch Set<Thumbnail> oder Thumbnail[]
		// ❗ mit Map<String, Thumbnail> thumbnails werden komponenten namen mit eingebunden
	}
```

Beispiel `Nach Namen gehen`

```Java
	// 1.ter Service
	@Service
	class AwtBicubicThumbnail implements Thumbnail 
	
	// 2.ter Service
	@Service
	class AwtNearestNeighborThumbnail  implements Thumbnail 

	// Verwendung
	@Autowired Thumbnail awtBicubicThumbnail; // Name der Komponente

```

### `@Resources`

Diese Kennzeichnung ist wie `@Autowired` eine Resource, die eine Resource bereitstellt.
ABER  `@Resource` bezieht sich immer auf den Namen und daher wird  `Namen` höher bewertet. d.h.`@Resource(name = "xx")`

Das bedeutet aber auch im Umkehrschluss, dass `@Resource` immer ein Objekt mit dem Namen auflöst

`@Resource setAA(Object profile)` würde mit Resource dann die Klasse `@Component Profile..` einbinden ABER 💢`@Autowired` würde dann **irgendein** `Object` einbinden, was keinen wirklichen Sinn macht. 

```ad-warning
Diese Annotation kann nicht bei Ctor wiring eingesetzt werden, nur bei Settern mit einem Parameter
```

### `ObjectProvider`

ObjectProvider wird ähnlich wie `Optional` verwendet.

```java
@Autowired
ObjectProvider<Thumbnail> maybeThumbnail; // Kann null oder Bean sein

---- // Später
maybeThumbnail.getIfAvailable() // null oder Bean
maybeThumbnail.getIfAvailable(NoopThumbnail::new) // Erzeugt Default Instanz wenn null
```

> [!info] Info: Zu Beachten
> 
ObjectProvider wird entweder **injiziert** oder mit `getBeanProvider` aus einem Applicationcontext geladen.

```java
// Beispiel 
	ObjectProvider<Thumbnail> maybeThumbnail = ctx.getBeanProvider(Thumbnail.class);
```

> [!danger]
> 
Gibt es bei der Bean Erzeugung Fehler, lösen bis auf `iterator()` und `stream()/orderedStream()` die Methoden eine `BeansException` aus

### @Order / @AutoconfigurationOrder

Spring berücksichtig bei gewissen Operationen die Priorität von Objekten bei @Autowired

* @Order (reguläre Komponenten) => `@Component @Order(123)`
	* Je niedriger der Wert, desto höher die Priorität 
* @AutoConfigurationOrder (Konfigurationsklassen) 

### @Bean Methoden
Oberklassen können `@Bean` Methoden bestitzen

```java
abstract class Thing {
  @Bean UUID uuid() {
	  return UUI.randomUUID();
  }
}
```

### Annotation @Inherited

Prinzipiell können Annotation auf Unterklassen vererbt werden.
ABER nur wenn der Annitationstyp `@java.lang.annotation.Inherited` ist 

## Lebenszyklus der Beans 

Wie ermittelt Spring DI den Baum der Objekte die in welcher Reihenfolge gebaut werden müssen ?

Dadurch das Annotationen und Ctor's gescannt und analysiert werden.

Um manuell Beans bereitstellen einfach `@Component` im Ctor dann `DefaultListableBeanFactory beanFactory` injekten lassen.

[[TODO]]: Beispiel aus Video dann auch implementieren.

### Annotations im Lebenszyklus 
* `@PostConstruct` => wird nach Dependency-Injection aufgerufen, kann auch mehrmals gesetzt werden :-)
* `@PreDestroy` => wird aufgerufen bevor Componente vom Container entfernt werden.
	* 👿Es können auch`JVM Shutdown-Hooks` verwendet werden
* Es gehen hier auch Interfaces die man implementiert, sollte aber nicht mehr genutzt werden 
	* InitializingBean
	* DisposableBean
	* Aware Schnittstellen
		* ApplicationContextAware.setApplicationContexst()
		* BeanNameAware:setEnvironment()
		* BeanClassLoaderAware:setBeanClassLoader
		* ... insgesamt **300** Schnittstellen
		* **BeanPostProcessor**
* `@Bean` => hier `initMethod` und `destroyMethod`
* `@DependsOn`
* `Lazy`
	* Globale settings:
		* Property: `spring.main.lazy-initialization=true`
		* Code: `SpringApplication.setLazyInitialiszation(true);`
* `SPEL`

Beispiel Vererbung der Lebenszyklus-Methoden:

```java
class IOResource {
	@PostContruct
	void init() {}
}

interface Closeable {
	@PreDestroy
	default void close() {}
}

...

@Service
class FileSytem extends IOResource implements Closeable {

}
```



### Callback Methoden alternative (BeanPostProcessor )

Eine Alternative für die Callback Methoden (PostConstruct, Predestroy) ist der `BeanPostProcessor`

Damit können:
* Realisierung von Injezierungen
* Aufrufen von bestimmten Methoden mit werten
* Proxies um Objekte zu bauen
* Starten von Hintergrundoperationen

BeanPostProcessor stellt **Post** und **Pre** Methoden "Initialization" bereit.

## Autokonfiguration (Magic :-))

*Spring Boot* stellt eine Menge von Autokonfiguration bereit.
Dann einfach mal nach **AutoConfigure** in Intellij suchen ;-)

> [!important] Important: Location Autoconfiguration class list (imports)
> 
In dem (jar) Verzeichnis META-INF gibt es ein Unterverzeichnis **spring** mit einer Datei *org.springframework.boot.autoconfigure.AutonConfiguration.imports*
Darin befindet sich eine Aufstellung der Autokonfiguration 


### ProxyBeanMethods 

Es ist möglich ein wenig Magic im Hintergund bei `@Configuration` zu vermeiden. Dazu dann `@Configuration(proxyBeanMethods=false)` nutzen. Das geht aber nur wenn keine Methode in der Klasse sich selbst aufrufen ;-)

siehe [When to use proxy methods](https://stackoverflow.com/questions/61266792/when-to-set-proxybeanmethods-to-false-in-springs-configuration)

### Interfaces 

Hiermit kann gesteuert werden wann welche Bean erzeugt /  genommen wird.

* @Conditional(xxx.class)
	* Hier kann auch eine eigene Klasse vererbt von Condition bereitgestellt werden. Die in @Conditional genutzt wird.
	* Dazu dann noch eine eigene Annotation und dann wird es schön einfach, da wir diese an eine Klasse setzen können.
* @ConditionalOnxxxx

### Autokonfiguration ausschließen

Über Annotation:
`@EnableAutoConfiguration (exclude = {DataSourceAutoConfiguration.class, HibernateJpaAutoConfiguration.class})`

Über z.B. Application.yaml (oder Env :-))

```yaml
spring.autoconfigure.exclude=org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration, DataSourceTransactionManagerAutoConfiguration.class,...
```


### Ausschalten Konfiguration 

Ersetzen von @SpringBootApplication durch
- @SpringBootConfiguration
- @ComponentScan
- weglassen von @EnableAutoConfigurarion

bleiben nur ein paar wenige vorhanden

> Tip: Startzeit reduzieren !!!


### Individuelle Konfiguration 

`@Import({PropertyPlaceholderAutoConfiguration.class,...})`


## Spring Startzeiten reduzieren 

1. Property `spring.main.lazy-initialization=true` <== Nicht in Produktion
2. Component Index erstellen !!
3. Functional bean Definitions !! 
4. EnablAutoConfiguration ausschalten und mit @import arbeiten

### Component Index 

Eine Datei die die Komponenten aufzählt die benötgt werden.

*META-INF/spring.components* mit voll qualifizierten Klassennamen
Spring erkennt diese Datei und erstellt dann kein Classpath scan !!

Mit `spring.index.ignore` kann das ausgeschaltet werden .

Aber wenn das Ein-/Ausgabesystem fix ist, gibt es keinen Unterschied,

### Functional Bean Definition

Alle managed Beans per Hand registieren.

d.h. aus Spring Application eine @Configuration machen (damit kein Scan gemacht wird)
und dann mit ctx.Register... registrieren

## Externe Konfigurationen  / Application Properties / Property Sources

Damit sind Application.properties / .yaml gemeint == Environment

> [!note]
> 
💡 Kommt ein Schlüssel mehrfach vor, gewinnt die letzte Zuweisung.

### PropertyResolver

Mit dem PropertyResolver können wir auf die Properties zugreifen.

```java
env.containsProperty("user.home");
env.getProperty("user.home");
env.getProperty("com.tutego.number-of-seminars",Integer.class);
```

### Statische Werte über @Value injizieren

Einfache Syntax = `@Value("10");`

### Dynamische Werte über @Value injizieren
- Typkonvertierung
- Default Values
- SpEL = # {}

Hinweis: kann auch an private Felder gesetzt werden und es können auch werte aus dem Environment ausgelesen werden die nicht in der Applikation.properties vorhanden ist ;-)

Einfache Syntax = `@Value("${xxx}");`
Mit Default Values = `@Value("${xxx:pmOO}");`
String or Default Null =`@Value("${xxx:#{null}}");` 
SpEL = `#{SpEL}`

Wenn Java > 11 verwendet wird ist es möglich an einem "Record" ein DefaultValue zu setzen = `@DefaultValue`

### Configuration-Properties

Mit `@EnableConfigurationProperts({xxxx.class})` kann man Konfigurationsklassen bereitstellen. Aber wenn viele vorhanden sind, ist das aufwendig.
Daher kann man `@ConfigurationPropertiesScan` oder `@ConfigurationProperties("com.tutego")` / `@PropertySource("classpath:email.properties"` nutzen.

```ad-seealso
title: Location gernerated property metadata json
Die findet man unter /target/classes/META-INF/spring-configuration-metadata.json

```

### Relaxed Binding (Namenskonvertierungen der Properties)

Darunter versteht man eine gewisse Flexibilität beim Mappen der Strings auf die Object-Properties

| Property                     | Type / Format                                         | 
| ---------------------------- | ----------------------------------------------------- |
| com.tutego.numerOfSeminars   | Standard Camel-Case-Syntax                            |
| com.tutego.numer-of-seminars | Kebak-case, empfohlen für properties / yaml FileSytem |
| com.tutego.numer_of_seminars | Snake-case, eine alternative für die Dateien          |
| COM_TUTEGO_NUMEROFSEMINARS   | Großschreibeformat, empfohlen für Umgebungsvariablen  |

Präfix muss immer in Kebab-case sein!

maven use properties = `mvn sprinb-boot:run -Dspring-boot.run.arguments="--arg1=value --arg2=value"`

### Profile 
`dev`,  `test`... sie wie bekannt == application-local.yaml


> [!Wichtig] Default Profile
> 	Das standard Profile ist `default` und wird immer geladen. d.h. application.yaml stellt alles zu verfügung  und die custom profile yaml überschreiben das dann.


Aktivieren = --spring.profiles.active=xxx oder in yaml mit 
```yaml
spring:
	profiles:
		active: "xxx"
```

## Events

Publish subscribe bzw EventBus

Geht auch mit @Async und SpEl

Für mögliche von Spring Events siehe `org.springframework.boot.context.event`

### Spring events 
| Event                                                       | Beschreibung                                                              |
| ----------------------------------------------------------- | ------------------------------------------------------------------------- |
| ContextRefreshedEvent                                       | Initialisieren oder Aktualisieren des ApplicationContexts (ctx.refresh()) |
| ContextStartedEvent                                         | Start des AppContext durch ctx.start()                                    |
| ContextStoppedEvent                                         | Stopp des AppContext durch ctx.stop()                                     |
| ContextClosedEvent                                          | Close des AppContext durch ctx.close()                                    |
| org.springframework.web.context.support.RequestHandledEvent | MVC wenn Request abgeschlossen wurde                                      |


#### ApplicationListener:

```java
@Component
public class MyListener implements ApplicationListener<ContextStartedEvent>
```

#### EventListener:

Ein EventListener kann auch mehrere Events handlen, dazu master Class aufnehmen.
z.b. ApplicationEvent event

```java
@Component
public class MyListener() {
	@EventListener
		public void onContextStartedEvent (ContextStartedEvent e) {
		....
		}
}
```

#### Publishing Events 
Events werden über `ApplicationEventPublisher` gesendet.
Dazu einfach den ApplicationEventPublisher  als Ctor Bean wiren.

```java
// Hier wird nun ein Event gesendet 
NewPhotoEvent newPhotoEvent = new NewPhotoEvent(1,"hallo");
publisher.publishEvent( newPhotoEvent);
```

#### Subscribe to events 

```java
@Service
public class MyService {

	@EventListener
	void onNewPhotoEvent( NewPhotoEvent event) {
	.....
	}

}
```

#### Generische Events 
d.h. nicht immer einen besonderen DatenTyp für die Meldung erzeugen 


### Resource 

nutzt Ant-Style patterns, wie 
z.B. /WEB-INF/*-context*  oder classpath:com/mycomp/**/application.xml (recursiv suchen)

#### Laden

- new ClassPathResource("xxx.csv");
- new DefaultResourceLoader().getResource("classpath:xxx.csv");
- @Autowired ResourceLoader resourceloader;
- @Value... -> @Value ("classpath:"folder/file.txt")

## Konverter (Typ-)

Es gibt automatische Konverter aber man kann auch eigene Konverter einbinden.


> [!Wichtig] Zeiten
> Dazu dann Duration nutzen..

Type von Properties oder Params in MVC [[Invalid date]]

siehe Interface `ConversionService` == org.springframework.core.convert

Standard ist `DefaultConversionService`.

### Beispielkonvertierungen

```java
var converter = new DefaultConversionService();

// {user=chris}
Properties p = converter.convert("user=chris", Properties.class);

// 2022-06-05
LocalDate ld = converter.convert(LocalDateTime.now(), LocalDate.class);

//[1,2,3]
int[] ia = converter.convert("1,2,3", int[].class);

// EUR
Currency c = converter.convert("EUR", Currency.class);

// germany
Locale l = converter.convert("GERMANY", Locale.class);

// DOES NOT WORK
List<Integer> input = List.of(1,2,3);
converter.convert(input, List<String>.class) (1)
```



 (1) `List<String>.class` führt zu einem Compilerfehler. Korrekt wäre List.class aber dann fehlt die Typinformation String.

Lösung = TypeDesriptor


```java
List<String> listOfStrings = (List<String>) converter.convert(input,
TypeDescriptor.forObject(input),
	TypeDescriptior.collection(List.class, TypeDescriptor.valueOf(String.class)));
```



![[Resources/902-1-5 ConverterRegistry.png]]

siehe  [Spring java api](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/convert/converter/Converter.html)
und [Example Implementation](https://github.com/spring-projects/spring-framework/blob/main/spring-core/src/main/java/org/springframework/core/convert/support/StringToUUIDConverter.java)

ConverterFactory = 1:N Konvertierung (Hirachie von Typen)

code:

```java
// Usage .. Input wird ein "c:\xxx\ooo\" sein, den wir in ein Path umwandeln wollen
@ShellMethod(.....)
public boolean exists(Path path)


// Custom Converter 
class StringToPathConverter implements Converter<String, Path> {

	@Override
	public Path convert(String source){
		return Path.of(source);
	}
}
```

### Lokalisierte Übersetzung
Printer: für das formatieren (Object -> String)
Parser: für das parsen (String -> Object)

d.h. Converter betrachtet keine Locale... Nur typen

## Hilfsklassen

- NonNull 
- NonNullApi
- NonNullFields
- Nullable
- usw

### Packet: `org.springframework.util`
- `MultiValueMap<K,V>` (Schnittstelle). Assoziiert einen Schlüssel mit einer Liste von Werten 
- `Assert`. Überprüft Methodenparameter auf Ihre Gültigkiet
- `FileCopyUtils` + `StreamUtils`
- `StringUtils's`

### Paket:  `org.springframework.data.util` 

- `Optionals`
- `Streamable<T>` -  Method return value :-)
- `StreamUtils`
- `Lazy<T>`

Beispiel Streamable 
```java
Iterable<Path> directories = FileSystems.getDefault().getRootDirectories();
Set<String> strings = 
	Streamable.of(directories)
		.map( String::valueOf )
		.and("cloud")
		.toSet();
System.out.println(strings); // [cloud, P:\, C:\]
```

