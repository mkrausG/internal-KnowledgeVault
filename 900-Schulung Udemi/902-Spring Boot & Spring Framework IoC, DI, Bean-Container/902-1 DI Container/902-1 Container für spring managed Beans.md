---
Topic: Container für spring managed Beans
Creation date: 09.02.2023 18:28
Modification date: Thursday 9th February 2023 18:29:08
Course: Udemy
Class:
Author: MKraus
Tags: 
- spring
- moc 
- schulung 
Id:
---

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-0-Spring Boot & Spring Framework IoC, DI, Bean-Container-MOC|Schulung Udemy]]

## TOC

- [[#Questions/Cues|Questions/Cues]]
- [[#Spring Container Managed Beans|Spring Container Managed Beans]]
	- [[#Spring Container Managed Beans#Application|Application]]
- [[#`@ComponentScan` mit basePackages|`@ComponentScan` mit basePackages]]
	- [[#`@ComponentScan` mit basePackages#includeFilters|includeFilters]]
	- [[#`@ComponentScan` mit basePackages#exceludeFilters|exceludeFilters]]
	- [[#`@ComponentScan` mit basePackages#@ComponentScan.Filter|@ComponentScan.Filter]]
- [[#Runner|Runner]]
	- [[#Runner#Commandlinerunner / Applicationrunner|Commandlinerunner / Applicationrunner]]
- [[#Exit / Beenden von Programmen|Exit / Beenden von Programmen]]
	- [[#Exit / Beenden von Programmen#Exception-Klassen implementieren.|Exception-Klassen implementieren.]]
	- [[#Exit / Beenden von Programmen#ExitCodeExceptionMapper|ExitCodeExceptionMapper]]
	- [[#Exit / Beenden von Programmen#ApplicationPID[FileWriter]|ApplicationPID[FileWriter]]]
- [[#Spring Shell|Spring Shell]]
	- [[#Spring Shell#Konfiguration|Konfiguration]]
- [[#Optionale Tätigkeiten|Optionale Tätigkeiten]]

### Questions/Cues
- Item

### Spring Container Managed Beans

#### Application

Es gibt mehrere Wege eine Spring Applikation zu starten.

1. MIt Application.run

1. SpringApplication instanziieren

```java
SpringApplication app = new SpringApplication(xxxx.class);
app.setHeadless(false); // kein AWT laden (GUI)
app.setBannerMode(Banner.Mode.OFF);
.....
app.run(args);
```

1. SpringApplicationBuilder
   
```java
    new SpringApplicationBuilder(xxx.class)
        .headless(false)
        .web(false)
        .run(args);
```

  

Der `ConfigurableApplicationContext` ist der eigentliche DI Container.

![[Resources/Udemy/springDIIco/2023-02-06-21-41-38.png]]

Application erweitert ListableBeanFactory. (Bean zugriffe)

see: [ListableBeanFactory](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/beans/factory/ListableBeanFactory.html)

```java
String[] getBeanDefinitionNames()
```

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

#### exceludeFilters

- Ausschließen von Typen

#### @ComponentScan.Filter
- includeFilter und excludeFilter sind vom Typ ComponentScan.Filter[]
- Der Filter enthält einen FilterTypen nach z.B. Basistypen, RegExAusrücken
- Der Standard ist FilterType.ANNOTATION

**Beispiele:**

**Annotation:**

![[Resources/Udemy/springDIIco/2023-02-06-22-02-37.png]]

**RegEx:**
  
![[Resources/Udemy/springDIIco/2023-02-06-22-03-42.png]]

**Custom:**
  
![[Resources/Udemy/springDIIco/2023-02-06-22-04-34.png]]

### Runner
Drei übliche Wege zum Starten eigener Anwendungen sind:
  1. Man reagiert auf ein Event nach dem Start des Containers
  1. Man holt sich eine eigene Bean aus dem Kontext und ruft eine Objectmethode auf
  1. Man implementiert einen Applicationrunner oder CommandlineRunner

#### Commandlinerunner / Applicationrunner
- Implementieren SPring-Managed-Beans die Schnittstellen `ApplicationRunner` oder `COmmandlineRunner` führt der Container sie automatisch nach dem Hochfahren aus.
- Das ist praktisch für eigene Kommandozeilenprogramme.
- Es können mehrere *Runner vorhanden sein, die Programcode am Anfang starten. Die Reihenfolge kann mit `@Order` bestimmen.
- 💥 Vorteil an `ApplicationRunner` ist, dass man Methoden hat um die Argumente zu bearbeiten / lesen
  
### Exit / Beenden von Programmen

Exit Code => steht für EXIT_SUCCESSS, alle anderen Wertei für Fehler.
Unter Dos heißt der ExitCode auch `errorLevel`.

```java
System.exit(-1);
```

ABER für Spring sollte man SpringApplication exit() nutzen da:
- controlled shutdown
- Context wird geschlossen
  
```java
@Autowired
private ApplicationContext ctx;
...
System.exit(SpringApplication.exit(ctx, () -> 2)); // return 2 as exitCode
```

#### Exception-Klassen implementieren.

![[Resources/Udemy/springDIIco/2023-02-06-22-16-20.png]]

#### ExitCodeExceptionMapper
![[Resources/Udemy/springDIIco/2023-02-06-22-16-44.png]]

#### ApplicationPID[FileWriter]
![[Resources/Udemy/springDIIco/2023-02-06-22-17-53.png]]

### Spring Shell
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-2 JShell|JShell]]

### Optionale Tätigkeiten 
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-1 Optionale Abhängigkeiten|  Optionale Abhängigkeiten]]