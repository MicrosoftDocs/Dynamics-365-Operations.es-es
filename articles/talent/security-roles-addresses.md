---
title: Acceder a direcciones privadas por rol de seguridad
description: Este tema explica cómo resolver el problema en que el cliente no puede tener acceso a direcciones privadas.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897106"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="0ff77-103">Acceder a direcciones privadas por rol de seguridad</span><span class="sxs-lookup"><span data-stu-id="0ff77-103">Access to private addresses by security role</span></span>

<span data-ttu-id="0ff77-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="0ff77-104">**Issue**</span></span>

<span data-ttu-id="0ff77-105">Después de que un cliente duplique un rol de seguridad e inicie sesión como dicho nuevo rol, el cliente no puede ver las direcciones que fueron marcadas como privadas.</span><span class="sxs-lookup"><span data-stu-id="0ff77-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="0ff77-106">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="0ff77-106">**Resolution**</span></span>

<span data-ttu-id="0ff77-107">Para solucionar el problema, el cliente debe seguir estos pasos para el rol de seguridad duplicado.</span><span class="sxs-lookup"><span data-stu-id="0ff77-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="0ff77-108">Vaya a **Administración de la organización \> Libreta de direcciones global \> Parámetros de libreta de direcciones global**.</span><span class="sxs-lookup"><span data-stu-id="0ff77-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="0ff77-109">En la pestaña **Seguridad de ubicación privada** , mueva el nuevo rol de seguridad desde la lista **Roles disponibles** a la lista **Roles seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="0ff77-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="0ff77-110">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ff77-110">Select **Save**.</span></span>

![Página de parámetros de la libreta de direcciones global](media/GAD-parameters.png)
