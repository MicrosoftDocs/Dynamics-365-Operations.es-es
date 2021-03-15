---
title: Creación de un movimiento de diario mediante una plantilla
description: Los asientos del diario registrados se pueden guardar como plantillas de asientos y aplicarse en un nuevo asiento del diario.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 234cfb98cc07f6c8c81821584e4e1d509d033477
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988583"
---
# <a name="create-a-journal-entry-using-template"></a>Creación de un movimiento de diario mediante una plantilla

[!include [banner](../../includes/banner.md)]

Los asientos del diario registrados se pueden guardar como plantillas de asientos y aplicarse en un nuevo asiento del diario. Este procedimiento usa la empresa de demostración USMF.

1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Entradas del diario > Diarios generales**.
2. En el **panel de acciones**, haga clic en **Nuevo**. Este procedimiento comienza por crear y registrar un asiento de diario, pero cualquier asiento del diario previamente registrado se puede guardar como plantilla.  
3. En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en **Líneas**.
7. En el campo **Tipo de cuenta**, escriba un valor.
8. En el campo **Descripción**, escriba un valor.
9. En el campo **Débito**, escriba un valor.
10. Haga clic en **Nuevo**.
11. En el campo **Tipo de cuenta**, escriba un valor.
12. En el campo **Descripción**, escriba un valor.
13. En el campo **Débito**, escriba un valor.
14. Haga clic en **Nuevo**.
14. En el campo **Cuenta**, especifique los valores deseados.
15. En el campo **Descripción**, escriba un valor.
16. En el campo **Crédito**, escriba un valor para saldar el asiento.
17. En el **panel de acciones**, haga clic en **Publicar**.
18. Haga clic en **Funciones**.
19. Haga clic en la plantilla **Guardar asiento**.
20. Este procedimiento supone un tipo de **Plantilla de porcentaje**. Haga clic en Aceptar.
    - Porcentaje: los importes del asiento se convierten en factores de porcentaje, lo que permite aplicar cualquier importe cuando se selecciona la plantilla de asientos.
    - Importe: los importes reales se almacenarán y se aplicarán.  
21. Haga clic en **Diarios generales**.
22. Haga clic en **Nuevo**.
23. En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.
24. En la lista, haga clic en el vínculo de la fila seleccionada.
25. Haga clic en **Líneas**.
26. Haga clic en **Funciones**.
27. Haga clic en **Seleccionar plantilla de asientos**.
28. Busque la plantilla que ha creado anteriormente. Haga clic en **Aceptar**. Es posible que tenga que hacer clic en **Paso anterior** y seleccionar la plantilla correcta si existen otras plantillas.  
29. En el campo **Importe**, especifique el importe que se aplicará al asiento. El campo **Importe** solo se muestra si la plantilla de asientos es del tipo Porcentaje.  
30. Haga clic en **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]