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
- [[#Runner|Runner]]
	- [[#Runner#Commandlinerunner / Applicationrunner|Commandlinerunner / Applicationrunner]]
- [[#Exit / Beenden von Programmen|Exit / Beenden von Programmen]]
- [[#Spring Shell|Spring Shell]]
- [[#Optionale Tätigkeiten|Optionale Tätigkeiten]]
- [[#Konfigurationsklassen und Fabrikmethoden|Konfigurationsklassen und Fabrikmethoden]]
- [[#Tips und Tricks|Tips und Tricks]]
	- [[#Tips und Tricks#[[Test]]|[[Test]]]]
		- [[#[[Test]]#Start von 2 ApplicationContext|Start von 2 ApplicationContext]]



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

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-3 ComponentScan mit base packages| ComponentScan mit base packages]]

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
  
> Tip: Debug Spring app = application.yml -> `debug=true`

### Exit / Beenden von Programmen

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-4 Exit von Programmen|Exit von Programmen]]

### Spring Shell
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-2 JShell|JShell]]

### Optionale Tätigkeiten 
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-1 Optionale Abhängigkeiten|  Optionale Abhängigkeiten]]

### Konfigurationsklassen und Fabrikmethoden

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1-5 Konfiguration und Fabrikmethoden|  Konfiguration und Fabrikmethoden]]

### Tips und Tricks

#### [[Test]] 

##### Start von 2 ApplicationContext
Damit kann man dann wenn man will , testen ob Nebenläufigkeit soweit funktioniert. d.h das 2 Instanzen von einer Projekt sich so verhält wie angenommen
