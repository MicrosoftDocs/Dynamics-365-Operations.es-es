---
title: Calcular la amortización de activos fijos en las entidades jurídicas
description: La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2575354af322827972ffa650e9c732170c5a6eb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "317002"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calcular la amortización de activos fijos en las entidades jurídicas

[!include [task guide banner](../../includes/task-guide-banner.md)]

La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso. Este procedimiento muestra cómo establecer y ejecutar el proceso para varias entidades jurídicas. Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Configure diarios de ejecución de depreciación entre empresas
1. Vaya a Activos fijos > Configuración > Parámetros de activos fijos.
2. Expanda la sección de propuestas de activos fijos.
3. Haga clic en Agregar.
4. En el campo Capa de registro, especifique o seleccione un valor.
5. En el campo Nombre del diario, especifique o seleccione un valor.
    * Repita la configuración del diario en la página de parámetros de activos fijos en cada entidad jurídica.  

## <a name="depreciation-run"></a>Ejecución de depreciación
1. Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación.
2. En el campo Capa de registro, especifique o seleccione un valor.
    * El nombre del diario se tomará de forma predeterminado de los parámetros de activos fijos. Puede cambiarlo aquí para la entidad jurídica actual.  
3. Especifique una fecha en el campo Fecha final.
    * Seleccione las entidades jurídicas que se incluirán en la ejecución de depreciación.  
    * Sólo se mostrarán en la lista las entidades jurídicas con diarios configurados para propuestas de activos fijos en la página de parámetros de activos fijos.  
4. Seleccione Sí en el campo Registrar diarios.
    * El filtrado de campos incluye todos los activos fijos, grupos, y libros para las entidades jurídicas seleccionadas para esta ejecución de depreciación.  
    * La opción de procesamiento por lotes se habilita de forma predeterminada. Cuando se habilita esta opción, la creación y el registro de diarios y depreciación se ejecutará en segundo plano.  
5. Haga clic en Crear diario.
6. Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.

