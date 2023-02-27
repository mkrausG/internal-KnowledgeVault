
# Proposed Steps

- Migrate to Spring boot 2.7, see migration guide: TODO Guide einfügen
  
  > [!important]
> 
Check for deprecated code usage and legacy config file processing, it will be REMOVED with the new major version

- [Update to 2.7.1](https://thepracticaldeveloper.com/book-update-2.7.1/)
- [Update to 3.0](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.0-Migration-Guide)
	- Updated Spring Security
		
		  
- Upgrade to Java 17
- Check third-party projects to have Jakarte EE 9 compatible releases
- Upgrade to Spring Boot 3 (Spring 6)


## Upgrade java 8 to java 17 (only Upgrade without using new technical stuff)

[[TODO]] 
* Maven 

### List of features

[💡Key features since java 8](https://reflectoring.io/java-release-notes/)

[Marco Behler list of features](https://www.marcobehler.com/guides/a-guide-to-java-versions-and-features)#

[Tabular List of Features]([https://www.marcobehler.com/guides/a-guide-to-java-versions-and-features](https://ondro.inginea.eu/index.php/new-features-in-java-versions-since-java-8/))

[List to copy code for feature](https://advancedweb.hu/a-categorized-list-of-all-java-and-jvm-features-since-jdk-8-to-18/)

### Upgrade Java

see [Upgrade stuff](https://blogs.oracle.com/javamagazine/post/its-time-to-move-your-applications-to-java-17-heres-why-and-heres-how)

[Better List](https://blogs.oracle.com/javamagazine/post/its-time-to-move-your-applications-to-java-17-heres-why-and-heres-how)

> [!important]
> 
Multirelease JAR functionality is one of the main features.. But we do not need to use it but we need to ensure that the old code still runs = Konfiguration for it. (export ... Module...)

- Deprecation
- Removed
	- Corba and Java EE Modules were removed 


## Upgrade to Spring 6
### Big Points
- Spring Framework introduces core abstractions
- Portfolio projects consistently integrate with htem
- Spring Boot provides auto-configuration

### Native executables

Native Compilation with GraalVM gets a higher priority.

For AOT generation just use `mvn spring-boot:aot-generate` without seperate plugings.

### Observability 

was:
- Spring Cloud Sleuth 
- Spring Cloud 
- Spring boot
- Spring Framework 
- Micrometer

Now:

- Spring Cloud 
- Spring boot
- Spring Framework 
- Micrometer (includes now tracing)


Code:
```java
// Beispiel Observability 
```

### Changes Spring Web MVC

- HttpMethods are no longer an enum, now use `HttpMethod lock = HttoMethod.valueOf("LOCK")`
- Outdated servlet based integrations are dropped
	- Commons Fileupload, now use `StandardServletMultipartResolver` instead
	- Tiles
	- Freemarker JSP support, now use FreeMarker templates views instead.