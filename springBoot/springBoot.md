# SpringBoot

## Lexique

- ### Annotations

    - @SpringBootApplication : We use this annotation to mark the main class of a Spring Boot application
    - @EnableAutoConfiguration : as its name says, enables auto-configuration. It means that Spring Boot looks for auto-configuration beans on its classpath and automatically applies them.
    - @RestController : It indicates that the class is a web controller and that its return values should be bound to the web response body.
    - @Autowired : L’annotation @Autowired permet d’activer l’injection automatique de dépendance. 


## route pour l'ui de la documentation

 > http://localhost:8080/swagger-ui/index.html

## accéder à l'ai=pi d'un autre post grace à l'ip

 > http://192.168.1.238:9090/user/1

## Eureka

Service permettant de de faire communiquer entre eux d'autres services qui s'enregistrent dessus
ainsi évitant de coder en dur les adresses IP et ports.
