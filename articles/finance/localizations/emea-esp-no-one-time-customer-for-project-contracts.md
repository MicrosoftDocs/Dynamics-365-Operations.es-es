---
title: Clientes plantilla
description: Este tema proporciona información sobre los clientes plantilla.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264394
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 63c2076740834c0ffb8f299850422cf0f8be37ee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183586"
---
# <a name="one-time-customers"></a><span data-ttu-id="b2971-103">Clientes plantilla</span><span class="sxs-lookup"><span data-stu-id="b2971-103">One-time customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2971-104">Este tema proporciona información sobre los clientes plantilla.</span><span class="sxs-lookup"><span data-stu-id="b2971-104">This topic provides information about one-time customers.</span></span>  

<span data-ttu-id="b2971-105">Un cliente plantilla es un cliente que no tiene una relación a largo plazo con su empresa.</span><span class="sxs-lookup"><span data-stu-id="b2971-105">A one-time customer is a customer who does not have a long-term relationship with your company.</span></span> <span data-ttu-id="b2971-106">Para los clientes plantilla, normalmente no es necesario guardar información como la dirección, el contacto, o los detalles de identificación fiscal.</span><span class="sxs-lookup"><span data-stu-id="b2971-106">For one-time customers, you typically don't need to save information like address, contact, or tax exempt details.</span></span> <span data-ttu-id="b2971-107">Para indicar que un cliente es un cliente plantilla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b2971-107">To indicate that a customer is a one-time customer, complete the following steps:</span></span>

1.  <span data-ttu-id="b2971-108">Abra la página **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="b2971-108">Open the **All customers** page.</span></span>
2.  <span data-ttu-id="b2971-109">Seleccione un nombre de cliente para abrir el registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="b2971-109">Select a customer name to open the customer's record.</span></span>
3.  <span data-ttu-id="b2971-110">En la ficha desplegable **Detalles varios**, establezca la opción **Cliente plantilla** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b2971-110">On the **Miscellaneous details** FastTab, set the **One-time customer** option to **Yes**.</span></span>
4.  <span data-ttu-id="b2971-111">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b2971-111">Click **Save**.</span></span>

<span data-ttu-id="b2971-112">**Nota:** para poder registrar transacciones para un cliente plantilla, debe especificar una cuenta para dicho cliente en el campo **Cuenta de cliente plantilla** de la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="b2971-112">**Note:** Before you can post transactions for a one-time customer, you must specify an account to use for one-time customers in the **One-time customer account** field on the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="b2971-113">Para España, puede especificar restricciones de usuario para la creacción de contratos de proyecto para clientes plantilla.</span><span class="sxs-lookup"><span data-stu-id="b2971-113">For Spain, you can restrict users from creating project contracts for one-time customers.</span></span> <span data-ttu-id="b2971-114">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2971-114">To do this, complete the following steps:</span></span>

1.  <span data-ttu-id="b2971-115">Abra la página **Parámetros de gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="b2971-115">Open the **Project management and accounting parameters** page.</span></span>
2.  <span data-ttu-id="b2971-116">Establezca el parámetro **No se permite usar clientes plantilla para contratos de proyectos** en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="b2971-116">Set the **No one-time customer for project contracts** parameter to **True**.</span></span>
3.  <span data-ttu-id="b2971-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b2971-117">Click **Save**.</span></span>




