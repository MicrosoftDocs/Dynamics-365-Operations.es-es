---
title: Cambiar entre diseños de proveedor
description: Este tema describe como cambiar la integración de datos de proveedor entre aplicaciones de Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: ffd7a4c01810578b4abb6942aeff76e5147fafa9
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173048"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="9e681-103">Cambiar entre diseños de proveedor</span><span class="sxs-lookup"><span data-stu-id="9e681-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="9e681-104">Flujo de datos del proveedor</span><span class="sxs-lookup"><span data-stu-id="9e681-104">Vendor data flow</span></span> 

<span data-ttu-id="9e681-105">Si elige usar la entidad **Cuenta** para almacenar proveedores del tipo **Organización** y la entidad **Contacto** para almacenar proveedores del tipo **Persona**, configure los siguientes flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e681-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="9e681-106">De lo contrario, esta configuración no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="9e681-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="9e681-107">Utilice el diseño de proveedor extendido para proveedores del tipo Organización</span><span class="sxs-lookup"><span data-stu-id="9e681-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="9e681-108">El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e681-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="9e681-109">Creará un flujo de trabajo para cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="9e681-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="9e681-110">Crear proveedores en la entidad Cuentas</span><span class="sxs-lookup"><span data-stu-id="9e681-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="9e681-111">Crear proveedores en la entidad Proveedores</span><span class="sxs-lookup"><span data-stu-id="9e681-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="9e681-112">Actualizar proveedores en la entidad Cuentas</span><span class="sxs-lookup"><span data-stu-id="9e681-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="9e681-113">Actualizar proveedores en la entidad Proveedores</span><span class="sxs-lookup"><span data-stu-id="9e681-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="9e681-114">Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e681-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="9e681-115">Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilal de proceso de flujo de trabajo **Crear proveedores en la entidad Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="9e681-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="9e681-116">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e681-116">Then select **OK**.</span></span> <span data-ttu-id="9e681-117">Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="9e681-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Crear proveedores en el proceso de flujo de trabajo de la entidad Cuentas](media/create_process.png)

2. <span data-ttu-id="9e681-119">Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilal de proceso de flujo de trabajo **Actualizar proveedores en la entidad Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="9e681-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="9e681-120">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e681-120">Then select **OK**.</span></span> <span data-ttu-id="9e681-121">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="9e681-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="9e681-122">Cree un proceso de flujo de trabajo para la entidad **Cuenta** y seleccione la plantilal de proceso de flujo de trabajo **Crear proveedores en la entidad Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9e681-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="9e681-123">Cree un proceso de flujo de trabajo para la entidad **Cuenta** y seleccione la plantilal de proceso de flujo de trabajo **Actualizar proveedores en la entidad Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9e681-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="9e681-124">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="9e681-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="9e681-125">Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="9e681-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Botón convertir a un flujo de trabajo en segundo plano](media/background_workflow.png)

6. <span data-ttu-id="9e681-127">Active los flujos de trabajo que ha creado para las entidades **Cuenta** y **Proveedor** para comenzar a utilizar la entidad **Cuenta** para almacenar información de proveedores del tipo **Organización**.</span><span class="sxs-lookup"><span data-stu-id="9e681-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="9e681-128">Utilice el diseño de proveedor extendido para proveedores del tipo Persona</span><span class="sxs-lookup"><span data-stu-id="9e681-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="9e681-129">El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e681-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="9e681-130">Creará un flujo de trabajo para cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="9e681-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="9e681-131">Crear proveedores de tipo Persona en la entidad Proveedores</span><span class="sxs-lookup"><span data-stu-id="9e681-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="9e681-132">Crear proveedores de tipo Persona en la entidad Contactos</span><span class="sxs-lookup"><span data-stu-id="9e681-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="9e681-133">Actualizar proveedores de tipo Persona en la entidad Contactos</span><span class="sxs-lookup"><span data-stu-id="9e681-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="9e681-134">Actualizar proveedores de tipo Persona en la entidad Proveedores</span><span class="sxs-lookup"><span data-stu-id="9e681-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="9e681-135">Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e681-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="9e681-136">Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilal de proceso de flujo de trabajo **Crear proveedores de tipo Persona en la entidad Contactos**.</span><span class="sxs-lookup"><span data-stu-id="9e681-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="9e681-137">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e681-137">Then select **OK**.</span></span> <span data-ttu-id="9e681-138">Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Contacto**.</span><span class="sxs-lookup"><span data-stu-id="9e681-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="9e681-139">Cree un proceso de flujo de trabajo para la entidad **Proveedor** y seleccione la plantilal de proceso de flujo de trabajo **Actualizar proveedores de tipo Persona en la entidad Contactos**.</span><span class="sxs-lookup"><span data-stu-id="9e681-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="9e681-140">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e681-140">Then select **OK**.</span></span> <span data-ttu-id="9e681-141">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Contacto**.</span><span class="sxs-lookup"><span data-stu-id="9e681-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="9e681-142">Cree un proceso de flujo de trabajo para la entidad **Contacto** y seleccione la plantilal **Crear proveedores del tipo Persona en la entidad Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9e681-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="9e681-143">Cree un proceso de flujo de trabajo para la entidad **Contacto** y seleccione la plantilal **Actualizar proveedores del tipo Persona en la entidad Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9e681-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="9e681-144">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="9e681-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="9e681-145">Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="9e681-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="9e681-146">Active los flujos de trabajo que ha creado en la entidad **Contacto** y **Proveedor** para comenzar a utilizar la entidad **Contacto** para almacenar información de proveedores del tipo **Persona**.</span><span class="sxs-lookup"><span data-stu-id="9e681-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
