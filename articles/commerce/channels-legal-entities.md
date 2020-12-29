---
title: Crear entidades jurídicas
description: En este tema se describe cómo crear entidades jurídicas en Microsoft Dynamics 365 Commerce. Deben crearse y configurarse antes de crear canales.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 28cbcc42505f1dc90c420adc812735841541c8e0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415499"
---
# <a name="create-legal-entities"></a><span data-ttu-id="ff0df-103">Crear entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="ff0df-103">Create legal entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ff0df-104">En este tema se describe cómo crear entidades jurídicas en Microsoft Dynamics 365 Commerce. Deben crearse y configurarse antes de crear canales.</span><span class="sxs-lookup"><span data-stu-id="ff0df-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

## <a name="overview"></a><span data-ttu-id="ff0df-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="ff0df-105">Overview</span></span>

<span data-ttu-id="ff0df-106">Una entidad jurídica es una organización que tiene una estructura jurídicas registrada o legislada.</span><span class="sxs-lookup"><span data-stu-id="ff0df-106">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="ff0df-107">Las entidades jurídicas pueden realizar contratos legales y tienen la obligación de preparar declaraciones para dar a conocer su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ff0df-107">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="ff0df-108">Una empresa en un tipo de entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-108">A company is a type of legal entity.</span></span> <span data-ttu-id="ff0df-109">Actualmente, las empresas son el único tipo de entidad jurídica que se puede crear y todas las entidades jurídicas están asociadas a un identificador de empresa.</span><span class="sxs-lookup"><span data-stu-id="ff0df-109">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="ff0df-110">Esta asociación existe porque algunas áreas funcionales del programa usan un id. de empresa, o *DataAreaId*, en sus modelos de datos.</span><span class="sxs-lookup"><span data-stu-id="ff0df-110">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="ff0df-111">En estas áreas funcionales, las empresas se usan como un límite para la seguridad de datos.</span><span class="sxs-lookup"><span data-stu-id="ff0df-111">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="ff0df-112">Los usuarios sólo pueden acceder a los datos de la empresa en la que han iniciado sesión en ese momento.</span><span class="sxs-lookup"><span data-stu-id="ff0df-112">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="ff0df-113">Al crear un canal debe especificar a qué entidad jurídica pertenece.</span><span class="sxs-lookup"><span data-stu-id="ff0df-113">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="ff0df-114">Crear una nueva entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="ff0df-114">Create a new legal entity</span></span>

<span data-ttu-id="ff0df-115">Para crear una nueva entidad jurídica en Dynamics 365 Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff0df-115">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ff0df-116">En el panel de navegación, vaya a **Módulos \> Configuración de sede central \> Entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="ff0df-116">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="ff0df-117">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ff0df-117">On the action pane, select **New**.</span></span> <span data-ttu-id="ff0df-118">El panel **Nueva entidad jurídica** aparece a la derecha.</span><span class="sxs-lookup"><span data-stu-id="ff0df-118">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="ff0df-119">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ff0df-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="ff0df-120">En el campo **Empresa**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ff0df-120">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="ff0df-121">En el campo **País o región**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ff0df-121">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="ff0df-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff0df-122">Select **OK**.</span></span> 

   ![Creación de entidad jurídica](media/legal-entities.png)

1. <span data-ttu-id="ff0df-124">En la sección **General**, proporcione la siguiente información general sobre la entidad jurídica:</span><span class="sxs-lookup"><span data-stu-id="ff0df-124">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="ff0df-125">Especifique un nombre de búsqueda, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ff0df-125">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="ff0df-126">Un nombre de búsqueda es un nombre alternativo que puede usarse para buscar esta entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-126">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="ff0df-127">Seleccione si la entidad jurídica se usa como una empresa de consolidación.</span><span class="sxs-lookup"><span data-stu-id="ff0df-127">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="ff0df-128">Seleccione si la entidad jurídica se usa como una empresa de eliminación.</span><span class="sxs-lookup"><span data-stu-id="ff0df-128">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="ff0df-129">Seleccione el **idioma predeterminado** de la entidad.</span><span class="sxs-lookup"><span data-stu-id="ff0df-129">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="ff0df-130">Seleccione la **zona horaria** para la entidad.</span><span class="sxs-lookup"><span data-stu-id="ff0df-130">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="ff0df-131">En la sección **Direcciones**, seleccione **Editar** para especificar la información de dirección, como la calle y el número, el código postal y la ciudad.</span><span class="sxs-lookup"><span data-stu-id="ff0df-131">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="ff0df-132">En la sección **Información de contacto**, especifique información sobre los métodos de comunicación, como direcciones de correo electrónico, URL y números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="ff0df-132">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="ff0df-133">En la sección **Informes estatutarios**, especifique los números de registro que se usan para informes estatutarios.</span><span class="sxs-lookup"><span data-stu-id="ff0df-133">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="ff0df-134">En la sección **Números de registro**, especifique cualquier información requerida por la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-134">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="ff0df-135">En la sección **Información de cuenta bancaria**, especifique las cuentas bancarias y los números de enrutamiento para la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-135">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="ff0df-136">En la sección **Comercio exterior y logística**, especifique la información de envío para la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-136">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="ff0df-137">En la sección **Secuencias numéricas**, se pueden ver las secuencias numéricas asociadas a la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-137">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="ff0df-138">Estará vacía para empezar.</span><span class="sxs-lookup"><span data-stu-id="ff0df-138">This will be empty to start with.</span></span>
1. <span data-ttu-id="ff0df-139">En la sección **Imagen de panel de información**, vea o cambie el logotipo o la imagen del panel asociados a la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-139">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="ff0df-140">En la sección **Registro de impuestos**, especifique los números de registro que se usan para hacer declaraciones a las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="ff0df-140">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="ff0df-141">En la sección **IRPF**, especifique la información de IRPF de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-141">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="ff0df-142">En la sección **Información fiscal** introduzca la información fiscal de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="ff0df-142">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="ff0df-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ff0df-143">Select **Save**.</span></span>

<span data-ttu-id="ff0df-144">En la imagen siguiente se muestran los detalles de una entidad jurídica de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ff0df-144">The following image shows details of an example legal entity.</span></span>

![Sección general de entidad jurídica](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="ff0df-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ff0df-146">Additional resources</span></span>

[<span data-ttu-id="ff0df-147">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="ff0df-147">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ff0df-148">Planificación de su jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="ff0df-148">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ff0df-149">Jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="ff0df-149">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="ff0df-150">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="ff0df-150">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ff0df-151">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="ff0df-151">Channel setup prerequisites</span></span>](channels-prerequisites.md)
