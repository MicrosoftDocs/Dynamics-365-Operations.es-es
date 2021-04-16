---
title: Crear un plan de empresas vinculadas
description: Este procedimiento muestra cómo crear un plan de empresas vinculadas.
author: ShylaThompson
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0fb787955a67776b24b626eb23b7c1a9df87a0c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841704"
---
# <a name="create-an-intercompany-plan"></a>Crear un plan de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un plan de empresas vinculadas. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Configurar un grupo de planificación de empresas vinculadas 
1. En el **Panel de exploración**, vaya a **Módulos > Planificación maestra > Configuración > Grupos de planificación empresas vinculadas**. 
2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro en el campo Nombre con un valor de “10”.
3. En la lista, marque la fila seleccionada.
4. Haga clic **Eliminar**. Este paso es necesario para reducir la ejecución empresas vinculadas de planificación.   La planificación de empresas vinculadas ejecutará una planificación maestra en un grupo de planificación, a partir de la secuencia de programación más baja.  
5. Haga clic en **Sí**.
6. Cierre la página.

## <a name="create-an-intercompany-plan"></a>Crear un plan de empresas vinculadas
1. En el **Panel de exploración**, vaya a **Módulos > Planificación maestra > Espacios de trabajo > Planificación maestra**.
2. Haga clic en **Planificación maestra de empresas vinculadas**.  
3. En el campo **Grupo de planificación de empresas vinculadas**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada. Seleccione el grupo 10 de planificación de empresas vinculadas.  
5. En el **Número de iteraciones de planificación para empresas vinculadas**, especifique "2". El grupo 10 de planificación de empresas vinculadas tiene dos miembros. Para extender los retrasos de la empresa de origen (USMF) a la empresa cliente (DEMF), deberá ejecutar las empresas vinculadas en ambas empresas dos veces. La primera iteración extenderá la demanda e identificará los retrasos en la empresa de origen (USMF). La segunda iteración extenderá los retrasos de USMF a DEMF.  
6. En el campo **Primera iteración**, seleccione "Regeneración".
7. En el campo **Iteraciones subsiguientes**, seleccione "Regeneración".
8. En el campo **Número de subprocesos**, especifique un número. Esto representa el número de subprocesos paralelos utilizados para la planificación.  
9. Haga clic en **Aceptar**.

## <a name="view-the-result-of-the-plan"></a>Ver el resultado del plan
1. En el campo **Plan**, haga clic en el botón desplegable para abrir la búsqueda.
2. En la lista, haga clic en el vínculo de la fila seleccionada. Haga clic en el vínculo para StaticPlan. Debe estar en la empresa USMF.  
3. Haga clic en **Pedidos planificados**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]