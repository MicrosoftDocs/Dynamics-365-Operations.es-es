---
title: Clientes plantilla
description: "Este tema proporciona información sobre los clientes plantilla."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264394
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6b94aec0956a967c1c342607cb4758e7220dffcb
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="one-time-customers"></a><span data-ttu-id="d2b01-103">Clientes plantilla</span><span class="sxs-lookup"><span data-stu-id="d2b01-103">One-time customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2b01-104">Este tema proporciona información sobre los clientes plantilla.</span><span class="sxs-lookup"><span data-stu-id="d2b01-104">This topic provides information about one-time customers.</span></span>  

<span data-ttu-id="d2b01-105">Un cliente plantilla es un cliente que no tiene una relación a largo plazo con su empresa.</span><span class="sxs-lookup"><span data-stu-id="d2b01-105">A one-time customer is a customer who does not have a long-term relationship with your company.</span></span> <span data-ttu-id="d2b01-106">Para los clientes plantilla, normalmente no es necesario guardar información como la dirección, el contacto, o los detalles de identificación fiscal.</span><span class="sxs-lookup"><span data-stu-id="d2b01-106">For one-time customers, you typically don't need to save information like address, contact, or tax exempt details.</span></span> <span data-ttu-id="d2b01-107">Para indicar que un cliente es un cliente plantilla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d2b01-107">To indicate that a customer is a one-time customer, complete the following steps:</span></span>

1.  <span data-ttu-id="d2b01-108">Abra la página **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-108">Open the **All customers** page.</span></span>
2.  <span data-ttu-id="d2b01-109">Seleccione un nombre de cliente para abrir el registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="d2b01-109">Select a customer name to open the customer's record.</span></span>
3.  <span data-ttu-id="d2b01-110">En la ficha desplegable **Detalles varios**, establezca la opción **Cliente plantilla** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-110">On the **Miscellaneous details** FastTab, set the **One-time customer** option to **Yes**.</span></span>
4.  <span data-ttu-id="d2b01-111">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-111">Click **Save**.</span></span>

<span data-ttu-id="d2b01-112">**Nota:** para poder registrar transacciones para un cliente plantilla, debe especificar una cuenta para dicho cliente en el campo **Cuenta de cliente plantilla** de la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-112">**Note:** Before you can post transactions for a one-time customer, you must specify an account to use for one-time customers in the **One-time customer account** field on the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="d2b01-113">Para España, puede especificar restricciones de usuario para la creacción de contratos de proyecto para clientes plantilla.</span><span class="sxs-lookup"><span data-stu-id="d2b01-113">For Spain, you can restrict users from creating project contracts for one-time customers.</span></span> <span data-ttu-id="d2b01-114">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2b01-114">To do this, complete the following steps:</span></span>

1.  <span data-ttu-id="d2b01-115">Abra la página **Parámetros de gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-115">Open the **Project management and accounting parameters** page.</span></span>
2.  <span data-ttu-id="d2b01-116">Establezca el parámetro **No se permite usar clientes plantilla para contratos de proyectos** en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-116">Set the **No one-time customer for project contracts** parameter to **True**.</span></span>
3.  <span data-ttu-id="d2b01-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2b01-117">Click **Save**.</span></span>





