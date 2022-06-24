---
title: Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)
description: En este artículo se explica cómo gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)
author: twheeloc
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 3d825e8699fbe10e080cd85f15d3d86f8c780f15
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880910"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)

[!include [banner](../includes/banner.md)]

La validación del número internacional de cuenta bancaria (IBAN) incrementa la cantidad de validación que se hace al agregar un IBAN a una cuenta bancaria.

La información sobre la estructura del IBAN se almacena en Microsoft Dynamics 365 Finance y se carga automáticamente cuando usa por primera vez el IBAN en cuentas bancarias. Contiene la longitud de IBAN, las posiciones iniciales del número de cuenta bancaria y el número de ruta, y la longitud del número de cuenta bancaria y el número de ruta.

## <a name="set-up-iban-structures"></a>Configurar estructuras de IBAN

1. Vaya a **Gestión de efectivo y bancos \> Configuración \> Estructuras del IBAN**.
2. Observe que las estructuras de IBAN para cada país o región se han configurado automáticamente.
3. Seleccione el botón **Editar** si la estructura debe ser actualizada para un país o región específicos.
4. Las definiciones de la estructura formarán parte de cada nueva versión. Puede usar el menú **Restablecer estructuras** para cargar las últimas definiciones después de cada actualización.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Valide la estructura de IBAN de una cuenta bancaria

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Cree una cuenta bancaria.
3. En la ficha desplegable **Información adicional**, especifique un IBAN.

    Si no coincide la longitud de IBAN con la longitud que se define para cada país o región, recibirá un mensaje de advertencia. No puede continuar si no coincide la longitud del IBAN con la longitud especificada en la estructura del IBAN.

    La validación también comprueba que el número de cuenta bancaria coincida con la parte del IBAN que representa el número de cuenta bancaria. Si no coincide el número de cuenta bancaria, recibirá un mensaje de advertencia. El mensaje es solo una advertencia. Puede continuar incluso si no coincide el número de cuenta bancaria.

    La validación también comprueba que el número de ruta bancaria coincida con la parte del IBAN que representa el número de ruta bancaria. El número de ruta incluye un número de banco y a menudo una sucursal bancaria adicional. Si no coincide el número de ruta bancaria, recibirá un mensaje de advertencia. El mensaje es solo una advertencia. Puede continuar incluso si no coincide el número de ruta bancaria.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
