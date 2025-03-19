# 🏪 Marketplace - Sistema de Base de Datos
## 📌 Descripción
Este proyecto consiste en el desarrollo de un sistema de **Marketplace**, en el cual vendedores y clientes pueden interactuar a través de publicaciones, ventas, pagos y envíos. Además, se implementará un modelo de **Inteligencia de Negocios (BI)** para el análisis y la toma de decisiones.

---

## 🏗️ Componentes del Proyecto

### 📂 Modelo Transaccional
Sistema de base de datos que gestiona:
- **Publicaciones**: Creación y administración de productos en venta.
- **Ventas**: Registro de compras realizadas por clientes.
- **Pagos**: Asociación de pagos a ventas.
- **Envíos**: Gestión de entregas de productos.
- **Facturación**: Cobros por publicaciones y comisiones de ventas.

### 🔄 Migración de Datos
- Implementación de **Stored Procedures (SP)** para normalizar y transferir datos.
- Transformación de la tabla maestra desorganizada en un modelo relacional estructurado.

### 📊 Inteligencia de Negocios (BI)
Modelo de datos orientado al análisis de métricas clave:
- **Tiempo promedio de publicaciones**.
- **Stock inicial promedio** por marca.
- **Ventas mensuales** por ubicación.
- **Rendimiento de rubros más vendidos**.
- **Volumen de ventas por franja horaria**.
- **Análisis de pagos en cuotas**.
- **Cumplimiento de tiempos de entrega**.
- **Facturación por provincia**.

---

## 🛠️ Tecnologías y Conceptos Utilizados
- **Microsoft SQL Server 2019**
- **SQL (T-SQL)**
- **Stored Procedures y Triggers**
- **Índices y optimización de consultas**
- **Modelado de datos (DER y Modelo Relacional)**
- **Consultas analíticas y vistas BI**

---

## 📂 Estructura del Proyecto
```
📦 marketplace_db
 ├── 📄 README.md  # Documentación principal
 ├── 📄 estrategia.pdf  # Justificación de diseño
 ├── 📄 DER.jpg  # Modelo Relacional
 ├── 📄 DER_BI.jpg  # Modelo de BI
 ├── 📂 data
 │   ├── script_creacion_inicial.sql  # Creación del modelo transaccional y migración
 │   ├── script_creacion_BI.sql  # Creación del modelo BI y carga de datos
```

---

## 🚀 Instalación y Uso

### 📥 Instalación de SQL Server
Descargar e instalar **Microsoft SQL Server 2019** y **SQL Server Management Studio (SSMS)** desde:
[SQL Server 2019 Express](https://www.microsoft.com/es-ar/sql-server/sql-server-2019)

### ⚙️ Creación de la Base de Datos
1. Abrir **SQL Server Management Studio** y conectarse al servidor.
2. Crear la base de datos ejecutando:
   ```sql
   CREATE DATABASE GD2C2024;
   ```

### 📜 Ejecución de Scripts
1. **Ejecutar el script de modelo transaccional:**
   ```sh
   sqlcmd -S localhost\SQLSERVER2019 -U usuario -P contraseña -i data/script_creacion_inicial.sql
   ```
2. **Ejecutar el script de BI:**
   ```sh
   sqlcmd -S localhost\SQLSERVER2019 -U usuario -P contraseña -i data/script_creacion_BI.sql
   ```

---

## 📊 Consultas BI y Reportes
Para obtener métricas analíticas, ejecutar las vistas creadas en el modelo BI:
```sql
SELECT * FROM BI_Ventas_Mensuales;
SELECT * FROM BI_Rendimiento_Rubros;
SELECT * FROM BI_Facturacion_Provincia;
```

---

## 📜 Licencia
Este proyecto es de código abierto y puede utilizarse con fines académicos y educativos.

