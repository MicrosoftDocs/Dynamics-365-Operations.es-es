---
title: Pedidos de calidad
description: Este tema describe cómo crear pedidos de calidad de forma manual o automática y cómo trabajar con ellos para realizar inspecciones y registrar los resultados de las pruebas en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d06cd7766f4445a248e0394e75ae390314762cf211a2780da76b4f52aa5bccd4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739811"
---
# <a name="quality-orders"></a>Pedidos de calidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear pedidos de calidad de forma manual o automática y cómo trabajar con ellos para realizar inspecciones y registrar los resultados de las pruebas en Microsoft Dynamics 365 Supply Chain Management.

## <a name="automatically-created-quality-orders"></a>Pedidos de calidad creados automáticamente

Puede configurar el sistema para que cree automáticamente pedidos de calidad, según las reglas de muestreo de artículos. Para más información, consulte [Muestreo de elementos de gestión de calidad](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Crear pedidos de calidad manualmente

Para crear un pedido de calidad manualmente, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Pedidos de calidad**, en el campo **Tipo de referencia**, seleccione la referencia de inventario con la que se relacionará su pedido de calidad. Para obtener una descripción de los tipos de referencia que están disponibles para su selección, consulte la sección [Tipos de referencia de pedidos de calidad](#ref-types), más adelante en este tema.

    > [!NOTE]
    > El inventario relacionado con la referencia seleccionada debe estar disponible. Si no hay inventario disponible para la combinación del tipo de referencia, la cantidad y las dimensiones de inventario que seleccione, recibirá un mensaje de error.

1. Siga uno de estos pasos, según el valor seleccionado en el campo **Tipo de referencia**:

    - Si selecciona **Inventario**, no se requiere información de referencia adicional.
    - Si seleccionó **Ventas** o **Compra**, especifique la siguiente información:

        - **Selección de cuenta**: referencie el número de cuenta del proveedor o del cliente.
        - **Número de referencia**: haga referencia al número de pedido de ventas o pedido de compra.
        - **Lote de referencia**: haga referencia a la línea de pedido de ventas o la línea de pedido de compra específica.

    - Si seleccionó **Producción**, **Cuarentena** o **Producción de coproductos**, en el campo **Número de referencia**, haga referencia al pedido de producción, orden de lote o número de orden de cuarentena.
    - Si seleccionó **Operación de ruta**, especifique la siguiente información:

        - **Número de referencia**: haga referencia al pedido de producción o número de pedido de lote.
        - **N.º oper.** - Referencia al número de operación de ruta específico.
        - **Operación**: hace referencia al número de operación de ruta específico.
        - **Recurso**: hacer referencia al recurso específico que se debe utilizar con la operación de ruta.

1. En el campo **Grupo de pruebas**, seleccione el grupo de pruebas que debe realizarse.
1. En el campo **Cantidad**, escriba la cantidad de los artículos que se deben probar.
1. En la sección **Dimensiones de inventario**, introduzca las dimensiones de inventario adicionales que sean necesarias para el artículo seleccionado.
1. Seleccione **Aceptar**.

Después de que se crea un pedido de calidad, puede comenzar a inspeccionar el inventario y registrar los resultados de la prueba. Para obtener más información sobre cómo registrar y validar los resultados de las pruebas, consulte [Inspeccionar la calidad de los productos](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Tipos de referencia de pedidos de calidad

Los pedidos de calidad se utilizan para realizar un seguimiento de los detalles de las inspecciones y los resultados de las pruebas para un inventario específico en su almacén. Un pedido de calidad debe incluir una referencia que represente el origen del inventario que se está probando. Los pedidos de calidad se pueden relacionar con los siguientes tipos de referencia:

- **Inventario**: este tipo de referencia indica que está inspeccionando el inventario disponible. Las inspecciones de este tipo suelen ser aleatorias o no planificadas y se realizan cuando un trabajador del almacén identifica un problema.
- **Ventas**: este tipo de referencia indica que está inspeccionando el inventario relacionado con un pedido de ventas específico. Las inspecciones de este tipo suelen estar relacionadas con las especificaciones del cliente o con la generación de un certificado de análisis (CoA) que debe proporcionarse a un cliente como parte de un envío. (Un CoA a veces también se conoce como un certificado de cumplimiento \[CoC\].)
- **Compra**: este tipo de referencia indica que está inspeccionando el inventario relacionado con un pedido de compra. Las inspecciones de este tipo se utilizan a menudo para inspeccionar las mercancías entrantes antes de que se pongan en el inventario o se consuman en los procesos de producción.
- **Producción**: este tipo de referencia indica que está inspeccionando el inventario relacionado con un pedido de producción. Las inspecciones de este tipo se utilizan a menudo para inspeccionar las mercancías terminadas antes de que se pongan en el inventario.
- **Cuarentena**: este tipo de referencia indica que está inspeccionando el inventario relacionado con un pedido de cuarentena. Los pedidos de cuarentena son un tipo especial de pedido que rastrea el inventario de un almacén separado o de un área separada de su almacén. Las inspecciones de este tipo se utilizan a menudo para inspeccionar mercancías que un cliente ha devuelto o que se han puesto en cuarentena para un análisis más detallado. Los pedidos de cuarentena se pueden generar a partir de pedidos de calidad. Alternativamente, se pueden generar a partir de otras fuentes, y luego los pedidos de calidad se pueden relacionar con los pedidos de cuarentena.
- **Operación de ruta**: este tipo de referencia indica que está inspeccionando el inventario relacionado con un paso específico de la ruta de un pedido de producción. Las inspecciones de este tipo se utilizan normalmente para analizar el trabajo en curso (WIP) de un producto antes de pasar al siguiente paso del proceso de producción.
- **Producción de coproductos**: este tipo de referencia indica que está inspeccionando el inventario relacionado con un coproducto de un pedido de producción. Las inspecciones de este tipo se utilizan normalmente para inspeccionar el coproducto de un pedido de lote antes de que el coproducto se agregue al inventario.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Ver y crear pedidos de calidad desde varias partes del sistema

Los pedidos de calidad se pueden crear manualmente. Alternativamente, se pueden crear automáticamente en función de las asociaciones de calidad que defina. Para obtener más información sobre cómo crear y gestionar la creación automática de pedidos de calidad, consulte [Asociaciones de calidad](quality-associations.md).

Puede utilizar la página de pedidos de calidad para crear manualmente un nuevo pedido de calidad o ver el estado de un pedido de calidad relacionado con otro registro. Hay varias formas de acceder a la página de pedidos de calidad.

### <a name="from-the-quality-orders-page"></a>Desde la página de pedidos de calidad

Para crear manualmente pedidos de calidad y ver todos los pedidos de calidad existentes, vaya a **Gestión de inventarios \> Tareas periódicas \> Gestión de calidad \> Pedidos de calidad**. Las secciones restantes de este tema proporcionan más información sobre cómo trabajar con la página **Pedidos de calidad**.

### <a name="from-sales-orders"></a>Desde pedidos de ventas

Para trabajar con pedidos de calidad relacionados con sus pedidos de venta, vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas** y luego siga cualquiera de estos pasos:

- Abra un pedido de ventas o selecciónelo en la cuadrícula. Luego, en el Panel de acciones, en la pestaña **Recoger y empaquetar**, en el grupo **Gestión de calidad**, seleccione **Pedidos de calidad** para abrir la página **Pedidos de calidad**. Allí, puede ver, crear o actualizar pedidos de calidad relacionados con el pedido de ventas.
- Abra un pedido de ventas y luego, en la pestaña **Encabezado**, seleccione la ficha desplegable **General**. El campo **Estado del pedido de calidad** muestra el estado general de todos los pedidos de calidad relacionados con el pedido de ventas.
- Abra un pedido de ventas y luego, en la pestaña **Líneas**, seleccione la ficha desplegable **Líneas de pedido de ventas**. La columna **Estado del pedido de calidad** muestra el estado de cada línea del pedido de ventas.

### <a name="from-purchase-orders"></a>Desde pedidos de compra

Para trabajar con pedidos de calidad relacionados con sus pedidos de compra, vaya a **Aprovisionamiento y orígenes \> Pedidos de compra \> Todos los pedidos de compra** y luego siga cualquiera de estos pasos:

- Abra un pedido de compra o selecciónelo en la cuadrícula. Luego, en el Panel de acciones, en la pestaña **Recepción**, en el grupo **Gestión de calidad**, seleccione **Pedidos de calidad** para abrir la página **Pedidos de calidad**. Allí, puede ver, crear o actualizar pedidos de calidad relacionados con el pedido de compra.
- Abra un pedido de compra y luego, en la pestaña **Encabezado**, seleccione la ficha desplegable **General**. El campo **Estado del pedido de calidad** muestra el estado general de todos los pedidos de calidad relacionados con el pedido de compra.
- Abra un pedido de compra y luego, en la pestaña **Líneas**, seleccione la ficha desplegable **Líneas de pedido de compra**. La columna **Estado del pedido de calidad** muestra el estado de cada línea del pedido de compra.

### <a name="from-production-orders"></a>Desde pedidos de producción

Para trabajar con pedidos de producción relacionados con sus pedidos de producción, vaya a **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** y luego siga cualquiera de estos pasos:

- Abra un pedido de producción o selecciónelo en la cuadrícula. Luego, en el Panel de acciones, en la pestaña **Vista**, en el grupo **Gestionar calidad**, seleccione **Pedidos de calidad** para abrir la página **Pedidos de calidad**. Allí, puede ver, crear o actualizar pedidos de calidad relacionados con el pedido de producción.
- Abra un pedido de producción o selecciónelo en la cuadrícula. Luego, en el panel de acciones, en la pestaña **Pedido de producción**, en el grupo **Detalles de producción**, seleccione **Ruta** para abrir la página **Ruta de producción**. Para ver los pedidos de calidad relacionados con una operación de ruta, siga uno de estos pasos:

    - Seleccione la operación de ruta de destino en la cuadrícula. Luego, en el panel de acciones, seleccione **Consultas \> Pedidos de calidad**.
    - Seleccione el valor en el campo **N.º oper.** para que la operación de ruta de destino abra su página de detalles **Ruta de producción**. En la ficha desplegable **General**, el campo **Estado del pedido de calidad** muestra el estado de los pedidos de calidad relacionados con la operación de la ruta.

- Abra un pedido de producción y seleccione a ficha desplegable **General**. El campo **Estado del pedido de calidad** muestra el estado de los pedidos de calidad relacionados con el pedido de producción.

### <a name="from-quarantine-orders"></a>Desde pedidos de cuarentena

Para trabajar con pedidos de producción relacionados con sus pedidos de cuarentena, vaya a **Gestión de inventario \> Tareas periódicas \> Gestión de calidad \> Pedidos de cuarentena** y luego siga cualquiera de estos pasos:

- Revise los valores en la columna **Estado del pedido de calidad**. De esta manera, puede conocer el estado general de todos los pedidos de calidad relacionados con cada pedido de cuarentena en la cuadrícula.
- Seleccione un pedido de cuarentena en la cuadrícula y luego, en el panel de acciones, seleccione **Pedidos de calidad** para ver, crear o actualizar pedidos de calidad relacionados con el pedido de cuarentena.

## <a name="advanced-actions-for-quality-orders"></a>Acciones avanzadas para pedidos de calidad

Puede realizar varias acciones en pedidos de calidad para administrar el estado, generar documentos y solicitar información adicional.

### <a name="reopen-a-quality-order"></a>Volver a abrir un pedido de calidad

De forma predeterminada, ya no puede editar ni actualizar un pedido de calidad después de que se haya validado y se hayan superado las pruebas. Sin embargo, en algunos casos, es posible que deba volver a abrir un pedido de calidad después de que se haya completado.

Para volver a abrir un pedido de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Abra el pedido de calidad validado o selecciónelo en la cuadrícula.
1. En el panel de acciones, seleccione **Volver a abrir pedido de calidad**.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Crear un certificado de análisis para un pedido de calidad

Un CoA es un informe generado por un equipo de aseguramiento de la calidad de una organización. Valida que un producto cumple con regulaciones o requisitos específicos. Sus clientes o establecimientos reguladores de su ubicación geopolítica pueden requerir los CoA. También pueden ser necesarios según su industria y el tipo de productos que maneja, compra, produce o vende.

Supply Chain Management le permite generar un CoA a partir de un pedido de calidad. El informe incluirá los resultados de cualquier prueba del pedido de calidad en la que la opción **Certificado de informe de análisis** esté configurada en *Sí*. Esta opción se puede configurar de forma predeterminada, en función de la prueba que defina en la página **Pruebas**. Sin embargo, puede reemplazar la configuración en pruebas específicas para pedidos de calidad específicos.

Para generar un CoA para un pedido de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Seleccione el pedido de calidad para el que desea crear un CoA.
1. En el panel de acciones, seleccione **Consultas \> Certificado de análisis**.
1. En la página **Certificado de análisis**, en el panel de acciones, seleccione **Nuevo**.
1. Opcional: en el campo **Contacto**, seleccione la persona de contacto a la que debe dirigirse el certificado.
1. En el panel de acciones, seleccione **Imprimir**.
1. En el cuadro de diálogo **Certificado de análisis** defina cómo se debe imprimir el informe. Luego seleccione **Aceptar** para imprimir el informe en una impresora, en pantalla, en un archivo o en un correo electrónico.
1. Cierre las páginas.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Bloquear o desbloquear inventario para un pedido de calidad

Cuando un pedido de calidad se genera automáticamente a partir de una asociación de calidad, el muestreo de artículos que se asigna a la asociación de calidad se puede configurar para bloquear la cantidad total de inventario de la referencia que se está probando. Para más información sobre muestreos de artículos, consulte [Muestreo de elementos de gestión de calidad](quality-item-sampling.md).

Si no está utilizando el bloqueo completo o si está creando manualmente un pedido de calidad, el sistema crea automáticamente un registro de bloqueo de inventario para la cantidad del artículo que se está probando en el pedido de calidad. En el registro que se crea en la página **Bloqueo de inventario**, el campo **Tipo de bloqueo de inventario** está configurado en *Pedido de calidad*.

Para ver y editar el bloqueo de inventario para un pedido de calidad que se selecciona en la página **Bloqueo de inventario**, seleccione **Consultas \> Bloqueo de inventario** en el panel de acciones. Para obtener más información, consulte [Bloqueo de inventario](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Pregunte sobre los detalles de un pedido de calidad

Utilice los siguientes botones en el panel de acciones de la página **Pedidos de calidad** para ver más información sobre un pedido de calidad o relacionada con él:

- **Consultas \> Detalles del trabajo**: abra una página donde pueda ver el trabajo del almacén relacionado con el pedido de calidad.
- **Consultas \> Disconformidades**: abra una página en la que pueda ver las disconformidades relacionadas con el pedido de calidad.
- **Inventario**: los comandos de este menú son comunes a todas las transacciones de inventario. Puede usarlos para ver o actualizar detalles como transacciones, inventario disponible, reservas y marcado.

### <a name="create-cases-related-to-quality-orders"></a>Crear casos relacionados con pedidos de calidad

Puede crear casos relacionados con pedidos de calidad. De esta manera, puede realizar un seguimiento de los detalles de los problemas y trabajar para encontrar una solución. Luego, puede utilizar las funciones de flujo de trabajo de la gestión de casos para enrutar un caso a través de un proceso empresarial predefinido para obtener aprobaciones adicionales u obtener más información sobre un problema específico. También puede utilizar la función de artículos de conocimientos para crear una base de conocimientos de soluciones para problemas comunes.

## <a name="case-management-examples-for-quality-management"></a>Ejemplos de gestión de casos para la gestión de la calidad

### <a name="example-1"></a>Ejemplo 1

Trabaja para una empresa de fabricación que debe seguir estrictas regulaciones relacionadas con la producción de productos regulados, como los alimentos. Los pedidos de calidad se utilizan para registrar y realizar un seguimiento de los detalles de la calidad de los artículos a lo largo del proceso de producción. Si un pedido de calidad no pasa pruebas específicas, puede haber un problema con el equipo. Los casos se utilizan para seguir un proceso comercial y derivar el problema a los ingenieros correctos, para poder determinar la causa raíz. Para facilitar el seguimiento de los procesos comerciales, la empresa mantiene una base de conocimientos de problemas comunes relacionados con pedidos de calidad y problemas de equipos.

### <a name="example-2"></a>Ejemplo 2

Trabaja para una empresa de distribución que envía productos que se pueden personalizar para varios países y regiones. Algunos clientes tienen especificaciones estrictas que deben seguirse. De lo contrario, es posible que se generen gastos, devoluciones o contracargos. Utilice pedidos de calidad para realizar un seguimiento de los detalles de cada prueba y los resultados que coinciden con los requisitos del cliente. Los casos se utilizan para revisar y aprobar los detalles del CoA antes de que el documento se genere y se adjunte junto con otros documentos de envío.

## <a name="additional-resources"></a>Recursos adicionales

- [Procesos de administración de la calidad](quality-management-processes.md)
- [Prueba de calidad](quality-tests.md)
- [Grupos de pruebas de calidad](quality-test-groups.md)
- [Asociaciones de calidad](quality-associations.md)
- [Procesos de administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
