---
title: "Configurar las reglas de coincidencia de conciliación bancaria"
description: "Este artículo explica cómo configurar reglas de coincidencia de conciliación y conjuntos de reglas de coincidencia de conciliación para ayudar con el proceso de conciliación bancaria. Las reglas de coincidencia de conciliación son un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de documento bancario durante el proceso de conciliación."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: e4c07a6afb90535c57f372d5b850919b5b34aaa4
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Configurar las reglas de coincidencia de conciliación bancaria

Este artículo explica cómo configurar reglas de coincidencia de conciliación y conjuntos de reglas de coincidencia de conciliación para ayudar con el proceso de conciliación bancaria. Las reglas de coincidencia de conciliación son un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de documento bancario durante el proceso de conciliación.

Puede configurar reglas de coincidencia de conciliación y conjuntos de reglas de coincidencia de conciliación para ayudar con el proceso de conciliación bancaria. Regla coincidente de conciliación es un conjunto de criterios que se usa para filtrar las líneas de extracto bancario y Microsoft Dynamics 365 para las líneas de las transacciones bancarias de las operaciones durante el proceso de conciliación. Use la página **Reglas que coinciden de conciliación** para configurar las reglas de coincidencia de conciliación. Puede configurar más de una regla de coincidencia y después crear un conjunto de reglas de coincidencia de conciliación bancaria en la página **Conjuntos de reglas de coincidencia de conciliación**. 

> [!NOTE] 
> Se utilizan las reglas coincidentes de conciliación bancaria si se concilia un extracto bancario electrónico mediante la conciliación bancaria anticipado. 

En la página **Reglas de coincidencia de conciliación**, puede seleccionar las acciones y los criterios de selección que se usarán cuando se ejecute la regla de coincidencia. ** En las acciones ** el grupo de campos, seleccione la acción que se realizará si la regla coincidente se ejecuta durante el proceso de conciliación.  

> [!NOTE] 
> La opción que seleccione determina los campos que aparecen.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Acción**                         |                                                                                                                                                                                                                                                                                                               | **Criterios de selección disponibles cuando se selecciona la acción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Hacer coincidir con documento bancario **       | Cree criterios para especificar cómo se concilian los documentos bancarios y las líneas del extracto bancario cuando la regla de coincidencia se ejecuta desde la página **Hoja de cálculo de conciliación bancaria**. Las líneas de transacción se seleccionan según los criterios adicionales configurados en las fichas desplegables.                                | ** Paso 1: Defina la regla coincidente ** – los criterias para especificar qué extractos bancarios deben coincidir con Dynamics 365 para las transacciones bancarias de las operaciones. **Paso 2 (opcional). Seleccione las líneas de extracto para las que se ejecutarán reglas de conciliación: **Aplicar un filtro con el que se ejecutará la línea de extracto.                                                                                                                                                                                                                                                                                                               |
| **Borrar líneas de extracto de inversión ** | Cree criterios para especificar cómo las líneas de extracto de inversión se deben quitar de la página **Hoja de cálculo de conciliación bancaria** cuando se ejecute la regla de coincidencia. Esta opción se usa cuando un error del banco hace que se muestren dos líneas de extracto bancario en el extracto bancario importado y las líneas se deben conciliar. | **Paso 1**:** Busque líneas de extracto de inversión. **Agregue los criterios de selección para seleccionar líneas seleccionar líneas de extracto bancario de inversión. Por ejemplo, para seleccionar solo los cheques, seleccione **Código de transacción bancaria** en el campo Campo, seleccione el signo más (+) en el campo **Operador** y especifique **Cheques** en el campo Valor. **Paso 2: Busque líneas de extracto originales**. Puede agregar criterios de selección para hacer coincidir líneas de documento bancario con las líneas del extracto bancario. ** Paso 3: La Dynamics 365 de la búsqueda para las transacciones bancarias de las operaciones ** – puede agregar criterios de selección a las 365 dinámicas de coincidencia para las transacciones bancarias de las operaciones a las líneas de extracto bancario. |
| **Mark new transactions**          | Cree criterios para especificar cómo se deben marcar las nuevas transacciones en la página **Hoja de cálculo de conciliación bancaria** cuando se ejecute la regla de coincidencia.                                                                                                                                                                 | **Paso 1: Busque líneas de extracto. **Agregue campos de selección para especificar qué líneas de extracto bancario se deben seleccionar en la página **Hoja de cálculo de conciliación bancaria**. ** Paso 2: La Dynamics 365 de la búsqueda para las transacciones bancarias de las operaciones ** – puede agregar criterios de selección a las líneas de documento bancario de la búsqueda. Si no se encuentra ningún documento bancario, una línea de extracto se marcará como nueva transacción.                                                                                                                                                                                                                                             |

 





