# 🥪 Sistema para la Distribución de Alimentos en Zonas Vulnerables

## 📌 Descripción  
Este proyecto es un sistema integral diseñado para mejorar el acceso a alimentos en comunidades vulnerables mediante la gestión eficiente de **heladeras comunitarias**. La solución aborda problemas clave como la falta de disponibilidad de viandas, la distribución ineficiente de donaciones y el monitoreo del estado de las heladeras.  

El sistema permite a los colaboradores registrarse, realizar **donaciones monetarias y de viandas**, gestionar la distribución de alimentos y recibir reconocimientos por su aporte. Además, integra **sensores** para monitorear la temperatura y detectar incidentes en las heladeras, asegurando la calidad y seguridad de los alimentos.  

---  

## 🛠️ Tecnologías Utilizadas  

- **Backend:** Java con el framework Javalin y Hibernate.  
- **Frontend:** Figma, HTML, CSS, JavaScript y Handlebars como motor de plantillas .  
- **Base de Datos:** MySQL con Hibernate como ORM para la persistencia de datos.  
- **APIs:** Integración con servicios externos para geolocalización y mensajería.  
- **Seguridad:** Implementación de OWASP Top Ten y autenticación segura con control de credenciales.  
- **Broker de Mensajería:** Para comunicación en tiempo real con las heladeras y reporte de alertas.  

---  

## ⭐ Características Principales  

### **Gestión de Colaboradores**  
- Registro de colaboradores (personas humanas y jurídicas).  
- Diversas formas de contribución: donaciones monetarias, entrega de viandas, distribución de viandas y administración de heladeras.  
- Sistema de reconocimiento y acumulación de puntos según el aporte realizado.  

### **Gestión de Heladeras**  
- Alta, baja y modificación de heladeras.  
- Ubicación y monitoreo en un mapa interactivo.  
- Sistema de suscripción a heladeras para recibir notificaciones sobre disponibilidad de alimentos o problemas técnicos.  

### **Distribución y Consumo de Viandas**  
- Registro de viandas con detalles como tipo de comida, fecha de caducidad y ubicación.  
- Control de acceso mediante tarjetas asignadas a personas en situación de vulnerabilidad.  
- Restricciones de uso de tarjetas para evitar abusos (cantidad limitada de extracciones por día).  

### **Monitoreo y Seguridad**  
- Sensores de temperatura para detectar anomalías y prevenir el deterioro de alimentos.  
- Sensores de movimiento para alertar posibles robos o accesos indebidos.  
- Reporte de incidentes y asignación automática de técnicos para la reparación de heladeras.  

### **Integraciones y Automatización**  
- API REST para interoperabilidad con otros sistemas.  
- Integración con servicio externo de recomendación de puntos estratégicos para colocar nuevas heladeras.  
- Integración con una pasarela de pagos para gestionar donaciones monetarias.  
- Interfaz conversacional en Telegram para que los técnicos registren incidentes y actualicen el estado de las heladeras.  

### **Reportes y Auditoría**  
- Reportes automáticos sobre cantidad de viandas donadas, distribuidas y consumidas.  
- Registro de fallas e incidentes técnicos.  
- Seguimiento de colaboraciones y gestión de auditoría.  

---  

## 📚 Documentación

### 📌 **Diagramas y Arquitectura**
- [📄 Diagrama de Clases](vianditasONG/docs/diagramas/diagramaDeClases/DDC.png)
- [🗄️ Diagrama Entidad-Relación](vianditasONG/docs/diagramas/diagramaEntidadRelacion/DER.png)
- [🚀 Diagrama de Despliegue](vianditasONG/docs/diagramas/DiagramaDeDespliegue.png)

### 🔌 **API REST**
- [📖 Documentación API REST](APIServicioRecomendadorDePuntosDeDonacion)

### 🛠️ **Instalación y Uso**
- ⚙️ Guía de Instalación
- 📘 Manual de Usuario
- [🎯 Casos de Uso](vianditasONG/docs/diagramas/casosDeUso/UseCaseDiagram.png)

### 🎨 **UX/UI**
- [📐 Wireframes](vianditasONG/docs/front/wireframes/wireframesTotales.pdf)
- [🖼️ Maquetado](vianditasONG/docs/front/maquetado/maquetado.fig)
- [📍 Flujo de Navegación](https://www.figma.com/design/u2p54juzHgMHk7J5hXyxkI/DDS)

### 📦 **Producto Final**
- 📸 Demo

---  

## 📝 Licencia

Este proyecto es de código abierto y puede utilizarse con fines académicos y educativos.
 



