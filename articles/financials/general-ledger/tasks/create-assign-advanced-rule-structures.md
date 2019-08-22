---
title: Crear y asignar estructuras de reglas avanzadas
description: En este tema se explica cómo crear y asignar una estructura de reglas avanzada a una estructura contable.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cff07c13553ea140f537160da7f93820d5e3f77a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834910"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Crear y asignar estructuras de reglas avanzadas

[!include [task guide banner](../../includes/task-guide-banner.md)]

En este tema se explica cómo crear y asignar una estructura de reglas avanzada a una estructura contable. Esta guía usa la empresa de demostración de USMF.

## <a name="create-an-advanced-rule-structure"></a>Crear una estructura de reglas avanzada
1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan de cuentas > Estructuras > Estructuras de reglas avanzada**.
2. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.
3. En el campo de **Estructura de reglas avanzada**, escriba un nombre para describir la estructura de reglas.
4. Seleccione **Aceptar**.
5. Seleccione **Agregar segmento**.
6. En la lista de segmentos, seleccione una dimensión financiera. Por ejemplo, **Almacén**.  
7. Seleccione **Agregar segmento**.
8. Seleccione **Activar**.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Aplicar una estructura de reglas avanzada a una estructura contable
1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan de cuentas > Estructuras > Configurar estructuras contables**.
2. En la lista, busque y seleccione la estructura contable a la que desea aplicar la regla avanzada.
3. Seleccione **Editar**. También puede seleccionar **Reglas avanzadas** y se le pedirá que ponga la estructura contable en **modo de borrador**.  
4. Seleccione **Reglas avanzadas**.
5. Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.
6. En el campo **Regla avanzada**, escriba un valor.
7. En el campo **Nombre**, escriba un valor.
8. Seleccione **Crear**.
9. Seleccione **Agregar nuevos criterios**.
10. En el campo **Lugar**, seleccione la cuenta principal o una dimensión financiera.
11. En el campo **Operador**, seleccione una opción, como **está entre** o **incluye**.
12. En el campo **Valor**, escriba un valor.
13. En el campo **hasta**, escriba un valor.
14. Seleccione **Agregar** para abrir el cuadro desplegable.
15. En la lista, busque la estructura de regla avanzada que desea usar cuando se cumplen los criterios especificados.
16. Seleccione **Agregar**.
17. Cierre la página.
18. Seleccione **Activar**.

