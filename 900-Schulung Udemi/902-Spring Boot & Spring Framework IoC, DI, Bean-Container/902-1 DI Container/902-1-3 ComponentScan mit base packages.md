---
Title: 902-3 ComponentScan mit base packages
Creation date: 12.02.2023 17:57
Modification date: Sunday 12th February 2023 19:02:13
Class:
Author: MKraus
Tags: 
- spring
- moc 
- schulung 
- componentscan
Id:
---

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]

# TOC

- [[#`@ComponentScan` mit basePackages|`@ComponentScan` mit basePackages]]
	- [[#`@ComponentScan` mit basePackages#includeFilters|includeFilters]]
	- [[#`@ComponentScan` mit basePackages#excludeFilters|excludeFilters]]
	- [[#`@ComponentScan` mit basePackages#@ComponentScan.Filter|@ComponentScan.Filter]]
		- [[#@ComponentScan.Filter#Annotation:|Annotation:]]
			- [[#Annotation:#Alternativ mit statisch importierten ComponenScan.Filter:|Alternativ mit statisch importierten ComponenScan.Filter:]]
		- [[#@ComponentScan.Filter#RegEx:|RegEx:]]
		- [[#@ComponentScan.Filter#Custom:|Custom:]]



### `@ComponentScan` mit basePackages


- Über `basePackages` lassen sich Wurzelverzeichnisse für das Classpath-Scanning setzen.

  - Fehlt die Angabe, bildet das Packet von der `@ComponentScan` annotierten Klasse die Wurzel

- Folgende Schreibweisen sind gleichbedeutend.
  
```java
@Configuration
@ComponentScan(basePackages = {"com.tutego.date4u.core",
"com.tutego.date4u.interfaces"})

// Besser ist aber
@ComponentScan(basePackageClass = {A.class, B.class})
...

@Configuration
@ComponentScan ({"com.tutego.date4u.core",
"com.tutego.date4u.interfaces"})
...
@Configuration
@ComponentScan("com.tutego.date4u.core","com.tutego.date4u.interfaces")
```
  
#### includeFilters

= includeFilters = einschließen Typen

#### excludeFilters

- Ausschließen von Typen

#### @ComponentScan.Filter
- `includeFilter` und `excludeFilter` sind vom Typ `ComponentScan.Filter[]`
- Der Filter enthält einen FilterTypen nach z.B. Basistypen, RegExAusrücken
- Der Standard ist FilterType.ANNOTATION

**Beispiele:**

##### Annotation:

Nur Klassen erkennen, die mit xxxx annotiert sind:

```java
@Configuration
@ComponentScan(
	useDefaultFilters = false,
	includeFilters = @ComponentScan.Filter( x1
			// type = FilterType.ANNOTATION,
			classes = { xxxx.class} )) x2
class SomeClass			
```

> x1 = FilterType.ANNOTATION ist der default
> x2 = classes ist ein Alias für `value`

###### Alternativ mit statisch importierten ComponenScan.Filter:

```java
@Configuration
@ComponentScan(
	useDefaultFilters = false,
	includeFilters = @Filter( xxxx.class)) 
class SomeClass			
```


##### RegEx:

Mit REGEX lässt sich über ein regulärer Ausdruck auf der Basis der einfachen und voll qualifizierten Typnamen filtern.

Alle Typen mit der Endung `New` oder `Old` sollen eingebunden werden, aber nicht xxxx.

```java
@Configuration
@ComponentScan(
	useDefaultFilters = false,
	includeFilters = @Filter(
		type = FilterType.REGEX, pattern = ".*(New|Old)"),
	excludeFilters = @Filter(
		type = FilterType.ASSIGNABLE_TYPE,
		classes = { xxxx.class})
class SomeClass			
```

> [!info]
> 
Spring nutzt intern Pattern und Matcher und keine Ant-Matcher.

##### Custom:
Über FilterType .CUSTOM können komplett eigene Filter gesetzt werden; die Filter Implementieren TypeFilter.

```java
class MyTypeFilter implements TypeFilter {
	@Override
	public boolean match( MetaDataReader metadataReder,
						  MetaDataReaderFactory, metadataReaderFactory) {
		ClassMetaData classMetaData = metaDataReader.getClassMetaData();
		...  
		}
}

@Configuration
@ComponentScan(
	useDefaultFilters = false,
	includeFilters =  @Filter(
		type = FilterType.CUSTOM,
		classes = MyTypeFilter.class)
)
```


