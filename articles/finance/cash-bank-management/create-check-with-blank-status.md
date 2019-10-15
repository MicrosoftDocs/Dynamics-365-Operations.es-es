---
title: Crear cheques que tengan el estado en blanco
description: En este tema se explica cómo crear cheques en blanco para una cuenta bancaria en la página de cheques.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: af79dd4831f2e7fc71c296922d73a9e42f7955b3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176081"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="bffa6-103">Crear cheques que tengan el estado en blanco</span><span class="sxs-lookup"><span data-stu-id="bffa6-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bffa6-104">En este tema se explica cómo crear cheques en blanco.</span><span class="sxs-lookup"><span data-stu-id="bffa6-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="bffa6-105">Por ejemplo, puede crear un cheque en blanco para registrar un cheque que ha resultado dañado y no se puede usar para el pago.</span><span class="sxs-lookup"><span data-stu-id="bffa6-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="bffa6-106">En la página **Cheques**, realice las tareas de mantenimiento para cheques.</span><span class="sxs-lookup"><span data-stu-id="bffa6-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="bffa6-107">Por ejemplo, puede crear nuevos números de cheque y eliminar cheques.</span><span class="sxs-lookup"><span data-stu-id="bffa6-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="bffa6-108">También puede crear cheques que tengan el estado **En blanco**.</span><span class="sxs-lookup"><span data-stu-id="bffa6-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="bffa6-109">Tras crear cheques en blanco, no se podrán eliminar ni volver a utilizar en el sistema.</span><span class="sxs-lookup"><span data-stu-id="bffa6-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="bffa6-110">Esta característica está disponible en la página **Cheques** únicamente si se activa la característica **Crear cheques con un estado en blanco en la página Cheques** en la página **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="bffa6-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="bffa6-111">Si la característica no está activada, los cheques con estado **En blanco** solo se pueden crear desde el cuadro de diálogo **Pago mediante cheque** durante el proceso de generación de pago en Proveedores.</span><span class="sxs-lookup"><span data-stu-id="bffa6-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="bffa6-112">Para abrir la página **Cheques**, vaya a **Gestión de efectivo y bancos \> Cuentas bancarias \> Cuentas bancarias** y, a continuación, en el panel de acciones, en la pestaña **Administrar pagos**, en el grupo **Información relacionada**, seleccione **Cheques**.</span><span class="sxs-lookup"><span data-stu-id="bffa6-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="bffa6-113">Como alternativa, vaya a **Gestión de efectivo y bancos \> Consultas e informes \> Cheques**.</span><span class="sxs-lookup"><span data-stu-id="bffa6-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="bffa6-114">A continuación, para crear cheques con estado **En blanco**, en el panel de acciones, seleccione **Crear cheques en blanco**.</span><span class="sxs-lookup"><span data-stu-id="bffa6-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="bffa6-115">Mientras el sistema está creando cheques en blanco, la cuenta bancaria asociada se desactiva temporalmente.</span><span class="sxs-lookup"><span data-stu-id="bffa6-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="bffa6-116">Este comportamiento reduce el riesgo de que se generen pagos a la vez que se crean cheques en blanco.</span><span class="sxs-lookup"><span data-stu-id="bffa6-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="bffa6-117">Tras completar el procesamiento, se reactiva la cuenta bancaria asociada.</span><span class="sxs-lookup"><span data-stu-id="bffa6-117">When the processing is completed, the associated bank account is reactivated.</span></span>
