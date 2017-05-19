---
title: "Definiciones de informes en el diseñador de informes financieros"
description: "Este artículo proporciona información acerca de las definiciones de informes. Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. Una definición de informe también proporciona opciones y ajustes para personalizar un informe."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 4b8264213cc7b8109b7300752e119d5c03d6239c
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="report-definitions-in-financial-report-designer"></a>Definiciones de informes en el diseñador de informes financieros

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de las definiciones de informes. Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. Una definición de informe también proporciona opciones y ajustes para personalizar un informe. 

Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. Una definición de informe también proporciona opciones y configuración adicionales que puede usar para personalizar un informe. Después de definir definiciones de filas y de columnas, debe combinarlas en una definición del informe. En este momento, también define otros aspectos de las definiciones, como el nivel de detalle y la fecha del informe. Después, puede guardar y generar un informe. Los informes financieros ofrecen los niveles de detalle siguientes:

-   Financiero
-   Financiero y contable
-   Financiero, contable y de transacciones

Sin embargo, en función de cómo se almacenen los datos en el sistema de Microsoft Dynamics ERP, los detalles de transacción pueden no estar disponibles en los informes.

## <a name="create-a-report-definition"></a>Crear una definición del informe
1.  En el diseñador de informes, en el menú **Archivo**, haga clic en **Nuevo** y luego seleccione **Definición del informe**.
2.  Especifique la información adecuada en las pestañas **Informe**, **Salida y distribución**, **Encabezados y pies de página** y **Parámetros**.

## <a name="contents-of-a-report-definition"></a>Contenido de una definición del informe
La siguiente tabla describe las pestañas en una definición del informe y cómo se usa la información.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabulación</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Informe</td>
<td>Crear un informe, configurar un informe o modificar un informe existente.</td>
</tr>
<tr class="even">
<td>Salida y distribución</td>
<td>Cambiar el tipo de salida y destino del informe.</td>
</tr>
<tr class="odd">
<td>Encabezados y pies de página</td>
<td>Definir y aplicar formato a los encabezados y los pies de página para el informe. Por ejemplo, puede agregar texto o imágenes al encabezado o al pie de página. Los informes financieros admiten archivos .bmp, .jpg y .png para imágenes. También puede agregar códigos de autotexto para insertar otra información, como el nombre de la empresa, el nombre del informe o el número de página.</td>
</tr>
<tr class="even">
<td>Parámetros</td>
<td>Especificar la configuración de la definición del informe, como los siguientes parámetros:
<ul>
<li>Formato e importes de redondeo</li>
<li>Formato de los informes de detalles</li>
<li>Formato de organigramas</li>
<li>Generar un informe de excepciones</li>
<li>Especificar conversión de divisa</li>
<li>Detalles del subtotal y de la cuenta de filtro</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Consulte también
--------

[Informes financieros](financial-reporting-intro.md)




