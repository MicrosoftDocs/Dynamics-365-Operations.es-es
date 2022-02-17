---
title: Modificar las relaciones jerárquicas para un puesto
description: Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d7996733575c2d3a23971d08eb101962c1f6bbd9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066634"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modificar las relaciones jerárquicas para un puesto


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado. La relación jerárquica se puede usar para enrutar documentos mediante el flujo de trabajo. El procedimiento también muestra cómo asignar el empleado a jerarquías adicionales. Por ejemplo, un empleado puede formar parte de un equipo de proyecto con una relación jerárquica informal con un supervisor de proyecto. Las relaciones jerárquicas adicionales se pueden definir en el puesto para adaptar distintos escenarios de proyecto o matriz. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Recursos humanos** \> **Puestos** \> **Puestos**.
2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **000091** para el campo **Puesto**.
3. En la lista, seleccione el vínculo de la fila seleccionada.
4. Expanda la sección **Notifica al puesto**.
5. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.
6. En el campo **Informa a**, especifique o seleccione un valor.
7. Seleccione **Crear**.
8. Expanda la sección **Relaciones**.
9. Seleccione **Agregar**.
10. Active la casilla de la izquierda de la cuadrícula.
11. En el campo **Nombre de jerarquía**, especifique o seleccione un valor (por ejemplo, **Proyecto**).
12. En el campo **Notifica al puesto**, especifique o seleccione un valor (por ejemplo **000437**).
13. Seleccione **Guardar**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
