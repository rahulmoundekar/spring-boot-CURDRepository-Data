# spring-boot-CURDRepository-Data

### Spring Boot Data enables JPA repository support by default.
  CrudRepository provides generic CRUD operation on a repository for a specific type. CrudRepository is a Spring data interface and to use it we need to create our interface by extending CrudRepository. Spring provides CrudRepository implementation class automatically at runtime. It contains methods such as save, findById, delete, count etc. Spring boot automatically detects our repository if the package of that repository interface is the same or sub-package of the class annotated with @SpringBootApplication.
  Spring boot can automatically detect our repository if the package of that interface is the same or sub-package of the class annotated with @SpringBootApplication and if not then we need to use @EnableJpaRepositories annotation with @SpringBootApplication.
  
### Maven POM.XML
    <dependency>
		    <groupId>org.springframework.boot</groupId>
		    <artifactId>spring-boot-starter-data-jpa</artifactId>
	  </dependency>
  
### Application Properties
  #### spring.data.jpa.repositories.enabled: 
    It enables JPA repositories. The default value is true. 
  
  #### spring.jpa.database: 
    It targets database to operate on. By default embedded database is auto-detected. 
  
  #### spring.jpa.database-platform: 
    It is used to provide the name of database to operate on. By default it is auto- detected. 
  
  #### spring.jpa.generate-ddl: 
    It is used to initialize schema on startup. By default the value is false. 
  
  #### spring.jpa.hibernate.ddl-auto: 
    It is DDL mode used for embedded database. Default value is create-drop. 
  
  #### spring.jpa.hibernate.naming.implicit-strategy: 
    It is Hibernate 5 implicit naming strategy fully qualified name. 
  
  #### spring.jpa.hibernate.naming.physical-strategy: 
    It is Hibernate 5 physical naming strategy fully qualified name. 
  
  #### spring.jpa.hibernate.use-new-id-generator-mappings: 
    It is used for Hibernate IdentifierGenerator for AUTO, TABLE and SEQUENCE. 
  
  #### spring.jpa.open-in-view: 
    The default value is true. It binds a JPA EntityManager to the thread for the entire processing of the request. 
  
  #### spring.jpa.properties.*: 
    It sets additional native properties to set on the JPA provider. 
  
  #### spring.jpa.show-sql: 
    It enables logging of SQL statements. Default value is false.
    
### CrudRepository Interface
 CrudRepository is an interface and extends Spring data Repository interface. CrudRepository provides generic CRUD operation on a repository for a specific type. It has generic methods for CRUD operation. To use CrudRepository we have to create our interface and extend CrudRepository. We need not to implement our interface, its implementation will be created automatically at runtime. Find some of CrudRepository methods. 
 
#### <S extends T> S save(S entity): Saves and updates the current entity and returns that entity. 
#### Optional<T> findById(ID primaryKey): Returns the entity for the given id. 
#### Iterable<T> findAll(): Returns all entities. 
#### long count(): Returns the count. 
#### void delete(T entity): Deletes the given entity. 
#### boolean existsById(ID primaryKey): Checks if the entity for the given id exists or not. 

CrudRepository has subinterface as PagingAndSortingRepository that provide additional methods to retrieve entities using the pagination and sorting abstraction.  
