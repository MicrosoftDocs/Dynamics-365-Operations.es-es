---
title: Grupos de objetos de servicio
description: "Los grupos de objetos son útiles para ordenar y filtrar los datos sobre objetos para informes y estadísticas."
author: YuyuScheller
manager: AnnBe
ms.date: 05/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2ab3ed8a8f36f980473b17b5dfed8cb3d0054253
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="service-object-groups"></a><span data-ttu-id="d70e3-103">Grupos de objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="d70e3-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d70e3-104">Los grupos de objetos son útiles para ordenar y filtrar los datos sobre objetos para informes y estadísticas.</span><span class="sxs-lookup"><span data-stu-id="d70e3-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="d70e3-105">Por ejemplo, puede agrupar objetos por ubicación geográfica o por tipo.</span><span class="sxs-lookup"><span data-stu-id="d70e3-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="d70e3-106">Agrupación por ubicación geográfica</span><span class="sxs-lookup"><span data-stu-id="d70e3-106">Group by geographical location</span></span>

<span data-ttu-id="d70e3-107">Puede utilizar este método de agrupación para mostrar dónde están ubicados los diferentes objetos de su empresa.</span><span class="sxs-lookup"><span data-stu-id="d70e3-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="d70e3-108">Los objetos de una agrupación por ubicación geográfica también pueden ser útiles, por ejemplo, en caso de que deba identificar los objetos para los que ya se ha proporcionado servicio en un determinado país o región.</span><span class="sxs-lookup"><span data-stu-id="d70e3-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="d70e3-109">ejemplo</span><span class="sxs-lookup"><span data-stu-id="d70e3-109">Example</span></span>

<span data-ttu-id="d70e3-110">Un cliente de Bélgica llama al centro de atención al cliente para crear un acuerdo de servicio para un objeto, ABC.</span><span class="sxs-lookup"><span data-stu-id="d70e3-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="d70e3-111">Usted ha vinculado un grupo de objetos de una ubicación geográfica, Bélgica, a todos los objetos para los que se ofrece servicio en Bélgica.</span><span class="sxs-lookup"><span data-stu-id="d70e3-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="d70e3-112">Si utiliza este grupo como filtro, puede saber rápidamente si el objeto ya existe como registro en el programa, o si debe configurar un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="d70e3-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="d70e3-113">Agrupación por tipo</span><span class="sxs-lookup"><span data-stu-id="d70e3-113">Group by type</span></span>

<span data-ttu-id="d70e3-114">Puede utilizar este método de agrupación para mostrar los tipos de objetos para los que ofrece servicio su empresa.</span><span class="sxs-lookup"><span data-stu-id="d70e3-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="d70e3-115">La agrupación de objetos por tipo también puede ser útil si, por ejemplo, desea crear un nuevo objeto a partir de objetos similares que ya existen en el programa.</span><span class="sxs-lookup"><span data-stu-id="d70e3-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="d70e3-116">ejemplo</span><span class="sxs-lookup"><span data-stu-id="d70e3-116">Example</span></span>

<span data-ttu-id="d70e3-117">Un cliente desea crear un acuerdo de servicio para un sistema de aire acondicionado, HIJ.</span><span class="sxs-lookup"><span data-stu-id="d70e3-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="d70e3-118">Aún no tiene un registro para este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d70e3-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="d70e3-119">No obstante, hay establecido un grupo de objetos llamado Aire Acondicionado, y ha vinculado este grupo a todos los objetos de aire acondicionado.</span><span class="sxs-lookup"><span data-stu-id="d70e3-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="d70e3-120">Por lo tanto, puede buscar e identificar rápidamente todos los demás dispositivos de aire acondicionado y utilizar la información de la plantilla de estos objetos para crear líneas de acuerdo de servicio para HIJ.</span><span class="sxs-lookup"><span data-stu-id="d70e3-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="d70e3-121">La utilización de grupos de objetos de esta manera permite configurar nuevos objetos rápidamente y determinar las tareas de servicio deben llevarse a cabo en ellos.</span><span class="sxs-lookup"><span data-stu-id="d70e3-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="d70e3-122">Creación de los grupos de objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="d70e3-122">Create service object groups</span></span>

<span data-ttu-id="d70e3-123">Cree grupos a los que puede asignar objetos de servicio.</span><span class="sxs-lookup"><span data-stu-id="d70e3-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="d70e3-124">Los objetos de servicio son artículos de inventario y otros productos para los que se realizan servicios.</span><span class="sxs-lookup"><span data-stu-id="d70e3-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="d70e3-125">Agrupando objetos de servicio, puede crear informes para objetos de servicio similares y relacionados.</span><span class="sxs-lookup"><span data-stu-id="d70e3-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="d70e3-126">Por ejemplo, un grupo de objetos de servicio podría constar de dos objetos de servicio: Un objeto de servicio es un kit, y el segundo objeto de servicio es el servicio para instalar el kit.</span><span class="sxs-lookup"><span data-stu-id="d70e3-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="d70e3-127">Para crear grupos de objetos de servicio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d70e3-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="d70e3-128">Haga clic en **Gestión de servicio > Configuración > Objetos de servicio > Grupos de objetos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="d70e3-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="d70e3-129">Haga clic en **Nuevo** para crear un nuevo grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="d70e3-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="d70e3-130">Especifique un nombre exclusivo para el grupo de objetos de servicio y, opcionalmente, una descripción.</span><span class="sxs-lookup"><span data-stu-id="d70e3-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="d70e3-131">Puede asignar objetos de servicio al grupo mediante el formulario **Objetos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="d70e3-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="d70e3-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d70e3-132">See also</span></span>

[<span data-ttu-id="d70e3-133">Crear objetos del servicio</span><span class="sxs-lookup"><span data-stu-id="d70e3-133">Create service objects</span></span>](create-service-objects.md)



