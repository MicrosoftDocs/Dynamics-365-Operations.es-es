---
title: "Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)"
description: "En este tema se explica cómo gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)"
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: es-es
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)

[!include [banner](../includes/banner.md)]

La validación de la cuenta del número internacional de cuenta bancaria (IBAN) incrementa la cantidad de validación que se hace al agregar un IBAN a una cuenta bancaria.

La estructura de IBAN se almacena en Microsoft Dynamics 365 for Finance and Operation y se carga automáticamente cuando usa por primera vez el IBAN en cuentas bancarias. El número de la cuenta bancaria forma parte de la estructura definida para un número IBAN. Basándose en esa estructura, si el puesto y la longitud del número de cuenta en el IBAN no coinciden con el puesto que está definido en la estructura para cada país o región, recibirá mensajes de advertencia.

## <a name="set-up-iban-structures"></a>Configurar estructuras de IBAN

1. Vaya a **Gestión de efectivo y bancos \> Configuración \> Estructuras del IBAN**.
2. Observe que las estructuras de IBAN para cada país o región se han configurado automáticamente.
3. Si debe personalizar las estructuras de un país o región específico, puede editarlas.
4. Las definiciones de la estructura formarán parte de cada nueva versión. Puede usar el menú **Restablecer estructuras** para cargar las últimas definiciones después de cada actualización.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valide la estructura de IBAN de una cuenta bancaria

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Cree una cuenta bancaria.
3. En la ficha desplegable **Información adicional**, especifique un IBAN.

    Si el puesto y la longitud del número de cuenta en el IBAN no coinciden con el puesto que está definido en la estructura para cada país o región, recibirá un mensaje. No puede continuar si no coincide la longitud del IBAN con la longitud en la estructura del IBAN.

    La validación también comprueba que el número de cuenta bancaria coincida con la parte del IBAN que representa el número de cuenta bancaria. Si no coincide con el número de cuenta bancaria, recibirá un mensaje de advertencia. El mensaje es solo una advertencia. Puede continuar incluso si no coincide el número de cuenta bancaria.

