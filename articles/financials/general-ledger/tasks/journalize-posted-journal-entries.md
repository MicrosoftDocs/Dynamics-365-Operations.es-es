--- 
title: Registrar en el diario movimientos de diario
description: Este procedimiento muestra los pasos para registrar en el diario las entradas del diario registradas.
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="journalize-posted-journal-entries"></a>Registrar en el diario movimientos de diario

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra los pasos para registrar en el diario las entradas del diario registradas. Este procedimiento usa la empresa de datos de demostración USMF.

1. Validar la configuración para registrar en el diario bajo Contabilidad general > Configuración de contabilidad > Parámetros de contabilidad general.
2. El campo Diario contable ampliado se puede establecer en Sí o No. Si Sí, la salida de informes es diferente.
3. Seleccione si el período puede cerrarse si el proceso de registro en el diario no se ha ejecutado.
    * Si esta opción se establece en Sí, no puede cerrarse el período hasta que el proceso de registro en el diario se haya completado para ese período.  
4. Cierre la página.
5. Vaya a Contabilidad general > Tareas periódicas > Creación de diarios.
6. Haga clic en Filtro.
7. Resalte la fila con los criterios de filtro que desee definir.
8. En el campo Criterios, especifique o seleccione los criterios de filtro.
9. Haga clic en Aceptar para cerrar la página de filtro.
10. Haga clic en Aceptar para iniciar el proceso de registro en el diario.
    * Se generará un informe después de que se complete el proceso.  


