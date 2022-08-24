---
title: Configurar un canal en línea
description: En este artículo se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: be9fafe8ece771ad6577db1cdb70af6f48e054cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272890"
---
# <a name="set-up-an-online-channel"></a>Configurar un canal en línea

[!include [banner](includes/banner.md)]

En este artículo se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce admite varios canales comerciales. Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas). Las tiendas en línea proporcionan a los clientes la opción de comprar productos de su tienda en línea además de en sus tiendas físicas.

Para crear una tienda en línea en Commerce, primero debe crear un canal en línea. Antes de crear un nuevo canal en línea, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).

Para poder crear un sitio nuevo, se debe crear al menos una tienda en línea en Commerce. Para más información, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Crear y configurar un nuevo canal en línea

Para crear y configurar un nuevo canal en línea, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Canales \> Tiendas en línea**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Nombre**, escriba un nombre para el nuevo canal.
1. En la lista desplegable **Entidad jurídica**, introduzca la entidad jurídica correspondiente.
1. En la lista desplegable **Almacén**, introduzca el almacén apropiado.
1. En el campo **Zona horaria de la tienda**, seleccione la zona horaria apropiada.
1. En el campo **Divisa**, seleccione la divisa apropiada.
1. En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido.
1. En el campo **Libreta de direcciones de cliente**, especifique una libreta de direcciones válida.
1. En el campo **Perfil de funcionalidad**, seleccione un perfil de funcionalidad si corresponde.
1. En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra la creación de un nuevo canal en línea.

![Nuevo canal en línea.](media/channel-setup-online-1.png)

La siguiente imagen muestra un ejemplo de canal en línea.

![Ejemplo de canal en línea.](media/channel-setup-online-2.png)

## <a name="assign-the-channel-to-a-commerce-scale-unit"></a>Asigne el canal a Commerce Scale Unit

Su nuevo canal debe estar asignado a Commerce Scale Unit. Para obtener instrucciones, consulte [Configurar canales para usar Commerce Scale Unit](../fin-ops-core/dev-itpro/deployment/initialize-retail-channels.md#configure-channels-to-use-commerce-scale-unit).

## <a name="set-up-languages"></a>Configurar idiomas

Si su sitio de comercio electrónico admite varios idiomas, expanda la sección **Idiomas** y agregue idiomas adicionales según sea necesario.

## <a name="set-up-payment-account"></a>Configurar una cuenta de pago

En la sección **Cuenta de pago** puede agregar un proveedor de pagos de terceros. Para obtener información sobre cómo configurar un conector de pagos de Adyen, consulte [Conector de pagos de Dynamics 365 para Adyen](./dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>Configuración de canal adicional

Las tareas adicionales requeridas para la configuración del canal en línea incluyen: configuración de métodos de pago, modos de entrega y asignación de grupo de cumplimiento.

La siguiente imagen muestra las opciones de configuración **Modos de entrega**, **Métodos de pago** y **Asignación de grupo de cumplimiento** en la pestaña **Configurar**.

![Acciones adicionales de configuración de canales en línea.](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pago

Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el panel de navegación, seleccione el método de pago deseado.
1. En la sección **General**, proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.
1. Configure opciones de configuración adicionales según sea necesario para el tipo de pago.
1. En el panel de acciones, seleccione **Guardar**.

En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.

![Ejemplo de métodos de pago.](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Configurar modos de entrega

Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **panel Acciones**.  

Para cambiar o agregar un modo de entrega, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.
1. En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.
1. En la sección **Canales comerciales**, seleccione **Agregar línea** para agregar el canal. Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.

En la imagen siguiente se muestra un ejemplo de mode de entrega.

![Configurar modos de entrega.](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Configurar una asignación de grupo de cumplimiento

Para configurar una asignación de grupo de cumplimiento, siga estos pasos.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimiento**.
1. En el panel de acciones, seleccione **Nueva**.
1. En la lista desplegable **Grupo de cumplimiento**, seleccione un grupo de cumplimiento.
1. En la lista desplegable **Descripción**, escriba una descripción.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de configuración de asignación de grupo de cumplimiento.

![Configurar la asignación de grupo de cumplimiento.](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Recursos adicionales

[Información general de canales](channels-overview.md)

[Requisitos previos de configuración del canal](channels-prerequisites.md)

[Configurar un canal comercial](channel-setup-retail.md)

[Configurar un canal de centro de llamadas](channel-setup-callcenter.md)

[Conector de pago de Dynamics 365 para Adyen](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
