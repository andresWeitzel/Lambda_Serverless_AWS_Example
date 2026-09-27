<div align="center">
<img src="./doc/assets/lambda.png" alt="Lambda Serverless AWS" width="100%" />
<div align="right">
<img width="16" height="16" src="./doc/assets/icons/devops/png/aws.png" alt="AWS" />
<img width="16" height="16" src="./doc/assets/icons/aws/png/lambda.png" alt="Lambda" />
<img width="16" height="16" src="./doc/assets/icons/devops/png/postman.png" alt="Postman" />
<img width="16" height="16" src="./doc/assets/icons/devops/png/git.png" alt="Git" />
<img width="16" height="16" src="./doc/assets/icons/aws/png/parameter-store.png" alt="Parameter Store" />
<img width="16" height="16" src="./doc/assets/icons/backend/javascript-typescript/png/nodejs.png" alt="Node.js" />
</div>
</div>

<br>

<br>

<div align="right">
  <a href="./README.md" title="Español">
    <img src="./doc/assets/translation/arg-flag.jpg" width="64" height="40" alt="Español" title="Español" />
  </a>
  <a href="./doc/assets/translation/README.en.md" title="Inglés">
    <img src="./doc/assets/translation/eeuu-flag.jpg" width="64" height="40" alt="Inglés" title="Inglés" />
  </a>
</div>

<br>

<div align="center">

# Lambda Serverless AWS ![(status-completed)](./doc/assets/icons/badges/status-completed.svg)

</div>

Una función Lambda para publicar con Serverless, sin construir la infraestructura a mano. Reúne Serverless Framework, Node.js 20 y deploy automático con GitHub Actions, para que un push a master deje la función Lambda en us-east-2, el recorrido del repositorio a la nube quede resuelto y puedas repetir el mismo flujo en tus propios servicios.

<div align="left">
<a href="https://www.youtube.com/playlist?list=PLCl11UFjHurBhSQCwGDw7uDd2yAu5tVsV" title="Playlist"><img src="./doc/assets/icons/detail-actions/playlist-pill.svg" alt="Playlist" title="Playlist" width="100" height="30" /></a>
</div>

<br>

## Índice 📜

<details>
 <summary>Ver detalles</summary>

<div align="right">

`Última actualización: 27/09/26`

</div>

### Sección 1) Descripción, configuración y tecnologías.

* [1.0) Descripción.](#10-descripción-)
* [1.1) Ejecución del proyecto.](#11-ejecución-del-proyecto-)
* [1.2) Tecnologías.](#12-tecnologías-)

### Sección 2) Documentación y referencias.

* [2.0) Documentación y referencias.](#20-documentación-y-referencias-)

</details>

<br>

## Sección 1) Descripción, configuración y tecnologías.

### 1.0) Descripción [🔝](#índice-)

<details>
 <summary>Ver detalles</summary>

* El servicio está definido en `serverless.yml`: una función Lambda (`lambdaServerlessTest`) con runtime Node.js 20, 512 MB de memoria y timeout de 10 segundos, en la región `us-east-2`.
* El handler vive en `src/index.js`. Es el ejemplo que recibe el evento y deja en el log un arreglo de números.
* El deploy corre solo. En cada push a `master`, el workflow `.github/workflows/master.yml` instala Node.js 20 y publica la función con Serverless Framework.

</details>

### 1.1) Ejecución del proyecto [🔝](#índice-)

<details>
 <summary>Ver detalles</summary>

* Clonamos el repositorio y entramos a la carpeta.

```bash
git clone https://github.com/andresWeitzel/Lambda_Serverless_AWS_Example.git
cd Lambda_Serverless_AWS_Example
```

* Hace falta Node.js 20, que es el mismo runtime de la función.
* El proyecto no declara dependencias de aplicación. El lockfile está vacío y `npm ci` deja el entorno listo para el workflow.
* El deploy no se hace desde la consola de AWS. Al pushear a `master`, GitHub Actions ejecuta `serverless deploy` con la acción `serverless/github-action@v3.2`.
* El workflow lee las credenciales desde los secrets del repositorio: `AWS_ACCESS_KEY_ID` y `AWS_SECRET_ACCESS_KEY`.

</details>

### 1.2) Tecnologías [🔝](#índice-)

<details>
 <summary>Ver detalles</summary>

| **Tecnología** | **Versión** | **Uso** |
| --- | --- | --- |
| [Node.js](https://nodejs.org/) | 20.x | Runtime de la función |
| [AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) | — | Ejecución en `us-east-2` |
| [Serverless Framework](https://www.serverless.com/framework/docs) | GitHub Action 3.2 | Definición del servicio y deploy |
| [GitHub Actions](https://docs.github.com/actions) | — | Publicación en cada push a `master` |
| [Git](https://git-scm.com/) | — | Control de versiones |

</details>

<br>

## Sección 2) Documentación y referencias.

### 2.0) Documentación y referencias [🔝](#índice-)

<details>
 <summary>Ver detalles</summary>

#### AWS

* [Documentación de AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
* [AWS Lambda con Node.js](https://docs.aws.amazon.com/lambda/latest/dg/lambda-nodejs.html)

#### Serverless Framework

* [Documentación del Framework](https://www.serverless.com/framework/docs)
* [Guía de AWS en Serverless](https://www.serverless.com/framework/docs/providers/aws/guide/intro)
* [GitHub Action de Serverless](https://github.com/serverless/github-action)

#### Repositorio y CI

* [Documentación de GitHub Actions](https://docs.github.com/actions)
* [Documentación de Node.js 20](https://nodejs.org/docs/latest-v20.x/api/)
* [Documentación de Git](https://git-scm.com/doc)

#### Aprendizaje

* [Playlist AWS Serverless](https://www.youtube.com/playlist?list=PLCl11UFjHurBhSQCwGDw7uDd2yAu5tVsV)

</details>
