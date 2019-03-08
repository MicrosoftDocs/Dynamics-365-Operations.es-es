---
title: Seguridad de usuario del portal de proveedor
description: Este artículo explica cómo configurar la seguridad para proveedores externos que usan el Portal de proveedor. Esta información se aplica solo a las versiones de febrero de 2016 &amp; mayo de 2016 de Dynamics AX.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 176eeb2ddb145d21f7ff9fd94a9a56e173caee59
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "367073"
---
# <a name="vendor-portal-user-security"></a><span data-ttu-id="95302-104">Seguridad de usuario del portal de proveedores</span><span class="sxs-lookup"><span data-stu-id="95302-104">Vendor portal user security</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95302-105">Este artículo explica cómo configurar la seguridad para proveedores externos que usan el Portal de proveedor.</span><span class="sxs-lookup"><span data-stu-id="95302-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="95302-106">Esta información se aplica solo a las versiones de febrero de 2016 &amp; mayo de 2016 de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="95302-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="95302-107">La funcionalidad del portal de proveedores se ha sustituido por la funcionalidad extendida de colaboración del proveedor en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="95302-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="95302-108">Para obtener más información acerca de la configuración de la seguridad para la colaboración de proveedor, consulte [Configurar y mantener la colaboración de proveedor](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="95302-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="95302-109">El portal de proveedores expone un sistema limitado de información acerca de los pedidos de compra a los proveedores externos.</span><span class="sxs-lookup"><span data-stu-id="95302-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="95302-110">Es importante configurar correctamente los permisos de usuario del portal de proveedores en Microsoft Dynamics AX, de modo que los proveedores no tengan acceso involuntario a información adicional en la instalación de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="95302-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="95302-111">**Importante:** a diferencia de otros usuarios, los proveedores externos no deben tener el rol de **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="95302-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="95302-112">El rol de **SystemUser** concede acceso a un conjunto de privilegios que no son convenientes para los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="95302-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="95302-113">Configuración de un usuario del portal de proveedores</span><span class="sxs-lookup"><span data-stu-id="95302-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="95302-114">Antes de crear una cuenta de usuario para alguien que utilizará el portal de proveedores, debe configurar el proveedor para que pueda colaborar con el portal de proveedores.</span><span class="sxs-lookup"><span data-stu-id="95302-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="95302-115">Use el campo **Colaboración del pedido de compra** en la pestaña **General** en la página **Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="95302-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="95302-116">Los proveedores externos que usan el portal de proveedores deben tener la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="95302-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="95302-117">Una cuenta de usuario Microsoft Azure Active Directory (AAD) se debe registrar para el proveedor en la página **Usuarios** de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="95302-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="95302-118">El proveedor debe tener el rol de seguridad **Proveedor (externo)**, no el rol de **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="95302-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="95302-119">**Nota**: el rol **SystemUser** se concede automáticamente cuando se crea una nueva cuenta de usuario en Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="95302-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="95302-120">Por lo tanto, debe quitar dicho rol y reconocer el mensaje de advertencia que reciba.</span><span class="sxs-lookup"><span data-stu-id="95302-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="95302-121">Al usuario proveedor no se le debe conceder permiso para agregar campos adicionales de las tablas de PO para la vista de PO.</span><span class="sxs-lookup"><span data-stu-id="95302-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="95302-122">En la pestaña **Personalización**, en la pestaña **Usuarios**, defina la opción **Personalización explícita permitida** para el usuario en **No**.</span><span class="sxs-lookup"><span data-stu-id="95302-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="95302-123">La cuenta de usuario se debe asociar con una persona de contacto registrada.</span><span class="sxs-lookup"><span data-stu-id="95302-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="95302-124">En la página **Usuarios**, seleccione una persona de contacto en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="95302-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="95302-125">La persona que seleccione debe tener el rol de **Contacto** para el proveedor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="95302-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="95302-126">Si la misma persona requiere el acceso al portal de proveedores para varias cuentas de proveedor (para distintas entidades jurídicas, quizás), cada una de las cuentas de usuario de dicha persona debe estar asociada a la misma persona de contacto registrada.</span><span class="sxs-lookup"><span data-stu-id="95302-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="95302-127">El rol de **Proveedor (externo)** incluye todas las capacidades básicas que se requieren para usar la funcionalidad que está disponible en el portal de proveedores.</span><span class="sxs-lookup"><span data-stu-id="95302-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="95302-128">Esta configuración ayuda a garantizar que la interfaz de usuario que el usuario externo verá está centrada únicamente en la situación planificada.</span><span class="sxs-lookup"><span data-stu-id="95302-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

<a name="additional-resources"></a><span data-ttu-id="95302-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="95302-129">Additional resources</span></span>
--------

[<span data-ttu-id="95302-130">Colaboración de proveedor</span><span class="sxs-lookup"><span data-stu-id="95302-130">Vendor collaboration</span></span>](collaborate-vendors-vendor-portal.md)



