---
title: "Infracciones y casos de directivas de auditoría"
description: "El artículo explica cómo se generan los casos de auditoría a partir de infracciones de reglas de directivas de auditoría. También incluye información acerca de las distintas maneras en que las directivas de auditoría usan el intervalo de fechas de selección de documentos."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 24ee0dbf01208f8decc167e11e84191eaae03edf
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="audit-policy-violations-and-cases"></a>Infracciones y casos de directivas de auditoría

[!include[banner](../includes/banner.md)]


El artículo explica cómo se generan los casos de auditoría a partir de infracciones de reglas de directivas de auditoría. También incluye información acerca de las distintas maneras en que las directivas de auditoría usan el intervalo de fechas de selección de documentos.

<a name="how-audit-cases-are-generated"></a>Cómo se crean casos de auditoría
-----------------------------

Las directivas de auditoría se usan para identificar los informes de gastos, los pedidos de compra y las facturas de proveedor que no cumplen con las reglas empresariales que defina y configure como reglas de directivas de auditoría. 

Las directivas de auditoría se ejecutan en modo por lotes. Cuando ejecuta una directiva de auditoría, todas las reglas de directivas que forman parte de esa directiva se ejecutan simultáneamente.

Cada regla de directivas evalúa un conjunto de documentos. La regla de directivas selecciona documentos que se encuentran en el intervalo de fechas de selección del documento y coinciden con los criterios especificados. Por ejemplo, una regla de directivas puede seleccionar los informes de gastos con comidas que superen 50,00. Otra regla de directivas puede seleccionar las facturas de proveedor que se deben pagar a un proveedor específico. Para cada documento que se seleccione del conjunto, se genera una infracción. Esa infracción es un registro de que un documento concreto, como la factura 12345, no cumple con la regla de directiva. 

Varios registros de infracción de auditoría se agrupan conjuntamente y se asocian a casos de auditoría. De forma predeterminada, los casos para cada directiva de auditoría se agrupan por la regla de directivas de auditoría. Si lo prefiere, puede seleccionar otros criterios de agrupación con la página **Criterios de agrupación de casos**. Por ejemplo, puede agrupar encabezados de gastos por id. de proyecto y facturas de proveedor por cuenta de proveedor. En este caso, todas las infracciones del encabezado de gastos con el mismo id. de proyecto se agruparán en el mismo caso, y todas las facturas de proveedor con la misma cuenta de proveedor se agruparán en el mismo caso. 

> [!NOTE]
> Para las reglas de directivas de auditoría basadas en un tipo de consulta **Duplicado**, las infracciones no se agrupan por regla de directivas o por los criterios especificados en la página **Criterios de agrupación de casos**. En su lugar, se agrupan por los criterios que se crean en la regla de directivas de auditoría. Por ejemplo, si una regla de directiva evalúa los informes de gastos para los gastos duplicados del mismo importe, id. de comerciante y fecha, todos los gastos que tengan los mismos valores en esos campos serán un caso. Los gastos que tengan valores diferentes, será un caso independiente.

Después de que se generen casos de auditoría, se gestionan con los procesos típicos para la gestión de casos.

## <a name="document-selection-date-ranges"></a>Intervalos de fechas de selección de documentos
Cuando se ejecute una directiva de auditoría, cada regla de directivas selecciona documentos del tipo especificado que tengan una fecha que esté en el intervalo de fechas de selección de documentos. El intervalo de fechas de selección de documentos se especifica en la página **Opciones adicionales**. Muchos documentos tienen más de una fecha asociada. El campo de fecha que la regla de directivas de auditoría usa se especifica en la página **Tipo de regla de directivas**.

Estas son alguna otras maneras de que una directiva de auditoría use el intervalo de fechas de selección de documentos:

-   La directiva usa la versión de cada regla de directivas que es efectiva el último día del intervalo de fechas de selección de documentos. Puede ver las fechas de vigencia para cada regla de directivas en la página de lista **Directivas de auditoría**.
-   La directiva usa los nodos de la organización asociados con la directiva el último día del intervalo de fechas de selección de documentos. Solo los nodos de la organización que están actualmente asociados a la directiva aparecen en la página de lista **Directivas de auditoría**.
-   Para las reglas de directivas que se basan en un tipo de consulta de **Enumerar búsqueda**, la directiva evalúa documentos para las entidades supervisadas que son efectivas el último día del intervalo de fechas de selección de documentos.


Para obtener más información, consulte [Reglas de directivas de auditoría](audit-policy-rules.md)




