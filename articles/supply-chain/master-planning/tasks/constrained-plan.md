---
title: Generar un plan con restricciones
description: Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d4af946a8dd4e5311bcb90386c88d5e7f205c4eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999865"
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