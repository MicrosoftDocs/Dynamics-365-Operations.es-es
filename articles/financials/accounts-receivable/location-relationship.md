---
title: "Agregar ubicación y tipos de relaciones de las partes"
description: "En este tema se explica cómo agregar una nueva ubicación y un tipo de relación de las partes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bf971bc6cf4b11de6381e369235d582678d074fc
ms.openlocfilehash: 8de914e0fb853cdc9aa36e55a02156757793abc3
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2018

---

# <a name="add-new-location-roles-and-party-relationship-types"></a><span data-ttu-id="90318-103">Agregar nuevos roles de ubicación y tipos de relaciones de las partes</span><span class="sxs-lookup"><span data-stu-id="90318-103">Add new location roles and party relationship types</span></span> 

## <a name="add-new-location-roles"></a><span data-ttu-id="90318-104">Agregar nuevas funciones de ubicación</span><span class="sxs-lookup"><span data-stu-id="90318-104">Add new location roles</span></span>

<span data-ttu-id="90318-105">Existen dos formas de agregar nuevos roles de ubicación para la dirección y la información de contacto:</span><span class="sxs-lookup"><span data-stu-id="90318-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="90318-106">Agréguelo a través de la página **Propósito de la dirección y de la información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="90318-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="90318-107">El nuevo rol se guardará en la tabla **LogisticsLocationRole** con el tipo = 0, lo que indica que la función no es un rol del sistema definido en la enumeración **LogisticsLocationRoleType** y sus extensiones.</span><span class="sxs-lookup"><span data-stu-id="90318-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="90318-108">Un usuario podrá utilizar esta función al crear la dirección o la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="90318-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Propósito de la dirección y de la información del contenido](media/Address-Contact.PNG)

-  <span data-ttu-id="90318-110">Agréguelo a la extensión de la enumeración **LogisticsLocationRoleType** y deje que se complete mediante el proceso de sincronización de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90318-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="90318-111">Crear una extensión para la enumeración **LogisticsLocationRoleType** y agregue el nuevo rol en la extensión.</span><span class="sxs-lookup"><span data-stu-id="90318-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="90318-113">Cree un nuevo archivo de recursos para el nuevo rol y, a continuación, asigne un valor para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="90318-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Nuevo archivo de recursos](media/Resource.PNG)
        
    3.  <span data-ttu-id="90318-115">Cree una clase de rellenado de datos y proporcione un método de controlador para rellenar el nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="90318-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Rellenado de datos](media/Dirdata.PNG)

    4.  <span data-ttu-id="90318-117">Para probar a rellenar el nuevo rol de ubicación, puede crear una clase ejecutable y denominar DirDataPopulation::insertLogisticsLocationRoles() en Main().</span><span class="sxs-lookup"><span data-stu-id="90318-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="90318-118">Una vez completado este proceso, debe ver el nuevo rol rellenado en la tabla **LogisticsLocationRole** con tipo \> 0.</span><span class="sxs-lookup"><span data-stu-id="90318-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="90318-119">El nuevo rol se mostrará en la página **Propósito de la dirección y de la información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="90318-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Insertar nueva ubicación](media/InsertNewLocation.PNG)

## <a name="add-new-party-relationship-types"></a><span data-ttu-id="90318-121">Agregar nuevos tipos de relación de terceros</span><span class="sxs-lookup"><span data-stu-id="90318-121">Add new party relationship types</span></span> 

<span data-ttu-id="90318-122">Existen dos formas de agregar un nuevo tipo de relación:</span><span class="sxs-lookup"><span data-stu-id="90318-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="90318-123">Agréguelo a través de la página **Tipos de relación**.</span><span class="sxs-lookup"><span data-stu-id="90318-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="90318-124">La nueva relación se guardará en **DirRelationshipTypeTable** con systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="90318-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Tipos de relaciones](media/Relationship.PNG)

-  <span data-ttu-id="90318-126">Agréguelo a la extensión de la enumeración **DirSystemRelationshipType** y deje que se complete mediante el proceso de sincronización de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="90318-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="90318-127">Crear una extensión para la enumeración **DirSystemRelationshipType** y agregar el nuevo tipo de relación.</span><span class="sxs-lookup"><span data-stu-id="90318-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="90318-128">Crear un inicializador para este nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="90318-128">Create an initializer for this new type.</span></span> <span data-ttu-id="90318-129">Puede encontrar varios ejemplos en el código del núcleo, uno de ellos es **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="90318-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="90318-130">Se trata de una clase de inicializador para el tipo de relación de las partes "Secundaria".</span><span class="sxs-lookup"><span data-stu-id="90318-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="90318-131">Puede empezar con su inicializador copiando y pegando este código y, a continuación, actualizar las áreas resaltadas.</span><span class="sxs-lookup"><span data-stu-id="90318-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="90318-133">Para probar a rellenar el nuevo tipo de relación, puede crear una clase ejecutable y denominar DirDataPopulation::insertDirRelationshipTypes() en Main().</span><span class="sxs-lookup"><span data-stu-id="90318-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="90318-134">Solo debería ver el nuevo tipo de relación en **DirRelationshipTypeTable** y el nuevo tipo de relación estará disponible en la página **Tipos de relación** .</span><span class="sxs-lookup"><span data-stu-id="90318-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Clase ejecutable](media/Runnable.PNG)

