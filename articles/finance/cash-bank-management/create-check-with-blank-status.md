---
title: Crear cheques que tengan el estado en blanco
description: En este tema se explica cómo crear cheques en blanco para una cuenta bancaria en la página de cheques.
author: abruer
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 1b01daa86055156092d035d61aad78a13349f869
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815965"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="e7a1f-103">Crear cheques que tengan el estado en blanco</span><span class="sxs-lookup"><span data-stu-id="e7a1f-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7a1f-104">En este tema se explica cómo crear cheques en blanco.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="e7a1f-105">Por ejemplo, puede crear un cheque en blanco para registrar un cheque que ha resultado dañado y no se puede usar para el pago.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="e7a1f-106">En la página **Cheques**, realice las tareas de mantenimiento para cheques.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="e7a1f-107">Por ejemplo, puede crear nuevos números de cheque y eliminar cheques.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="e7a1f-108">También puede crear cheques que tengan el estado **En blanco**.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="e7a1f-109">Tras crear cheques en blanco, no se podrán eliminar ni volver a utilizar en el sistema.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="e7a1f-110">Esta característica está disponible en la página **Cheques** únicamente si se activa la característica **Crear cheques con un estado en blanco en la página Cheques** en la página **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="e7a1f-111">Si la característica no está activada, los cheques con estado **En blanco** solo se pueden crear desde el cuadro de diálogo **Pago mediante cheque** durante el proceso de generación de pago en Proveedores.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="e7a1f-112">Para abrir la página **Cheques**, vaya a **Gestión de efectivo y bancos \> Cuentas bancarias \> Cuentas bancarias** y, a continuación, en el panel de acciones, en la pestaña **Administrar pagos**, en el grupo **Información relacionada**, seleccione **Cheques**.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="e7a1f-113">Como alternativa, vaya a **Gestión de efectivo y bancos \> Consultas e informes \> Cheques**.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="e7a1f-114">A continuación, para crear cheques con estado **En blanco**, en el panel de acciones, seleccione **Crear cheques en blanco**.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="e7a1f-115">Mientras el sistema está creando cheques en blanco, la cuenta bancaria asociada se desactiva temporalmente.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="e7a1f-116">Este comportamiento reduce el riesgo de que se generen pagos a la vez que se crean cheques en blanco.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="e7a1f-117">Tras completar el procesamiento, se reactiva la cuenta bancaria asociada.</span><span class="sxs-lookup"><span data-stu-id="e7a1f-117">When the processing is completed, the associated bank account is reactivated.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]