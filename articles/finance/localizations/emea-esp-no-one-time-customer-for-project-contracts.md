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
ms.custom: 264394
ms.search.region: Spain
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 498e3d65fd30ae7a79bb6ea30a586a4def39b203
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992730"
---
# <a name="one-time-customers"></a><span data-ttu-id="c96f5-103">Clientes plantilla</span><span class="sxs-lookup"><span data-stu-id="c96f5-103">One-time customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c96f5-104">Este tema proporciona información sobre los clientes plantilla.</span><span class="sxs-lookup"><span data-stu-id="c96f5-104">This topic provides information about one-time customers.</span></span>  

<span data-ttu-id="c96f5-105">Un cliente plantilla es un cliente que no tiene una relación a largo plazo con su empresa.</span><span class="sxs-lookup"><span data-stu-id="c96f5-105">A one-time customer is a customer who does not have a long-term relationship with your company.</span></span> <span data-ttu-id="c96f5-106">Para los clientes plantilla, normalmente no es necesario guardar información como la dirección, el contacto, o los detalles de identificación fiscal.</span><span class="sxs-lookup"><span data-stu-id="c96f5-106">For one-time customers, you typically don't need to save information like address, contact, or tax exempt details.</span></span> <span data-ttu-id="c96f5-107">Para indicar que un cliente es un cliente plantilla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c96f5-107">To indicate that a customer is a one-time customer, complete the following steps:</span></span>

1.  <span data-ttu-id="c96f5-108">Abra la página **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-108">Open the **All customers** page.</span></span>
2.  <span data-ttu-id="c96f5-109">Seleccione un nombre de cliente para abrir el registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="c96f5-109">Select a customer name to open the customer's record.</span></span>
3.  <span data-ttu-id="c96f5-110">En la ficha desplegable **Detalles varios**, establezca la opción **Cliente plantilla** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-110">On the **Miscellaneous details** FastTab, set the **One-time customer** option to **Yes**.</span></span>
4.  <span data-ttu-id="c96f5-111">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-111">Click **Save**.</span></span>

<span data-ttu-id="c96f5-112">**Nota:** para poder registrar transacciones para un cliente plantilla, debe especificar una cuenta para dicho cliente en el campo **Cuenta de cliente plantilla** de la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-112">**Note:** Before you can post transactions for a one-time customer, you must specify an account to use for one-time customers in the **One-time customer account** field on the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="c96f5-113">Para España, puede especificar restricciones de usuario para la creacción de contratos de proyecto para clientes plantilla.</span><span class="sxs-lookup"><span data-stu-id="c96f5-113">For Spain, you can restrict users from creating project contracts for one-time customers.</span></span> <span data-ttu-id="c96f5-114">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c96f5-114">To do this, complete the following steps:</span></span>

1.  <span data-ttu-id="c96f5-115">Abra la página **Parámetros de gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-115">Open the **Project management and accounting parameters** page.</span></span>
2.  <span data-ttu-id="c96f5-116">Establezca el parámetro **No se permite usar clientes plantilla para contratos de proyectos** en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-116">Set the **No one-time customer for project contracts** parameter to **True**.</span></span>
3.  <span data-ttu-id="c96f5-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c96f5-117">Click **Save**.</span></span>




