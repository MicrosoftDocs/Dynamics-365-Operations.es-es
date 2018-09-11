--- 
title: Crear y asignar estructuras de reglas avanzadas
description: "Esta guía de tareas describe los pasos de la creación y asignación de una estructura de regla avanzada a una estructura contable."
author: aprilolson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ebad4ec9ec6242978a26007a64416ae1b2af5c28
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-assign-advanced-rule-structures"></a>Crear y asignar estructuras de reglas avanzadas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tareas describe los pasos de la creación y asignación de una estructura de regla avanzada a una estructura contable. Esta guía usa la empresa de demostración de USMF.


## <a name="create-an-advanced-rule-structure"></a>Crear una estructura de reglas avanzada
1. Vaya a Contabilidad general > Plan contable > Estructuras > Estructuras de regla avanzadas.
2. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
3. En el campo de Estructura de reglas avanzada, escriba un nombre para describir la estructura de la regla.
4. En el campo Descripción, escriba un valor para describir la estructura.
5. Haga clic en Aceptar
6. Haga clic en Agregar segmento.
7. En la lista de segmentos, seleccione una dimensión financiera.
    * Por ejemplo, Almacén.  
8. Haga clic en Agregar segmento.
9. En la lista, haga clic en el vínculo de la estructura de regla avanzada para verla.
10. Haga clic en Activar.
11. Haga clic en Activar.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Aplicar una estructura de reglas avanzada a una estructura contable
1. Cierre el formulario.
2. Cierre la página.
3. Vaya a Contabilidad general > Plan contable > Estructuras > Configurar estructuras contables.
4. En la lista, busque y seleccione la estructura contable a la que desea aplicar la regla avanzada.
5. Haga clic en el nombre de la estructura contable para abrirla.
6. Haga clic en Editar.
    * También puede hacer clic en Reglas avanzadas y se le pedirá que ponga la estructura contable en el modo de borrador.  
7. Haga clic en Reglas avanzadas.
8. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
9. En el campo Regla avanzada, escriba un valor.
10. En el campo Nombre, escriba un valor.
11. Haga clic en Crear.
12. Haga clic en Agregar nuevos criterios.
13. En el campo Lugar, seleccione la cuenta principal o una dimensión financiera.
14. En el campo Operador, seleccione una opción, como está entre e incluye.
15. En el campo Valor, escriba un valor.
16. En el campo hasta, escriba un valor.
17. Haga clic en Agregar para abrir el cuadro desplegable.
18. En la lista, busque la estructura de regla avanzada que desea usar cuando se cumplen los criterios especificados.
19. Haga clic en Agregar.
20. Cierre la página.
21. Haga clic en Activar.
22. Haga clic en Activar.


