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

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="e6d02-103">Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)</span><span class="sxs-lookup"><span data-stu-id="e6d02-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6d02-104">La validación de la cuenta del número internacional de cuenta bancaria (IBAN) incrementa la cantidad de validación que se hace al agregar un IBAN a una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="e6d02-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="e6d02-105">La estructura de IBAN se almacena en Microsoft Dynamics 365 for Finance and Operation y se carga automáticamente cuando usa por primera vez el IBAN en cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="e6d02-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="e6d02-106">El número de la cuenta bancaria forma parte de la estructura definida para un número IBAN.</span><span class="sxs-lookup"><span data-stu-id="e6d02-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="e6d02-107">Basándose en esa estructura, si el puesto y la longitud del número de cuenta en el IBAN no coinciden con el puesto que está definido en la estructura para cada país o región, recibirá mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="e6d02-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="e6d02-108">Configurar estructuras de IBAN</span><span class="sxs-lookup"><span data-stu-id="e6d02-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="e6d02-109">Vaya a **Gestión de efectivo y bancos \> Configuración \> Estructuras del IBAN**.</span><span class="sxs-lookup"><span data-stu-id="e6d02-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="e6d02-110">Observe que las estructuras de IBAN para cada país o región se han configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e6d02-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="e6d02-111">Si debe personalizar las estructuras de un país o región específico, puede editarlas.</span><span class="sxs-lookup"><span data-stu-id="e6d02-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="e6d02-112">Las definiciones de la estructura formarán parte de cada nueva versión.</span><span class="sxs-lookup"><span data-stu-id="e6d02-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="e6d02-113">Puede usar el menú **Restablecer estructuras** para cargar las últimas definiciones después de cada actualización.</span><span class="sxs-lookup"><span data-stu-id="e6d02-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="e6d02-114">Valide la estructura de IBAN de una cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="e6d02-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="e6d02-115">Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="e6d02-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="e6d02-116">Cree una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="e6d02-116">Create a bank account.</span></span>
3. <span data-ttu-id="e6d02-117">En la ficha desplegable **Información adicional**, especifique un IBAN.</span><span class="sxs-lookup"><span data-stu-id="e6d02-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="e6d02-118">Si el puesto y la longitud del número de cuenta en el IBAN no coinciden con el puesto que está definido en la estructura para cada país o región, recibirá un mensaje.</span><span class="sxs-lookup"><span data-stu-id="e6d02-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="e6d02-119">No puede continuar si no coincide la longitud del IBAN con la longitud en la estructura del IBAN.</span><span class="sxs-lookup"><span data-stu-id="e6d02-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="e6d02-120">La validación también comprueba que el número de cuenta bancaria coincida con la parte del IBAN que representa el número de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="e6d02-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="e6d02-121">Si no coincide con el número de cuenta bancaria, recibirá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="e6d02-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="e6d02-122">El mensaje es solo una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e6d02-122">This message is only a warning.</span></span> <span data-ttu-id="e6d02-123">Puede continuar incluso si no coincide el número de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="e6d02-123">You can continue even if the bank account number doesn't match.</span></span>

