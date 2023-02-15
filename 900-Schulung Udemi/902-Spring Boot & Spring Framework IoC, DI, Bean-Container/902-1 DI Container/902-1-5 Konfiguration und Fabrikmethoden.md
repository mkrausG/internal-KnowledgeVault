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