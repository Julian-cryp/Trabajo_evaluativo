# Nombre del Proyecto
Es una plataforma para poder ingresar actividades, para ver Nombre, Descripcion, Fecha, Hora, Estado.

## Descripción
Este proyecto fue desarrollado como parte del curso de BackEnd y tiene como objetivo Consolidar los conceptos de Jsp, Servlet, Dependencias y simples funciones de Crud. Utiliza tecnologías Java Web como Servlets, JSP y base de datos para ofrecer una experiencia interactiva y funcional.

## Tecnologías Utilizadas
- Jdk 21
- NetBeans 19
- Servlets y JSP
- Apache Tomcat 9.0.108
- PhpMyAdmin 
- HTML
  
## Estructura del Proyecto
 El proyecto consta de una estructura de la siguiente manera:
 
ProyectoEvaluativo/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── logica/                  # Clases de negocio (Tarea.java, svTarea.java)
│   │   │   ├── persistencia/           # JPA Controllers y DAO (TareaJpaController.java, ControladoraPersistencia.java)
│   │   │   ├── excepciones/            # Excepciones personalizadas
│   │   │   └── controlador/            # Definicion de funciones para su uso(Controlador_Tarea.java)
│   │   ├── resources/
│   │   │   └── META-INF/
│   │   │       └── persistence.xml     # Configuración JPA
│   │   └── webapp/
│   │       ├── WEB-INF/
│   │       │   └── web.xml             # Configuración del Servlet
│   │       ├── Mostrar_tareas.jsp
│   │       └── Controlar_Tarea.jsp
├── pom.xml                             # Maven: dependencias y configuración
└── nb-configuration.xml                

## Dependencias:
 <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.asm</artifactId>
            <version>9.4.0</version>
        </dependency>
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.antlr</artifactId>
            <version>2.7.12</version>
        </dependency>
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.jpa.jpql</artifactId>
            <version>2.7.12</version>
        </dependency>
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.moxy</artifactId>
            <version>2.7.12</version>
        </dependency>
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>jakarta.persistence</artifactId>
            <version>2.2.3</version>
        </dependency>
        <dependency>
            <groupId>javax</groupId>
            <artifactId>javaee-api</artifactId>
            <version>8.0</version>
            <scope>provided</scope>
        </dependency>
        <!-- EclipseLink JPA -->
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.core</artifactId>
            <version>2.7.12</version>
        </dependency>
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.jpa</artifactId>
            <version>2.7.12</version>
        </dependency>
        <dependency>
            <groupId>org.eclipse.persistence</groupId>
            <artifactId>org.eclipse.persistence.jpa.modelgen.processor</artifactId>
            <version>2.7.12</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.30</version>
        </dependency>

##Como ejecutarlo: 

Las credenciales de MYsql son 

User : root 
Password : Julian102914*

Credenciales de TOMCAT 
User : admin
Password : admin 

Para ejecutar el programa se tiene que realizar los siguientes pasos:
1. una base de datos de nombre "tareas_act"
2. Se crea dos tablas las cuales son:
   1# tarea:
   CREATE TABLE tarea(
   id int Primary key AUTO_INCREMENT,
   nombre varchar(109),
   descripcion varchar(109),
   estado varchar(20),
   fecha varchar(18),
   hora varchar(18),
   );


   2# sequence (Esto se realizo debido a que al correr el programa el archivo daba errores en este archivo asi que se creo manualmente de esta manera):

   CREATE TABLE SEQUENCE (
  SEQ_NAME VARCHAR(50) NOT NULL,
  SEQ_COUNT INTEGER NOT NULL,
  PRIMARY KEY (SEQ_NAME)

);

2.1 se ingreso una fila :
INSERT INTO SEQUENCE (SEQ_NAME, SEQ_COUNT) VALUES ('Tarea_class_SEQ', 1);

2.2 En caso que en el archivo devuelva errores de tipo SEQUENCE ingrese este dato en el archivo tarea.java al principio

   @Id
@GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "tarea_seq")
@SequenceGenerator(name = "tarea_seq", sequenceName = "Tarea_class_SEQ", allocationSize = 1)
private long id;

En esa línea de código se observa que, al realizar el debug del programa la entidad busca generar por tipo sequence y el generador previamente definido (tarea_seq). 

Luego se valida el generador secuencial el cual es "Tarea_class_SEQ", allocationSize = 1" el cual indica el SEQ_NAME y busca la locationsize el cual tambien se ha definido. 


#Al realizar esos pasos El archivo Funcionara 













   
   



