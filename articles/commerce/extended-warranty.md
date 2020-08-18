---
title: Crear y configurar garantías ampliadas
description: En este tema se tratan las garantías ampliadas y se describe cómo crearlos y configurarlos en Microsoft Dynamics 365 Commerce.
author: sijoshi
manager: annbe
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a875343d9b93f5ebf2c2992fba8b2f182310461e
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621202"
---
# <a name="create-and-configure-extended-warranties"></a>Crear y configurar garantías ampliadas

[!include [banner](includes/banner.md)]

En este tema se tratan las garantías ampliadas y se describe cómo crearlos y configurarlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los clientes eligen cada vez más servicios y soporte técnico ampliado cuando compran productos, especialmente productos de consumo que se venden a un precio superior, como teléfonos y ordenadores. Al proporcionar garantías ampliadas para la compra, los minoristas pueden ayudar a fidelizar a los clientes. Las garantías ampliadas permiten a los clientes saber a dónde pueden acudir para obtener servicio y soporte técnico. Por lo tanto, pueden confiar en que sus problemas se abordarán de manera efectiva.

Las garantías ampliadas se pueden vender a los clientes en un canal minorista durante la compra inicial del producto. También se pueden vender por tiempo limitado después de la compra inicial.

### <a name="warranty-item-setup"></a>Configuración del artículo de garantía

Dynamics 365 Commerce proporciona una funcionalidad que le permite crear un artículo de garantía y establecer atributos para él. Estos atributos incluyen la asociación entre un producto y un artículo de garantía, el precio de la garantía y la duración de la garantía. Después de configurar un artículo de garantía y entregarlo a la unidad organizativa, un minorista puede vender garantías a través de Modern Point of Sale (MPOS), tiendas en línea y otros canales minoristas.

### <a name="warranty-item-sales"></a>Venta del artículo de garantía

Las garantías ampliadas se venden en un canal minorista durante la compra inicial del producto. También se pueden vender por tiempo limitado después de la compra inicial.

En el punto de venta (PDV), se pide a los asociados de ventas que agreguen una garantía ampliada cuando un producto relacionado se agrega al carrito de un cliente. Por lo tanto, se presenta una oportunidad de ventas adicionales o ventas cruzadas para los asociados de ventas como parte del flujo de ventas.

Los clientes también pueden volver más tarde y comprar una garantía ampliada para un producto que compraron previamente. En estos casos, un asociado de ventas puede buscar la transacción original y vender al cliente el artículo de garantía ampliada relacionado.

### <a name="warranty-terminology"></a>Terminología sobre garantías

La siguiente tabla define algunos términos relacionados con la garantía.

| Condición | Descripción |
|------------------------------|--------------|
| Garantía ampliada y garantía | Un *garantía ampliada* se refiere a un acuerdo de servicio o contrato que brinda una garantía prolongada a los clientes. La garantía ampliada incluye el servicio adicional de reemplazar o reparar bienes durante el período de cobertura de la garantía ampliada. |
| Garantía del fabricante | Una *garantía del fabricante* (a menudo denominada *garantía limitada*) es la garantía que reciben los clientes cuando compran un producto. Estas son algunas características de la garantía del fabricante:<ul><li>El coste de la garantía está incluido en el coste del producto. Los clientes no tienen que pagar ningún importe adicional por la garantía del fabricante.</li><li>Dependiendo de la categoría del producto, la garantía del fabricante generalmente dura 30 días, seis meses o un año. (Para la mayoría de los productos electrónicos de consumo, la garantía dura un año).</li><li>La garantía cubre cualquier defecto causado por fallos mecánicos o eléctricos. La cobertura es limitada y no incluye daños accidentales al producto comprado. Los clientes que deseen proteger los productos que compran contra daños cotidianos deben invertir en una garantía ampliada. Las garantías ampliadas duran de dos a diez años, en función de la categoría del producto. También tienen una cobertura más amplia y cubren contratiempos cotidianos, como salpicaduras, derrames y manchas.</li></ul> |
| Artículo de garantía | Un *artículo de garantía* es un artículo de garantía ampliada que se vende para un artículo sujeto a garantía. Un ejemplo es un plan de protección accidental de dos años para equipos portátiles. |
| Artículo sujeto a garantía | Un *artículo sujeto a garantía* es un producto serializado para el que se vende una garantía. Por ejemplo, un equipo portátil es un artículo sujeto a garantía por el que se venden garantías ampliadas de dos y tres años. |
| Grupo de garantía | Un *grupo de garantía* es una relación entre los artículos de garantía y artículos sujetos a garantía. El PDV utiliza grupos de garantía para determinar qué artículos de garantía se debe solicitar a los asociados de ventas que agreguen cuando se agrega un artículo garantizado al carrito de un cliente. |
| Directiva de garantía | Una *póliza de garantía* es una entidad que se crea en Commerce cuando se vende una póliza de garantía. Una póliza de garantía incluye información como las fechas de inicio y finalización del artículo de garantía comprado, los términos y condiciones y el número de serie del producto garantizado. Los números de póliza de garantía se pueden compartir con los clientes, de modo que tengan una referencia para el artículo de garantía ampliada que compraron. |

