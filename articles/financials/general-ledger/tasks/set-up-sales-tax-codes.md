---
title: Configurar códigos de impuestos
description: Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f29442c2ef2e3d0008a74298fda218e4cbd93f8e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571592"
---
# <a name="set-up-sales-tax-codes"></a>Configurar códigos de impuestos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.

Esta tarea usa la empresa de demostración USMF.



1. Vaya a Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos.
2. Haga clic en Nuevo.
3. En el campo de código de impuestos, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Seleccione un período de liquidación para especificar qué autoridad fiscal y en qué intervalos tienen que notificarse y pagarse estos impuestos.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Seleccione un grupo de registro para especificar las cuentas principales para registrar los impuestos en contabilidad general.
8. En la lista, busque y seleccione el registro deseado.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. Expanda la ficha desplegable Cálculo.
    * La ficha desplegable Cálculo tiene varios campos que controlan cómo se calcularán los importes de impuestos.  
11. En el panel de acciones, haga clic en Código de impuestos.
12. Haga clic en Valores.
13. En la lista, marque la fila seleccionada.
14. Especifique el valor de este código de impuestos.
    * En la ficha desplegable Cálculo, en el campo Origen, si está seleccionado el importe por unidad, el valor se multiplicará por la cantidad de la transacción para calcular el importe de impuestos.  Si el código de impuesto no es un impuesto basado en la unidad, el valor es un porcentaje que se aplica en el origen de este código de impuesto para calcular el importe de impuestos.     
15. Haga clic en Guardar.
16. Cierre la página.
17. Haga clic en Guardar.

