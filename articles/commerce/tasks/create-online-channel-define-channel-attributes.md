---
title: Creación del canal en línea y definición de los atributos del canal
description: Este procedimiento le guía por la creación de un nuevo canal en línea y su adición a la jerarquía organizativa.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f15b035c01801041d637a2d315d8a3ddcc9d6540
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140969"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="04da7-103">Creación del canal en línea y definición de los atributos del canal</span><span class="sxs-lookup"><span data-stu-id="04da7-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04da7-104">Este procedimiento le guía por la creación de un nuevo canal en línea y su adición a la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="04da7-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="04da7-105">Debe crear la jerarquía organizativa para poder crear un nuevo canal en línea.</span><span class="sxs-lookup"><span data-stu-id="04da7-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="04da7-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="04da7-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="04da7-107">Crear un nuevo canal en línea</span><span class="sxs-lookup"><span data-stu-id="04da7-107">Create a new online channel</span></span>
1. <span data-ttu-id="04da7-108">Vaya a Retail y Commerce > Canales > Tiendas en línea.</span><span class="sxs-lookup"><span data-stu-id="04da7-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="04da7-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="04da7-109">Click New.</span></span>
3. <span data-ttu-id="04da7-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="04da7-111">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="04da7-112">En el campo Zona horaria de la tienda, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="04da7-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="04da7-113">En el campo Cliente predeterminado, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="04da7-114">En el campo Libreta de direcciones de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="04da7-115">En el campo Condiciones de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="04da7-116">En el campo Método de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="04da7-117">En el campo Perfil de notificación por correo electrónico, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="04da7-118">Expanda la sección Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="04da7-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="04da7-119">En el campo BusinessUnit, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="04da7-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="04da7-120">Defina de forma similar el valor para las demás dimensiones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="04da7-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="04da7-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="04da7-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="04da7-122">Agregar el canal en línea a la jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="04da7-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="04da7-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="04da7-123">Close the page.</span></span>
2. <span data-ttu-id="04da7-124">Vaya a Administración de la organización > Organizaciones > Jerarquías organizativas.</span><span class="sxs-lookup"><span data-stu-id="04da7-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="04da7-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="04da7-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="04da7-126">Haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="04da7-126">Click View.</span></span>
5. <span data-ttu-id="04da7-127">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="04da7-127">Click Edit.</span></span>
    * <span data-ttu-id="04da7-128">Puede seleccionar cualquier nodo de jerarquía bajo el que desea insertar el nuevo canal.</span><span class="sxs-lookup"><span data-stu-id="04da7-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="04da7-129">Haga clic en Insertar.</span><span class="sxs-lookup"><span data-stu-id="04da7-129">Click Insert.</span></span>
7. <span data-ttu-id="04da7-130">Haga clic en el canal de Commerce.</span><span class="sxs-lookup"><span data-stu-id="04da7-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="04da7-131">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="04da7-131">Click OK.</span></span>
9. <span data-ttu-id="04da7-132">Haga clic en Publicar para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="04da7-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="04da7-133">En el campo Fecha de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="04da7-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="04da7-134">Haga clic en Publicar.</span><span class="sxs-lookup"><span data-stu-id="04da7-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="04da7-135">Configurar los pedidos para la notificación casi en tiempo real</span><span class="sxs-lookup"><span data-stu-id="04da7-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="04da7-136">Vaya a Retail y Commerce > Configuración de sede > Parámetros > Parámetros de Commerce.</span><span class="sxs-lookup"><span data-stu-id="04da7-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="04da7-137">Establezca el servicio en tiempo real de uso para la creación de pedidos de comercio electrónico en “Sí”.</span><span class="sxs-lookup"><span data-stu-id="04da7-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="04da7-138">Ejecute la programación de distribución 1070 para sincronizar los cambios con la base de datos de canal.</span><span class="sxs-lookup"><span data-stu-id="04da7-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 


