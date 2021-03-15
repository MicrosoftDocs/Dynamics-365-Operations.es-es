---
title: Resumen de canales
description: Este tema presenta una visión general de los canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e060fe2a578296f079653244ed4d5676313e5ea8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963069"
---
# <a name="channels-overview"></a>Resumen de canales


[!include [banner](includes/banner.md)]

Este tema presenta una visión general de los canales en Microsoft Dynamics 365 Commerce. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar cada canal.

## <a name="types-of-channels"></a>Tipos de canales

Dynamics 365 Commerce admite tres tipos de canales diferentes: de minorista, de centro de llamadas y en línea.

### <a name="retail-channels"></a>Canales comerciales

Los canales minoristas representan tiendas físicas estándar. Cada tienda puede tener sus propios registros de punto de venta (PDV), cuentas de ingresos y gastos, y personal. 

### <a name="call-center-channels"></a>Canal de centro de llamadas

Los canales de centro de llamadas representan pedidos de centro de llamadas y administración de clientes.

### <a name="online-channels"></a>Canales en línea

Los canales en línea representan escaparates de comercio electrónico en línea. Cuando se crea un canal en línea, hay que crear un sitio con la herramienta Configurador de sitios de Microsoft Dynamics 365 Commerce u otra solución de comercio electrónico de terceros.

## <a name="channel-setup-basics"></a>Fundamentos de la configuración de canales

La configuración de canales se realiza en la herramienta Commerce. Cada canal puede tener sus propios métodos de pago, grupos de precios, jerarquías de productos, surtidos y conjunto de productos. Una vez creado un canal, puede asignar los productos que desea que tenga y vender. Cada tipo de canal tiene un conjunto único de características que puede ser necesario configurar. Por ejemplo, un canal minorista necesita empleados, registros y clientes asignados. Una vez que se crea un nuevo canal, debe asignarse a una jerarquía organizativa.

## <a name="channel-setup-prerequisites"></a>Requisitos previos de configuración de canales

Para poder configurar un canal, antes debe completar algunas tareas de requisitos previos, en función del tipo de canal. Para obtener más información, consulte [Requisitos previos de configuración de canales](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Configurar un canal

Después de completar las tareas de requisitos previos, use los siguientes vínculos para obtener más instrucciones de configuración.

- [Configurar un canal comercial](channel-setup-retail.md)
- [Configurar un canal de centro de llamadas](channel-setup-callcenter.md)
- [Configurar un canal en línea](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>Recursos adicionales

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Configurar un canal comercial](channel-setup-retail.md)
    
[Configurar un canal en línea](channel-setup-online.md)

[Configurar un canal de centro de llamadas](channel-setup-callcenter.md)

[Configurar jerarquías organizativas](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]