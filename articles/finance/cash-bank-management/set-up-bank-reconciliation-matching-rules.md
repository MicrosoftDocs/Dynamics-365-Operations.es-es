---
title: Configurar las reglas de coincidencia de conciliación bancaria
description: Este artículo explica cómo configurar reglas de coincidencia de conciliación y conjuntos de reglas de coincidencia de conciliación para ayudar con el proceso de conciliación bancaria. Las reglas de coincidencia de conciliación son un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de documento bancario durante el proceso de conciliación.
author: angelad116
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: kfend
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac5ab5e2bcb9a63bb52d5a74bd5e4b5db51ba603
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803947"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Configurar las reglas de coincidencia de conciliación bancaria

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar reglas de coincidencia de conciliación y conjuntos de reglas de coincidencia de conciliación para ayudar con el proceso de conciliación bancaria. Las reglas de coincidencia de conciliación son un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de documento bancario durante el proceso de conciliación.

Puede configurar reglas de coincidencia de conciliación y conjuntos de reglas de coincidencia de conciliación para ayudar con el proceso de conciliación bancaria. Una regla de coincidencia de conciliación es un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de transacción bancaria de Dynamics 365 Finance durante el proceso de conciliación. Use la página **Reglas que coinciden de conciliación** para configurar las reglas de coincidencia de conciliación. Puede configurar más de una regla de coincidencia y después crear un conjunto de reglas de coincidencia de conciliación bancaria en la página **Conjuntos de reglas de coincidencia de conciliación**. 

> [!NOTE] 
> Las reglas de coincidencia de conciliación se usan si concilia un extracto bancario electrónico mediante la conciliación bancaria avanzada. 

En la página **Reglas de coincidencia de conciliación**, puede seleccionar las acciones y los criterios de selección que se usarán cuando se ejecute la regla de coincidencia. En el grupo de campos **Acciones**, seleccione la acción que se llevará a cabo cuando se ejecute la regla de coincidencia durante el proceso de conciliación.  

De forma predeterminada, las reglas coincidentes coincidirán con el primer documento bancario que cumpla con los criterios de la regla coincidente. Si varios documentos bancarios cumplen los criterios de la regla, el parámetro para requerir la coincidencia manual se puede activar yendo a **Gestión de efectivo y bancos > Configuración > Parámetros de gestión de efectivo y bancos > Conciliación bancaria > Requerir cotejo manual cuando las reglas de cotejo de conciliación bancaria avanzada encuentran varios documentos que coinciden en el importe**.

> [!NOTE] 
> La opción que seleccione determina los campos que aparecen.

| Acción | Descripción   | Criterios de selección disponibles cuando se selecciona la acción     |
|--------|---------------|----------------------------------------------------------|
| **Hacer coincidir con documento bancario**       | Cree criterios para especificar cómo se concilian los documentos bancarios y las líneas del extracto bancario cuando la regla de coincidencia se ejecuta desde la página **Hoja de cálculo de conciliación bancaria**. Las líneas de transacción se seleccionan según los criterios adicionales configurados en las fichas desplegables. | <ul><li>**Paso 1: Defina la regla de conciliación** - Seleccione criterios para especificar qué extractos bancarios se deben conciliar con las transacciones bancarias de Finance.</li><li> **Paso 2 (opcional). Seleccione las líneas de extracto para las que se ejecutarán reglas de conciliación:** Aplicar un filtro con el que se ejecutará la línea de extracto.</li></ul>                                       |
| **Borrar líneas de extracto de inversión** | Cree criterios para especificar cómo las líneas de extracto de inversión se deben quitar de la página **Hoja de cálculo de conciliación bancaria** cuando se ejecute la regla de coincidencia. Esta opción se usa cuando un error del banco hace que se muestren dos líneas de extracto bancario en el extracto bancario importado y las líneas se deben conciliar. |<ul><li> **Paso 1**:**Busque líneas de extracto de inversión.** Agregue los criterios de selección para seleccionar líneas seleccionar líneas de extracto bancario de inversión. Por ejemplo, para seleccionar solo los cheques, seleccione **Código de transacción bancaria** en el campo **Campo**, seleccione el signo más (+) en el campo **Operador** y especifique **Cheques** en el campo **Valor**. </li><li>**Paso 2: Busque líneas de extracto originales**. Puede agregar criterios de selección para hacer coincidir líneas de documento bancario con las líneas del extracto bancario. </li><li>**Paso 3: Busque transacciones bancarias de Finance** - Puede agregar criterios de selección para hacer coincidir transacciones bancarias de Finance con líneas de extracto bancario.</li></ul>  |
| **Marcar transacciones nuevas**          | Cree criterios para especificar cómo se deben marcar las nuevas transacciones en la página **Hoja de cálculo de conciliación bancaria** cuando se ejecute la regla de coincidencia.                                                                                                                                                                 | <ul><li>**Paso 1: Busque líneas de extracto.** Agregue campos de selección para especificar qué líneas de extracto bancario se deben seleccionar en la página **Hoja de cálculo de conciliación bancaria**.</li><li> **Paso 2: Busque en finanzas y operaciones**: puede agregar criterios de selección para buscar líneas de documentos bancarios. Si no se encuentra ningún documento bancario, una línea de extracto se marcará como nueva transacción. </li></ul>         |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

