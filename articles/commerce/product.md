---
title: Agregar recomendaciones de producto en PDV
description: Este artículo describe el uso de las recomendaciones de productos en un dispositivo de punto de venta (PDV).
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460066"
---
# <a name="add-product-recommendations-on-pos"></a>Agregar recomendaciones de producto en PDV

[!include [banner](includes/banner.md)]

En su base, las recomendaciones de productos son una aplicación empresarial de transformación que abarcan entre todos los aspectos de ventas comerciales para experiencias de detección de productos completas, atractivas y personalizadas. Para implementar esta característica en PDV, siga los pasos en [cómo agregar recomendaciones a los dispositivos de PDV.](add-recommendations-control-pos-screen.md) 

Para obtener más información sobre las características de recomendaciones de productos, lea la [información general sobre recomendaciones de productos.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Situaciones

Las recomendaciones de productos se habilitan para los siguientes escenarios de PDV. Están disponibles en PDV en la nube o en PDV moderno (MPOS).

1. En la página **Detalles del producto**:

    - Si un empleado de tienda visita una página de **Detalles del producto** a la hora de buscar transacciones anteriores a través de distintos canales, el servicio de recomendación sugiere artículos adicionales que es probable que se adquieran de forma conjunta. Dependiendo de los complementos para el servicio, los minoristas pueden mostrar las recomendaciones **Comprar aspecto similar** y **Comprar descripción similar** para productos, además de recomendaciones personalizadas para usuarios que cuentan con un historial de compras previo.

    [![Recomendaciones en la página Detalles de producto.](./media/proddetails.png)](./media/proddetails.png)

2. En la página **Transacción**:

    - El motor de recomendación sugiere artículos basados en la lista completa de artículos en la cesta que con frecuencia se adquieren conjuntamente.

    > [!NOTE]
    > Para mostrar recomendaciones en la página **Transacción**, el minorista tiene que actualizar el diseño de la pantalla en Dynamics 365 Commerce. El control **Recomendaciones** debe quitarse de la página **Transacción**.

    [![Recomendaciones de la página de la transacción.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configure Commerce para habilitar las recomendaciones de PDV 

Para configurar recomendaciones de productos, confirme que ha completado el proceso de aprovisionamiento para las recomendaciones de productos de Commerce siguiendo los pasos en [Habilitar recomendaciones de productos](../commerce/enable-product-recommendations.md). De forma predeterminada, las recomendaciones aparecen en las páginas **Detalles de producto** y **Detalles del cliente** después de completar los pasos de aprovisionamiento y los datos se han cocinado correctamente. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Agregar recomendaciones a la pantalla de transacción

1. Para agregar recomendaciones a la pantalla de transacción, siga los pasos en [Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md).
1. Para reflejar los cambios que se realizaron en el diseñador de diseño de pantalla de PDV, ejecute el trabajo de configuración del canal **1070** en Commerce headquarters.

> [!NOTE] 
> Si desea habilitar las recomendaciones de POS mediante el uso del archivo de valores separados por comas (CSV) de RecoMock, debe implementar el archivo CSV en la biblioteca de activos de Microsoft Dynamics Lifecycle Services (LCS) antes de configurar el administrador de diseño. Si usa el archivo CSV de RecoMock, no tiene que habilitar las recomendaciones. El archivo CSV está disponible solo para fines de demostración. Se recomienda para clientes o arquitectos de soluciones que desean imitar la apariencia de las listas de recomendaciones con fines de demostración sin tener que comprar una unidad de mantenimiento de existencias (SKU) adicional.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
