---
title: Crear jerarquías de modelado de organización para organizaciones B2B
description: Este tema describe cómo crear jerarquías de modelado organizativo para organizaciones de empresa a empresa (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035960"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="d5c97-103">Crear jerarquías de modelado de organización para organizaciones B2B</span><span class="sxs-lookup"><span data-stu-id="d5c97-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5c97-104">Este tema describe cómo crear jerarquías de modelado organizativo para organizaciones de empresa a empresa (B2B) en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5c97-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d5c97-105">En la sede central de Commerce, las organizaciones que son socios comerciales están representadas por clientes y entidades jerárquicas de clientes.</span><span class="sxs-lookup"><span data-stu-id="d5c97-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="d5c97-106">La organización socio comercial y sus usuarios se representan como clientes, y las jerarquías de clientes se utilizan para asociar esos clientes entre sí.</span><span class="sxs-lookup"><span data-stu-id="d5c97-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="d5c97-107">Cuando un socio comercial solicita unirse a un sitio de comercio electrónico B2B, se realizan las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d5c97-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="d5c97-108">Además, se crean dos nuevos registros de clientes en el sistema: un registro de cliente **De tipo organización** para la organización del socio comercial y un registro de cliente **De tipo persona** para el solicitante (es decir, el usuario socio comercial que envió la solicitud).</span><span class="sxs-lookup"><span data-stu-id="d5c97-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="d5c97-109">Se crea un nuevo registro de jerarquía de clientes en **Cliente \> Jerarquía de clientes**.</span><span class="sxs-lookup"><span data-stu-id="d5c97-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="d5c97-110">Este registro tiene las siguientes propiedades de encabezado:</span><span class="sxs-lookup"><span data-stu-id="d5c97-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="d5c97-111">**Id. de jerarquía de clientes**: identificador único para la jerarquía de clientes.</span><span class="sxs-lookup"><span data-stu-id="d5c97-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="d5c97-112">Este id. usa la secuencia numérica que se define en los parámetros compartidos de Commerce en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5c97-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="d5c97-113">**Nombre**: el nombre de la organización socio comercial, como se especifica en la solicitud de incorporación.</span><span class="sxs-lookup"><span data-stu-id="d5c97-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="d5c97-114">**Objetivo**: esta propiedad se establece en el valor predefinido **Organización de B2B**.</span><span class="sxs-lookup"><span data-stu-id="d5c97-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="d5c97-115">**Organización**: id. de cliente del socio comercial.</span><span class="sxs-lookup"><span data-stu-id="d5c97-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="d5c97-116">Estos son los detalles del registro de jerarquía de clientes:</span><span class="sxs-lookup"><span data-stu-id="d5c97-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="d5c97-117">El registro de cliente del solicitante está asociado con la jerarquía de clientes.</span><span class="sxs-lookup"><span data-stu-id="d5c97-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="d5c97-118">El rol de administrador está asociado con el solicitante.</span><span class="sxs-lookup"><span data-stu-id="d5c97-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="d5c97-119">Cuando el administrador agrega más usuarios a la organización de socios comerciales en un sitio B2B, se crea un nuevo registro de cliente para cada usuario en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5c97-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="d5c97-120">Este registro de cliente también se agrega al registro de jerarquía de clientes relevante para el socio comercial y tiene el rol de "usuario".</span><span class="sxs-lookup"><span data-stu-id="d5c97-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="d5c97-121">En la mayoría de los casos, los valores de propiedad correspondientes de todos los registros de clientes de una jerarquía deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="d5c97-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="d5c97-122">Por ejemplo, como todos los usuarios socios comerciales deben obtener precios similares para los productos, su grupo de precios y las configuraciones asociadas deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="d5c97-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="d5c97-123">Sin embargo, el sistema no aplica esta coherencia.</span><span class="sxs-lookup"><span data-stu-id="d5c97-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="d5c97-124">Por lo tanto, los usuarios de la sede central de Commerce correspondientes son responsables de garantizar que los valores y las configuraciones de las propiedades coincidan para todos los clientes en una jerarquía determinada.</span><span class="sxs-lookup"><span data-stu-id="d5c97-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="d5c97-125">Los usuarios de la sede central de Commerce pueden ver los valores de propiedades de todos los registros de clientes de la jerarquía en una vista en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d5c97-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="d5c97-126">Seleccione las propiedades de registro de cliente relevantes seleccionando los nombres de las pestañas en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="d5c97-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="d5c97-127">Los usuarios pueden ver y editar directamente los valores de propiedad desde esta vista.</span><span class="sxs-lookup"><span data-stu-id="d5c97-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="d5c97-128">Como alternativa, si desea aplicar todos los valores del registro de cliente administrador a todos los registros de cliente usuario, seleccione **Reemplazar** en los detalles de la jerarquía de clientes.</span><span class="sxs-lookup"><span data-stu-id="d5c97-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5c97-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d5c97-129">Additional resources</span></span>

[<span data-ttu-id="d5c97-130">Configurar un sitio de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="d5c97-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="d5c97-131">Administrar usuarios socios comerciales en sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="d5c97-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="d5c97-132">Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="d5c97-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="d5c97-133">Establecer límites de cantidad de productos para sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="d5c97-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)
