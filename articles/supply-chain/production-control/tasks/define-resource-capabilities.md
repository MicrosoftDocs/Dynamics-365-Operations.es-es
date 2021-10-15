---
title: Definir capacidades de recursos
description: Las capacidades del recurso describen lo que pueden realizar los recursos de operaciones.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42451da0bd465ce3a18ecf18570f3331847474c1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579121"
---
# <a name="define-resource-capabilities"></a>Definir capacidades de recursos

[!include [banner](../../includes/banner.md)]

Las capacidades del recurso describen lo que pueden realizar los recursos de operaciones. Durante la programación, los requisitos de cada trabajo y la operación se asocian con las capacidades de recursos disponibles. Esta guía de la tarea le ayudará a crear una capacidad del recurso y asignarla a un recurso. La empresa de datos de prueba utilizada para crear esta tarea es USMF.


## <a name="create-a-resource-capability"></a>Crear una capacidad de recurso
1. Vaya a Capacidades de recursos.
2. Haga clic en Nuevo.
3. En el campo Capacidad, escriba la identificación de la capacidad del recurso.
    * Para una operación concreta, se usa la identificación de capacidad para especificar que los recursos deben tener esta capacidad para realizar la operación.  
4. En el campo Descripción, escriba una descripción para la capacidad.

## <a name="assign-capability-to-a-resource"></a>Asignar capacidad a un recurso
1. Haga clic en Agregar.
2. En el campo Recurso, escriba la identificación del recurso.
    * Una capacidad del recurso se puede asignar a uno o varios recursos.  
3. En el campo Caducidad, especifique una fecha.
    * Puede usar este campo para especificar que un recurso tiene la capacidad solo durante un tiempo limitado.  
4. En el campo Prioridad, especifique un número.
    * Cuando programe trabajos y operaciones, puede especificar si los recursos se seleccionan por prioridad. Si elige esto y más de un recurso puede realizar el trabajo o la operación por la fecha solicitada, se selecciona el recurso que tiene la prioridad más baja con respecto a la capacidad necesaria.  
5. En el campo Nivel, escriba un número.
    * Cuando especifica que un trabajo o una operación requiere una capacidad en particular, también puede especificar el nivel mínimo requerido. Use el nivel de capacidad para diferenciar los recursos que pueden realizar el mismo trabajo, pero a distintas velocidades, puntos fuertes tamaños, etc.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]