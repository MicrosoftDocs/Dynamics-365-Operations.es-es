---
title: Configurar las reglas y los parámetros para el tránsito directo y la estrategia de presión
description: Este procedimiento muestra los pasos para crear Reglas de reabastecimiento.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc5404e5eb1679659604a6268fa09519a7a4282e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003736"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a>Configurar las reglas y los parámetros para el tránsito directo y la estrategia de presión

[!include [banner](../includes/banner.md)]

Este procedimiento muestra los pasos para crear Reglas de reabastecimiento. Las reglas de reabastecimiento se pueden usar para controlar la manera en que los productos se distribuyen a los almacenes al usar tránsito directo y estrategia de presión. Las reglas de reabastecimiento se pueden configurar para tiendas o grupos de tiendas. El peso definido para cada línea en una regla controlará la manera en que las cantidades de productos se distribuirán entre almacenes al usar reglas de reabastecimiento como el método de distribución en tránsito directo o estrategia de presión. Este procedimiento usa la empresa de prueba USRT.

1. Vaya a Reglas de reabastecimiento.
2. Haga clic en Nuevo.
3. En el campo Regla de reabastecimiento, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Guardar.
6. Haga clic en Agregar.
7. En la lista, marque la fila seleccionada.
    * Puede elegir Jerarquía de reabastecimiento o Canal para el tipo. El valor controla si la selección en Nombre será una jerarquía de canales o un canal específico.  Para este ejemplo, déjelo establecido como una Jerarquía de reabastecimiento.  
8. En el campo Nombre, seleccione un valor.
    * El valor del peso predeterminado se rellena con el peso definido en el almacén.  Este peso se puede usar para la Regla de reabastecimiento o puede especificar un nuevo peso en el campo Peso.  
9. En el campo Peso, escriba un número.
10. Haga clic en Agregar.
11. En la lista, marque la fila seleccionada.
12. En el campo Tipo, seleccione "Canal".
13. En el campo Nombre, especifique o seleccione un valor.
14. En el campo Peso, escriba un número.
15. Haga clic en Guardar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]