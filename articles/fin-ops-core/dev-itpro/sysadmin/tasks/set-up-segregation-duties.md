---
title: Configuración de segregación de controles
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcbd32131f9980a4f55e91b9d7ad48171069f72e
ms.sourcegitcommit: 316200579dd5b04ad76f276a2ed6b0f55fa8c812
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "4826403"
---
# <a name="set-up-segregation-of-duties"></a>Configuración de segregación de controles

[!include [banner](../../includes/banner.md)]

Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios. Este concepto se denomina "segregación de controles". Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y la que procese el pago al proveedor. La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades. También puede usar la segregación de controles para aplicar directivas de control internas. Complete el siguiente procedimiento para crear una regla. Es necesario ser administrador del sistema para completar el procedimiento.

1. Vaya a **Administración del sistema** > **Seguridad** > **Segregación de controles** > **Reglas de segregación de controles**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre** escriba un valor para la regla.
4. En el campo **Primer deber**, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado. Seleccione el primer deber controlado por la regla.
6. En el campo **Segundo deber**, haga clic en el botón desplegable para abrir la búsqueda. 
7. En la lista, busque y seleccione el registro deseado. Seleccione el segundo deber controlado por la regla.
10. En el campo **Gravedad**, seleccione una opción. Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.  
11. En el campo **Riesgo de seguridad**, escriba un valor. Escriba una descripción del riesgo para la seguridad.  
12. En el campo **Mitigación de seguridad**, escriba un valor. Escriba una descripción de las acciones para mitigar el riesgo de seguridad. Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.     
13. Haga clic en **Guardar**.

> [!IMPORTANT] 
> El cumplimiento de las reglas para la segregación de controles no se verifica cuando crea una regla. Puede crear una regla que cree un conflicto para los roles existentes. Las asignaciones de roles de usuario existentes también pueden estar en conflicto con la nueva regla. Debe validar el cumplimiento después de crear o modificar una regla. Para más información, consulte [Identificar y resolver conflictos de segregación de controles](identify-resolve-conflicts-segregation-duties.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]