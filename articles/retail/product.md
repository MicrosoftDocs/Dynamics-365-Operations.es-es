---
title: Recomendaciones de productos en PDV
description: Este tema describe el uso de las recomendaciones de productos en un dispositivo de punto de venta (PDV).
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 98c84e987c40adf136d0240117f7b0f119bf2f59
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811126"
---
# <a name="product-recommendations-on-pos"></a>Recomendaciones de productos en PDV

[!include [banner](includes/banner.md)]

En su base, las recomendaciones de productos son una aplicación empresarial de transformación que abarcan entre todos los aspectos de ventas al por menor para experiencias de detección de productos completas, atractivas y personalizadas. Para implementar esta característica en PDV, siga los pasos en [cómo agregar recomendaciones a los dispositivos de PDV.](add-recommendations-control-pos-screen.md) 

Para obtener más información sobre las características de recomendaciones de productos, lea la [información general sobre recomendaciones de productos.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Situaciones

Las recomendaciones de productos se habilitan para los siguientes escenarios de PDV. Están disponibles en PDV en la nube o en PDV moderno (MPOS).

1. En la página **Detalles del producto**:

    - Si un empleado de tienda visita una página de **Detalles del producto** a la hora de buscar transacciones anteriores a través de distintos canales, el servicio de recomendación sugiere artículos adicionales que es probable que se adquieran de forma conjunta.

    [![Recomendaciones en la página Detalles de producto](./media/proddetails.png)](./media/proddetails.png)

2. En la página **Transacción**:

    - El motor de recomendación sugiere artículos basados en la lista completa de artículos en la cesta que con frecuencia se adquieren conjuntamente.

    > [!NOTE]
    > Para mostrar recomendaciones en la página **Transacción**, el minorista tiene que actualizar el diseño de la pantalla en Dynamics 365 for Retail. El control **Recomendaciones** debe quitarse de la página **Transacción**.

    [![Recomendaciones de la página de la transacción](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a>Configure Dynamics 365 Retail para habilitar las recomendaciones de PDV

Siga estos pasos para configurar recomendaciones de productos:

1. Asegúrese de que el servicio se ha actualizado a la **compilación 10.0.6**.
2. Siga las instrucciones de cómo [habilitar recomendaciones de productos](../commerce/enable-product-recommendations.md) para su negocio.
3. Opcional: para mostrar recomendaciones en la pantalla de transacción, vaya a **Diseño de pantalla**, elija su diseño de pantalla, inicie el **Diseñador de pantalla** y quite el control de **recomendaciones** cuando sea necesario.
4. Vaya a **Parámetros de ventas al por menor** seleccione **Aprendizaje automático** y seleccione **Sí** en **Habilitar recomendaciones de PDV**.
5. Para ver recomendaciones sobre el PDV, ejecute el trabajo de configuración global **1110**. Para reflejar los cambios realizados en el diseñador de pantalla del PVD, ejecute el trabajo de configuración de canal **1070**.



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Solucionar problemas donde tiene recomendaciones de productos ya habilitadas

- Vaya a **Parámetros de ventas al por menor** \> **Listas de recomendaciones** \> **Deshabilitar recomendaciones de productos** y ejecute **Trabajo de configuración global \[9999\]**. 
- Si agregó el **Control de recomendaciones** a su pantalla de transacción mediante el **Diseñador de pantalla**, quítelo también.
- Si tiene preguntas adicionales, consulte [Preguntas más frecuentes sobre las recomendaciones del producto](../commerce/faq-recommendations.md) para obtener más información.

## <a name="additional-resources"></a>Recursos adicionales

[Agregue un control de recomendaciones a la pantalla de transacción en dispositivos de PDV](add-recommendations-control-pos-screen.md)

[Visión general de recomendaciones de producto](../commerce/product-recommendations.md)

[Habilitar recomendaciones de producto](../commerce/enable-product-recommendations.md) 
