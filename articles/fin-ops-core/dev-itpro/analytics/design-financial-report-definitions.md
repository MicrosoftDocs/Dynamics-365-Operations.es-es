---
title: Definiciones de informes en el diseñador de informes financieros
description: Este artículo proporciona información acerca de las definiciones de informes.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.form: FinancialReports
ms.openlocfilehash: 2ffef335c694af56486ccd7738818c4edda49b9e
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802562"
---
# <a name="report-definitions-in-financial-report-designer"></a>Definiciones de informes en el diseñador de informes financieros

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las definiciones de informes. Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. Una definición de informe también proporciona opciones y ajustes para personalizar un informe. 

Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. Una definición de informe también proporciona opciones y valores de configuración que puede usar para personalizar un informe. Después de definir definiciones de filas y de columnas, debe combinarlas en una definición del informe. En este momento, también define otros aspectos de las definiciones, como el nivel de detalle y la fecha del informe. Después, puede guardar y generar un informe. Los informes financieros ofrecen los niveles de detalle siguientes:

- Financiero
- Financiero y contable
- Financiero, contable y de transacciones

No obstante, según la forma en que se almacenan los datos en el sistema Microsoft Dynamics ERP, es posible que los detalles de transacción no estén disponibles en los informes.

## <a name="create-a-report-definition"></a>Crear una definición del informe
1. En Report designer, en el menú **Archivo**, haga clic en **Nuevo** y luego seleccione **Definición del informe**.
2. Especifique la información adecuada en las pestañas **Informe**, **Salida y distribución**, **Encabezados y pies de página** y **Parámetros**.

## <a name="contents-of-a-report-definition"></a>Contenido de una definición del informe
La siguiente tabla describe las pestañas en una definición del informe y cómo se usa la información.

<table>
<thead>
<tr>
<th>Pestaña</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>Informe</td>
<td>Crear un informe, configurar un informe o modificar un informe existente.</td>
</tr>
<tr>
<td>Salida y distribución</td>
<td>Cambiar el tipo de salida y destino del informe.</td>
</tr>
<tr>
<td>Encabezados y pies de página</td>
<td>Definir y aplicar formato a los encabezados y los pies de página para el informe. Por ejemplo, puede agregar texto o imágenes al encabezado o al pie de página. Los informes financieros admiten archivos .bmp, .jpg y .png para imágenes. También puede agregar códigos de autotexto para insertar otra información, como el nombre de la empresa, el nombre del informe o el número de página.</td>
</tr>
<tr>
<td>Parámetros</td>
<td>Especificar la configuración de la definición del informe, como los siguientes parámetros:
<ul>
<li>Formato e importes de redondeo</li>
<li>Formato de los informes de detalles</li>
<li>Formato de organigramas</li>
<li>Generar un informe de excepciones</li>
<li>Especificar conversión de divisa</li>
<li>Detalles del subtotal y de la cuenta de filtro</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