## <a name="create-a-warranty-item"></a>Crear artículo de garantía

Para crear un artículo de garantía en Commerce, siga estos pasos.

1. Vaya a **Venta minorista y comercio \> Productos y categorías \> Productos**.
1. Seleccione **Nuevo** para crear un artículo de garantía.
1. En el cuadro de diálogo **Nuevo producto** en el campo **Tipo de producto**, seleccione **Servicio**.
1. En el campo **Subtipo de producto**, seleccione **Producto**.
1. En el campo **Tipo de servicio de producto**, seleccione **Servicio**.
1. En el campo **Nombre del producto**, indique el nombre de producto.
1. En el campo **Categoría minorista**, seleccione un valor en el cuadro de diálogo desplegable y luego seleccione **Aceptar**.
1. En el campo **Número de producto**, indique el número del producto.
1. Seleccione **Aceptar**.
1. En la página **Detalles del producto**, en la ficha desplegable **Garantía**, configure los campos **Unidad de tiempo** y **Duración**.

    | Nombre de campo | Valor | Descripción |
    |------------|-------|-------------|
    | Unidad de tiempo | **Días**, **Semanas**, **Meses** o **Años** | Este campo especifica la unidad de tiempo que se utiliza para la garantía. |
    | Período de tiempo | Un valor entero positivo | Este campo especifica la duración de la garantía en la unidad de tiempo seleccionada. |

    Por ejemplo, para una garantía de dos años, configure el campo **Unidad de tiempo** en **Años** y el campo **Duración** en **2**. Alternativamente, configure el campo **Unidad de tiempo** en **Meses** y el campo **Duración** en **24**, como se muestra en la siguiente ilustración.

    ![Página de detalles del producto para un artículo de garantía](./media/ew-time-properties.png)

1. Seleccione **Guardar** para guardar el artículo de garantía.
1. Entregue el producto de garantía a la empresa para que pueda venderse. Para obtener más información, consulte [Configurar productos minoristas](set-up-retail-products.md).
1. En la página **Detalles del producto publicado**, en la ficha desplegable **Garantía**, configure los campos **Rango de precio base**, **Límite inferior** y **Limite superior**.

    | Nombre de campo | Valor | Descripción |
    |------------|-------|-------------|
    | Base de rango de precios | **Ninguno**, **Precio base** o **Precio de venta** | <ul><li>**Ninguno**: los valores **Límite inferior** y **Limite superior** de los rangos de precios no son aplicables.</li><li>**Precio base**: una garantía determinada será aplicable si el precio base (es decir, el precio sin descuentos) del artículo sujeto a garantía está entre los valores **Límite inferior** y **Limite superior** que se especifican aquí, en función del precio del artículo sujeto a garantía.</li><li>**Precio de venta**: este valor está reservado para uso futuro.</li></ul> |
    | Límite inferior, límite superior | Un valor entero positivo | Estos campos definen los límites de precio superior e inferior del artículo con garantía, y cómo el artículo sujeto a garantía actual es aplicable al artículo sujeto a garantía. Estos límites pueden basarse en el precio base del artículo sujeto a garantía (también conocido como el precio para venta minorista sugerido por el fabricante \[MSRP\]). Si el campo **Rango de precio base** se establece en **Precio base**, solo un artículo sujeto a garantía(producto) que tenga un precio base entre los valores **Límite inferior** y **Limite superior** activará un aviso para agregar el artículo de garantía en el punto de venta. |

    Por ejemplo, la siguiente ilustración muestra el campo **Rango de precio base** establecido en **Precio base**, el campo **Límite inferior** establecido en 500 $, y el campo **Limite superior** establecido en 1000 $.
    
    ![Página de detalles del producto publicado para un artículo de garantía](./media/ew-release-product-details.png)

