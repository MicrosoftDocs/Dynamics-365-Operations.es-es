---
title: Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)
description: En este tema se explica cómo gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: e44b855165752baeb42d3c9952c35982ef24b0f5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815869"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)

[!include [banner](../includes/banner.md)]

La validación del número internacional de cuenta bancaria (IBAN) incrementa la cantidad de validación que se hace al agregar un IBAN a una cuenta bancaria.

La información acerca de la estructura de IBAN se almacena en Microsoft Dynamics 365 Finance. Esta información se carga automáticamente al usar por primera vez el IBAN en cuentas bancarias. Contiene la longitud de IBAN, las posiciones iniciales del número de cuenta bancaria y el número de ruta, y la longitud del número de cuenta bancaria y el número de ruta.

## <a name="set-up-iban-structures"></a>Configurar estructuras de IBAN

1. Vaya a **Gestión de efectivo y bancos \> Configuración \> Estructuras del IBAN**.
2. Observe que las estructuras de IBAN para cada país o región se han configurado automáticamente.
3. Si quiere personalizar las estructuras de un país o región específico, puede editarlas.
4. Las definiciones de la estructura formarán parte de cada nueva versión. Puede usar el menú **Restablecer estructuras** para cargar las últimas definiciones después de cada actualización.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valide la estructura de IBAN de una cuenta bancaria

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Cree una cuenta bancaria.
3. En la ficha desplegable **Información adicional**, especifique un IBAN.

    Si no coincide la longitud de IBAN con la longitud que se define para cada país o región, recibirá un mensaje de advertencia. No puede continuar si no coincide la longitud del IBAN con la longitud especificada en la estructura del IBAN.

    La validación también comprueba que el número de cuenta bancaria coincida con la parte del IBAN que representa el número de cuenta bancaria. Si no coincide el número de cuenta bancaria, recibirá un mensaje de advertencia. El mensaje es solo una advertencia. Puede continuar incluso si no coincide el número de cuenta bancaria.

    La validación también comprueba que el número de ruta bancaria coincida con la parte del IBAN que representa el número de ruta bancaria. El número de ruta incluye un número de banco y a menudo una sucursal bancaria adicional. Si no coincide el número de ruta bancaria, recibirá un mensaje de advertencia. El mensaje es solo una advertencia. Puede continuar incluso si no coincide el número de ruta bancaria.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]