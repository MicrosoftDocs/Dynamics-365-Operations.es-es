---
title: Dados de demostración para recomendaciones de productos de omnicanal
description: Este documento pretende proporcionar instrucciones acerca de cómo aprovechar las recomendaciones del producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 81af4c1bb7828c9b346a3ef514d8657e853dcefb
ms.sourcegitcommit: c526cfd1f823df1ff33ded95e599a72f0a15cc5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2226415"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Dados de demostración para recomendaciones de productos de omnicanal

Este documento pretende proporcionar instrucciones acerca de cómo aprovechar las recomendaciones del producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.

Las recomendaciones de producto omnicanal proporcionan un conjunto de listas de productos ordenadas generadas por programación o de forma dirigida. Estas listas se pueden usar en varias situaciones, en función de la necesidad empresarial. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendaitons-overview.md)

Para productos de entornos de Dynamics de nivel 2 y más las recomendaciones se calculan automáticamente en función de los datos del cliente.
El uso de datos de demostración para recomendaciones de productos no deshabilita ninguna solución de recomendación de productos ya aprovisionada en el entorno ni los costes vinculados a su uso.

Para los producto de entornos de nivel 1, las recomendaciones solo se basan de datos estáticos de demostración almacenados en un archivo csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Habilitar datos de demostración de productos en un entorno

Los clientes deben implementar la **Extensión de demostración de vista previa de Dynamics 365 Commerce** para entorno respectivo, que habilita automáticamente los datos de demostración para las recomendaciones de productos.

## <a name="default-demo-data"></a>Datos de demostración predeterminados
Cada entorno de tipo Onebox incorpora un conjunto preinstalado de datos de demostración para recomendaciones de productos almacenado en el archivo separado comas **“reco_demo_data.csv”**, que se encuentra en la misma carpeta que este documento en Retail Server.

Estos datos se estructuran en las siguientes columnas

| Nombre de columna         | Obligatorio          | Descripción                                                                                                                                 | Valores posibles                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | El tipo de lista específico de recomendaciones de productos que el punto de datos de demostración va a generar.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | El número de unidad operativa específico donde se espera que aparezcan las recomendaciones de productos.                                        |                                                                              |
| Categoría            |                    |    La categoría para la que debe devolverse la lista específica. Si no se especifica ninguna categoría, la lista es solo para la los primeros elementos de la jerarquía de navegación.    |                                                                              |
| SeedItemId          |                    |    Para las listas que requieren semilla (RecoPeopleAlsoBuy y RecoCart), el producto para el que esas listas deben mostrar productos adicionales.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Uno o más productos que se devolverán como el resultado, separado por **‘;’**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Personalizar datos de demostración
Los clientes pueden editar los datos predeterminados de prueba con cualquier información de producto y categoría que se configure en la sede. Una vez que se actualice el CSV, las recomendaciones de productos devueltas para los clientes inmediatamente reflejarán los cambios.

La extensión contiene un archivo de datos denominado RecoMockDataset.csv que permita que el cliente controle el conjunto de datos usado para activar los resultados de las recomendaciones simuladas. El nombre de archivo se puede controlar con la configuración de la extensión mediante la configuración **ext.Recommendations.DemoFilePath**. Esto permite a los clientes disponer de varios conjuntos de datos varios que se pueden intercambiar fácilmente entre ellos a través de la configuración.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de productos](product-recommendations-overview.md)

[Planificación de entorno](environment-planning.md)
