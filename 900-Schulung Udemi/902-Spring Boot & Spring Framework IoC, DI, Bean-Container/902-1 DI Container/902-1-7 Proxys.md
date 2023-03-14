---
Title: 902-1-7 Proxys
Creation date: 2023-03-Tu 17:59
modiModificationfication date: Tuesday 14th March 2023 17:59:36
Author: mkraus
Id: 
Tags: 
- spring
- moc 
- schulung
- proxys
Type:
---

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]

- [[#902-1-7 Proxys|902-1-7 Proxys]]
	- [[#902-1-7 Proxys#Eigene Proxys bauen|Eigene Proxys bauen]]


# 902-1-7 Proxys

Damit wird das Proxy Pattern implementiert.

Spring erzeugt die Proxys selber. d.h vererben von Objecten.. mit cglib.
!! Nutz Interfaces.. Klassen dürfen keinen privaten Ctor haben.

Einsatz in Spring:
- [Transaktionsmanagement](https://spring.io/guides/gs/managing-transactions/)
- [Caching](https://spring.io/guides/gs/caching/)
- [Validierung](https://spring.io/guides/gs/validating-form-input/)
- [Asynchrone Aufrufe](https://spring.io/guides/gs/async-method/)
- [Spring Retry](https://github.com/spring-projects/spring-retry)

## Eigene Proxys bauen

Das kann u.a. mit ProxyFactory gemacht werden.

Angenommen java.util.List soll add(null) ignorieren.

Code:
```java
ProxyFactory factory = new ProxyFactory(new ArrayList<>());

MethodInterceptor methodInterceptor = invocation ->
	(invocation.getMethod().getName() == "add") &&
	isNull(invocation.getArguments()[0])) ? false : invocation.proceed();
factory.addAdvice(methodInterceptor)

// Usage 
List list= (List) factory.getProxy();
list.add("One");
System.out.println(list);
list.add(null);
lidt.add("Two");
System.out.println(list);

// Ausgabge
[One]
[One, Two]
```