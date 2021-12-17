---
tag: toc
cssclass: myClass
---

** TOC**
- [[#Erste Ebene|Erste Ebene]]
- [[#Zweite Ebene|Zweite Ebene]]
	- [[#Informatik%%2%%|Informatik]]
	- [[#Bundesdruckerei%%2%%|Bundesdruckerei]]
- [[#Dritte Ebene|Dritte Ebene]]
	- [[#Informatik%%3%%|Informatik]]
	- [[#Bundesdruckerei%%3%%|Bundesdruckerei]]
- [[#Vierte Ebene|Vierte Ebene]]
	- [[#Informatik%%4%%|Informatik]]
	- [[#Bundesdruckerei%%4%%|Bundesdruckere]]
- [[#Eben Pro Dokument|Eben Pro Dokument]]
- [[#Beispiel|Beispiel]]



#Todo Hier dann die ebenen anders aufbauen.. da wir jeweils andere brauchen
# Erste Ebene
| Klasse | Inhalt                                       |
| ------ | -------------------------------------------- |
| 0      | Informatik, Informationswissenschaft         |
| 1      | Bundesdruckerei                              | 
| 5      | Naturwissenschaften, Mathematik              |
| 6      | Technik, Medizhin, angewandte Wissenschaften |
| 8      | Literatur                                    |

# Zweite Ebene
## Informatik%%2%%
| Klasse | Inhalt                                                   |
| ------ | -------------------------------------------------------- |
| 00     | Informatik, Informationswissenschaften, allgemeine Werke |
| 01     | Bibliographien                                           |
| 02     | Bibliotheks- und Informationswissenschaften              |
| 03     | Sachbücher                                               |
| 04     | Nicht zugeordnet                                         |
| 05     | Zeitschriften, Journale, Ebooks                          |
| 08     | Angebote                                                 |
| 09     | Manuskripte & seltene Bücher                             |

## Bundesdruckerei%%2%%
| Klasse | Inhalt    |
| ------ | --------- |
| 10     | Allgemein | 

# Dritte Ebene 
## Informatik%%3%%
| Klasse | Inhalt       |
| ------ | ------------ |
| 000    | Admin        | 
| 001    | Web          |
| 002    | Spring       |
| 003    | Kubernetes   |
| 004    | Asp Net      |
| 005    | Asp Net Core |
| 006    | Asp MVC      |

## Bundesdruckerei%%3%%
| Klasse | Inhalt    |
| ------ | --------- |
| 100    | Allgemein | 

# Vierte Ebene
## Informatik%%4%%
| Klasse | Inhalt     |
| ------ | ---------- |
| 000.0   | Asp Net    |
| 000.1   | CSharp     |
| 000.2   | Java       |
| 000.3   | Kotlin     |
| 000.4   | JavaScript |
| 000.5   | SQL        |

## Bundesdruckerei%%4%%
| Klasse | Inhalt    |
| ------ | --------- |
| 100.0  | Allgemein |

# Eben Pro Dokument
Damit sind dann die nachfolgenden Dokumente gedacht. 
Die werden einfach mit einem Bindestrich und  einer ==fortlaufenden== Nummer und einem Namen separiert erneut mit einem Bindestrich angegeben.

```ad-info
Es kann nun auch sein, das wir mehr als nur eine Datei für ein Thema erzeugen wollen, daher ist das Schema mit der fortlaufenden Nummer folgendermaßen zu erweitern.

\-x-\<name>  ==> Hauptseite
\-x-y\<name>  ==> Unterseite der Hauptseite, wobei auch y ein fortlaufender Zähler ist 
!!! ggf. auf 10.000 stellen gehen wegen Sortierung von Dateien..
```
z.B.
002.2-\<fortlaufende Nummer\>-Name

# Beispiel
| Klasse                              | Inhalt                                                      |
| ----------------------------------- | ----------------------------------------------------------- |
| 002.2                               | Informatik - Spring - Java                                  |
| 002.2-1-Configuration               | Beispiel Spring Java Configuration thema                    |
| 002.2-1-1-Configuration-Validierung | Beispiel einer Unterseite für die Spring Java Configuration | 
