---
title: Crear recomendaciones con datos de demostración
description: Este tema ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7ccb0b6c5aace0fc76c6886299fba7369abed860
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972384"
---
# <a name="create-recommendations-with-demo-data"></a>Crear recomendaciones con datos de demostración

[!include [banner](includes/banner.md)]

Este tema ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.

Las recomendaciones de producto omnicanal proporcionan un conjunto de listas de productos generadas por programación o de forma dirigida. Estas listas se pueden usar en varias situaciones, en función de la necesidad empresarial. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).

Para entornos de Dynamics 365 de nivel 2 y superior, las recomendaciones de productos se calculan automáticamente en función de los datos del cliente. El uso de datos de demostración para recomendaciones de productos no deshabilita ninguna solución de recomendación de productos ya aprovisionada en el entorno ni los costes vinculados a su uso.

Para entornos de nivel 1, las recomendaciones de productos solo se basan en datos estáticos de demostración almacenados en un archivo .csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Habilitar datos de demostración de productos en un entorno
Para habilitar datos de demostración para recomendaciones de productos, tiene que implementar la Extensión de demostración de vista previa de Dynamics 365 Commerce para el entorno respectivo. Hacerlo automáticamente habilita los datos de demostración de recomendaciones de productos.

## <a name="default-demo-data"></a>Datos de demostración predeterminados
Cada entorno de tipo OneBox incorpora un conjunto preinstalado de datos de demostración para recomendaciones de productos almacenado en el archivo separado por comas “reco_demo_data.csv”, que se encuentra en Commerce Scale Unit.

Los datos se estructuran en las siguientes columnas.

| Nombre columna         | Obligatorio          | Descripción                                                                                                                                 | Valores posibles                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | El tipo de lista específico de recomendaciones de productos que el punto de datos de demostración va a generar.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | El número de unidad operativa específico donde se espera que aparezcan las recomendaciones de productos.                                        |                                                                              |
| Categoría            |                    |    La categoría para la que debe devolverse la lista específica. Si no se especifica ninguna categoría, la lista es solo para los primeros elementos de la jerarquía de navegación.    |                                                                              |
| SeedItemId          |                    |    Para las listas que requieren inicialización (RecoPeopleAlsoBuy y RecoCart), el producto para el que esas listas deben mostrar productos adicionales.            |                                                                              |
| CustomerId          |                    |    Para listas que requieren un identificador de cliente (RecoPicks).  El valor predeterminado '0' se aplica a todos los clientes.          |                                                                              |
| ItemIds             | :heavy_check_mark: | Uno o más productos que se devolverán como resultado, separados por signos de punto y coma.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Personalizar datos de demostración
Puede editar los datos predeterminados de prueba con cualquier información de producto y categoría que se configure en la sede. Después de actualizar el .csv, las recomendaciones de productos devueltas para los clientes inmediatamente reflejarán los cambios.

La extensión contiene un archivo de datos denominado "RecoMockDataset.csv", que le permite controlar el conjunto de datos usado para activar los resultados de las recomendaciones simuladas. El nombre de archivo se puede controlar con la configuración de la extensión mediante la configuración **ext.Recommendations.DemoFilePath**. Esto le permite disponer de varios conjuntos de datos que se pueden intercambiar fácilmente entre ellos a través de la configuración.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)
