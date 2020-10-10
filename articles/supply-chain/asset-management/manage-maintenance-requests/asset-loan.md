---
title: Activos prestados
description: En este tema se describe cómo registrar activos prestados en la Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cba680d0ad626e0275539d7478a83639a9d22635
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889658"
---
# <a name="asset-loans"></a><span data-ttu-id="c1c3b-103">Activos prestados</span><span class="sxs-lookup"><span data-stu-id="c1c3b-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="c1c3b-104">Si su empresa recibe activos para trabajos de reparación o de mantenimiento de ubicaciones internas o de clientes, y si presta temporalmente activos a dichas ubicaciones o clientes, Administración de activos puede hacer un seguimiento de los activos prestados.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="c1c3b-105">Registrar activos prestados en una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c1c3b-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="c1c3b-106">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="c1c3b-107">Seleccione la solicitud de mantenimiento en la que desea registrar un activo prestado y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="c1c3b-108">En la página **Solicitud**, seleccione **Enviar activo prestado**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="c1c3b-109">Seleccione el activo y especifique la fecha de devolución prevista.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="c1c3b-110">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="c1c3b-111">Solo puede enviar un activo prestado si está disponible un activo del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="c1c3b-112">El activo que preste debe tener una estado de ciclo de vida de activo que permita su uso como un activo prestado, como **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="c1c3b-113">Cuando se registra el activo prestado, el estado de ciclo de vida del activo se actualiza automáticamente **OnLoan**, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="c1c3b-114">Para ver una lista de todos los activos que ha prestado a otras ubicaciones o clientes, seleccione **Administración de activos** \> **Común** \> **Activo prestado** \> **Todos los activos prestados**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="c1c3b-115">Si la casilla **Finalizado** está activada para un activo, significa que se ha registrado el activo como devuelto a su empresa.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Administrar solicitudes de mantenimiento](media/06-manage-maintenance-requests.png)

<span data-ttu-id="c1c3b-117">En la página **Activos prestados activos** puede ver una lista de todos los activos prestados que aún no se han devuelto a su empresa.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="c1c3b-118">Registrar activos prestados como devueltos</span><span class="sxs-lookup"><span data-stu-id="c1c3b-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="c1c3b-119">Seleccione **Administración de activos** \> **Común** \> **Activo prestado** \> **Activos prestados activos**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="c1c3b-120">Seleccione el activo prestado que desea registrar como devuelto y, a continuación, seleccione **Devolver activo prestado**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="c1c3b-121">En el campo **Devuelto**, especifique la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="c1c3b-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-122">Select **OK**.</span></span>
5. <span data-ttu-id="c1c3b-123">Actualice la página de la lista **Activos prestados activos** y compruebe que el activo prestado ya no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="c1c3b-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>
