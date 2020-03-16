---
title: Configurar un canal de centro de llamadas
description: En este tema se describe cómo crear un nuevo canal de centro de llamadas en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057888"
---
# <a name="set-up-a-call-center-channel"></a>Configurar un canal de centro de llamadas


[!include [banner](includes/banner.md)]

En este tema se describe cómo crear un nuevo canal de centro de llamadas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

En Dynamics 365 Commerce, un centro de llamadas es un tipo de canal que se puede definir en la aplicación. La definición de un canal para las entidades de su centro de llamadas permite que el sistema vincule datos específicos y valores predeterminados de procesamiento de pedidos a los pedidos de ventas. Una empresa puede definir varios canales de centro de llamadas en Commerce. 

Antes de crear un nuevo canal de centro de llamadas, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Crear y configurar un nuevo canal de centro de llamadas

Para crear y configurar un nuevo centro de llamadas, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Canales \> Centros de llamadas \> Todos los centros de llamadas**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Nombre**, escriba un nombre para el nuevo canal.
1. Seleccione la **Entidad jurídica** apropiada en la lista desplegable.
1. Seleccione la ubicación de **Almacén** apropiada en la lista desplegable.
1. En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido.
1. En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido.
1. Proporcione un código de información de **Anulación del precio**. Tenga en cuenta que puede que tenga que crear antes un código de información para esto.
1. Proporcionar un código de información de **Código de retención**. Tenga en cuenta que puede que tenga que crear antes un código de información para esto.
1. Proporcione un código de información de **Crédito**. Tenga en cuenta que puede que tenga que crear antes un código de información para esto.
1. Seleccione **Guardar**.

La siguiente imagen muestra la creación de un nuevo canal de centro de llamadas.

![Nuevo canal de centro de llamadas](media/channel-setup-callcenter-1.png)

La siguiente imagen muestra un ejemplo de canal de centro de llamadas.

![Ejemplo de canal de centro de llamadas](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Configuración de canal adicional

Las tareas adicionales requeridas para la configuración del canal de centro de llamadas incluyen: configuración de métodos de pago y modos de entrega.

La siguiente imagen muestra las opciones de configuración de **Modos de entrega** y **Métodos de pago** en la pestaña **Configurar**.

![Acciones adicionales de configuración de canales de centro de llamadas](media/channel-setup-callcenter-3.png)

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

## <a name="additional-resources"></a>Recursos adicionales

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Funcionalidad de ventas del centro de llamadas](call-center-functionality.md)

[Configurar opciones de procesamiento de pedidos de centro de llamadas](set-up-order-processing-options.md)

[Catálogos del centro de llamadas](call-center-catalogs.md)

[Configurar y trabajar con alertas de fraude](set-up-fraud-alerts.md)

[Configurar programas de continuidad para centros de llamadas](set-up-continuity-program.md)
