---
title: Cambiar entre diseños de proveedor
description: Este tema describe como cambiar la integración de datos de proveedor entre aplicaciones de Finance and Operations y Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744474"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="6f113-103">Cambiar entre diseños de proveedor</span><span class="sxs-lookup"><span data-stu-id="6f113-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="6f113-104">Flujo de datos del proveedor</span><span class="sxs-lookup"><span data-stu-id="6f113-104">Vendor data flow</span></span> 

<span data-ttu-id="6f113-105">Si elige usar la tabla **Cuenta** para almacenar proveedores del tipo **Organización** y la tabla **Contacto** para almacenar proveedores del tipo **Persona**, configure los siguientes flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f113-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="6f113-106">De lo contrario, esta configuración no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="6f113-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="6f113-107">Utilice el diseño de proveedor extendido para proveedores del tipo Organización</span><span class="sxs-lookup"><span data-stu-id="6f113-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="6f113-108">El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f113-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="6f113-109">Creará un flujo de trabajo para cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f113-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="6f113-110">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="6f113-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="6f113-111">Crear proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="6f113-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="6f113-112">Actualizar proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="6f113-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="6f113-113">Actualizar proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="6f113-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="6f113-114">Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6f113-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="6f113-115">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores en la tabla Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="6f113-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="6f113-116">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f113-116">Then select **OK**.</span></span> <span data-ttu-id="6f113-117">Este flujo de trabajo gestiona el escenario de creación de proveedor para la tabla **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="6f113-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Crear proveedores en el proceso de flujo de trabajo de la tabla Cuentas](media/create_process.png)

2. <span data-ttu-id="6f113-119">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores en la tabla Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="6f113-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="6f113-120">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f113-120">Then select **OK**.</span></span> <span data-ttu-id="6f113-121">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la tabla **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="6f113-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="6f113-122">Cree un proceso de flujo de trabajo para la tabla **Cuenta** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="6f113-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="6f113-123">Cree un proceso de flujo de trabajo para la tabla **Cuenta** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="6f113-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="6f113-124">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="6f113-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="6f113-125">Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="6f113-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Botón convertir a un flujo de trabajo en segundo plano](media/background_workflow.png)

6. <span data-ttu-id="6f113-127">Active los flujos de trabajo que ha creado para las tablas **Cuenta** y **Proveedor** para comenzar a utilizar la tabla **Cuenta** para almacenar información de proveedores del tipo **Organización**.</span><span class="sxs-lookup"><span data-stu-id="6f113-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="6f113-128">Utilice el diseño de proveedor extendido para proveedores del tipo Persona</span><span class="sxs-lookup"><span data-stu-id="6f113-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="6f113-129">El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f113-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="6f113-130">Creará un flujo de trabajo para cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f113-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="6f113-131">Crear proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="6f113-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="6f113-132">Crear proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="6f113-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="6f113-133">Actualizar proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="6f113-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="6f113-134">Actualizar proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="6f113-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="6f113-135">Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6f113-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="6f113-136">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores de tipo Persona en la tabla Contactos**.</span><span class="sxs-lookup"><span data-stu-id="6f113-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="6f113-137">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f113-137">Then select **OK**.</span></span> <span data-ttu-id="6f113-138">Este flujo de trabajo gestiona el escenario de creación de proveedor para la tabla **Contacto**.</span><span class="sxs-lookup"><span data-stu-id="6f113-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="6f113-139">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores de tipo Persona en la tabla Contactos**.</span><span class="sxs-lookup"><span data-stu-id="6f113-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="6f113-140">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f113-140">Then select **OK**.</span></span> <span data-ttu-id="6f113-141">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la tabla **Contacto**.</span><span class="sxs-lookup"><span data-stu-id="6f113-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="6f113-142">Cree un proceso de flujo de trabajo para la tabla **Contacto** y seleccione la plantilla **Crear proveedores del tipo Persona en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="6f113-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="6f113-143">Cree un proceso de flujo de trabajo para la tabla **Contacto** y seleccione la plantilla **Actualizar proveedores del tipo Persona en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="6f113-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="6f113-144">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="6f113-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="6f113-145">Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="6f113-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="6f113-146">Active los flujos de trabajo que ha creado en las tablas **Contacto** y **Proveedor** para comenzar a utilizar la tabla **Contacto** para almacenar información de proveedores del tipo **Persona**.</span><span class="sxs-lookup"><span data-stu-id="6f113-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>
