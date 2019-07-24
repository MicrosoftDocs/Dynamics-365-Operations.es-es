---
title: Procesamiento de producto con peso capturado con la gestión de almacenes
description: Este tema describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.
author: perlynne
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 85b6cad04032877b63b4da3a097cae82c63f36ad
ms.sourcegitcommit: bf05924747368a5204c4c70882e3347bfa295e29
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "1633092"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Procesamiento de producto con peso capturado con la gestión de almacenes

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/pivate-preview-banner.md)]


## <a name="feature-exposure"></a>Exposición de la función

Para usar la gestión de almacén para procesar los productos con peso capturado, debe usar una clave de configuración de la licencia para activar la funcionalidad. (Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**. A continuación, en la pestaña **Claves de configuración** , expanda **Comercio \> Administración del almacén y el transporte**, y seleccione la casilla para **Peso capturado para el almacén**).

> [!NOTE]
> Tanto la clave de configuración de la licencia **Administración del almacén y el transporte** y las claves de configuración de la licencia **Procesar distribución \> Peso capturado** también se deben activar.

Después de que se vuelva a activar la clave de configuración de la licencia, al crear un producto liberado, puede seleccionar **Peso capturado**. También puede asociar el producto lanzado a un grupo de dimensiones de almacenamiento que el parámetro **Procesos de gestión de almacenes de uso** se ha seleccionado.

Para poder usar el producto en la gestión del almacén, debe hacer cierta configuración básica del producto para peso capturado:

- Defina la conversión nominal del peso entre la unidad de peso capturado (cuadro) y la unidad de inventario (kilogramo \[kg\]) como parte de una definición de conversión de unidades.
- Defina tolerancias mínimas y máximas de peso como parte de la configuración de la unidad de peso capturado.
- Configurar un grupo de la secuencia de la unidad en la unidad de peso capturado se define como la referencia de almacén inferior (SKU).
- Configurar una directiva de manipulación de artículos con peso capturado

