# LiterAlura - Catálogo Inteligente de Libros 📚

*LiterAlura* es una aplicación de consola que te permite explorar el mundo de los libros clásicos. Desarrollada en Java con Spring Boot, consume la API de Gutendex para convertir tu terminal en un catálogo literario interactivo con persistencia en base de datos.

## ✨ Características Principales
- 🔍 *Búsqueda inteligente de libros* por título (ej: "pride", "quixote")
- 📚 *Catálogo persistente* en base de datos PostgreSQL
- 👥 *Gestión de autores* con datos biográficos
- 🗓 *Filtro histórico*: Autores vivos en cualquier año
- 🌍 *Búsqueda por idioma* (español, inglés, francés, portugués)
- ⚠ *Validación anti-duplicados*: No permite registrar el mismo libro dos veces

## 🛠 Tecnologías Utilizadas
| Componente       | Tecnología           |
|------------------|----------------------|
| Lenguaje         | Java 24              |
| Framework        | Spring Boot 3.5.4    |
| Persistencia     | Spring Data JPA      |
| Base de Datos    | PostgreSQL           |
| Consumo API      | RestTemplate         |
| Gestión Dependencias | Maven             |

## 📦 Estructura del Proyecto


literatura/
├── src/
│ ├── main/
│ │ ├── java/com/alura/literatura/
│ │ │ ├── Main.java # Punto de entrada
│ │ │ ├── model/ # Entidades JPA
│ │ │ │ ├── Autor.java # Modelo de autor
│ │ │ │ └── Libro.java # Modelo de libro
│ │ │ ├── repository/ # Repositorios de datos
│ │ │ │ ├── AutorRepository.java # Consultas de autores
│ │ │ │ └── LibroRepository.java # Consultas de libros
│ │ │ ├── service/ # Lógica de negocio
│ │ │ │ ├── APIService.java # Consumo de Gutendex API
│ │ │ │ └── MenuService.java # Interfaz de usuario
│ │ │ └── dto/ # Objetos de transferencia
│ │ │ └── DatosLibro.java # Mapeo JSON de API
│ │ └── resources/
│ │ └── application.properties # Configuración DB
├── pom.xml # Configuración Maven


## 🚀 Instalación y Ejecución (Paso a Paso)

### 1. Crear base de datos en PostgreSQL
```sql
CREATE DATABASE literatura-1

Edita src/main/resources/application.properties con:

spring.datasource.url=jdbc:postgresql://localhost:tu_numero_de_server/literatura-1
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña;

======================================
        CATÁLOGO LITERALURA
======================================
1 - Buscar libro (ej: pride, quixote)
2 - Ver todos los libros
3 - Ver todos los autores
4 - Autores vivos en año (ej: 1850)
5 - Libros por idioma (es/en/fr/pt)
0 - Salir
======================================
