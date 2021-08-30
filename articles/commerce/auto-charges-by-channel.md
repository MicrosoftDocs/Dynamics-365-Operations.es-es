---
title: Habilitar y configurar cargos automáticos por canal
description: Este tema explica cómo habilitar y configurar los cargos automáticos por canal en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d905819d1e0c8223c74509bfb357b3aaa51d20305a2857061eadb0b0ff8f6b9b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727639"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Habilitar y configurar cargos automáticos por canal

Este tema explica cómo habilitar y configurar los cargos automáticos (autocargos) por canal en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Es posible que tenga escenarios en los que se deben aplicar tarifas de reciclaje u otras tarifas a un grupo de productos que se venden en todas o algunas tiendas en un estado específico (por ejemplo, California). La función **Habilitar cargas automáticas de filtro por canal** en Commerce le permite especificar cargos automáticos por canal (por ejemplo, un canal específico físico). Esta función está disponible en Dynamics 365 Commerce versión 10.0.10 y posterior.

Para habilitar y configurar los cargos automáticos por canal, debe completar las siguientes tareas:

- Active la característica **Habilitar cargas automáticas de filtro por canal**.
- Configure el propósito de la jerarquía organizativa.
- Defina cargas automáticas por canal.

> [!NOTE]
> La característica **Habilitar cargas automáticas de filtro por canal** solo funciona si la función de carga automática avanzada también está activada. Para obtener información sobre cómo activar la función de cargos automáticos avanzados, consulte [Cargos automáticos avanzados omnicanal](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Active la característica Habilitar cargas automáticas de filtro por canal

Para habilitar los cargos automáticos por canal en Commerce, siga estos pasos.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. En la pestaña **No habilitada**, en la lista **Nombre de característica**, busque y seleccione **Habilitar cargas automáticas de filtro por canal**.
1. En la esquina inferior derecha, seleccione **Habilitar ahora**. Después de que la función se haya activado, aparecerá en la lista en la pestaña **Todo**.
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. En el panel izquierdo, busque y seleccione el trabajo **1110** (**Configuración global**).
1. En el Panel de acciones, seleccione **Ejecutar ahora** para propagar los cambios de configuración.

> [!WARNING]
> Si desactiva la característica **Habilitar cargas automáticas de filtro por canal** después de que ya la haya usado, el campo **Relación del canal minorista** bajo **Cargos automáticos** ya no aparecerá y perderá todas las configuraciones existentes. Si la eliminación de las configuraciones **Relación del canal minorista** harán que las reglas de carga automática se dupliquen, un intento de desactivar la función fallará. Antes de desactivar la función, asegúrese de revisar todas las reglas de cargos automáticos y realizar los cambios necesarios.

## <a name="configure-the-organization-hierarchy-purpose"></a>Configure el propósito de la jerarquía organizativa

Un nuevo propósito de la jerarquía organizativa que se denomina **Cargo de auto minorista** ha sido creado para administrar la jerarquía de cargos automáticos por canal.

Para asignar una jerarquía predeterminada a un propósito de jerarquía de organización en Commerce, siga estos pasos.
        
1. Vaya a **Administración de la organización \> Organizaciones \> Propósitos de jerarquías organizativas**.
1. En el panel izquierdo, seleccione **Cargo de auto minorista**.
1. En **Jerarquías asignadas**, seleccione **Agregar**.
1. En el cuadro de diálogo **Jerarquías organizativas**, seleccione una jerarquía organizativa (por ejemplo, **Tiendas minoristas por región**) y luego seleccione **Aceptar**.
1. En **Jerarquías asignadas**, seleccione **Establecer como predeterminada**.
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. En el panel izquierdo, busque y seleccione el trabajo **1040** (**Productos**).
1. En el panel de acciones, seleccione **Ejecutar ahora**.
1. Repita los dos pasos anteriores para ejecutar los trabajos **1070** (**Configuración del canal**) y **1110** (**Configuración global**).

![Configuración del propósito de la jerarquía organizativa de cargo automático minorista.](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Defina cargos automáticas por canal

Después de haber activado la característica **Habilitar cargos automáticas de filtro por canal** y configurado el propósito de jerarquía organizativa **Cargo minorista automático**, los cargos automáticos por canal se pueden definir en el nivel de encabezado del pedido o en el nivel de línea de pedido.

Para definir los cargos automáticos por canal en Commerce, siga estos pasos.

1. Vaya a **Clientes \> Configuración de cargos \> cargos automáticos**.
1. En el panel izquierdo, en el campo **Nivel**, seleccione **Encabezado** o **Línea**, dependiendo de los requisitos de su negocio.
1. En el campo **Código de canal minorista**, seleccione el código de canal apropiado (por ejemplo, **Tabla** o **Grupo**). Si la configuración predeterminada, **Todos**, se utiliza, las reglas de carga se aplican a todos los canales.

    - Si selecciona **Grupo**, asegúrese de que se cree un grupo de cargos de canal minorista en **Retail and Commerce \> Configuración del canal \> Cargos \> Grupos de cargos de canales minoristas**.
    - Si selecciona **Tabla**, puede seleccionar un canal específico (por ejemplo, **San Francisco**) en el campo **Relación del canal minorista**.

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. En el panel izquierdo, busque y seleccione el trabajo **1040** (**Productos**).
1. En el panel de acciones, seleccione **Ejecutar ahora**.
1. Repita los dos pasos anteriores para ejecutar los trabajos **1070** (**Configuración del canal**) y **1110** (**Configuración global**).
    
![Cargos automáticos definidos por canal.](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Supuesto de ejemplo

El siguiente ejemplo describe los pasos necesarios para configurar un producto para que se cobren tarifas de reciclaje cuando el producto se vende a través de un canal físico de San Francisco. El ejemplo también muestra cómo aparecen los cargos automáticos en la aplicación de punto de venta (PDV) de Commerce.

La organización define un código de cargos que se denomina **RECICLAR**, como se muestra en la siguiente ilustración.

![Código de cargos de RECICLAR.](media/Auto-charges-charge-code.png)

Se crea un cargo automático al nivel de línea. Tiene la siguiente configuración:

- El campo **Código de cuenta** se establece en **Todos**.
- El campo **Código de artículo** se establece en **Tabla**.
- El campo **Relación del artículo** se establece en Id. de producto **91001**.
- El campo **Código modo de entrega** se establece en **Todos**.
- El campo **Código de canal minorista** se establece en **Tabla**.
- El campo **Relación del canal minorista** se establece en tienda **San Francisco**.

Se crea una línea de cargos automáticos. Tiene la siguiente configuración:

- El campo **Divisa** se establece en **USD**.
- El campo **Código de cargos** se establece en **RECICLAR**.
- El campo **Categoría** se establece en **Fijo**.
- El campo **Cargos** se establece en **6,25 $**.

![Configuración del cargo automática de nivel de línea y la línea de cargo automática.](media/Auto-charges-recyclingfee-line-fee.png)

En la aplicación PDV, se crea un pedido de ventas en el canal de la tienda **San Francisco**. La línea **Cargos** línea muestra la tarifa de reciclaje de **6,25 $**.

Seleccionando **Opciones de transacción \> Cargos \> Administrar cargos** en la aplicación PDV, puede ver el código de cargos y la descripción de la tarifa de reciclaje.

![Tarifa de reciclaje en la aplicación PDV.](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>Recursos adicionales

[Cargos automáticos avanzados omnicanal](omni-auto-charges.md)

[Prorratear los cargos de encabezado con las líneas de ventas coincidentes](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]