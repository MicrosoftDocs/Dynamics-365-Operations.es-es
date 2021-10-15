---
title: Generar un plan con restricciones
description: Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.
author: ChristianRytt
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fea315d41d01cb578d7d60c9eb7006e4b6c3362
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578353"
---
# <a name="generate-a-constrained-plan"></a>Generar un plan con restricciones

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad. El plan garantiza que la fabricación no comience antes de que los materiales estén disponibles y que no se reserven recursos en exceso. 

La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento se va a utilizar para el planificador de producción.


## <a name="set-up-a-constrained-plan"></a>Configurar un plan restringido
1. En la página principal, seleccione el espacio trabajo **Planificación maestra**.
2. Seleccione **Planes maestros** en la lista de vínculos en el extremo derecho del área de trabajo.
3. En la lista, busque y seleccione el registro deseado. Ejemplo: **StaticPlan**  
4. Seleccione **Sí** en el campo **Capacidad limitada**.
5. En el campo **Límite de tiempo de capacidad finita**, indique `30`.
6. Expanda la sección **Límites de tiempo en días**.
7. Seleccione **Sí** en el campo **Capacidad**.
8. En el campo **Límite de tiempo de programación de capacidad (días)**, escriba un número. Ejemplo: `60`  
9. Seleccione **Sí** en el campo **Retrasos calculados**.
10. En el campo **Calcular límite de tiempo de retrasos (días)**, escriba un número. Ejemplo: `60` 
11. Expanda la sección **Retrasos calculados**.
12. Seleccione **Sí** en todos los campos **Agregar el retraso calculado a la fecha de requisito**.
13. Cierre la página.

## <a name="create-a-constrained-plan"></a>Crear un plan restringido
1. Seleccione **Ejecutar**.
2. En el campo **Plan maestro**, especifique o seleccione el plan para el que ha configurado restricciones.  
3. Seleccione **Aceptar**.
4. Seleccione **Pedidos planificados**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]