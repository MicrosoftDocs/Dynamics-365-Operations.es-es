---
title: "Reglas de directivas de auditoría"
description: "Puede usar directivas de auditoría para evaluar si ciertos informes de gastos, facturas de proveedor y pedidos de compra para asegurarse de que cumplan las reglas de directivas que ha creado. Todas las reglas asociadas a una directiva de auditoría se ejecutan en el modo por lotes, de acuerdo con la programación que haya especificado.  Cada regla de directivas pertenece a un tipo de regla de directivas. Sólo puede haber una regla de directivas activa por cada tipo de regla de directivas."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: 68f31f00a30513b7d2f3f36a39eaf1cfe7a219a1
ms.contentlocale: es-es
ms.lasthandoff: 08/01/2017

---

# <a name="audit-policy-rules"></a>Reglas de directivas de auditoría

[!include[banner](../includes/banner.md)]


Puede usar directivas de auditoría para evaluar si ciertos informes de gastos, facturas de proveedor y pedidos de compra para asegurarse de que cumplan las reglas de directivas que ha creado. Todas las reglas asociadas a una directiva de auditoría se ejecutan en el modo por lotes, de acuerdo con la programación que haya especificado.  Cada regla de directivas pertenece a un tipo de regla de directivas. Sólo puede haber una regla de directivas activa por cada tipo de regla de directivas. 

<a name="queries-and-query-types"></a>Consultas y tipos de consulta
-----------------------

Para crear una regla de directivas de auditoría, en primer lugar se selecciona un tipo de regla de directivas. El tipo de regla de directivas determina la consulta del árbol de objetos de aplicación (AOT) que se usa como punto de partida para crear la regla de directivas. También especifica el tipo de consulta que se usará para la regla de directivas. La consulta determina el documento de origen que evalúa la regla de directivas. También especifica los campos del documento de origen que identifican tanto la entidad jurídica y como la fecha que se usará al seleccionar documentos para una auditoría. El tipo de consulta controla los campos predeterminados de la página de consulta y de la página Regla de directivas de auditoría. En la tabla siguiente se incluyen los tipos de consulta disponibles para reglas de directivas de auditoría.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de consulta</th>
<th>Propósito</th>
<th>Más información</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Condicional</td>
<td>Evalúe los atributos del documento de origen respecto a los valores especificados.</td>
<td></td>
</tr>
<tr class="even">
<td>Agregado</td>
<td>Evalúe varios documentos de origen o líneas de documento de origen respecto a una regla de directivas agregando valores numéricos.</td>
<td></td>
</tr>
<tr class="odd">
<td>Muestra</td>
<td>Seleccione de manera aleatoria un porcentaje especificado de los documentos de origen para evaluar si se infringen las directivas.</td>
<td>Al seleccionar esta opción, use la página Regla de directivas de auditoría para especificar el porcentaje de documentos que se seleccionarán de manera aleatoria para una auditoría.</td>
</tr>
<tr class="even">
<td>Duplicado</td>
<td>Evalúe los documentos de origen para determinar si contienen entradas duplicadas en campos específicos.</td>
<td>Al seleccionar esta opción, use la página Regla de directivas de auditoría para especificar el número de días que desea agregar al inicio del intervalo de fechas de selección de documentos al comprobar si existen entradas duplicadas en los documentos.</td>
</tr>
<tr class="odd">
<td>Enumerar búsqueda</td>
<td>Evalúe entidades específicas de los documentos de origen.</td>
<td>El documento raíz de la consulta define el documento al que se está realizando la auditoría. La consulta debe ser una consulta de lista que incluya una referencia a la tabla dirpartytable. Esta opción sólo se puede usar con las siguientes consultas del AOT:
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (Empleados supervisados del informe de gastos)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Proveedores supervisados de pedido de compra)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (proveedores supervisados de factura de proveedor)</li>
</ul>
Al seleccionar esta opción, especifique las entidades supervisadas en la página Regla de directivas de auditoría.</td>
</tr>
<tr class="even">
<td>Búsqueda de palabra clave</td>
<td>Evalúe los documentos de origen para determinar si contienen ciertas palabras.</td>
<td>Al seleccionar esta opción, especifique las palabras que se buscarán en la página Regla de directivas de auditoría. La página Regla de directivas de auditoría también incluye opciones que permiten especificar las tablas y campos en que desea buscar las palabras especificadas.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Parámetros comunes
Todas las reglas de directivas de una directiva de auditoría concreta comparten los mismos parámetros de lotes y el mismo intervalo de fechas de selección de documentos. Estos parámetros se especifican para la directiva en la página Opciones adicionales.



<a name="see-also"></a>Consulte también
--------

[Infracciones de directivas de auditoría y casos](audit-policy-violations-cases.md)
[Defina directivas de auditoría para los documentos de origen](tasks/define-audit-policies-source-documents.md)