Para obtener más información, consulte [Configuración y mantenimiento de artículos con peso capturado](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Ajustes de transacciones

Dado que el peso del inventario cuando especifica un almacén puede ser diferente del peso cuando se emite el inventario fuera del almacén, el procesamiento de producto con peso capturado debe ajustar el inventario.

**Ejemplo 1**

Durante un proceso de producción **Notificar como terminado** , el peso de entrada de una matrícula de entidad de almacén que contiene ocho cajas de un producto con peso capturado se captura como 80,1 kilogramos. La matrícula de entidad se almacena en el área de productos finalizados y durante el proceso de almacenado, algo de peso se pierde en el aire.

Más adelante, como parte de un proceso de selección de pedido de ventas, el peso de la misma matrícula de entidad se captura como 79,8 kilogramos. Por tanto, en el sistema, dispondrá una diferencia del peso como parte del conjunto de dimensiones físico.

En este caso, el sistema ajusta automáticamente la diferencia registrando una transacción para los 0,3 kg que faltan.

**Ejemplo 2**

En su definición, un producto se configura para tolerar un peso mínimo de 8 kilogramos y un máximo de 12 kg para la unidad **Caja** de peso capturado.

Tiene dos cajas del producto y tienen un peso registrado de 16 kilogramos. Si un trabajador del almacén pesa y selecciona una de las cajas, y el peso se captura como 9 kg, la caja restante pesará 7 kilogramos. Sin embargo, dado que 7 kg por debajo del peso mínimo, el sistema realiza un ajuste automático para aumentar el peso del inventario disponible en 1 kilogramo.

Para configurar las cuentas en que estos ajustes se registrarán, vaya a **Coste la administración \> Directivas de integración contable configurados \> Registro**. A continuación, en la pestaña **Inventario** , defina las cuentas siguientes:

- Cuenta de pérdidas de peso capturado 
- Cuenta de ganancias de peso capturado 

## <a name="catch-weight-item-handling-policy"></a>Directiva de manipulación de artículos con peso capturado

El artículo con directiva de administración de peso capturado define los dos flujos principales de gestión de almacenes de los artículos: cuando el peso de los artículos se obtiene, y cómo se captura.

Puede definir cuando el peso se captura para ventas y el procesamiento del pedido de transferencia. El peso se puede capturar durante cualquiera de los siguientes procesos:

- **Selección** - El peso se captura durante las líneas iniciales del trabajo de la selección de trabajo del pedido.
- **Embalaje** - La captura peso se durante el embalaje manual. (Debe enviar los artículos a una instalación de embalaje).

Si el peso real se captura en la instalación de acondicionamiento durante los procesos de embalaje de contenedor, no se solicitará a los trabajadores del almacén capturar el peso de trabajo durante la selección. En su lugar, el peso medio del inventario físico se usará como el peso del inventario seleccionado que va al área de embalaje.

Para los procesos internos de gestión de almacenes como correcciones del recuento y ajustes, se puede definir si se captura el peso. Si no capturó el peso, se usará el nominal.

También puede definir cómo se captura el peso. En uno de los dos flujos principales, las etiquetas de peso capturado se siguen y se utilizan para capturar peso. En el otro flujo, etiquetas de peso capturado no se siguen.

- **Sí** El artículo utiliza etiquetas de peso capturado. Cada número de etiqueta representa una unidad de peso capturado (caja), y un peso y otra información está asociado con la etiqueta. Para los procesos de salida, se utiliza el peso que está asociado a la etiqueta.
- **No** - El artículo no utiliza etiquetas de peso capturado. Los procesos de pesado de entrada y salida se basan en el peso real que se captura durante cada proceso.

El proceso de seguir etiquetas de peso capturado se puede usar para los artículos que no cambiarán el peso durante el período de almacenado. El peso se captura sólo durante el proceso de entrada del almacén. Durante el proceso de salida, las etiquetas de peso capturado sólo se digitalizan, y los pesos que están asociados a las etiquetas se usarán para el procesamiento de salida transaccional.

### <a name="how-to-capture-catch-weight"></a>¿Cómo capturar el peso capturado?

Cuando se usa el seguimiento de la etiqueta de peso capturado, siempre se debe crear una etiqueta para cada captura de peso que reciba la unidad y cada etiqueta se debe asociar siempre en un peso.

Por ejemplo, **Caja** es la unidad de peso capturado, y usted recibe un pallet de ocho cajas. En este caso, deberán crearse ocho etiquetas únicas de peso capturado, y un peso se debe asociar a cada etiqueta. En función de la etiqueta de entrada con peso capturado, el peso de las ocho cajas puede capturarse, y el peso medio se puede distribuir a cada caja, o se puede capturar un peso único para cada caja.

Cuando el seguimiento de la etiqueta de peso capturado no se usa, el peso se puede obtener para cada conjunto de dimensiones (por ejemplo, para cada matrícula de entidad y dimensión de seguimiento). Como alternativa, el peso se puede capturar en función de un nivel agregado, como cinco matrículas de entidad (pallets).

Para los métodos para capturar el peso de salida, puede definir si el pesado se realiza para cada unidad de peso capturado (es decir, por caja), o si el peso se captura basándose en la cantidad que se seleccionada (por ejemplo, tres cajas). Tenga en cuenta que para el proceso de selección de la línea y el de movimiento interno, el peso medio se usará si se usa la opción **No capturado**.

Para limitar que los procesos de selección de la gestión de almacenes capturen pesos que puedan generar ajustes beneficios/pérdidas en los pesos capturados, puede usar el método de varianza de peso de salida.

## <a name="supported-scenarios"></a>Escenarios admitidos

No todos los flujos de trabajo son compatibles con el procesamiento de producto con peso capturado en la gestión de almacenes. Actualmente se aplican las siguientes restricciones.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configurar productos de peso capturado para los procesos de gestión de almacenes

- Para los productos con peso capturado, el grupo de dimensiones de almacenamiento para artículos no se puede modificar (para poder utilizar procesos de gestión de almacenes con ellos).
- Solo el procesamiento de la fórmula se admite para los productos con peso capturado (no lista de materiales).
- Los productos con peso capturado no se pueden asociar un grupo de dimensiones de seguimiento mediante la dimensión del propietario.
- Los productos con peso capturado no se pueden usar como servicios.
- Los productos con peso capturado se pueden usar como “productos mantenidos en existencias” sólo como parte el grupo de modelos de artículos.
- Los productos con peso capturado no se pueden usar junto con la funcionalidad para seguir “Activo en proceso de ventas.”
- Los productos con peso capturado no se pueden usar junto con la funcionalidad para capturar números de serie. Por lo tanto, los productos no se pueden transferir de “en blanco” a un número de serie como parte de la selección/proceso de embalaje.
- Los productos con peso capturado no se pueden usar junto con la funcionalidad para registrar números de serie antes del consumo.
- Los productos con peso capturado con variante habilitada no se pueden usar junto con la funcionalidad para convertir unidades de medida variables.
- No se puede marcar productos de peso capturado como "kit de producto" minorista.
- Los productos con peso capturado sólo se pueden usar en un grupo de secuencias que tenga unidades de gestión de material de peso capturado y que contenga la unidad de peso capturado como la secuencia más baja.
- Para los productos con peso capturado, la unidad de inventario se puede convertir a la unidad de peso capturado si la conversión genera una cantidad nominal mayor de 1.
- La configuración de los códigos de barras para los productos con peso capturado no admite una configuración variable de peso.
 
### <a name="order-processing"></a>Procesamiento de pedidos

- La creación de aviso de envío por adelantado (estructuras de ASN/embalaje) no admite la información de peso.
- La cantidad del pedido debe mantenerse según la unidad de peso capturado.
 
### <a name="inbound-warehouse-processing"></a>Procesamiento de entradas en el almacén

- Recibir las matrículas requiere que los pesos sean asignados durante el registro, porque la información del peso no se admite como parte del aviso de envío por adelantado. Cuando se usan los procesos de la etiqueta de peso capturado, el número de etiqueta se debe asignar manualmente por unidad de peso capturado.
 
### <a name="inventory-and-warehouse-operations"></a>Operaciones de inventarios y almacenes

- La creación manual de pedidos de cuarentena no se admite para los productos con peso capturado.
- El movimiento manual de inventario relacionado con el trabajo no se admite para los productos de peso capturado.
- Los productos de peso capturado no admiten la consolidación de matrículas de entidad.
- La carga del número de matrícula de entidad al inicializar las existencias del almacén no se admite para los productos con peso capturado.
- Los procesos de equilibrio por lotes no son admitidos para los productos de peso capturado.
- La gestión del inventario negativo físico no se admite para los productos con peso capturado.
- El marcado de inventario no se puede usar para los productos con peso capturado.
 
### <a name="outbound-warehouse-processing"></a>Procesamiento de salidas en el almacén

- La funcionalidad para la selección del clúster no se admite para los productos con peso capturado.
- El procesamiento del almacén de la selección y el embalaje no se admite para los productos con peso capturado.
- Para los productos con peso capturado, el trabajo que se define en una plantilla de trabajo puede ejecutarse automáticamente.
- La funcionalidad para la inversión de trabajo no se admite para los productos con peso capturado.
- Para los productos con peso capturado, no se admite el procesamiento manual de instalación de acondicionamiento donde se realiza el trabajo después de que se pongan contenedores.
- La funcionalidad para el escaneo pieza a pieza no se admite para los productos con peso capturado.
 
### <a name="production-processing"></a>Proceso de producción

- Para los productos con peso capturado, sólo se admiten los pedidos de lote para los productos de la fórmula.
- La funcionalidad kanban no se admite para los productos con peso capturado.
- Para los productos con peso capturado, los números de serie no se pueden registrar antes del consumo.
- La funcionalidad para la inversión de matrículas de entidad se admite para los productos con peso capturado.
- Para los productos con peso capturado, el notificar como terminado no se puede registrar por número de serie.

### <a name="transportation-management-processing"></a>Procesado de la administración del transporte

- Los productos de peso capturado no admiten el procesado de área de trabajo de planificación de la carga.
- Las líneas de la solicitud de transporte no se admiten para los productos con peso capturado.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Otras restricciones y comportamientos para el procesamiento de productos con peso capturado con la gestión de almacenes

- Durante los procesos de la selección en los que no se pide al usuario identificar dimensiones de seguimiento, la asignación del peso se realiza en función del peso medio. Este comportamiento aparece si, por ejemplo, una combinación de dimensiones de seguimiento se usa en la misma ubicación y, después de que un usuario procese selección, sólo un valor de la dimensión de seguimiento se deja en la ubicación.
- Cuando el inventario se reserva para un producto con peso capturado que está configurado para los procesos de gestión de almacenes, la reserva se realiza en función del peso mínima definido, incluso si esta cantidad es la cantidad que se ha administrado a mano. Este comportamiento difiere del comportamiento de los artículos que no se configuran para los procesos de la gestión de almacenes.
- Los procesos que usan el peso como parte de los cálculos de la capacidad (umbrales de la gama, descansos del máximo del trabajo, máximos de contenedor, capacidades de carga de la ubicación, etc.) no utilizan el peso real del inventario. En su lugar, los procesos se basan en el peso de administración física que se define para el producto.
- En general, la funcionalidad minorista no es admitida para los productos de peso capturado.
 
### <a name="catch-weight-tags"></a>Etiqueta de peso capturado

Actualmente, la funcionalidad de las etiquetas de peso capturado sólo admite como parte de los escenarios siguientes:

- Al procesar el pedido de compra recibido por la aplicación del almacén.
- Al procesar la carga recibida por la aplicación del almacén.
- Para las matrículas de entidad recibidas relacionadas con la carga de un pedido de compra, la asignación del peso se solicita durante el proceso de recepción. Por el contrario, para transferir el pedido recibido, se usa el peso de los datos de envío del pedido de transferencia.
- Para el artículo del pedido de transferencia y la recepción de la línea procedente de un almacén del proceso de administración de fuera del almacén.
- El procesamiento de pedidos de devolución de ventas puede registrar etiquetas de peso capturado, pero el proceso no se validará si las etiquetas son las mismas que se enviaron originalmente para una línea de pedido de ventas particular.
- Cuando procesar un estado de inventario cambiado mediante la aplicación del almacén.
- Cuando una transferencia desde el almacén se realiza mediante la aplicación del almacén.
- Al procesar el ajuste de entrada y salida mediante la aplicación del almacén.
- Al seleccionar el trabajo se procesa para las ventas y pedidos de transferencia. (Recuerde que las etiquetas de peso capturado no se pueden registrar para la selección de componente de producto).
- Cuando las cantidades seleccionadas se reducen de las líneas de carga, independientemente de si los contenedores están utilizados.
- Cuando los productos están embalados en los contenedores en una instalación de acondicionamiento.
- Cuando se vuelven a abrir los contenedores.
- Cuando los productos de la fórmula se notifican como terminado mediante la aplicación del almacén.
- Cuando las cargas de transporte se procesan usando la aplicación del almacén.

Una etiqueta de peso capturado se puede crear mediante un proceso de la aplicación de almacenamiento de datos, manualmente en el formulario o crearla mediante un proceso de la entidad de los datos. Si una etiqueta de peso capturado se asocia a una línea de entrada del documento de origen, como por ejemplo una línea de pedido de compra, la etiqueta es registrada. Si la línea se usa para el procesamiento de salida. La etiqueta se actualizará como enviada.
