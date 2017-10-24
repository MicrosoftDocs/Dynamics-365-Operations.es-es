---
title: Explorador de origen de contabilidad
description: "Este artículo proporciona información acerca del explorador del origen de contabilidad, que puede usar para análisis detallado de la información de origen detrás de asientos contables de la contabilidad general."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3f5ed28400f333776ce4a5de47ce52aed49094e3
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="accounting-source-explorer"></a>Explorador de origen de contabilidad

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca del explorador del origen de contabilidad, que puede usar para análisis detallado de la información de origen detrás de asientos contables de la contabilidad general.

El Explorador de origen de la contabilidad es una nueva página que muestra la información de origen. Puede usar el Explorador del origen de contabilidad como herramienta independiente o analizar los detalles detrás de asientos contables de la contabilidad general. Por ejemplo, puede usar el Explorador de origen de contabilidad para obtener la información de origen detallada para un saldo en Saldo de comprobación o para una transacción de asiento. Puede usar la característica Exportar a Microsoft Excel para segmentar y desglosar la información en Microsoft Excel (por ejemplo, en una tabla dinámica o un informe de tablas dinámicas).

El Explorador de origen de contabilidad siempre muestra el mismo importe total por cuenta contable que muestra la Contabilidad general (por ejemplo, en un Saldo de comprobación). Como en un Saldo de comprobación, puede mostrar segmentos en columnas independientes. Solo tiene que seleccionar el conjunto adecuado de dimensiones financieras. 

Puede usar parámetros para definir un intervalo de fechas para el análisis. Esta funcionalidad también es similar a la funcionalidad de Saldo de comprobación.

Para todos los documentos que usan el marco del documento de origen, El explorador de origen de contabilidad muestra información adicional basada en las distribuciones contables y, si procede, en distribuciones contables del proyecto. Esta información incluye el tipo de importe monetario, el proyecto, la actividad, la categoría y la propiedad de línea. A continuación se muestran algunos ejemplos del análisis que puede realizar:

-   Desviaciones entre los pedidos de compra y las facturas de proveedor, porque cada desviación está representada por un tipo de importe monetario, como la desviación de cargos
-   Gastos y horas facturables frente a no facturables por proyecto, unidad de negocio y cuenta principal

Para documentos de origen que usen el concepto de identidades de referencia de documento de origen, el Explorador de origen de contabilidad muestra incluso más detalles, como el cliente, el proveedor, el trabajador, el producto, la cantidad, el texto de unidad y las descripciones. A continuación se muestran algunos ejemplos del análisis que puede realizar:

-   Los gastos de hotel por unidad de negocio y el marca de hotel para un período fiscal, en función de los informes de gastos
-   Descuentos por proveedor, producto, departamento

Para estos documentos, también puede navegar hasta el documento de origen real desde el Explorador de origen de contabilidad.