1. Seleccione el artículo de garantía al canal donde se venderá. Para obtener más información, consulte [Configurar selecciones](set-up-assortments.md).

### <a name="example"></a>Ejemplo

Un equipo portátil que es artículo sujeto a garantía (producto) tiene un precio base 999 $, y hay dos artículos de garantía para equipo portátil:

- La garantía\_1 tiene un límite inferior de 500 $ y un límite superior de 1000 $, y el campo **Rango de precio base** se establece en **Precio base**.
- La garantía\_2 tiene un límite inferior de 1001 $ y un límite superior de 2000 $, y el campo **Rango de precio base** se establece en **Precio base**.

En este caso, cuando el equipo portátil sujeto a garantía se agrega al carrito de un cliente, a aparece una solicitud de agregar la garantía\_1 en el punto de venta, porque el precio del equipo portátil está entre los límites inferior y superior de la garantía\_1.

> [!NOTE]
> Para este ejemplo, si desea que se muestren mensajes de solicitud para la garantía\_1 y garantía\_2, independientemente del precio del artículo sujeto a garantía, establezca el campo **Rango de precio base** en **Ninguno**.

## <a name="configure-channel-specific-settings"></a>Configurar ajustes específicos del canal

La configuración específica del canal le permite especificar si se debe mostrar un aviso para agregar un artículo de garantía en el punto de venta cuando se agrega un artículo sujeto a garantía al carrito de un cliente.

Para configurar la configuración específica por canal en Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Garantía \> Configuración de garantía**.
1. En la pestaña **Canal específico**, en al columna **Aviso para garantía** para su canal, siga uno de estos pasos:

    - Seleccione la casilla de verificación si se debe mostrar una solicitud para el artículo de garantía en el punto de venta cuando el artículo sujeto a garantía se agrega al carrito.
    - Borre la casilla de verificación si no se debe mostrar una solicitud para el artículo de garantía en el punto de venta cuando el artículo sujeto a garantía se agrega al carrito.

1. Ejecutar la tarea **1070** para sincronizar los datos con el canal.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>Configure una secuencia numérica para las políticas de garantía

