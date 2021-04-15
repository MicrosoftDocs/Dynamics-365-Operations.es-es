---
title: Utilizar el motor de precios de Dynamics 365 Commerce con Dynamics 365 Sales
description: Este tema describe cómo usar el motor de precios de Microsoft Dynamics 365 Commerce para crear presupuestos de ventas en Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: 364cc5adf0358ffa952750149ad31d62cbd35e87
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751443"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Utilizar el motor de precios de Dynamics 365 Commerce con Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Este tema describe cómo usar el motor de precios de Microsoft Dynamics 365 Commerce para crear presupuestos de ventas en Dynamics 365 Sales.

El motor de precios de Dynamics 365 Commerce es compatible con la mayoría de los escenarios de precios de empresa a consumidor (B2C), como precios a nivel de tienda, precios basados en afiliación y lealtad, descuentos combinados, descuentos por cantidad y descuentos por umbral. El motor de fijación de precios utiliza reglas complejas para determinar el mejor precio para un presupuesto o pedido determinado.

Cuando usa [escritura dual](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), tiene tres opciones para sus necesidades de precios. Puede usar el precio estático que proviene de la lista de precios en Dynamics 365 Sales, el motor de precios en Dynamics 365 Supply Chain Management o el motor de precios en Dynamics 365 Commerce. Entre estas opciones, el motor de precios de Commerce se adapta mejor a los escenarios B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Utilice el motor de precios de Commerce en Sales

> [!NOTE]
> Actualmente, el motor de precios de Commerce solo se puede utilizar para la creación de cotizaciones en Sales. La integración de pedidos de venta con el motor de precios de Commerce aún no está disponible.

Cuando los usuarios inician una cotización en Sales, el marco de escritura dual copia los detalles de la cotización a Commerce. Cualquier cambio en las líneas de cotización existentes o cualquier línea de presupuesto recién agregada en Sales se copia en Commerce. Cuando los usuarios quieran utilizar el motor de precios de Commerce para fijar el precio de la cotización, pueden seleccionar **Presupuesto de precio** para actualizar los precios del presupuesto, según el motor de precios de Commerce. Los precios se actualizan automáticamente tanto en Sales como en Commerce.

## <a name="prerequisites"></a>Requisitos previos

- Antes de poder utilizar el motor de precios de Commerce en Sales , debe seguir los pasos en [Cliente potencial a efectivo en escritura dual](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).
- Debe desactivar la evaluación de acuerdos comerciales para la entrada manual siguiendo estos pasos:

    1. En su entorno de Commerce vaya a **Clientes \> Configuración \> Parámetros de clientes**.
    1. En la pestaña **Precios**, en la ficha desplegable **Evaluación de acuerdos comerciales**, borre la casilla de verificación **Entrada manual**.

## <a name="additional-resources"></a>Recursos adicionales

[Cliente potencial a efectivo en doble escritura](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]