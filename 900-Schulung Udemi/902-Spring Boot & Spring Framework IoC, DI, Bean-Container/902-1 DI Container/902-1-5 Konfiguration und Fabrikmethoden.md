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
- [[#`@Resources`|`@Resources`]]

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

Das ist ein Typ den man als Parameter (z.B. Constructor  in einer @Bean factory method) übergeben kann. Über den `InjectionPoint` kann dann die Factory Methode erfahren wer, also welcher `InjectionPoint` jetzt vorhanden ist und kann dann entscheiden wie die Bean ggf aufgebaut / initialisiert werden.

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
Import muss nicht in Spring benötigt, da ClassPathScanning das automatisch bereitstellt.
ABER
Wenn die Beans in anderen Paketen / Namespaces als in dem eigenen Namespace liegen muss entweder `@Import` oder `ClassPathScanning` angepasst werden :-)

### ImportSelector

Mit einem `ImportSelector` kann man eine Möglichkeit zur Verfügung stellen, das unterschieden wird welche Bean dann bereitgestellt wird.
D.h. wir haben ein interface das 2 **unterschiedliche** Implementierungen bereitstellen.
Mit dem ImportSelector wird dann unterschieden welche Implementierung bereitgestellt wird.

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
> Dabei aber YAGNI beachten. Es kann auch eine Direkte Implementierung (also ohne Interface) verwendet werden, wenn nur eine Implementierung dafür geplant ist :-) Aber besser wäre es mit Interfaces zu arbeiten, da ein Austauschen einfacher wäre.
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
5. Nach Namen gehen (d.h. variable so benennen wie Komponenten Namen nur starting lowercase) (! ist aber nicht so sauber)

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

Diese Kennzeichnung ist wie @Autowired die eine Resource bereitstellt ABER  `@Resource` stellt bewusst einen `Namen` höher bewertet. d.h.`@Resource(name = "xx")`

```ad-warning
Diese Annotation kann nicht bei Ctor wiring eingesetzt werden, nur bei Settern mit einem Parameter
```

### `ObjectProvider`

ObjectProvider wird ähnlich wie `Optional` verwendet.