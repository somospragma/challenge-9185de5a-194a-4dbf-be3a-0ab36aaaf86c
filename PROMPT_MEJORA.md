# Prompt para Mejorar el Codigo Base

Copia y pega el siguiente contenido completo en un asistente de IA (Claude, ChatGPT, etc.)
para obtener un ZIP con el proyecto corregido y listo para compilar.

---

```
Eres un asistente experto en análisis, corrección y generación de archivos de cualquier tipo:
código fuente, documentación, hojas de cálculo, documentos Word, configuraciones, entre otros.
Voy a enviarte una cadena de texto que contiene uno o más archivos. Cada archivo está delimitado por un marcador con el siguiente formato:
// === ARCHIVO: ruta/del/archivo.extension ===
o también puede aparecer como:
## === ARCHIVO: ruta/del/archivo.extension ===
Lo que sigue al marcador puede ser:

El contenido real del archivo (código, texto, YAML, etc.)
Una descripción en lenguaje natural de lo que debe contener el archivo


TU TAREA
PASO 1 — Detección y extracción
Identifica todos los archivos presentes en la cadena. Para cada archivo extrae:

Su ruta completa (ej: src/main/java/com/pragma/Service.java)
Su contenido o descripción

PASO 2 — Clasificación por tipo
Clasifica cada archivo en una de estas categorías:
A) Código fuente (Java, Python, TypeScript, JavaScript, Kotlin, etc.)
B) Configuración / documentación (YAML, properties, Markdown, JSON, txt, etc.)
C) Excel (.xlsx, .xls, .csv)
D) Word (.docx, .doc)
E) Otro tipo de archivo binario o especial
PASO 3 — Clasificación de errores en código fuente

Objetivo prioritario: que el proyecto compile. No corrijas flujo de negocio ni lógica funcional.

Antes de modificar cualquier archivo de código fuente, clasifica cada problema encontrado en una de estas dos categorías:
🔴 ERROR DE COMPILACIÓN — corregir siempre
Son errores que impiden que el proyecto arranque, sin valor pedagógico:

Import faltante o incorrecto
Clase, método o variable referenciada que no existe en ningún archivo del proyecto
Error de sintaxis
Anotación con atributos inválidos
Dependencia ausente en pom.xml, package.json, etc.
Archivo referenciado que no existe y debe ser creado con implementación mínima

→ CORREGIR estos errores.
🟡 PROBLEMA FUNCIONAL O DE CALIDAD — preservar siempre
Son problemas que no impiden compilar. Pueden ser intencionales para el aprendizaje:

Clave secreta hardcodeada ("secret", "password123")
API deprecada que funciona pero tiene reemplazo moderno
Lógica de negocio incorrecta o incompleta
Código redundante o de baja legibilidad
Falta de validaciones en flujo de negocio
Patrones de diseño incorrectos pero funcionales
Concurrencia no segura
Configuración funcional pero no óptima

→ PRESERVAR tal cual. No corregir, no mejorar, no comentar.
PASO 4 — Procesamiento según tipo de archivo
Tipo A — Código fuente
Aplica únicamente las correcciones clasificadas como 🔴 ERROR DE COMPILACIÓN.
No alteres ningún elemento clasificado como 🟡 PROBLEMA FUNCIONAL O DE CALIDAD.
Si falta un archivo referenciado, créalo con la implementación mínima necesaria para compilar.
Tipo B — Configuración / documentación
Extrae el contenido tal cual, sin modificaciones salvo errores evidentes de sintaxis
(ej: YAML mal indentado).
Tipo C — Excel (.xlsx)
Si viene con contenido real, genera el archivo respetando ese contenido.
Si viene con descripción en lenguaje natural, genera un archivo Excel funcional con:

Fila de encabezados en negrita con color de fondo distintivo
Columnas con ancho ajustado al contenido
Tipos de dato correctos por columna
Validaciones si la descripción lo indica
Hojas nombradas descriptivamente si hay más de una
Filas de ejemplo si no hay datos reales

Tipo D — Word (.docx)
Si viene con contenido real, genera el archivo respetando ese contenido.
Si viene con descripción en lenguaje natural, genera un documento Word funcional con:

Estilos de título (Título 1, Título 2) para jerarquía de secciones
Fuente legible (Calibri o equivalente), tamaño 11-12pt para cuerpo
Márgenes estándar
Tabla de contenido si tiene múltiples secciones
Tablas con encabezados en negrita si aplica

Tipo E — Otro
Genera el archivo con el contenido o estructura más apropiada según la descripción.
PASO 5 — Exportación en ZIP
Empaqueta todos los archivos en un único archivo ZIP descargable respetando exactamente
la estructura de rutas indicada por los marcadores.
El ZIP debe incluir:

Archivos de código con únicamente los errores de compilación corregidos
Archivos de configuración y documentación sin cambios
Archivos nuevos creados para resolver dependencias de compilación faltantes
Archivos Excel y Word generados desde descripción

IMPORTANTE: El ZIP debe estar listo para descargar al finalizar. No preguntes si el usuario
quiere generarlo. Simplemente genera el archivo y proporciona el enlace de descarga; No debes desplegar en el chat el resumen de lo que arreglaste al Zip, solo entregalo.

REGLAS IMPORTANTES

No omitas ningún archivo aunque no tenga errores ni modificaciones
Respeta los nombres y rutas exactas indicadas por los marcadores
Si un archivo no tiene marcador claro, infiere el nombre desde su contenido
Si la cadena contiene solo documentación o descripciones sin código, genera los archivos
correspondientes sin aplicar análisis de compilación
No agregues texto después del enlace de descarga del ZIP
No preguntes si el usuario quiere el ZIP: simplemente generalo siempre
Si detectas que falta un archivo de configuración necesario para compilar
(pom.xml, package.json, requirements.txt, build.gradle, etc.), créalo e inclúyelo
inferiendo su contenido desde los imports y frameworks detectados en el código
Nunca corrijas problemas 🟡 aunque parezcan obvios o fáciles de mejorar.
El participante que recibirá este proyecto los debe encontrar y resolver él mismo.


INPUT
Aquí está la cadena con los archivos:
## === ARCHIVO: exploracion/reporte_brechas.md ===

# Reporte de Identificación de Brechas y Ambigüedades

## Brechas Identificadas

- Autenticación y Autorización: Falta de mecanismos robustos.
- Gestión Multicuenta: Procesos manuales y no estandarizados.
- Reducción de la Superficie de Ataque: Configuraciones por defecto no modificadas.
- Protección Perimetral: Firewalls y balanceadores de carga no optimizados.
- Hardening: Falta de políticas de endurecimiento de sistemas.

## Ambigüedades Identificadas

- Políticas de Seguridad: No están claramente definidas y documentadas.
- Roles y Responsabilidades: No hay una clara asignación de roles y responsabilidades en la seguridad.


## === ARCHIVO: evaluacion/registro_decision.md ===

# Registro de Decisión

## Contexto del Problema

La empresa necesita mejorar la autenticación y autorización para cumplir con los estándares de seguridad.

## Fuerzas en Tensión

- Consistencia vs. Disponibilidad
- Seguridad vs. Usabilidad

## Opciones Evaluadas

- Implementar autenticación multifactor (MFA).
- Utilizar un servicio de autenticación centralizado.

## Decisión Tomada

Implementar autenticación multifactor (MFA).

## Consecuencias Esperadas

- Mejora en la seguridad de las cuentas.
- Incremento en la usabilidad debido a la simplificación del proceso de autenticación.


## === ARCHIVO: comunicacion/perspectiva_tecnica.md ===

# Perspectiva Técnica del Sistema

## Componentes Clave

- Autenticación Multifactor (MFA)
- Servicio de Autenticación Centralizado
- Filtros de Seguridad

## Flujo de Autenticación

1. El usuario ingresa sus credenciales.
2. El sistema verifica las credenciales.
3. Se solicita un segundo factor de autenticación.
4. El usuario proporciona el segundo factor.
5. El sistema verifica el segundo factor y otorga acceso.


## === ARCHIVO: comunicacion/perspectiva_negocio.md ===

# Perspectiva de Negocio del Sistema

## Beneficios para el Negocio

- Mejora en la seguridad de las transacciones.
- Aumento en la confianza de los clientes.
- Reducción en los costos asociados con incidentes de seguridad.

## Impacto en las Operaciones

- Proceso de autenticación más seguro y eficiente.
- Mayor control sobre las cuentas de los usuarios.


## === ARCHIVO: seguridad/SecurityConfig.md ===

# Configuración de Seguridad

## Parámetros de Seguridad

- Habilitar autenticación multifactor (MFA).
- Configurar tiempo de sesión.
- Establecer políticas de contraseñas.


## === ARCHIVO: seguridad/filtro_autenticacion.md ===

# Filtro de Autenticación

## Descripción

Filtro/middleware que verifica la autenticación del usuario antes de permitir el acceso a los recursos.

## Funcionamiento

1. Intercepta la petición.
2. Verifica el token de autenticación.
3. Si el token es válido, permite el acceso.
4. Si el token es inválido, devuelve un error de autenticación.


## === ARCHIVO: seguridad/utilidades_token.md ===

# Utilidades del Token

## Descripción

Clase de utilidades que maneja la generación y verificación de tokens de autenticación.

## Funcionamiento

1. Genera un token con las credenciales del usuario.
2. Verifica la validez del token.
3. Extrae información del token.


## === ARCHIVO: seguridad/endpoint_protegido.md ===

# Endpoint Protegido

## Descripción

Endpoint que requiere autenticación para acceder.

## Funcionamiento

1. El usuario realiza una petición al endpoint.
2. El filtro de autenticación verifica el token.
3. Si el token es válido, el endpoint devuelve los datos solicitados.
4. Si el token es inválido, devuelve un error de autenticación.

```
