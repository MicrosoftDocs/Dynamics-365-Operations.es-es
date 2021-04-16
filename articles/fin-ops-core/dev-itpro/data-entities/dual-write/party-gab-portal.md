---
title: Uso de Power Portal con el modelo de datos de parte
description: Este tema describe los cambios en los roles web de Power Portal debido al modelo de datos de parte en escritura dual.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833099"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="b7d1d-103">Uso de Power Portal con el modelo de datos de parte</span><span class="sxs-lookup"><span data-stu-id="b7d1d-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b7d1d-104">La versión de la solución de orquestación de aplicaciones de escritura dual 2.0.999.0 y posteriores incluye cambios en el modelo de datos en la libreta de direcciones global y de partes para las tablas Cuenta y Contacto.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="b7d1d-105">Los cambios permiten relaciones de varios a varios que admiten escenarios empresariales avanzados.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="b7d1d-106">Estos cambios no son compatibles con los roles web del portal, incluido el portal del cliente, que se envían listos para usar o que existían en su ambiente antes de instalar la escritura dual.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="b7d1d-107">Para que los roles web funcionen como se esperaba, debe crear nuevos roles web utilizando el nuevo modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="b7d1d-108">En resumen, la forma en que interactúan las tablas ha cambiado, pero los permisos de las tablas en el portal del cliente no han cambiado.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="b7d1d-109">Este tema explica cómo crear nuevos roles web que funcionen con el nuevo modelo de datos avanzado.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="b7d1d-110">Este diagrama muestra la relación de la tabla **sin** el modelo de datos de parte y de libreta de direcciones global:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![sin modelo de parte](media/without-party-model.PNG)

<span data-ttu-id="b7d1d-112">Este diagrama muestra la relación de la tabla **con** el modelo de datos de parte y de libreta de direcciones global:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![con modelo de parte](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="b7d1d-114">Crear un permiso de tabla nuevo</span><span class="sxs-lookup"><span data-stu-id="b7d1d-114">Create a new table permission</span></span>

<span data-ttu-id="b7d1d-115">Para crear estos nuevos permisos de tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="b7d1d-116">Inicie sesión en [Power Apps](https://make.powerapps.com) y vaya a sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="b7d1d-117">Seleccione su aplicación de Administración de portales.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="b7d1d-118">En la barra lateral, seleccione **Seguridad > Permisos de tabla**.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="b7d1d-119">Debe crear tres permisos nuevos:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="b7d1d-120">Conexión de contacto a parte</span><span class="sxs-lookup"><span data-stu-id="b7d1d-120">Contact to Party connection</span></span>
    + <span data-ttu-id="b7d1d-121">Conexión de parte a contacto</span><span class="sxs-lookup"><span data-stu-id="b7d1d-121">Party to Account connection</span></span>
    + <span data-ttu-id="b7d1d-122">Conexión de cuenta a pedido</span><span class="sxs-lookup"><span data-stu-id="b7d1d-122">Account to Order connection</span></span>

4. <span data-ttu-id="b7d1d-123">Cree y guarde un nuevo permiso para la conexión de contacto a parte, estableciendo estos parámetros:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="b7d1d-124">**Nombre**: conexión de parte a cuenta (o su elección)</span><span class="sxs-lookup"><span data-stu-id="b7d1d-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="b7d1d-125">**Nombre de tabla**: msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="b7d1d-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="b7d1d-126">**Sitio web**: portal del cliente</span><span class="sxs-lookup"><span data-stu-id="b7d1d-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="b7d1d-127">**Ámbito**: contacto</span><span class="sxs-lookup"><span data-stu-id="b7d1d-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="b7d1d-128">**Privilegios**: Seleccionar todo</span><span class="sxs-lookup"><span data-stu-id="b7d1d-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="b7d1d-129">**Roles web**: usuarios autenticados, representante del cliente (o su elección)</span><span class="sxs-lookup"><span data-stu-id="b7d1d-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="b7d1d-130">Cree y guarde un nuevo permiso para la conexión de parte a contacto, estableciendo estos parámetros:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="b7d1d-131">**Nombre**: conexión de parte a cuenta (o su elección)</span><span class="sxs-lookup"><span data-stu-id="b7d1d-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="b7d1d-132">**Nombre de tabla**: cuenta</span><span class="sxs-lookup"><span data-stu-id="b7d1d-132">**Table Name**: account</span></span>
    + <span data-ttu-id="b7d1d-133">**Sitio web**: portal del cliente</span><span class="sxs-lookup"><span data-stu-id="b7d1d-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="b7d1d-134">**Ámbito**: primario</span><span class="sxs-lookup"><span data-stu-id="b7d1d-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="b7d1d-135">**Privilegios**: Seleccionar todo</span><span class="sxs-lookup"><span data-stu-id="b7d1d-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="b7d1d-136">**Permiso de tabla principal**: conexión de contacto a parte</span><span class="sxs-lookup"><span data-stu-id="b7d1d-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="b7d1d-137">Cree y guarde un nuevo permiso para la conexión de cuenta a pedido, estableciendo estos parámetros:</span><span class="sxs-lookup"><span data-stu-id="b7d1d-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="b7d1d-138">**Nombre**: conexión de cuenta a pedido (o su elección)</span><span class="sxs-lookup"><span data-stu-id="b7d1d-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="b7d1d-139">**Nombre de tabla**: salesorder</span><span class="sxs-lookup"><span data-stu-id="b7d1d-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="b7d1d-140">**Sitio web**: portal del cliente</span><span class="sxs-lookup"><span data-stu-id="b7d1d-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="b7d1d-141">**Ámbito**: primario</span><span class="sxs-lookup"><span data-stu-id="b7d1d-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="b7d1d-142">**Privilegios**: Seleccionar todo</span><span class="sxs-lookup"><span data-stu-id="b7d1d-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="b7d1d-143">**Permiso de tabla principal**: conexión de parte a cuenta</span><span class="sxs-lookup"><span data-stu-id="b7d1d-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
