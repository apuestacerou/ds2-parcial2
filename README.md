- Api parcial 2 , desarrollo de software 2
- 2 BRANCHES -> MAIN AND MASTER
- HUMBERTO FAJARDO - ID:409483
- video url : https://www.youtube.com/watch?v=x4ONRNNw-ao
# 🧩 Descripción del Proyecto

**API REST** para gestión de tareas implementada con **arquitectura limpia** en **Node.js + Express**.  
El sistema permite **crear, listar, actualizar y eliminar tareas** con diferentes estados:  
`pending`, `in-progress`, `completed`.

---

## 🧱 2. Decisiones de Diseño

###  Arquitectura Limpia Implementada

Se implementó una **arquitectura limpia** con **separación estricta de responsabilidades**, siguiendo el patrón de capas:

#### 🔹 Controller Layer
Maneja únicamente las peticiones HTTP, validación básica de parámetros y formateo de respuestas.  
No contiene lógica de negocio ni acceso directo a datos.

#### 🔹 Service Layer
Contiene toda la **lógica de negocio**, orquestación de operaciones y validaciones de reglas de negocio.  
Actúa como intermediario entre los *controllers* y *repositories*.

#### 🔹 Repository Layer
Encapsula completamente el **acceso a datos**, proporcionando una interfaz limpia para operaciones CRUD  
sin exponer detalles de implementación.

#### 🔹 Model Layer
Representa el **dominio puro** de la aplicación con lógica específica del negocio  
(por ejemplo, el cálculo automático de `isOverdue`).

#### 🔹 DTO Layer
Maneja la **transferencia de datos entre capas**, validando la entrada y formateando la salida.
> La arquitectura permite cambiar la implementación de persistencia (de memoria a base de datos)  
> sin afectar las capas superiores.

---

## ⚙️ Decisiones Técnicas

- **Node.js + Express:** Elegido por su simplicidad, amplio ecosistema y adecuación para APIs REST ligeras.  
- **Almacenamiento en memoria:** Implementado para simplicidad y portabilidad, fácilmente reemplazable por bases de datos.  
- **Validaciones estrictas:** Fechas futuras obligatorias, estados controlados, manejo consistente de errores.  
- **Respuestas JSON estructuradas:** Formato consistente con campos `success`, `data`, `message` y `error`.


> 💡 Esta separación garantiza **mantenibilidad**, **testabilidad** y cumplimiento
