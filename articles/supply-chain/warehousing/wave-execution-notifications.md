---
title: Notificaciones de ejecución de oleadas
description: Este tema describe la ejecución de notificaciones de oleada y explica cómo configurarlas.
author: Mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: b6218610b673963f5d43e1b29c6fc356ea977935
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672525"
---
# <a name="wave-execution-notifications"></a>Notificaciones de ejecución de oleadas

[!include [banner](../includes/banner.md)]

La función *Notificaciones de ejecución de olas* utiliza eventos comerciales y el Centro de actividades para enviar notificaciones relacionadas con la ejecución de la oleada. Le permite especificar los tipos de eventos que generan notificaciones, los almacenes que las generan y los usuarios que las reciben.

El botón **Mostrar mensajes** (símbolo de campana) en el lado derecho de la barra de navegación indica cuando un mensaje del Centro de actividades está disponible para el usuario actual. El usuario puede seleccionar el botón **Mostrar mensajes** para abrir el Centro de actividades y revisar los mensajes.

Los eventos comerciales ocurren cuando se ejecutan procesos comerciales. Los procesos comerciales se componen de tareas. Durante un proceso empresarial, los usuarios que participan en él realizan acciones empresariales para completar esas tareas. Los eventos empresariales proporcionan un mecanismo que permite que los sistemas externos reciban notificaciones de aplicaciones de finanzas y operaciones. De esta manera, los sistemas pueden realizar acciones comerciales en respuesta a los eventos de negocio. Para obtener más información, consulte [Resumen de eventos de negocio](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>Activar o desactivar la característica Notificaciones de ejecución de oleada

A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada. Los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Notificaciones de ejecución de oleada* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Escenario: enviar notificaciones de ejecución por lotes de oleadas al centro de actividades

Este escenario muestra el flujo de un extremo a otro para enviar notificaciones sobre errores de ejecución de lotes de oleadas a un rol específico a través del Centro de actividades.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Asegúrese de que las oleadas se ejecuten en modo por lotes

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la ficha desplegable **Procesar oleadas**, establezca la opción **Procesamiento por lotes** en *Sí*.

> [!NOTE]
> Si desea deshabilitar las notificaciones de ejecución por lotes de oleadas, configure la opción **Deshabilitar las notificaciones por lotes de procesamiento de oleadas** a *Sí*.

### <a name="configure-a-wave-notification-policy"></a>Configurar una directiva de notificación de oleadas

Las políticas de notificación de oleada definen los tipos de notificaciones que se envían y los usuarios a los que se notifica.

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Directivas de notificación de oleadas**.
1. Cree un registro que tenga la siguiente configuración:

    - **Directiva de notificación de oleada:** *24BatchError*
    - **Descripción:** *Error de lote de oleadas del almacén 24*
    - **Enviar notificación en:** *Solo error*
    - **Al rol:** *Administrador del sistema*

        > [!NOTE]
        > Dado que este escenario utiliza datos de demostración, el rol *Administrador de sistema* se selecciona en aras de la simplicidad. Por lo tanto, debido a que ha iniciado sesión como usuario administrador del sistema, recibirá las notificaciones. Sin embargo, en la práctica, generalmente debe seleccionar un rol más específico para notificar acerca de los errores de ejecución de lotes de oleadas, como *Jefe de almacén*.

1. En el panel Acciones, seleccione **Guardar**.

### <a name="configure-a-wave-template"></a>Configurar una plantilla de oleada

Las plantillas de oleada le permiten vincular instancias específicas de métodos de oleada a unas plantillas de etiqueta de oleada correspondiente.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el panel de lista, configure el campo **Tipo de plantilla de oleada** a *Transporte* y luego seleccione la plantilla de oleada *24 Envío predeterminado* para el almacén 24.
1. En la ficha desplegable **General**, establezca el campo **Directiva de notificación de oleada** en *24BatchError*.

### <a name="configure-a-work-template"></a>Configurar una plantilla de trabajo

Las plantillas de trabajo se utilizan durante la ejecución de la oleada para generar trabajo. Para este escenario, la ejecución de la oleada debería provocar un error. Al configurar la consulta de la plantilla de trabajo para usar un almacén inexistente, se asegurará de que la ejecución de la oleada falle y, por lo tanto, envíe una notificación.

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En el panel de lista, configure el campo **Tipo de plantilla de trabajo** a *Pedidos de ventas* y luego seleccione la plantilla de oleada *24 Fase SO* para el almacén 24.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango** pestaña, edite la siguiente fila (o agréguela si no existe):

    - **Tabla:** *Transacciones laborales temporales*
    - **Tabla derivada:** *Transacciones laborales temporales*
    - **Campo:** *Almacén*
    - **Criterios:** cambiar el valor de *24* a *Error*.

1. Seleccione **Aceptar** y confirme los cambios.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Crear un pedido de ventas y liberarlo en el almacén

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Cree un pedido de ventas con la siguiente configuración:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *24*

1. En la ficha desplegable **Líneas de pedido de venta**, agregue una línea de pedido de ventas que tenga los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *10*

    > [!NOTE]
    > Estos artículos y cantidades son solo ejemplos. El almacén especificado debe tener existencias suficientes.

1. Con la nueva línea seleccionada en la ficha desplegable **Líneas de pedido de ventas**, seleccione **Inventario \> Reserva** en la barra de herramientas.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote**. A continuación, cierre la página.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

### <a name="notifications-from-wave-batch-job-execution"></a>Notificaciones de la ejecución de trabajos por lotes de oleadas

Dependiendo de la configuración de sus eventos de negocio, eventualmente recibirá una notificación sobre el fallo de ejecución de la oleada. El mensaje del Centro de actividades se parecerá al siguiente ejemplo e incluirá un enlace a la oleada que falló.

> **Error durante la ejecución de la oleada**  
> Se produjo un error al ejecutar la oleada USMF-000000001.  
> Últimos mensajes: No se creó ningún trabajo para Oleada USMF-000000001.
>
> **ESTADO**  
> Activa
>
> Abrir detalles de la oleada

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
