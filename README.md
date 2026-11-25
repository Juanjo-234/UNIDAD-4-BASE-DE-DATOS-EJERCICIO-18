# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-18
1. Entidades Principales y Personal
producto: Almacena el catálogo de productos terminados fabricados por la planta. Sus campos son codigo_producto (clave primaria), nombre_comercial, descripcion_tecnica y tiempo_fabricacion.

empleado: Registra al personal de la fábrica, incluyendo operarios, inspectores y supervisores. Contiene id_empleado (clave primaria), nombre, apellido, email, rol y telefono.

componente: Contiene los elementos, insumos o piezas individuales que conforman los artículos. Posee codigo_componente (clave primaria), nombre_comercial, laboratorio, num_lote y codigo_producto (clave foránea).

2. Estructura de Montaje y Fabricación
linea_montaje: Administra las líneas de ensamblaje físicas de la planta. Sus atributos son codigo_linea (clave primaria), descripcion y id_empleado (clave foránea que referencia al responsable a cargo).

orden_fabricacion: Controla las órdenes de producción emitidas por la gerencia. Sus campos incluyen numero_orden (clave primaria), fecha_emision, cantidad, estado, linea_asignada y codigo_producto (claves foráneas hacia la línea de montaje y el producto).

unidad_produccion: Registra los lotes o unidades específicas fabricadas. Sus atributos son id_unidad_produccion (clave primaria), cantidad_producida, fecha_produccion, numero_orden y codigo_producto.

3. Control de Calidad y Relaciones Jerárquicas
parte: Tabla asociativa autorreferencial que permite estructurar la jerarquía de componentes y ensamblajes complejos (relación de componente padre y subcomponente). Su clave primaria es compuesta por (codigo_componente_padre, codigo_componente).

inspeccion_calidad: Gestiona las revisiones, auditorías y pruebas de calidad aplicadas a la producción. Sus campos son id_inspeccion (clave primaria), fecha, hora, resultado, id_empleado (inspector) y id_unidad_produccion.


IMAGEN DE EJEMPLO DE UNA CONSULTA:
<img width="965" height="336" alt="image" src="https://github.com/user-attachments/assets/669aa7e2-4a90-4aca-8839-3ee187ab1aa5" />


4. Restricciones e Integridad Referencial
El script configura de manera estricta las reglas de validación mediante claves primarias y foráneas para asegurar la consistencia relacional entre componentes, productos, órdenes de fabricación, líneas de montaje, personal y controles de calidad.
