---
title: Cambiar convenciones de depreciación para varios activos fijos
description: Esta tarea actualiza la convención de amortizaciones de un grupo de activos fijos especificado.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a71b24b0c2ea072aeff8c994cfdac10bc57b64c6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823989"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a>Cambiar convenciones de depreciación para varios activos fijos

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]