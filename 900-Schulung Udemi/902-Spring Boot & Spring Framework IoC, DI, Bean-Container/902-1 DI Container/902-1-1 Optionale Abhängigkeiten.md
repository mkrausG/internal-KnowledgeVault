
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]
[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|]]

## TOC

- [[#Optionale Abhängigkeiten|Optionale Abhängigkeiten]]
	- [[#Optionale Abhängigkeiten#Option 1: Annotationsattribut|Option 1: Annotationsattribut]]
	- [[#Optionale Abhängigkeiten#Option 2:  @Nullable (aus einem beliebigen Paket)|Option 2:  @Nullable (aus einem beliebigen Paket)]]
	- [[#Optionale Abhängigkeiten#Option 3: Einsatz von Optional|Option 3: Einsatz von Optional]]
	- [[#Optionale Abhängigkeiten#Option 4. Object Provider|Option 4. Object Provider]]
- [[#Zyklische Abhängigkeiten|Zyklische Abhängigkeiten]]
- [[#Andere Dinge injizieren|Andere Dinge injizieren]]


### Optionale Abhängigkeiten
* Spring-managed Beans können fehlen, und dann soll der Container keine Injierung durchführen. Das muss allerdings expliziert ausgewiesen werden.

#### Option 1: Annotationsattribut

```java
@Autowired(required=false)
Thumbnail maybeThumbnail
```

#### Option 2:  @Nullable (aus einem beliebigen Paket)
z.B. aus `javax.annotation.Nullable` oder `org.springframework.lang.Nullable`

```java
@Autowired @Nullable Thumbnail maybeThumbnail;
```

#### Option 3: Einsatz von Optional

```java
@Autowired Optional<Thumbnail> maybeThumbnail;
```

#### Option 4. Object Provider

```java
@Autowired ObjectProvider<Thumbnail> maybeThumbnail;
```

Für optionale Abhängigkeiten eignen sich "Setter" gut.

### Zyklische Abhängigkeiten

Ab Spring Boot 2.6 sind diese nicht Zulässig.
d.h. 
```java
@Component class A { @Autowired B b;}
@Component class B { @Autowired A a;}
```

Das kann aber ausgesetzt werden mit:
1. `spring.main.allow-circular-references=true`
2. Setter nutzen
3. `@Lazy`-Annotation bei `@Autowired` einsetzen

### Andere Dinge injizieren

Im Grunde kann alles was im DI Container vorhanden ist auch eingebunden werden.
Darunter fallen auch:
* Bean Factory
* ApplicationContext
* Environment
* ResourceLoader
* ApplicationEventPublisher
* MessageSource bzw. deren konkreten Untertypen (ConfigurableApplicationContext)
