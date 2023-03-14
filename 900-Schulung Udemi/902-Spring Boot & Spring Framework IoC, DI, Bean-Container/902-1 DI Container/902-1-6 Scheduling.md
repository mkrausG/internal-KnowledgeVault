---
Title: 902-1-6 Scheduling
Creation date: 14.02.2023 18:29
Modification date: Tuesday 14th February 2023 18:29:38
Author: MKraus
Tags: 
- spring
- moc 
- schulung
- scheduling
Type:
---

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]

- [[#902-1-6 Scheduling|902-1-6 Scheduling]]
	- [[#902-1-6 Scheduling#Einschalten|Einschalten]]
	- [[#902-1-6 Scheduling#Konfiguration|Konfiguration]]


# 902-1-6 Scheduling

Wird wenn konfiguriert, in anderen Threads ausgeführt. 


```ad-important
title: Default Settings
Es wird als Standard immer nur ein Scheduler laufen, das kann aber anders konfiguriert werden. 
d.h. der Default Pool Size = 1.
Kann mit `spring.task.scheduling.pool.size=5` geändert werden.

```



## Einschalten

`@EnableScheduling`

## Konfiguration

```java
@Configuration
@EnableScheduling
class SchedulingConf {
	
}
```