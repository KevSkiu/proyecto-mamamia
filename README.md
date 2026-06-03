🍕 Sistema de Ventas Online — Pizzería Mamamia
Aplicación web full-stack para la gestión, visualización y pedido de productos de una pizzería. El proyecto incluye una interfaz de cliente para realizar pedidos en línea y un panel de administración para gestionar categorías y productos.

Proyecto académico del curso Herramientas de Desarrollo — Universidad Tecnológica del Perú (UTP), 2026.


📋 Tabla de Contenidos

Descripción
Tecnologías
Arquitectura
Estructura del Proyecto
Requisitos Previos
Instalación
Configuración de la Base de Datos
Ejecución
Flujo de Trabajo Git
Equipo


📝 Descripción
Mamamia es un sistema de ventas online que permite a los clientes explorar el menú de una pizzería, agregar productos al carrito y realizar pedidos. Los administradores pueden gestionar el catálogo de categorías y productos a través de un panel dedicado.
Funcionalidades principales:

Registro e inicio de sesión de usuarios
Visualización del menú organizado por categorías
Carrito de compras con cálculo automático de totales
Gestión de pedidos
Panel de administración para categorías y productos


🛠 Tecnologías
CapaTecnologíaFrontendHTML5, CSS3, JavaScript (Vanilla JS)BackendJava 17, Spring Boot 4.0.8PersistenciaSpring Data JPA, HibernateBase de datosMySQL 8Build toolMavenControl de versionesGit + GitHubGestión ágilTrello (Kanban)IDEIntelliJ IDEA

🏗 Arquitectura
El proyecto sigue una arquitectura Cliente-Servidor de tres capas:
┌─────────────┐      HTTP/REST      ┌─────────────┐      JDBC      ┌─────────────┐
│   Frontend  │ ─────────────────▶  │   Backend   │ ────────────▶  │    MySQL    │
│ (Vanilla JS)│ ◀─────────────────  │(Spring Boot)│ ◀────────────  │  (Hibernate)│
└─────────────┘                     └─────────────┘                └─────────────┘

Frontend: archivos estáticos interpretados por el navegador.
Backend: API REST que gestiona la lógica de negocio y la persistencia.
Base de datos: MySQL con tablas generadas automáticamente por Hibernate.


📁 Estructura del Proyecto
proyecto-mamamia/
├── frontend/                          # Cliente (archivos estáticos)
│   ├── css/                           # Hojas de estilo
│   ├── img/                           # Imágenes
│   ├── index.html                     # Página principal
│   ├── login.html                     # Inicio de sesión
│   ├── carrito.html                   # Carrito de compras
│   ├── perfil.html                    # Perfil de usuario
│   └── admin.html                     # Panel de administración
│
└── backend/                           # Servidor (Spring Boot)
    ├── src/main/java/com/mamamia/backend/
    │   ├── model/                     # Entidades JPA
    │   │   ├── Categoria.java
    │   │   └── Producto.java
    │   └── BackendApplication.java    # Clase principal
    ├── src/main/resources/
    │   └── application.properties     # Configuración de la BD
    └── pom.xml                        # Dependencias Maven

⚙ Requisitos Previos
Antes de iniciar, asegúrate de tener instalado:

Java JDK 17 o superior
MySQL 8 o superior
Maven (incluido en el wrapper mvnw)
Git


🚀 Instalación
Clona el repositorio en tu máquina local:
bashgit clone https://github.com/KevSkiu/proyecto-mamamia.git
cd proyecto-mamamia

🗄 Configuración de la Base de Datos

Asegúrate de tener MySQL en ejecución.
El backend creará la base de datos automáticamente. Verifica la configuración en backend/src/main/resources/application.properties:

propertiesspring.datasource.url=jdbc:mysql://localhost:3306/mamamia_db?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

⚠️ Ajusta username y password según tu instalación local de MySQL.


▶ Ejecución
Backend
bashcd backend
./mvnw spring-boot:run
El servidor se iniciará en http://localhost:8080.
Frontend
Abre los archivos HTML de la carpeta frontend/ directamente en el navegador, o sírvelos con una extensión como Live Server.

🌿 Flujo de Trabajo Git
El equipo utiliza la estrategia Git Flow adaptado con las siguientes ramas:
RamaPropósitomainCódigo estable y aprobado (producción)developIntegración de funcionalidades en desarrollofeature/*Desarrollo de nuevas característicasbugfix/*Corrección de errores
Convención de commits
Se sigue el estándar Conventional Commits, vinculando cada commit a su tarea en Trello:
feat: #B-03 crear entidad Categoria para la base de datos
fix: #B-05 corregir longitud de campo nombre
PrefijoUsofeat:Nueva funcionalidadfix:Corrección de errordocs:Documentaciónrefactor:Reestructuración de código
Proceso de contribución
bash# 1. Actualizar develop
git checkout develop
git pull

# 2. Crear rama de trabajo
git checkout -b feature/B-XX-nombre-tarea

# 3. Confirmar cambios
git add .
git commit -m "feat: #B-XX descripción de la tarea"

# 4. Publicar la rama
git push -u origin feature/B-XX-nombre-tarea

# 5. Abrir Pull Request en GitHub hacia develop

🔒 Regla del equipo: ningún cambio se fusiona a main o develop sin pasar por un Pull Request revisado por otro integrante.


👥 Equipo
IntegranteCódigoSoto De la Cruz, Jorge GermánU21215343Jorge Diego, Lui YamirU22327424Varas Veliz, Kevin YuriU22234199Canchanya Estrella, Jared JhairU22238042Enriquez Tello, Ivan SmithU22215862
Docente: Danila Raquel Neira Sacaski
Curso: Herramientas de Desarrollo — UTP, 2026
