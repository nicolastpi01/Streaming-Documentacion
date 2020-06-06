# Streaming-Documentacion

![icono](./media.png)

https://github.com/nicolastpi01/Streaming-Documentacion.git

## Objetivo

Creación de un servicio cliente servidor para streaming de videos gratuitos.

Se decidio usar el Stack React+TS y .NET Core por la familiaridad en el trabajo.

## Streaming-Backend
Clonar Repo https://github.com/nicolastpi01/Streaming-Backend.git

### Instalacion
Se uso Visual Studio 2019 Community
	+SDK .NET Core 3.1
	+ASP.Net Core con C#

Además por comodidad se incluyo la libreria 'DotNetEnv@1.4.0' para la lectura de ficheros de configuración .env

El motor de base de datos elegido fue MySql, para ello se uso el conector de Pomelo@3.1, porque se perdio parte del soporte por Oracle.
En caso de querer cambiarla, cambiar el conector usado en el <a href="https://github.com/nicolastpi01/Streaming-Backend/blob/master/Streaming/Startup.cs" title="Repositorio de la Documentacion"> Startup.cs</a>.

Para correrlo se debe generar la base de datos utilizando EF Core con los comandos

<code>
dotnet ef Migrations Add <nombre>
dotnet ef database update
</code>

Esto creara las tablas vacias para su consumo.

## Streaming-Frontend
Clonar Repo https://github.com/nicolastpi01/Streaming-Frontend.git

### Instalacion
Se uso Visual Studio Code con pluggins de React+Typescript

Para testing se uso la libreria jest@25.5.1 que requiere node -v >10.14.2
Se puede instalar usando los comandos

<code>
nvm install 10.14.2;
nvm use 10.14.2
</code>

### Configuracion
Crear en la carpeta src un archivo auth_config.json con la siguiente configuracion:

<code>
{
    "domain": "*",
    "clientID": "*",
    "redirectUri": "*",
    "audience": "*",
    "cacheLocation": "*"
}
</code
	
donde
<ul>
  <li>domain y clientID son parte de la configuracion de la aplicacion de Auth0, se obtienen de sus settings.</li>
  <li>redirectUri es la url de la app que la consume, para pruebas locales puede usarse localhost:puerto.</li>
  <li>cacheLocation donde se almacenaran las credenciales, como "localstorage" o similares.</li>
  <li>audience...</li>
</ul>


