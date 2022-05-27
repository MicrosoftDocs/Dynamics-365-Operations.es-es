---
title: Detalles de línea de trabajo
description: En este tema se ofrece información sobre la página Detalles de la línea de trabajo, que muestra una lista completa, ordenable y filtrable de las líneas de trabajo individuales en su sistema.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4d7c6991c0171b0e09752b3305e0fa11a25b7833
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674121"
---
# <a name="work-line-details"></a>Detalles de línea de trabajo

[!include [banner](../includes/banner.md)]

La página **Detalles de la línea de trabajo** muestra una lista completa, ordenable y filtrable de las líneas de trabajo individuales en su sistema. Proporciona una visión general completa del trabajo que se está planificando y ejecutando en el almacén. Puede cambiar fácilmente entre ver todas las líneas de trabajo y ver solo las líneas de trabajo abiertas. Los detalles que se proporcionan para cada línea incluyen el estado del trabajo, el número de artículo, la ubicación, la cantidad de trabajo, el id. de carga y el id. de envío.

## <a name="turn-on-the-work-line-details-feature"></a>Activar la característica de detalles de la línea de trabajo

A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla o deshabilitarla si es necesario. Aquí, la característica aparece como:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Detalles de la línea de trabajo*

## <a name="open-and-use-the-work-line-details-page"></a>Abrir y usar la página Detalles de la línea de trabajo

Para ver la lista de detalles de la línea de trabajo, vaya a **Gestión de almacenes \> Trabajo \> Detalles de la línea de trabajo**. Desde aquí, puede realizar las siguientes acciones:

- Utilizar el campo **Filtrar** para buscar líneas que tengan un valor determinado para cualquier parámetro disponible. (Los parámetros disponibles incluyen muchos parámetros que no se muestran como columnas en la cuadrícula).
- Utilizar la casilla **Mostrar cerradas** para mostrar u ocultar líneas cerradas.
- Seleccionar **Mostrar dimensiones** para abrir el cuadro de diálogo **Presentación de dimensiones**, donde puede optar por mostrar u ocultar varias columnas de dimensión en la cuadrícula.
- Seleccionar cualquier encabezado de columna para abrir un menú en que puede optar por ordenar o filtrar la lista por valores en esa columna.
- Seleccionar una línea de trabajo y luego seleccione **Cambiar locación** para abrir un cuadro de diálogo donde puede cambiar la ubicación de esa línea de trabajo. La ubicación que especifique anulará la configuración de la directiva de ubicación.
- Seleccionar una línea de trabajo y luego seleccione **Cancelar línea de trabajo** para abrir un cuadro de diálogo donde puede reducir parcial o totalmente la cantidad de esa línea de trabajo.
- Ajustar cantidades.
- Ver las transacciones detrás de cualquier línea de trabajo.

## <a name="try-out-the-feature"></a>Probar la característica

En esta sección se ofrece una demostración de tres partes que muestra cómo trabajar con detalles de la línea de trabajo.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en esta demostración mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar esta demostración como guía cuando trabaje en un sistema de producción. Sin embargo, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Verificar que la configuración del escenario incluye suficiente inventario disponible

Si está trabajando con los datos de demostración **USMF**, primero debe asegurarse de que su sistema esté configurado para que haya suficiente inventario disponible en cada ubicación de picking. Para esta demostración, la expectativa es que tenga el siguiente inventario disponible:

- **Artículo M9200:** 45 ea. (o más)
- **Artículo M9202:** 10 ea. (o más)

Siga estos pasos para verificar que hay suficiente inventario disponible y para hacer los ajustes necesarios.

1. Vaya a **Gestión de almacenes \> Configuración \> Directivas de ubicación**, y determine qué ubicaciones de picking se utilizan para el picking de pedidos de ventas en el almacén 51. (Para obtener más información, consulte [Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md).)
1. Compruebe los niveles de inventario en las ubicaciones pertinentes.
1. Ajuste el inventario según sea necesario. Puede crear movimientos manuales, utilizar el reabastecimiento o aplicar cualquier otro flujo para ajustar el inventario.

