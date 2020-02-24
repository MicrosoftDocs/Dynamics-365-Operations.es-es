---
title: Configurar un canal en línea
description: En este tema se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9b7a2b8fd157df8b39e9e227d188a3802cacb4e3
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002436"
---
# <a name="set-up-an-online-channel"></a>Configurar un canal en línea


[!include [banner](includes/banner.md)]

En este tema se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Dynamics 365 Commerce admite varios canales comerciales. Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas). Las tiendas en línea proporcionan a los clientes la opción de comprar productos de su tienda en línea además de en sus tiendas físicas.

Para crear una tienda en línea en Commerce, primero debe crear un canal en línea. 

Antes de crear un nuevo canal en línea, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).

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

![Nuevo canal en línea](media/channel-setup-online-1.png)

La siguiente imagen muestra un ejemplo de canal en línea.

![Ejemplo de canal en línea](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a>Configurar idiomas

Si su sitio de comercio electrónico admite varios idiomas, expanda la sección **Idiomas** y agregue idiomas adicionales según sea necesario.

## <a name="set-up-payment-account"></a>Configurar una cuenta de pago

En la sección **Cuenta de pago** puede agregar un proveedor de pagos de terceros. Para obtener información sobre cómo configurar un conector de pagos de Adyen, consulte [Conector de pagos de Dynamics 365 para Adyen](../retail/dev-itpro/adyen-connector.md).

## <a name="additional-channel-set-up"></a>Configuración adicional de canal

Las tareas adicionales requeridas para la configuración del canal en línea incluyen: configuración de métodos de pago, modos de entrega y asignación de grupo de cumplimiento.

La siguiente imagen muestra las opciones de configuración **Modos de entrega**, **Métodos de pago** y **Asignación de grupo de cumplimiento** en la pestaña **Configurar**.

![Acciones adicionales de configuración de canales en línea](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pago

Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el panel de navegación, seleccione el método de pago deseado.
1. En la sección **General**, proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.
1. Configure opciones de configuración adicionales según sea necesario para el tipo de pago.
1. En el panel de acciones, seleccione **Guardar**.

En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.

![Ejemplo de métodos de pago](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Configurar modos de entrega

Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **Panel de acciones**.  

Para cambiar o agregar un modo de entrega, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.
1. En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.
1. En la sección **Canales comerciales**, seleccione **Agregar línea** para agregar el canal. Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.

En la imagen siguiente se muestra un ejemplo de mode de entrega.

![Configurar modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Configurar una asignación de grupo de cumplimiento

Para configurar una asignación de grupo de cumplimiento, siga estos pasos.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimiento**.
1. En el panel de acciones, seleccione **Nueva**.
1. En la lista desplegable **Grupo de cumplimiento**, seleccione un grupo de cumplimiento.
1. En la lista desplegable **Descripción**, escriba una descripción.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de configuración de asignación de grupo de cumplimiento.

![Configurar la asignación de grupo de cumplimiento](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Recursos adicionales

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Configurar un canal comercial](channel-setup-retail.md)

[Configurar un canal de centro de llamadas](channel-setup-callcenter.md)

[Conector de pago de Dynamics 365 para Adyen](../retail/dev-itpro/adyen-connector.md)
