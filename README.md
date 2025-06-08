# github-actions

## Basics

Se basa en archivos de configuiración en formato YAML. Los principales conceptos son:

- **Workflows**: Son procesos automatizados que se ejecutan en respuesta a **eventos** en un repositorio de GitHub.
Corresponden a cada archivo `.yml` o `.yaml` en el directorio `.github/workflows` del repositorio.

- **Events**: Son actividades que desencadenan la ejecución de un workflow, como un push a la rama principal o la creación de un pull request.

- **Jobs**: Son unidades individuales de trabajo dentro de un workflow. Cada job se ejecuta en un entorno específico (**Runner**) y puede tener múltiples **pasos**.

- **Steps**: Son las acciones individuales que se ejecutan dentro de un job. Cada step puede ejecutar un comando, un script o una **acción de GitHub**. Esta ultima es un contenedor reutilizable de código que puede ser compartido y utilizado en diferentes workflows. Hay un marketplace de acciones de GitHub donde se pueden encontrar y utilizar de forma libre [https://github.com/marketplace](https://github.com/marketplace).

Un ejemplo con comentarios se encuentra en ['ymls/deploy.yml'](ymls/deploy.yml), allí se ven los conceptos principales. En ['ymls/artifacts_test.yml'](ymls/artifacts_test.yml) se pueden ver ejemplos de uso de **artifacts**. Los **artifacts** son archivos o directorios que se generan durante la ejecución de un workflow y que se pueden almacenar y compartir entre jobs del mismo. Esto es útil para pasar resultados de un job a otro o para almacenar resultados de pruebas, por ejemplo.

Dentro de ['ymls/strategy-test.yml'](ymls/strategy-test.yml) se pueden ver  un corto ejemplo de uso de **estrategias** en GitHub Actions. Las estrategias permiten ejecutar un job en múltiples combinaciones de configuraciones, como diferentes versiones de un lenguaje de programación o diferentes sistemas operativos. Esto es útil para pruebas cruzadas y para asegurar que el código funcione en diferentes entornos.

## CI/CD - Integración Continua y Entrega Continua
La integración continua (CI) y la entrega continua (CD) son prácticas de desarrollo de software que permiten a los equipos entregar cambios de manera más rápida y confiable. GitHub Actions facilita la implementación de estas prácticas al permitir la automatización de flujos de trabajo de construcción, prueba y despliegue.

- **Integración Continua (CI)**: Se refiere al proceso de fusionar cambios de código en un repositorio compartido de manera frecuente. Cada cambio se verifica mediante la ejecución de pruebas automatizadas, lo que ayuda a detectar errores de manera temprana y a mantener la calidad del código.

- **Entrega Continua (CD)**: Es la práctica de mantener el código en un estado desplegable en todo momento. Esto implica automatizar el proceso de despliegue para que los cambios se puedan liberar a producción de manera rápida y segura.

Para estudiar esto, se presenta un proyecto muy simple basado en node.js que se encuentra en el directorio ['project-test-GITHUBACT'](project-test-GITHUBACT). Este, además de servir como ejemplo, también permite entender el uso de los **Secrets** y variables de entorno en github. El workflow para este proyecto se encuentra en `.github/workflows/deploy_project.yml`.