---
title: Obtener recomendaciones de producto mediante datos de prueba
description: Este documento ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: af8a30e69d9ed143e045950efdcece207f6da14c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697944"
---
# <a name="get-product-recommendations-using-demo-data"></a>Obtener recomendaciones de producto mediante datos de prueba
Este documento ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.

Las recomendaciones de producto omnicanal proporcionan un conjunto de listas de productos generadas por programación o de forma dirigida. Estas listas se pueden usar en varias situaciones, en función de la necesidad empresarial. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).

Para entornos de Dynamics 365 de nivel 2 y superior, las recomendaciones de productos se calculan automáticamente en función de los datos del cliente. El uso de datos de demostración para recomendaciones de productos no deshabilita ninguna solución de recomendación de productos ya aprovisionada en el entorno ni los costes vinculados a su uso.

Para entornos de nivel 1, las recomendaciones de productos solo se basan en datos estáticos de demostración almacenados en un archivo .csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Habilitar datos de demostración de productos en un entorno
Para habilitar datos de demostración para recomendaciones de productos, tiene que implementar la Extensión de demostración de vista previa de Dynamics 365 Commerce para el entorno respectivo. Hacerlo automáticamente habilita los datos de demostración de recomendaciones de productos.

## <a name="default-demo-data"></a>Datos de demostración predeterminados
Cada entorno de tipo Onebox incorpora un conjunto preinstalado de datos de demostración para recomendaciones de productos almacenado en el archivo separado por comas “reco_demo_data.csv”, que se encuentra en Retail Server.

Los datos se estructuran en las siguientes columnas.

| Nombre de columna         | Obligatorio          | Descripción                                                                                                                                 | Valores posibles                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | El tipo de lista específico de recomendaciones de productos que el punto de datos de demostración va a generar.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | El número de unidad operativa específico donde se espera que aparezcan las recomendaciones de productos.                                        |                                                                              |
| Categoría            |                    |    La categoría para la que debe devolverse la lista específica. Si no se especifica ninguna categoría, la lista es solo para los primeros elementos de la jerarquía de navegación.    |                                                                              |
| SeedItemId          |                    |    Para las listas que requieren inicialización (RecoPeopleAlsoBuy y RecoCart), el producto para el que esas listas deben mostrar productos adicionales.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Uno o más productos que se devolverán como el resultado, separado por ‘;’.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Personalizar datos de demostración
Puede editar los datos predeterminados de prueba con cualquier información de producto y categoría que se configure en la sede. Una vez que se actualice el .csv, las recomendaciones de productos devueltas para los clientes inmediatamente reflejarán los cambios.

La extensión contiene un archivo de datos denominado 'RecoMockDataset.csv' que le permite controlar el conjunto de datos usado para activar los resultados de las recomendaciones simuladas. El nombre de archivo se puede controlar con la configuración de la extensión mediante la configuración **ext.Recommendations.DemoFilePath**. Esto le permite disponer de varios conjuntos de datos que se pueden intercambiar fácilmente entre ellos a través de la configuración.


```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Planificación de entorno](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