Cada póliza de garantía se identifica de manera única mediante un número de póliza de garantía generado por una secuencia numérica. Para obtener más información sobre las secuencias numéricas, consulte [Información general de secuencias numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Para configurar una secuencia numérica para las pólizas de garantía en Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Garantía \> Configuración de garantía**.
1. En la pestaña **Secuencias numéricas**, en la fila para la referencia **Póliza de garantía**, especifique o seleccione un valor en el campo **Código de secuencia numérica**.

## <a name="set-up-a-warranty-group"></a>Configurar un grupo de garantías

Un grupo de garantía es una relación entre los artículos de garantía y artículos sujetos a garantía. El PDV utiliza grupos de garantía para determinar qué artículos de garantía se debe solicitar a los asociados de ventas que agreguen cuando se agrega un artículo garantizado al carrito de un cliente.

Para configurar un grupo de garantías en Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Garantía \> Grupos de garantía**.
1. Seleccione **Nuevo** para crear un grupo de garantía.
1. En el campo **Nombre**, escriba un nombre para el grupo nuevo.
1. En la ficha desplegable **General**, en el campo **Descripción** escriba una descripción del grupo.
1. En la ficha desplegable **Productos de garantía**, seleccione **Agregar línea** para agregar un artículo de garantía.
1. En el campo **Orden de visualización**, especifique un número para clasificar el grupo de garantía en el punto de venta. El PDV mostrará los elementos de garantía en orden ascendente en el aviso de garantía.
1. En la ficha desplegable **Productos sujetos a garantía**, seleccione **Agregar línea** para agregar productos sujetos a garantía.
1. Si el artículo de garantía es aplicable a una categoría completa de artículos sujetos a garantía (productos), seleccione la categoría en el campo **Categoría**. Si el artículo de garantía es aplicable a un artículo sujeto a garantizado (producto) específico, seleccione el producto en el campo **Producto**.
1. En la ficha desplegable **Canales aplicables**, seleccione **Agregar línea** para agregar el canal donde desea vender el artículo de garantía.
1. Seleccione **Guardar** para guardar la configuración.
1. Seleccione **Publicar** para publicar el grupo de garantía.
1. Ejecutar la tarea **1040** para sincronizar los datos con el canal.

## <a name="sell-warranty-items-at-the-pos"></a>Vender artículos de garantía en el punto de venta

Dos operaciones de PDV permiten a los asociados de ventas vender artículos de garantía durante el flujo de trabajo para compras de clientes:

- **Agregar garantía**: esta operación activa un mensaje que muestra las garantías aplicables para un artículo con garantía que se selecciona en el carrito.
- **Agregar garantía a la transacción existente**: esta operación permite a los asociados de ventas vender garantías para los artículos sujetos a garantía que se vendieron anteriormente. Los asociados de ventas pueden encontrar la transacción original para un artículo con garantía especificando el número de recibo de la transacción.

La siguiente ilustración muestra un ejemplo de una página de terminal del PDV con un aviso para agregar un artículo de garantía para la compra actual de un artículo sujeto a garantía.

![Ejemplo de un aviso para agregar un artículo de garantía para la compra actual](./media/ew-sell-warranty.png)

La siguiente ilustración muestra un ejemplo de la característica para agregar un artículo de garantía para un artículo sujeto a garantía que se vendió anteriormente.

![Ejemplo de la característica para agregar un artículo de garantía para un artículo sujeto a garantía vendido anteriormente](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Procesar transacciones de garantía

Cuando las garantías se venden en transacciones de pago al contado, después de que las transacciones se publican en la sede de Commerce, los usuarios de Commerce pueden ejecutar la tarea **Procesar transacciones de garantía** para procesar las transacciones de garantía y crear políticas de garantía.

Para procesar transacciones de garantía en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Garantía \> Procesar transacciones de garantía**.
1. En el cuadro de diálogo **Elegir nodos organizativos**, en el campo **Jerarquía organizacional**, seleccione un valor.
1. En la lista **Nodos organizativos disponibles**, seleccione una tienda individual o, si desea crear el trabajo por lotes para un grupo de tiendas, un nodo.
1. Seleccione el botón de flecha a la derecha para agregar su selección a la lista **Nodos organizativos seleccionados**.
1. Seleccione la pestaña **Ejecutar en segundo plano**.
1. Seleccione la opción **Procesamiento por lotes** en **Sí** y luego seleccione **Periocidad**.
1. En el cuadro de diálogo **Definir periodicidad**, en el campo **Fecha de inicio**, seleccione o ingrese una fecha de inicio para la recurrencia.
1. En el campo **Hora de inicio**, seleccione o especifique una hora de inicio para la periodicidad.
1. Siga uno de estos pasos:

    - Seleccione la opción **Sin fecha de finalización** si la periodicidad nunca debe terminar.
    - Seleccione la opción **Terminar después** si la recurrencia debe terminar después de un número específico de ejecuciones. Si seleccione esta opción, especifique el número de ejecuciones.
    - Seleccione la opción **Finalizar el** si la periodicidad deber terminar en una fecha específica. Si seleccione esta opción, seleccione o indique la fecha.

1. Seleccione **Aceptar**.
1. Seleccione **Aceptar**.

## <a name="warranty-policies"></a>Pólizas de garantía

Cuando se vende una garantía extendida, se crea automáticamente una entidad de póliza de garantía. Los números de póliza de garantía se pueden compartir con los clientes, de modo que tengan una referencia para el artículo de garantía que compraron. Las propiedades de la póliza de garantía incluyen la fecha de inicio de la vigencia y la fecha de vencimiento de la garantía, los términos y condiciones, y el número de serie del artículo sujeto a garantía para el que se vendió la garantía.

> [!NOTE]
> Las propiedades de la póliza de garantía se generan automáticamente cuando se crean las entidades de la póliza de garantía. Actualmente, no se pueden configurar ni editar manualmente.

La siguiente tabla describe las propiedades de la póliza de garantía y sus valores. En la sede de Commerce la tabla de la base de datos se denomina WARRANTYPOLICY.

| Nombre de la propiedad | Valor | Descripción |
|---------------|-------|-------------|
| PolicyNumber | Una cadena de caracteres (máximo de 20 caracteres) | El número de póliza de la garantía |
| WarrantiedItemId | Una cadena de caracteres (máximo de 20 caracteres) | El identificador del elemento sujeto a garantía |
| WarrantiedInventoryLotId | Una cadena de caracteres (máximo de 20 caracteres) | El identificador del lote del inventario sujeto a garantía |
| WarrantiedSerialNumber | Una cadena de caracteres (máximo de 20 caracteres) | El número de serie del artículo sujeto a garantía |
| WarrantiedFulfilledDate | Una fecha | La fecha de cumplimiento del elemento sujeto a garantía |
| WarrantyItemId | Una cadena de caracteres (máximo de 20 caracteres) | El identificador del elemento de garantía |
| WarrantyInventoryLotId | Una cadena de caracteres (máximo de 20 caracteres) | El identificador del lote del inventario del elemento de garantía |
| WarrantySalesDate | Una fecha | La fecha de venta del elemento de garantía |
| WarrantyEffectiveDate | Una fecha | La fecha de vigencia de la póliza de garantía |
| WarrantyExpirationDate | Una fecha | La fecha de vencimiento de la póliza de garantía |
| CustAccount | Una cadena de caracteres (máximo de 20 caracteres) | El número de cuenta del cliente |
| Estado | **Creado**, **Anulado**, **Eficaz** o **Caducado** | El estado de vigencia de la póliza de garantía |
| Notas | Una cadena de caracteres (máximo de 255 caracteres) | Notas sobre la póliza de garantía, como los términos y condiciones |

## <a name="frequently-asked-questions-faq"></a>Preguntas frecuentes

**¿Por qué no veo un aviso de garantía en el punto de venta?**

Asegúrese de que el artículo de garantía esté clasificado en el canal. También asegúrese de que el grupo de garantía esté configurado de manera que incluya el canal relevante.

**Cuando intento agregar una garantía a una transacción existente y especificar el número de recibo del pedido del cliente, ¿por qué no veo ninguna línea de transacción?**

Los recibos solo se pueden encontrar si se ejecuta un trabajo de extracción (trabajo E) para cargar los recibos en la sede de Commerce. Para ejecutar el trabajo E, vaya a **Retail y Commerce \> TI de Retail y Commerce \> Horario de distribución**, seleccione la tarea **P-0001**, y luego seleccione **Ejecutar ahora**.

**¿Por qué la característica de garantía se aplica solo a productos serializados?**

Una garantía es un servicio que se proporciona para un producto específico y único. En Dynamics 365, un producto solo se puede identificar por un número de serie.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar productos comerciales](set-up-retail-products.md)

[Configurar selecciones](set-up-assortments.md)

[Visión general de las secuencias numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)
