---
Title: 902-1-4 Exit von Programmen
Creation date: 12.02.2023 19:20
Modification date: Sunday 12th February 2023 19:44:38
Class:
Author: MKraus
Tags: 
- spring
- moc 
- schulung 
---

[[900-Schulung Udemi/902-Spring Boot & Spring Framework IoC, DI, Bean-Container/902-1 DI Container/902-1 Container für spring managed Beans|<<]]

# Toc

- [[#Exception-Klassen implementieren.|Exception-Klassen implementieren.]]
- [[#ExitCodeExceptionMapper|ExitCodeExceptionMapper]]
- [[#ApplicationPID[FileWriter]|ApplicationPID[FileWriter]]]


Exit Code => steht für `EXIT_SUCCESSS`, alle anderen Werte für Fehler.

> [!info]
> Unter Dos heißt der ExitCode auch `errorLevel`.

```java
System.exit(-1);
```

ABER für Spring sollte man SpringApplication exit() nutzen, da:
- controlled shutdown
- Context wird geschlossen
  
```java
@Autowired
private ApplicationContext ctx;
...
System.exit(SpringApplication.exit(ctx, () -> 2)); // return 2 as exitCode
```

## Exception-Klassen implementieren.

Eine Exception-Klasse kann `ExitCodeGenenator` implementieren, und immer wenn diese Exception ausgelöst wird, beendet sich die Spring-Boot-Anwendung mit dem gelieferten Exit-Code.

```java
class InsufficientDiskSpaceException extends RuntimeException
									implements ExitCodeGenenator { InsufficientDiskSpaceException( String message ) { 
	super( message );
	}
	@Override
	public int getExitCode() {
		return 2;
	}
}

// An anderer Stelle:
throw new InsufficientDiskSpaceException( "Was only 2 KiB" );
```

## ExitCodeExceptionMapper

Die Exception-Klasse möchte man vielleicht nicht an Spring binden. 
Ein `ExitCodeExceptionMapper` kann ein Exception-Typ auf einen Exit-Code abbilden.

```java
@Component
class MyExitCodeExceptionMappen implements ‭ExitCodeExceptionMapper {
	@0verride public int getExitCode( Throwable exception ) {
	return
	(exception.getCause() instanceof InsufficientDiskSpaceException) ? 2 : 0;
	}
}

class InsufficientDiskSpaceException extends RuntimeException { 
	InsufficientDiskSpaceExceptionC String message ) { 
		super( message );
	}
}
```

## ApplicationPID[FileWriter]

```java
@SpringBootApplication
public class ShutdownDemo {
	public static void main( Stning[] args ) {
			SpringApplication app = new SpningApplication( ShutdownDemo.class );
			app.setDefaultPnopenties( Map.of("spring.pid.fail-on-write-erpon",true) );
			app.addListeners( new ApplicationPidFileWniten() ); // "application.pid" 
			try ( ConfigunableApplicationContext nun = app.run( angs ) ) {
				Logger log = LoggerFactory.getLoggen( ShutdownDemo.class ); 
				log.info(	new ApplicationPid() );
				new Scanner( System.in ).nextLine();
			}
	}
}
```



Java-Anwendungen kann man extern über eine PID (process identifier) beenden.
Unter Unix dient dazu `kill <PID> — identisch mit kill -15 <PID> (SIGTERM)` - oder ` .hart'mit kill -9 <PID> (SIGKILL)`.
•	`cat application.pid | xangs kill -9`
•	Bei SIGTERM laufen noch die Shutdown-Hooks, ein SIGKILL kann ein Programm nicht mehr verarbeiten, das Betriebssystem beendet das Programm.
