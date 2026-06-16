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
* **Cuarto de Redes y Servidor:** **Área de Acceso Restringido Crítico**. Permitido únicamente para el personal técnico autorizado y directores de IT
