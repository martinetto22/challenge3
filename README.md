# Challenge 3: Despliegue de Helm Chart en AKS - GitHub Actions Workflow

Este proyecto automatiza el despliegue de un Helm chart en un clúster de AKS utilizando GitHub Actions. El workflow gestiona la instalación de un chart almacenado en un Azure Container Registry (ACR), utilizando Terraform para manejar la infraestructura.

## Contenido
- **variables.yaml:** Contiene las variables clave como el repositorio de Terraform, el nombre del ACR y el chart a desplegar.
- **github_workflow.yaml:** Define el flujo de trabajo para desplegar el chart en AKS.

## Requisitos previos
- **Azure CLI:** Para autenticarse y gestionar recursos en Azure.
- **Terraform:** Utilizado para manejar la infraestructura.
- **Helm:** Requerido para gestionar el despliegue de los charts.
- **kubectl:** Necesario para interactuar con el clúster de AKS.

## Uso
1. Clona este repositorio y personaliza el archivo variables.yaml según tu entorno.
2. Asegúrate de tener los secretos de GitHub configurados:
   
    - AKS_RESOURCE_GROUP
    - AKS_CLUSTER_NAME
    - TERRAFORM_CLOUD_TOKEN
    - ARM_CLIENT_ID
    - ARM_CLIENT_SECRET
    - ARM_SUBSCRIPTION_ID
    - ARM_TENANT_ID

3. Ejecuta el workflow manualmente en GitHub Actions a través de la opción workflow_dispatch.

El workflow instalará las dependencias necesarias, extraerá el chart desde el ACR, y lo desplegará en el clúster de AKS, asegurando siempre utilizar la última versión disponible del chart.