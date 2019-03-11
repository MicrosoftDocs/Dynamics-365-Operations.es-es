---
title: Cambiar convenciones de depreciación para varios activos fijos
description: Esta tarea actualiza la convención de amortizaciones de un grupo de activos fijos especificado.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7a79b2edf64f0063253d3f2a23b0020eceb87c0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "324270"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a>Cambiar convenciones de depreciación para varios activos fijos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea actualiza la convención de amortizaciones de un grupo de activos fijos especificado. Esta guía de la tarea usa la empresa de demostración USMF.

1. Vaya a Activos fijos > Tareas periódicas > Actualización masiva
2. En el campo Libro amortización, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo Colocado en inicio de servicio, inserte una fecha.
5. En el campo Colocado en fin de servicio, inserte una fecha.
    * Solo se actualizarán los activos que forman parte del libro de amortización seleccionado y que se han colocado en servicio entre estas fechas.  
6. En el campo Convención de amortizaciones actual, seleccione una opción.
    * Solo se actualizarán los activos que tienen la convención de amortizaciones actual.  
7. En el campo Convención de amortizaciones nueva, seleccione una opción.
    * Compruebe que el informe se imprima en el destino deseado.  
8. Expanda la sección Registros que incluir.
9. Haga clic en Filtro.
10. En la lista, seleccione el grupo de activos fijos.
11. En el campo Criterios, haga clic en el botón desplegable para abrir la búsqueda.
12. Seleccione el grupo de activos fijos que desee.
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. Haga clic en Aceptar
15. Haga clic en Aceptar
    *  Los resultados del proceso se muestran en el informe de actualización masiva.     

