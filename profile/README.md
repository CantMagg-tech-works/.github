<h1>Proyecto: CantMagg eCommerce Backend</h1>

<h2>Descripción</h2>
<p>Este proyecto es un backend desarrollado para un sistema de eCommerce basado en una arquitectura de microservicios. El proyecto es parte de un desarrollo colaborativo entre Antonio Canteros (backend) y Erik Maggio (frontend móvil), cuyo objetivo es crear una solución flexible y adaptable para aplicaciones móviles desarrolladas en Kotlin utilizando Jetpack Compose en Android Studio.</p>
<p>El backend está pensado para ser utilizado por cualquier plataforma de comercio electrónico, con la posibilidad de añadir un BFF (Backend For Frontend) para adaptarse a las necesidades específicas de la app móvil de Erik. Aunque el proyecto está en etapa de desarrollo, las tecnologías y módulos mencionados a continuación serán implementados definitivamente en futuras fases.</p>

<h2>Tabla de Contenidos</h2>
<ul>
    <li><a href="#arquitectura">Arquitectura</a></li>
    <li><a href="#tecnologias">Tecnologías Utilizadas</a></li>
    <li><a href="#instalacion">Instalación</a></li>
    <li><a href="#uso">Uso</a></li>
    <li><a href="#contribuciones">Contribuciones</a></li>
    <li><a href="#licencia">Licencia</a></li>
</ul>

<h2 id="arquitectura">Arquitectura</h2>

![Diagrama de Arquitectura](https://drive.google.com/uc?export=view&id=16XLyJa7wimJHDwvgykbGSdtCL4UFnjl7)

<p>El proyecto sigue una arquitectura de microservicios, como se muestra en el diagrama. Está compuesto por los siguientes servicios:</p>

<ul>
    <li><strong>Config Server</strong>: Gestiona la configuración centralizada para todos los servicios.</li>
    <li><strong>Auth Server</strong>: Gestiona la autenticación de usuarios y la generación de tokens con OAuth2 y JWT.</li>
    <li><strong>Eureka Server</strong>: Descubrimiento de servicios.</li>
    <li><strong>Api Api Gateway</strong>: Controla los usuarios y la autenticación.</li>
</ul>

<h3>Microservicios:</h3>
<ul>
    <li><strong>Api Products</strong>: Maneja la gestión de productos.</li>
    <li><strong>Api Sales</strong>: Administra las ventas.</li>
    <li><strong>Api Purchases</strong>: Gestiona las compras.</li>
    <li><strong>Api Shopping Cart</strong>: Controla la gestion del carrito de compras.</li>
    <li><strong>Api Users</strong>: Controla los usuarios y la autenticación.</li>
</ul>
<p>Cada microservicio tiene su propia base de datos para garantizar la escalabilidad y la independencia entre los servicios.</p>

<h2 id="tecnologias">Tecnologías Utilizadas</h2>
<ul>
    <li><strong>Java 21</strong></li>
    <li><strong>Spring Boot 3</strong> con los siguientes módulos:</li>
    <ul>
        <li>Spring Web: Para la creación de APIs RESTful.</li>
        <li>Spring Data JPA: Para la persistencia de datos.</li>
        <li>Spring Security: Para la gestión de seguridad y autenticación.</li>
        <li>Spring Cloud: Para la configuración distribuida y el descubrimiento de servicios.</li>
        <li>Spring Validation: Para la validación de entradas en las APIs.</li>
    </ul>
    <li><strong>Maven</strong>: Para la gestión de dependencias y construcción del proyecto.</li>
    <li><strong>PostgreSQL</strong>: Como base de datos relacional.</li>
    <li><strong>Docker</strong>: Para la contenerización de microservicios.</li>
    <li><strong>Swagger</strong>: Documentación de las APIs.</li>
    <li><strong>MapStruct</strong>: Para la conversión entre entidades y DTOs.</li>
    <li><strong>JUnit 5</strong> y <strong>Mockito</strong>: Para las pruebas unitarias y de integración.</li>
</ul>

<h2 id="instalacion">Instalación</h2>

<h3>Prerrequisitos</h3>
<ul>
    <li>Java 21 o superior.</li>
    <li>Maven instalado.</li>
    <li>Docker y Docker Compose.</li>
    <li>PostgreSQL instalado o en contenedor.</li>
</ul>

<h3>Pasos de instalación</h3>
<ol>
    <li>Clona el repositorio:
        <pre><code>git clone https://github.com/CantMagg-tech-works/api-users.git
cd api-users</code></pre>
    </li>
    <li>Construye los microservicios con Maven:
        <pre><code>mvn clean install</code></pre>
    </li>
    <li>Levanta los contenedores con Docker Compose:
        <pre><code>docker-compose up --build</code></pre>
    </li>
    <li>Accede a los microservicios:</li>
    <ul>
        <li><strong>Eureka Server</strong>: <a href="http://localhost:8761">http://localhost:8761</a></li>
        <li><strong>Api Gateway</strong>: <a href="http://localhost:8080">http://localhost:8080</a></li>
        <li><strong>Api Products</strong>: <a href="http://localhost:8081">http://localhost:8081</a></li>
        <li><strong>Api Sales</strong>: <a href="http://localhost:8082">http://localhost:8082</a></li>
        <li><strong>Api Purchases</strong>: <a href="http://localhost:8083">http://localhost:8083</a></li>
        <li><strong>Api Users</strong>: <a href="http://localhost:8084">http://localhost:8084</a></li>
        <li><strong>Api Shopping Cart</strong>: <a href="http://localhost:8085">http://localhost:8085</a></li>
    </ul>
</ol>

<h2 id="uso">Uso</h2>
<p>Cada microservicio expone una serie de endpoints REST. A continuación, se muestra un ejemplo de uso para la API de productos:</p>

<h3>Obtener todos los productos</h3>
<pre><code>GET /api/v1/users</code></pre>

<h3>Guardar nuevo usuario</h3>
<pre><code>POST /api/v1/users
{
    "username": "usuario ejemplo",
    "phone": "011290758"
}
</code></pre>

<h2 id="contribuciones">Contribuciones</h2>
<p>Este proyecto está en desarrollo. Las contribuciones son bienvenidas, especialmente en la implementación de nuevas características y optimización de los microservicios.</p>
<ol>
    <li>Haz un fork del repositorio.</li>
    <li>Crea una nueva rama para tu funcionalidad:
        <pre><code>git checkout -b nueva-funcionalidad</code></pre>
    </li>
    <li>Haz commit de tus cambios:
        <pre><code>git commit -m 'Agregada nueva funcionalidad'</code></pre>
    </li>
    <li>Sube la rama:
        <pre><code>git push origin nueva-funcionalidad</code></pre>
    </li>
    <li>Abre un Pull Request.</li>
</ol>

<h2 id="licencia">Licencia</h2>
<p>Este proyecto está licenciado bajo la <strong>Licencia MIT</strong> - consulta el archivo LICENSE para más detalles.</p>
