## 2.4. Ubiquitous Language

En esta sección se presentan los términos clave del proyecto UI-Topic. Estos términos han sido acordados en el equipo del proyecto y serán usados de manera consistente en la comunicación, documentación y desarrollo del sistema.

 **Term (EN)**               | **Definición (ES)** |
|----------------------------|---------------------|
| **Supply item** *(Insumo)* | Ingrediente o producto consumible necesario para la preparación de platos en el restaurante. Su stock se monitorea continuamente. |
| **Product** *(Producto)* | Elemento registrado en el inventario, puede ser consumible (como alimentos) o no consumible (como utensilios o envases). |
| **Supplier** *(Proveedor)* | Entidad externa encargada de abastecer insumos al restaurante según los pedidos realizados. |
| **Inventory manager** *(Administrador de inventario)* | Persona responsable de supervisar los niveles de stock y realizar pedidos a proveedores. |
| **Stock level** *(Nivel de stock)* | Cantidad disponible de un insumo o producto en el sistema. Puede estar en estado normal, bajo o crítico. |
| **Critical stock level** *(Nivel crítico de stock)* | Umbral mínimo definido para un insumo. Si el stock disponible cae por debajo de este valor, se activa una alerta. |
| **Supply request** *(Solicitud de insumos)* | Pedido formal realizado al proveedor cuando un insumo necesita ser reabastecido. Puede ser generado automáticamente por el sistema o de forma manual. |
| **Replenishment** *(Reposición)* | Proceso mediante el cual un insumo es reabastecido tras recibir un pedido aprobado. Afecta directamente el stock. |
| **Inventory alert** *(Alerta de inventario)* | Notificación automática generada por el sistema cuando un insumo alcanza el nivel crítico o hay un consumo inesperado. |
| **Verified supplier** *(Proveedor verificado)* | Proveedor aprobado por el restaurante para recibir pedidos automáticos del sistema. Debe cumplir ciertos criterios de calidad y tiempo de entrega. |
| **Internal consumption** *(Consumo interno)* | Uso de insumos dentro del restaurante que no está relacionado a ventas directas, como pruebas de recetas o pérdidas por caducidad. |
| **Supply history** *(Historial de insumos)* | Registro de entradas, salidas, consumos y pedidos relacionados a cada insumo del restaurante. |
| **Menu dependency** *(Dependencia de menú)* | Relación entre los platos del menú y los insumos requeridos para su preparación. Afecta el cálculo de stock disponible. |
