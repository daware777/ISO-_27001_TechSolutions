# 📋 Guía de Inventario de Activos y Delimitación del Alcance
**Documento de Trabajo:** `Activos de Información.docx`  
**Caso de Estudio:** TechSolutions  

---

## 🔹 Paso 1: Identificar Activos de Información

### Inventario Inicial por Sucursal

#### **Sucursal San José (Oficina Central)**
* **Computadoras:** 10 unidades (5 de escritorio / 5 laptops).
* **Servidores:** 1 Servidor Central.
* **Bases de Datos:** 3 bases de datos principales (Clientes, Productos, Ventas).
* **Conectividad y Redes:** 3 Módems.
* **Periféricos de Operación:** Escáneres de códigos de barras y Datáfonos de cobro.
* **Resiliencia Energética:** 1 Planta eléctrica de emergencia (autonomía mínima de 1 hora para todo el local) y 2 UPS.

#### **Sucursal Cartago**
* **Computadoras:** 10 unidades (5 de escritorio / 5 laptops).
* **Conectividad y Redes:** 3 Módems.
* **Periféricos de Operación:** Escáneres de códigos de barras y Datáfonos de cobro.
* **Resiliencia Energética:** 1 Planta eléctrica de emergencia (autonomía mínima de 1 hora para todo el local) y 2 UPS.

### Clasificación de Importancia de los Activos

| Activo de Información | Clasificación de Criticidad | Justificación Operativa |
| :--- | :--- | :--- |
| **Computadoras de Escritorio** | 🔴 **Alto** | Equipos fijos esenciales para cajas y atención al cliente. |
| **Laptops** | 1000000000 🟡 **Medio** | Equipos móviles asignados a soporte técnico y tareas flexibles. |
| **Servidor Central** | 🔴 **Alto** | Núcleo del procesamiento local y alojamiento de servicios. |
| **Bases de Datos (x3)** | 🔴 **Alto** | Contienen la información crítica de Clientes, Productos y Ventas. |
| **Datáfonos** | 🔴 **Alto** | Canal directo para la recaudación financiera y transacciones. |
| **Escáneres de Código de Barras** | 🔴 **Alto** | Vitales para la agilidad de la venta física y control de stock. |

---

## 🔹 Paso 2: Definición del Alcance del SGSI

### 2.1 Definir Límites Físicos y Áreas Restringidas
El perímetro físico del sistema se concentra en las operaciones distribuidas de la empresa, divididas en las siguientes zonas de acceso controlado:

* **Oficina Central / Dirección:** Zona exclusiva para directores de departamento y ejecutivos corporativos bajo necesidad justificada.
* **Mesa de Servicio y Soporte:** Espacio de trabajo para los agentes de IT, el taller de reparaciones lógicas y el acceso técnico directo.
* **Cuarto de Redes y Servidor:** **Área de Acceso Restringido Crítico**. Permitido únicamente para el personal técnico autorizado y directores de IT.
* **Tienda y Bodega:** Zona comercial abierta al público. El ingreso a la **Bodega de Productos** está restringido exclusivamente a agentes de ventas y técnicos autorizados para el retiro de stock.

### 2.2 Definir Límites Virtuales y Lógicos
La infraestructura digital se segmenta mediante **redes VLAN independientes** para asegurar que el tráfico y las vulnerabilidades de un entorno no interfieran con las operaciones de los demás.

* **Entorno de Tienda y Cajas:** Permite acceso controlado de lectura/escritura a las bases de datos de catálogo, clientes y actualización de stock en línea.
* **Entorno de Mesa de Servicio:** Acceso al catálogo y base de datos de clientes. Integra un servicio cloud externo (**Atlassian**) para la gestión y seguimiento de tickets de reparación técnica.
* **Entorno de Dirección y Operaciones:** Acceso total y centralizado a las 3 bases de datos (Clientes, Productos, Ventas) para control de servicios y métricas del negocio.
* **Canales Públicos y Nube:** * **Página Web Pública:** Acceso libre en internet donde los usuarios externos crean cuentas, gestionan sus productos comprados y levantan tickets de soporte.
    * **Entorno Interno de Ventas/TI:** Interfaz para verificar disponibilidad de stock en tiempo real entre bodegas y sucursales.
    * **Entorno de Reportes Cloud:** Módulo analítico en la nube para el control centralizado de ventas y auditoría de inventario.

---

## 🔹 Paso 3: Identificación de Partes Interesadas

Se determina que todas las áreas de la organización actúan como partes interesadas dentro del SGSI, asignando las siguientes responsabilidades de seguridad:

* 👥 **Agentes de Ventas y Servicio al Cliente:** Primera capa de interacción con los datos. Tienen prohibido editar o alterar la estructura de las bases de datos de forma directa. Capturan la información diaria de transacciones y stock; un proceso automatizado se encarga de procesar y alimentar las bases de datos de manera segura.
* 🛠️ **Agentes de IT y Redes:** Custodios técnicos de la infraestructura corporativa. Son encargados del mantenimiento, aseguramiento y actualización de la página web, terminales de caja, laptops de testeo, servidor central, routers, firewalls y circuito cerrado de televisión (CCTV).
* 💼 **Dirección y Alta Gerencia:** Gobierno corporativo y cumplimiento normativo. Responsables de mantener el control administrativo de los activos, gestión de personal (planillas), supervisión de ingresos, operaciones generales y relación contractual con proveedores de tecnología.

---

## 🔹 Paso 4: Inventario Consolidado de Activos (Para Evaluación de Riesgos)

Para los fines del análisis y evaluación de riesgos, los activos se desglosan formalmente en las siguientes cuatro categorías fundamentales:

### 🖥️ Hardware
* 10 Computadoras de escritorio.
* 10 Laptops corporativas.
* 1 Computadora dedicada exclusivamente a testeos de hardware en taller.
* Cámaras de Circuito Cerrado de Televisión (CCTV) distribuidas en Tienda, Bodega y Taller.
* 8 Datáfonos de cobro transaccional.
* 10 Escáneres de códigos de barras.
* 6 Módems/Routers de comunicación.
* 1 Servidor Físico Central.
* 2 Firewalls locales perimetrales.
* 4 Fuentes de alimentación y 4 unidades de respaldo eléctrico (UPS).

### ⚙️ Software
* **Sistemas Operativos de Usuario:** Microsoft Windows (en la mayoría de terminales de trabajo).
* **Sistema Operativo del Servidor:** Linux (entorno de producción).
* **Plataforma Web Corporativa:** Aplicación montada en el servidor local.
* **Software de Seguridad:** Solución Antivirus Kaspersky con administración centralizada.

### 📊 Datos
* Registros e inventario de Stock de artículos y productos.
* Historiales de Ventas e ingresos financieros.
* Módulo de Tickets e historial de reparaciones técnicas.
* Bases de datos de Clientes (datos personales y cuentas activas).
* Datos administrativos internos (Planilla de empleados y registros de pagos).
* Logs y entradas de registro de la página web.

### 👥 Personal (Recursos Humanos)
* 10 Agentes de servicio al cliente y ventas.
* 10 Técnicos de IT y administración de redes.
* 2 Jefes encargados de la Mesa de Servicio.
* 2 Contadores generales.
* 2 Secretarias administrativas.
* 4 Colaboradores de servicios misceláneos.
* 2 Directores ejecutivos.
