<p align="center">
  <a href="https://platzi.com/cursos/next-2020/" target="_blank">
    <img alt="Curso de Next.js" src="https://static.platzi.com/media/achievements/badge-nextjs-2259fc68-f86b-486e-bc09-95311a887985.png" width="60" />
  </a>
</p>
<h1 align="center">
  Saga de Next.js de Platzi
</h1>
<p align="center">
  <a href="https://platzi-plantpedia.vercel.app" target="_blank">
    https://platzi-plantpedia.vercel.app
  </a>
</p>

Este repositorio recopila el proyecto de la Saga de Next.js dictado por [@jonalvarezz](https://twitter.com/jonalvarezz) para [Platzi](https://platzi.com). Los cursos que componen la saga son:

- [Curso de Next.js: Sitios Estáticos y Jamstack](https://platzi.com/cursos/nextjs-jamstack)
- [Curso de Next.js: Internacionalización de Aplicaciones Web con i18n](https://platzi.com/cursos/nextjs-internacionalizacion)
- [Curso de Next.js: Deploy a Producción](https://platzi.com/cursos/nextjs-deploy)
- [Curso de Next.js: Grandes Datasets](https://platzi.com/cursos/nextjs-datasets)
- [Curso de Next.js: Autenticación](https://platzi.com/cursos/nextjs-auth)
- [Curso de Next.js: Seguridad con OWASP](https://platzi.com/cursos/nextjs-seguridad-owasp)

## Tabla de contenidos

- [🔎 ¿Cómo trabajar en este proyecto?](#-cómo-trabajar-en-este-proyecto)
- [🤖 Guía rápida de desarrollo](#-gu%C3%ADa-rápida-para-desarrollar)
- [⚙️ Importar contenido a Contentful](#%EF%B8%8F-importar-contenido-a-contentful)
- [🧑‍🏫 Otras preguntas y respuestas](#-otras-preguntas-y-respuestas)
- [🐞 ¿Encontraste un error o mejora?](#-encontraste-un-error-o-mejora)

## 💻 CMS usado en el proyecto: [Contentfull](https://app.contentful.com/)

## Notas

- [📝 Notas del Curso de Next.js: Sitios Estáticos y Jamstack](#📝-Notas-del-Curso-de-Next.js:-Sitios-Estáticos-y-Jamstack)
- [📝 Notas del Curso de Next.js: Optimización y Deploy a Producción](#📝-Notas-del-Curso-de-Next.js:-Optimización-y-Deploy-a-Producción)

## 🔎 ¿Cómo trabajar en este proyecto?

El curso es totalmente práctico y progresivo. Este repositorio sólo existe como una guía para cuando lo necesites. Puedes realizar todo el curso en tu propio proyecto y tu propio repositorio.

El repositorio y toda la saga está dividido por etiquetas de Git. Empieza desde la etiqueta git correspondiente al módulo del curso que te interese:

1.  Clona el repositorio, si no lo has hecho aún:

    ```sh
    git clone git@github.com:jonalvarezz/platzi-plantpedia.git
    ```

1.  Actualiza la información de las etiquetas:

    ```sh
    git fetch --tags
    ```

1.  Lista las etiquetas disponibles:

    ```sh
    git tag
    ```

    Deberías ver algo como:

    ```sh
    0-inicio
    1-incremental-rendering
    10-react-query
    11-memoization
    ...
    ```

1.  Inicia un nuevo branch desde el punto que desees:

    ```sh
    git checkout -b el-nombre-de-mi-branch etiqueta-elegida

    # Por ejemplo, para crear un branch llamado 'dev' desde el módulo '10-react-query'
    git checkout -b dev 10-react-query
    ```

    🔥 Eso es todo, ya puedes iniciar con todos los cambios incluídos hasta ese módulo.

    > 💡 En la sección de [Releases](https://github.com/jonalvarezz/platzi-plantpedia/releases) puedes encontrar toda la lista de etiquetas.

<details><summary>¿Cómo subo mis cambios a otro repositorio?</summary><p>

Git permite manejar varios repositorios remotos en una misma copia local. [Aquí encuentras más información](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes) y te dejaré el cheatsheet a continuación:

```sh
# Crea tu nuevo repositorio en GitHub/GitLab/otro.
# Asumamos la URL es git@github.com:jonalvarezz/mi-repo-mas-bello.git
# Agrega el nuevo remote

git remote add mi-repo git@github.com:jonalvarezz/mi-repo-mas-bello.git

# Para push
git push mi-repo branch-a-hacer-push


# Para pull
git pull mi-repo branch-a-hacer-push
```

</p></details>

## 🤖 Guía Rápida Para Desarrollar

1. Instala dependencias

   ```sh
   yarn
   ```

1. Inicia el proyecto

   ```sh
   yarn dev
   ```

   El sitio estará disponible en http://localhost:3000.

> ⚠️ Dependiendo del lugar en la saga donde te ubiques podrías necesitar algunas Variables de Entorno. Revisa [`.env.local.example`](https://github.com/jonalvarezz/platzi-plantpedia/blob/main/.env.local.example) y el [Curso de Next.js: Deploy a Producción](https://platzi.com/cursos/nextjs-deploy)

## ⚙️ Importar contenido a Contentful

El proyecto utiliza un Content Management System (CMS) llamado [Contenful](https://www.contentful.com/). En el primer curso de esta Saga [Next.js: Sitios Estáticos y Jamstack](https://platzi.com/cursos/nextjs-jamstack) vemos en detalle como configurarlo.

Los pasos son:

1. Crea una cuenta en [Contentful](https://www.contentful.com) y crea un nuevo espacio (Space) vacio.

1. Crea un nuevo **Content Managment Token**, guarda su valor y el de tu **Space ID**.

   > 💡 Lo generas desde Your Space > Settings > API Keys > Content Management tokens.

1. Modifica el archivo `import/config.json` con los valores del punto anterior.

   ```sh
   cd platzi-plantpedia
   nano import/config.json
   ```

1. Instala la herramienta CLI de Contentful:

   ```sh
   npm install -g contentful-cli
   ```

1. Corre el siguiente comando desde la raiz de este proyecto:

   ```sh
   cd platzi-plantpedia
   contentful space import --config import/config.json
   ```

   > 💡 La importación puede tardar varios minutos.

1. En el navegador, verifica que el contenido se haya importado en la pestaña **Model** y **Content**.

   > 💡 Deberías ver al menos 400 registros creados entre entradas e imágenes.

1. Adicionalmente, puedes interactuar con tu contenido utilizando el [explorador de GraphQL](https://www.contentful.com/developers/docs/references/graphql/):

   Abre en tu navegador: `https://graphql.contentful.com/content/v1/spaces/{SPACE}/explore?access_token={CDA_TOKEN}`

   > 💡 Reemplaza `{SPACE}` y `{CDA_TOKEN}` por tus valores propios.

## 🧑‍🏫 Otras preguntas y respuestas

<details>
  <summary>¿Cómo se creo la carpeta `api` y `api/generated`?</summary>
  <p>

> 💡 Si utilizas este repositorio como lo vimos en clase y usas el [contenido de Contentful que se provee](#%EF%B8%8F-importar-contenido-a-contentful), no es necesario correr o realizar algo para la auto-generación de código.

Gracias a que utilizamos GraphQL, **auto-generamos** el archivo `api/generated/graphql.ts` para producir:

- Los tipos de datos del Modelo de nuestro contenido
- El tipo esperado en la respuesta de cada API
- Una función lista (`getSdk`) para realizar el fetch de cada URL.

> 💡 El código es auto-generado usando `graphql-codegen`. No se vió en clase pero se dejo como reto avanzado.

Otros datos claves son:

- `queries.graphql` indica todo lo que se debe auto-generar.
- `codegen.yml` es el archivo de configuración.
- La auto-generación se puede correr con:

  ```sh
  ACCESS_TOKEN=<access_token> SPACE_ID=<space_id> yarn build:schema
  ```

Luego, el archivo `api/index.ts` y `api/selectors.ts` son una capa que ge creado encima – un _wrapper_ – para exportar funciones y tipos más fáciles de usar.

  </p>
</details>

<details><summary>La librería X no está en su última versión</summary><p>

Si te encuentras trabajando desde una de las etiquetas de git es posible que las librerías no estén en su versión más actual.

Para obtener el proyecto funcionando con las versiones más actualizadas deberás crear un branch desde el último commit de `main`:

```sh
git fetch
git checkout -b dev origin/main`
```

> 💡 El último commit también representa el proyecto terminado con todas las sagas incluidas.

Las versiones de las librerías solo se mantienen actualizadas al final proyecto pero no se hace en cada etiqueta de git para no introducir cambios que causen que el código sea diferente al visto en la clase.

</p></details>

## 🐞 ¿Encontraste un error o mejora?

Ayuda a otros estudiantes con eso que acabas de descubrir que haría este curso y respositorio mucho mejor.

- En [Issues](https://github.com/jonalvarezz/platzi-plantpedia/issues/new) puedes reportar errores, agregar sugerencias y comentarios.
- Por su parte, los [Pull Request](https://github.com/jonalvarezz/platzi-plantpedia/pulls) siempre estarán abiertos para recibir mejoras puntuales.

Happy hacking!

---

# Notas del Curso de Next.js: Sitios Estáticos y Jamstack

## Metodos de rendering

### Apuntes

- Existen 3 formas de realizar un proceso de rendering:
  1. Client-side
     - Sucede bajo demanda en el navegador
     - El navegador cada vez que visite nuestro sitio, el trabajo lo realizara el navegador de tus usuarios
     - Ej.: Cada que agregas JS usando la etiqueta src, debido a que estamos diciendo al navegador que ejecute nuestra etiqueta, descargue y que procese el JS para convertirlo en HTML
     - Ej.: create-react-app ⇒ Es un boilerplate para crear aplicaciones React, sin agregar cambios y servidores, lo que terminaremos enviando a los usuarios, será una aplicación client-side
  2. Server-side
     - Significa que tenemos un servidor que se encarga ya sea de forma total o parcial de hacer el rendering de JS y transformarlo a HTML
     - El navegador recibe por parte del servidor HTML ya listo para mostrarse
     - Sucede bajo demanda en el servidor
     - La gran mayoría de lenguajes y frameworks backend
     - Symfony (PHP), WordPress clásico (PHP), Flash (Python), Django (Python), etc.
  3. Static rendering
     - Trata del que el HTML se construya en el proceso de compilación
     - Transformará el código JS a HTML una sola vez en "build time"
     - Jekill, Wintersmith, Gatsby, Hugo, Next.js

> Rendering procesar pedazos de código (JS) y datos para mostrar su resultado (HTML)

💡 Next.js te permite crear aplicaciones híbridas

- Next.js te permitirá escoger entre uno o más rendering modes para las diferentes páginas de tu aplicación

```cmd
📌 **RESUMEN:** Existen 3 formas de poder hacer un proceso de rendering, client side la cual el navegador
del cliente se encargará de transformar el JS a HTML, server side que significa que un servidor se encargara
de la transformación baja demando o Static rendering, en la cual el proceso de renderizado se realiza una
única vez al momento de compilar la aplicación
```

---

## Trade-offs de SSG

### Apuntes

- Al final, solo son archivos estáticos (HTML, CSS y JS): el deployment es el más fácil y puede hacer en cualquier servidor
  - Sin contar que no necesita muchos recursos,
  - No necesita mucho trabajo por parte del servidor
  - Podemos almacenar en un CDN para que sea superveloz
- El SEO y performance de carga serán de los mejores
- No todos los sitios se pueden generar de forma estática. Debido a que los datos debes obtenerlos en tiempo real y no estarán incrustados directamente en el HTML Ej.:
  - Páginas de usuario
  - Información personalizada
  - Dashboard
- El build time mientras más páginas se tenga más lento será el proceso

---

## Incremental Static Generation

### Apuntes

[DOC Vercel](https://vercel.com/docs/concepts/next.js/incremental-static-regeneration)

[POST](https://www.smashingmagazine.com/2021/04/incremental-static-regeneration-nextjs/)

- Incremental Static Site Generation te ermite poder crear nuevas páginas bajo demanda sin tener que volver a compilar la aplicacion otra vez
- Puedes generar un conjunto de páginas iniciales, y dejar otras por generar bajo demanda del usuario

![img](https://vercel.com/_next/image?url=%2Fdocs-proxy%2Fstatic%2Fdocs%2Fconcepts%2Fnext.js%2Fisr%2Fgeneration.png&w=1080&q=75)

- Lo que nos permite tener:
  - Compilaciones mucho más rápidas ⇒ Debido a que no tendrás que compilar todas las páginas al momento de correr el comando de compilación
  - Poder refrescar la información cada cierto tiempo

### Estrategias de generación

Debido a que Next.js te permite compilar previamente un conjunto de páginas que tú como desarrolladora puedes definir. Existen diferentes formas de usar esta característica del framework, las cuales puedes configurar al momento de devolver el objeto de configuración en `getStaticPaths`

- `fallback: blocking` Cuando se requiera una página que no se generó anteriormente ya sea en build time o bajo demanda, lo que hará Next.js será **inmediatamente generar la página** y mandarla al usuario
- `fallback: true` Cuando se requiera una página que no se generó anteriormente ya sea en build time o bajo demanda, lo que hará Next.js será **inmediatamente mandar una página estática de carga al usuario** y mandarla al usuario. Posteriormente, cuando esté lista la página se volverá a renderizar con la página generada

### Enfoque stale-while-revalidate

Consiste en el siguiente procedimiento

1. Generación de páginas (build)
2. Respuesta desde el caché

En caso de nuevo contenido:

1. Nueva página (background)
2. Respuesta de página vieja
3. Respuesta con la nueva página

Este enfoque se conoce por:

- Stale ⇒ Respondiendo con las páginas que están en caché
- while - revalidate ⇒ Next.js estará mirando que tiene que cambiar, actualizar y responderá con páginas vencidas o cache
- Cabe aclarar que las actualizaciones sucederán en segundo plano, lo importante es la información que tan actualizada este para el usuario

```cmd
📌 **RESUMEN:** Con ISSG puedes generar páginas bajo demanda, las cuales pueden estar generadas mediante dos
estrategias de forma bloqueante y de la forma en que el usuario esta consiente del estado de carga. También
puedes configurar una página de tal manera que cada cierto tiempo se actualice, esta técnica usa el enfoque
state-while-revalidate, en la cual Next.js estará mirando que tiene que cambiar, actualizar y respondiendo
con páginas guardadas en caché.
```

## Trade-off ISSG

### Apuntes

- La flexibilidad de server-side rendering con las bondades de static generation
- Requiere un servidor con Node.js
  - No siempre es posible contar con un servidor Node.js ya que pueden ocurrir casos en que tengas un proyecto legacy con servidor PHP u otro.
  - Si no lo tenemos, nuestra complejidad aumentara bastante al punto de no ser viable usar esta estrategia
- El build-time no aumenta con el número de páginas
- La revalidación brinda mucha más flexibilidad
  - Con un número podemos especificar a Next.js lo cual sera el tiempo de actualización de la información
- Así mismo puede ser peligroso, ej.: no poder ajustar los tiempos de revalidación ante un enlace que se vuelve viral.
- No es pato para todas las páginas. Ej.: páginas de usuario o información personalizada, dashboard en tiempo real.
- No es un problema en sitios con pocas páginas
  - Podemos utilizar este enfoque cuando tenemos miles de páginas

---

## Otras alternativas de build

### Apuntes

### **Server-Side Rendering**

- La información siempre estará actualizada
- Poder modificar la respuesta con base en la petición puede ser muy conveniente
- Golpear el servidor por cada petición puede ser costoso
  - Consume recursos = dinero

### **Exportar HTML**

- Se producen archivos estáticos y el servidor de Node.js es desacoplado

### **Trade-offs: Exportar**

- No hay backend, por tanto no hay servidores por mantener
- Se puede subir a servidores de archivos estáticos, como GitHub Pages
- Muchas funcionalidades se deshabilitarán:
  - Server-side rendering (getServerSideProps)
  - Incremental SIte Generation
  - Revalidación
  - Rutas API
  - Internacionalización
  - next/image\*

---

# Notas del Curso de Next.js: Optimización y Deploy a Producción

## Este curso es la continuacion del curso de Next.js: Sitios Estáticos y Jamstack. [Repo](https://github.com/BraianVayletGlobant/curso-next-sitios-estaticos-jamstack-platzi)

## Clases

- Clase1: Presentacion
- Clase2: [¿Para qué necesitamos variables de entorno?](#¿Para-qué-necesitamos-variables-de-entorno?)
- Clase3: [Moviendo las llaves a variables de entorno](#Moviendo-las-llaves-a-variables-de-entorno)
- Clase4: [Llaves de alcance público (browser) y privadas (server)](<#Llaves-de-alcance-público-(browser)-y-privadas-(server)>)
- Clase5: [Paquete cross-env y consideraciones en otros sistemas operativos](#Paquete-cross-env-y-consideraciones-en-otros-sistemas-operativos)
- Clase6: [Componente Image de Next.js](#Componente-Image-de-Next.js)
- Clase7: [Image API: configurando nuestro propio loader avanzado](#Image-API:-configurando-nuestro-propio-loader-avanzado)
- Clase8: [Shallow navigation, router.query y data fetching](#Shallow-navigation,-router.query-y-data-fetching)

---

# ¿Para qué necesitamos variables de entorno?

## 🧩 Variables de entorno

### Ideas/conceptos claves

Una variable de entorno es una variable dinámica que puede afectar al comportamiento de los procesos en ejecución en un ordenador. Son parte del entorno en el que se ejecuta un proceso.

### Apuntes

- Generalmente, son secretos que solo una máquina en particular debe saber. Ej.: la contraseña de la base de datos
  - Permite almacenar una “contraseña” donde únicamente nos interesa
- No deben versionarse
  - Peor aún si el repositorio es público, ya que existe montones de bots automatizados para encontrar estas llaves

```cmd
   💡 En caso de subir por accidente una variable de entorno, no sirve de nada crear otro commit, porque quedará en la historia del repositorio, la mejor solución es crear otra llave de entorno
```

### ¿Qué buscamos?

1. Los secretos no sean compartidos, pero…
2. Como desarrollador quiero conocer que secretos necesito para que la aplicación funcione.

   - Debe ser una lista clara la cual especifique que llaves necesito para que la aplicación no tenga ningún problema

3. La aplicación debe ser capaz de cargar y leer nuestros secretos

### Implementación

- Existen diferentes formas de implementar las variables de entorno, una de ellas es la siguiente estructura, donde existe:
- Documento de ejemplo

### Versionado

- Contiene una lista de llaves necesarias
- Sin los valores de las llaves ⇒ En el peor de los casos puede existir algún valor, pero es porque nada malo pueda pasar

```
ACCESS_TOKEN=
URL_DB=
```

### Una copia del documento

- Ignorado por el versionador (Git).
- Contiene las llaves necesarias con valores necesarios.

## 📌 **RESUMEN:**

Las variables de entorno, son la mejor forma de poder guardar contraseñas, llaves, etc. (secretos) ya que estas no son compartidas, establece una lista clara de que secretos necesita la aplicación para que no se rompa y es capaz de cargar y leer dichos valores de la lista de secretos

> Links:
>
> - [variables de entorno en node](https://www.youtube.com/watch?v=tZ3bLXoD6i0)

# Moviendo las llaves a variables de entorno

## 🖱 Variables de entorno en Next.js

### Apuntes

- Existen dos tipos de variables de entorno en Next.js, estas se diferencian principalmente del lugar de ejecución ya sea en el navegador o en el servidor
- La forma en la que maneja Next.js las llaves es de la siguiente forma:
  - MY_VARIABLE: Solo disponible en el servidor (Node.js)
  - NEXT_PUBLIC_MY_VARIABLE: Disponible en el cliente (navegador)
- El motivo por el que Next.js requiere agregar el prefijo NEXT_PUBLIC es porque de esta manera te hace consiente que esta variable estará expuesta públicamente en el navegador

## 📌 **RESUMEN:**

Next.js administra las variables según las necesitemos en el servidor o lleguen al cliente, estas últimas implican que podrán estar expuestas en el navegador. Para hacerte consiente de la implementación de la misma requiere el prefijo `NEXT_PUBLIC`

> Links:
>
> - [Environment Variables](https://nextjs.org/docs/basic-features/environment-variables)
> - [Environment Variables - config](https://nextjs.org/docs/api-reference/next.config.js/environment-variables)

# Llaves de alcance público (browser) y privadas (server)

Variables de entorno en NextJs.

Si las nombramos como NEXT_PUBLIC_MY_VARIABLE estas van a poder ser accesibles desde el clinete como desde el servidor, gracias a agregar el NEXT_PUBLIC

En el caso de que las nombremos como MY_VARIABLE, seran solo accesibles desde el servidor de Node.js y desde el fichero api.

# Paquete cross-env y consideraciones en otros sistemas operativos

**cross-env:** es una utilidad que sirve para que las variables de entorno sean reconocidas y se puedan utilizar independientemente del sistema operativo en el que estemos desarrollando.

La gran mayoría de los servicios de internet y de servidores ya cuentan con soporte para incorporar variables de entorno, tal es el caso de:

- Vercel
- Heroku
- Github Actions, entre otras

Si bien las variables de entorno existen hace mucho tiempo, no significa que funcionen de la misma forma en todos los sistemas
operativos

_“La forma de cargar variables de entorno puede variar por sistema operativo”_

Principalmente en Windows y Linux existe una gran diferencia. Ej:

```bash
# Windows
set MY_SECRET=<your token here>

# Unix (macOS + Linux)
export MY_SECRET=<your token here>
```

### La solución es utilizar siempre **cross-env**

Es una buena práctica, Next.js ya cuenta integrado por si mismo este paquete, pero para otro tipo de proyectos o aplicaciones, es muy buena práctica utilizarlo.

Además, que la mayoría de los servidores ya cuenta con soporte para las variables de entorno

> Links:
>
> - [Encrypted secrets - GitHub Docs](https://docs.github.com/es/actions/security-guides/encrypted-secrets)
> - [Configuration and Config Vars](https://devcenter.heroku.com/articles/config-vars)
> - [Environment Variables](https://vercel.com/docs/concepts/projects/environment-variables)

# Componente Image de Next.js

### ¿Cómo funciona?

Next.js va creando imágenes de diferentes tamaños en el servidor, las cuales según el tamaño del dispositivo se irán cargando.

Existen servidores los cuales se encargan únicamente de la manipulación de imágenes, los cuales están optimizados para el manejo de imágenes a gran escala y Next.js brinda la flexibilidad para el uso de los mismos

Entonces, para la imágenes que están guardadas de manera local es decir dentro de la carpeta del proyecto es necesario hacer un import de la ruta de la imagen por ejemplo:

```js
import profilePic from '../public/picture.png'
```

Next.js va a determinar el width y el height de la imagen.
Si se usa una imagen remota si es necesario especificar las dimensiones ya que Next no tiene acceso a la imagen durante el proceso de build.

## 📌 **RESUMEN:**

Para crear imágenes responsivas se pueden realizar mediante el componente propio de Next.js el cual creará las mismas mediante el servidor de Node.js o también puede delegar este trabajo a servicios especializados en el mismo

> Links:
>
> - [next/image](https://nextjs.org/docs/api-reference/next/image)
> - [Image Component and Image Optimization](https://nextjs.org/docs/basic-features/image-optimization)

# Image API: configurando nuestro propio loader avanzado

Trabajamos en el codigo, implementando el componente Image que integra la api de contentfull con la de next.js

# Shallow navigation, router.query y data fetching

- Es una navegación no profunda
- También conocido como Routing en memoria
  - La URL se actualiza, pero el sitio no recarga
- En Next.js la forma en la que funciona es:
  - Utilizar el router
  - Especificamos la opción de shallow

```
👀 La URL se actualizará, pero el estado del componente no, además que Next.js si tiene `getStaticProps`, `getServerSideProps`, etc. Next.js no llamará a los mismos
```

- Simplemente, el componente se va a actualizar con los cambios de router y se va a renderizar manteniendo el estado del mismo
- Shallow Navigation funciona únicamente en rutas similares
  - Donde exista un padre compartido

## 📌 **RESUMEN:**

Shallow Navigation principalmente nos ayuda a cambiar la URL de la aplicación sin volver a ejecutar los métodos de traída de datos (`getStaticProps`, `getServerSideProps`, `getStaticPaths`) además que no cambia el estado del componente

> Links:
>
> - [Routing: Shallow Routing | Next.js](https://nextjs.org/docs/routing/shallow-routing)

---
