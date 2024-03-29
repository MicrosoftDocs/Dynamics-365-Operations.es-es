---
title: Grupos de cuentas de consolidación y cuentas de consolidación adicionales
description: Este artículo proporciona información sobre grupos de cuentas de consolidación y cuentas de consolidación adicionales y explica cómo se utilizan.
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9e66190fe0bab24545bf19eba59facded63ee197
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882031"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupos de cuentas de consolidación y cuentas de consolidación adicionales

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre grupos de cuentas de consolidación y cuentas de consolidación adicionales y explica cómo se utilizan.

## <a name="consolidation-account-groups"></a>Grupos de cuentas de consolidación

Los grupos de cuentas de consolidación permiten crear grupos de las cuentas que desee usar para consolidar los datos. Normalmente, un grupo de cuentas de consolidación representa un plan de cuentas exigido por el gobierno. Un grupo de cuentas de consolidación también puede asignar cuentas a un grupo definido por la sede de la empresa. Los grupos de cuentas de consolidación están en la zona **Configuración** del módulo **Consolidaciones**. Al agregar un nuevo grupo, especifique un identificador único para el grupo de cuentas y un nombre.

## <a name="additional-consolidation-accounts"></a>Cuentas de consolidación adicional
Las cuentas de consolidación adicionales permiten asignar una cuenta de un plan contable existente a un grupo de cuentas de consolidación. Después, puede especificar un valor y un nombre de la cuenta de consolidación. 

Los grupos de cuentas de consolidación adicionales están en la zona **Configuración** del módulo **Consolidaciones**. Al crear una nueva cuenta de consolidación, debe especificar la siguiente información:

-   **Cuenta principal**: este campo es una búsqueda que muestra todas las cuentas principales que se basan en el plan contable que seleccionó en la página. Al seleccionar una cuenta, el nombre se especifica en el campo **Nombre de la cuenta principal**.
-   **Grupo de cuentas de consolidación**: utilice este campo para especificar un grupo al que asignar la cuenta. Si consolida de dos formas diferentes, debe agregar la misma cuenta a los cuatro grupos de cuentas de consolidación.
-   **Cuenta de consolidación**: especifique el valor de la cuenta de consolidación. Este valor no tiene que ser una cuenta de un plan contable. Puede ser cualquier valor que necesite.
-   **Nombre de cuenta de consolidación**: permite especificar el nombre de la cuenta que desea que aparezca en consultas e informes.
-   **Nivel del SAT**: este campo se usa para informar sobre extractos de cuenta a las autoridades fiscales mexicanas. 

Cuando haya terminado de crear los grupos de cuentas de la consolidación y las cuentas de consolidación adicionales, puede seleccionar el grupo en el proceso en línea de consolidación.


Para obtener más información, consulte [Crear grupos de consolidación y cuentas de consolidación adicionales](../general-ledger/tasks/create-consolidation-groups.md) 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