### <a name="part-1-create-picking-work"></a>Parte 1: Crear trabajo de picking

Antes de empezar a crear un trabajo, asegúrese de que su almacén esté configurado para responder a las solicitudes de trabajo de la manera esperada.

Soga estos pasos para crear un trabajo de picking.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para abrir el cuadro de diálogo **Crear pedido de ventas**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en _US-001_.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en _51_.

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre su nuevo pedido de ventas. Incluye una nueva fila vacía en la cuadrícula **Líneas de pedido de ventas**. En esta línea de pedido, establezca los siguientes valores:

    - **Código de artículo:** _M9200_
    - **Cantidad:** _20_
    - **Unidad**: _u_

1. Seleccione la nueva línea de pedido y, en el menú **Inventario**, seleccione **Reserva** para abrir la página **Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**. El sistema crea un envío, lo agrega a una nueva carga y crea el trabajo requerido.
1. Cree un segundo pedido de ventas para la misma cuenta de cliente y almacén que utilizó para el primer pedido. Agregue las siguientes dos líneas a este pedido:

    - **Línea 1**: establezca el campo **Número de artículo** a _M9200_, el campo **Cantidad** a _25_ y el campo **Unidad** a _ea_.
    - **Línea 2**: establezca el campo **Número de artículo** a _M9202_, el campo **Cantidad** a _10_ y el campo **Unidad** a _ea_.

1. Repita los pasos 6 a 8 para reservar el inventario para cada línea de pedido (uno a la vez) y, a continuación, repita el paso 9 para liberar el pedido al almacén.

### <a name="part-2-change-the-location-for-a-work-line"></a>Parte 2: Cambiar la ubicación de una línea de trabajo

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de la línea de trabajo**.
1. Busque y seleccione una de las líneas de trabajo que creó para esta demostración.
1. Seleccione **Cambiar ubicación** para abrir el cuadro de diálogo **Seleccionar nueva ubicación**.
1. En el cuadro de diálogo **Seleccionar nueva ubicación**, en el campo **Ubicación**, seleccione una nueva ubicación para la línea de trabajo.
1. Seleccione **Aceptar** para aplicar su cambio y cerrar el cuadro de diálogo.

> [!IMPORTANT]
> Puede enviar cambios de ubicación solo si la nueva ubicación tiene suficiente inventario disponible (para un picking) o si pasa la validación de tipo de ubicación (para una colocación).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>Parte 3: Cambiar la cantidad de una línea de trabajo o cancelar una línea de trabajo

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de la línea de trabajo**.
1. Busque y seleccione una de las líneas de trabajo que creó para esta demostración. Tenga en cuenta que puede cancelar o cambiar cantidades solo para líneas de trabajo donde el tipo de trabajo es _picking_.
1. Seleccione **Cancelar línea de trabajo** para abrir el cuadro de diálogo **Cantidad a cancelar**.
1. En el cuadro de diálogo **Cantidad a cancelar**, cambie el valor del campo **Cantidad** para especificar la cantidad que debe *extraerse de* la cantidad que se especifica actualmente para la línea. De forma predeterminada, el campo **Cantidad** muestra la cantidad completa.

    - Si cancela la cantidad completa, el valor **Estado del trabajo** se cambiará a _Cancelado_, pero el campo **Cantidad de trabajo** aún mostrará el valor original.
    - Si cancela solo una parte de la cantidad, el valor **Cantidad de trabajo** se actualizará para mostrar el nuevo valor, pero el campo **Estado del trabajo** no cambiará.

1. Seleccione **Aceptar** para aplicar su cambio y cerrar el cuadro de diálogo.

> [!IMPORTANT]
> Si cancela solo una parte de la cantidad de una línea de trabajo, también debe eliminar la cantidad obsoleta de la línea de carga. De lo contrario, a menos que la entrega incompleta esté configurada correctamente, la línea de carga no se puede confirmar en el envío.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]