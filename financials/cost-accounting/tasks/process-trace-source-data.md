--- 
title: Procesar datos de origen y hacer un seguimiento
description: Todo el procesamiento de datos se ejecuta por trabajos.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 9de7d5d241a65add894e0c6ae4840cd05753a419
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="process-and-trace-source-data"></a>Procesar datos de origen y hacer un seguimiento

[!include[task guide banner](../../includes/task-guide-banner.md)]

Todo el procesamiento de datos se ejecuta por trabajos. Para cada trabajo y proveedor de datos, se crea un diario para documentar que se ejecutó el proceso y que las entradas se procesaran en el trabajo actual. Use este procedimiento para configurar un origen de datos y después para realizar un seguimiento del origen de un asiento de coste específico. Este registro usa la empresa USP2 con los datos para demostración. Para completar esta tarea, asegúrese de que reproduce las siguientes guías de tareas: “Crear un libro mayor de contabilidad de costes“, “Definir unidades de control de costes" y "Gestionar un origen de datos para el libro mayor de contabilidad de costes".

1. Vaya a Contabilidad de costes > Configuración de libro mayor > Libros mayores de contabilidad de costes.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione el libro mayor de contabilidad de costes que creó anteriormente.  
3. Haga clic en Versiones reales.
4. En el panel de acciones, haga clic en Procesamiento de datos de origen.
5. Haga clic en Diarios de transferencia de entradas de contabilidad general.
6. En la lista, busque y seleccione el registro deseado.
7. Haga clic en Entradas del diario.
8. En la lista, marque la fila seleccionada.
9. Haga clic en Entradas de costes.
10. Haga clic en Entrada de origen-
11. En el panel de acciones, haga clic en Procesamiento de datos de origen.
12. Haga clic en Contabilidad general.
13. En el campo Periodo de calendario fiscal, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Período 9 de año fiscal 2017.  
14. Haga clic en Aceptar

