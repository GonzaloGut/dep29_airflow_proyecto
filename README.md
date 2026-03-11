# Pipeline de Ventas End-to-End: GCP + Airflow

Este proyecto implementa una arquitectura de datos moderna para la ingesta, procesamiento y almacenamiento de transacciones de ventas en tiempo real. Utiliza un enfoque **Event-Driven** para garantizar la resiliencia y escalabilidad del flujo de datos.

## 🏗️ Arquitectura
El flujo de datos sigue la siguiente ruta:
**FastAPI (Producer)** -> **GCP Pub/Sub** -> **Apache Airflow (Orquestador)** -> **Cloud Storage (Data Lake)** -> **BigQuery (Data Warehouse)**.

## 🛠️ Stack Tecnológico
- **Lenguaje:** Python (FastAPI)
- **Nube (GCP):** Pub/Sub, Cloud Storage, BigQuery, IAM.
- **Orquestación:** Apache Airflow.
- **Contenedorización:** Docker & Docker Compose.

## 🚀 Cómo ejecutar el proyecto

### 1. Prerrequisitos
- Tener instalado **Docker** y **Docker Compose**.
- Contar con una cuenta de **Google Cloud Platform** y un archivo de credenciales (`key.json`) de una Service Account con permisos para Pub/Sub, Storage y BigQuery.

### 2. Configuración del Entorno
Clona el repositorio y crea un archivo `.env` en la raíz con las siguientes variables:
```env
GCP_PROJECT_ID=tu-id-de-proyecto
PUB_SUB_TOPIC=nombre-del-topic
PUB_SUB_SUBSCRIPTION=nombre-de-suscripcion
GCP_SERVICE_ACCOUNT_KEY=/ruta/en/contenedor/key.json

Ejecutar con Docker Compose:
```bash
docker-compose up airflow-init
docker-compose up -d
