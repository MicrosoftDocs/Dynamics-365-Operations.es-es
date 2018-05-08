--- 
title: "Calcular la amortización de activos fijos en las entidades jurídicas"
description: "Este procedimiento muestra cómo establecer y ejecutar el proceso de depreciación para varias entidades jurídicas."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: es-es
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calcular la amortización de activos fijos en las entidades jurídicas

[!include [task guide banner](../../includes/task-guide-banner.md)]

La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso. Este procedimiento muestra cómo establecer y ejecutar el proceso para varias entidades jurídicas. Usa el rol de contable.  

Esta grabación usa la empresa de demostración USMF.


Subtarea de (16) pasos: Configure diarios de ejecución de depreciación entre empresas. 

1. En primer lugar, debe configurar los diarios que usará en la depreciación entre empresas en cada entidad jurídica. Vaya a Activos fijos > Configuración > Parámetros de activos fijos. 
2. Expanda la sección de propuestas de activos fijos. 
3. Cree un registro con el nombre del diario que se usará para cada capa de registro en la entidad jurídica. Si los libros no se registran en la contabilidad general, la capa de registro Ninguna se debe seleccionar con el diario asociado. Haga clic en Agregar. 
4. En el campo Capa de registro, especifique o seleccione un valor. 
5. En el campo Nombre del diario, especifique o seleccione un valor. 
6. Repita la configuración del diario en la página de parámetros de activos fijos en cada entidad jurídica. 

Subtarea: calcular depreciación.

1. Use la página Crear propuesta de depreciación para iniciar la ejecución de depreciación en entidades jurídicas. Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación. 
2. En el campo Capa de registro, especifique o seleccione un valor. 
3. El nombre del diario se tomará de forma predeterminado de los parámetros de activos fijos. Puede cambiarlo aquí para la entidad jurídica actual. 
4. Especifique una fecha en el campo Fecha final. 
5. Seleccione las entidades jurídicas que se incluirán en la ejecución de depreciación. Sólo se mostrarán en la lista las entidades jurídicas con diarios configurados para propuestas de activos fijos en la página de parámetros de activos fijos. 
6. Cuando está habilitada, la opción Registrar diarios enviará automáticamente los diarios de depreciación cuando se crean. Si no están seleccionados, los diarios se crearán, pero no se registrarán, para que pueda revisar los detalles antes de registrarlos. Seleccione Sí en el campo Registrar diarios. 
7. El filtrado de campos incluye todos los activos fijos, grupos, y libros para las entidades jurídicas seleccionadas para esta ejecución de depreciación. 
8. La opción de procesamiento por lotes se habilita de forma predeterminada. Cuando se habilita esta opción, la creación y el registro de diarios y depreciación se ejecutará en segundo plano. 
9. Haga clic en Crear diario. 
10. Debe ver los diarios de depreciación creados en las entidades jurídicas respectivas. Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.

