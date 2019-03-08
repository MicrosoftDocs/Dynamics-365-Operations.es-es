---
title: Gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)
description: En este tema se explica cómo gestionar la validación de la cuenta del número internacional de cuenta bancaria (IBAN)
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 19e0528b95952de8e5503c361efcfeca4c529caf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "360012"
---
# <a name="manage-international-bank-account-number-iban-validation"></a><span data-ttu-id="9c6a0-103">Gestionar la validación del número internacional de cuenta bancaria (IBAN)</span><span class="sxs-lookup"><span data-stu-id="9c6a0-103">Manage International Bank Account Number (IBAN) validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c6a0-104">La validación del número internacional de cuenta bancaria (IBAN) incrementa la cantidad de validación que se hace al agregar un IBAN a una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="9c6a0-105">La información acerca de la estructura de IBAN se almacena en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="9c6a0-106">Esta información se carga automáticamente al usar por primera vez el IBAN en cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="9c6a0-107">Contiene la longitud de IBAN, las posiciones iniciales del número de cuenta bancaria y el número de ruta, y la longitud del número de cuenta bancaria y el número de ruta.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="9c6a0-108">Configurar estructuras de IBAN</span><span class="sxs-lookup"><span data-stu-id="9c6a0-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="9c6a0-109">Vaya a **Gestión de efectivo y bancos \> Configuración \> Estructuras del IBAN**.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="9c6a0-110">Observe que las estructuras de IBAN para cada país o región se han configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="9c6a0-111">Si quiere personalizar las estructuras de un país o región específico, puede editarlas.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="9c6a0-112">Las definiciones de la estructura formarán parte de cada nueva versión.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="9c6a0-113">Puede usar el menú **Restablecer estructuras** para cargar las últimas definiciones después de cada actualización.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="9c6a0-114">Valide la estructura de IBAN de una cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="9c6a0-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="9c6a0-115">Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="9c6a0-116">Cree una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-116">Create a bank account.</span></span>
3. <span data-ttu-id="9c6a0-117">En la ficha desplegable **Información adicional**, especifique un IBAN.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="9c6a0-118">Si no coincide la longitud de IBAN con la longitud que se define para cada país o región, recibirá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="9c6a0-119">No puede continuar si no coincide la longitud del IBAN con la longitud especificada en la estructura del IBAN.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="9c6a0-120">La validación también comprueba que el número de cuenta bancaria coincida con la parte del IBAN que representa el número de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="9c6a0-121">Si no coincide el número de cuenta bancaria, recibirá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="9c6a0-122">El mensaje es solo una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-122">This message is only a warning.</span></span> <span data-ttu-id="9c6a0-123">Puede continuar incluso si no coincide el número de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="9c6a0-124">La validación también comprueba que el número de ruta bancaria coincida con la parte del IBAN que representa el número de ruta bancaria.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="9c6a0-125">El número de ruta incluye un número de banco y a menudo una sucursal bancaria adicional.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="9c6a0-126">Si no coincide el número de ruta bancaria, recibirá un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="9c6a0-127">El mensaje es solo una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-127">This message is only a warning.</span></span> <span data-ttu-id="9c6a0-128">Puede continuar incluso si no coincide el número de ruta bancaria.</span><span class="sxs-lookup"><span data-stu-id="9c6a0-128">You can continue even if the bank routing number doesn't match.</span></span>
