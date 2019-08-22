---
title: Registrar en el diario movimientos de diario
description: Este procedimiento muestra los pasos para registrar en el diario las entradas del diario registradas.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbf7ee8063487303cd4c8d2b76a8b44bacc86193
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846400"
---
# <a name="journalize-posted-journal-entries"></a>Registrar en el diario movimientos de diario

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

