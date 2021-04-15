---
title: Modificar las relaciones jerárquicas para un puesto
description: Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4f54a162305a81b65f0657cd572df75a9dcbd38
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794454"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modificar las relaciones jerárquicas para un puesto

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado. La relación jerárquica se puede usar para enrutar documentos mediante el flujo de trabajo. El procedimiento también muestra cómo asignar el empleado a jerarquías adicionales. Por ejemplo, un empleado puede formar parte de un equipo de proyecto con una relación jerárquica informal con un supervisor de proyecto. Las relaciones jerárquicas adicionales se pueden definir en el puesto para adaptar distintos escenarios de proyecto o matriz. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a Recursos humanos > Puestos > Puestos.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre el campo Puesto según un valor de "000091".
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Expanda la sección Notifica al puesto.
5. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
6. En el campo Informa a, especifique o seleccione un valor.
7. Haga clic en Crear.
8. Expanda la sección Relaciones.
9. Haga clic en Agregar.
10. Active la casilla de la izquierda de la cuadrícula.
11. En el campo Nombre de jerarquía, especifique o seleccione un valor.
    * Ejemplo: Proyecto  
12. En el campo Notifica al puesto, especifique o seleccione un valor.  Ejemplo: 000437
13. Haga clic en Guardar.



[!INCLUDE[footer-include](../includes/footer-banner.md)]