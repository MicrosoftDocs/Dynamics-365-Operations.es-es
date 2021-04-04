---
title: Cambiar entre diseños de proveedor
description: Este tema describe como cambiar la integración de datos de proveedor entre aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 78d4c547f544d95c66490e5610374a5c4598b266
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565608"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="63b8e-103">Cambiar entre diseños de proveedor</span><span class="sxs-lookup"><span data-stu-id="63b8e-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="63b8e-104">Flujo de datos del proveedor</span><span class="sxs-lookup"><span data-stu-id="63b8e-104">Vendor data flow</span></span> 

<span data-ttu-id="63b8e-105">Si elige usar la tabla **Cuenta** para almacenar proveedores del tipo **Organización** y la tabla **Contacto** para almacenar proveedores del tipo **Persona**, configure los siguientes flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="63b8e-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="63b8e-106">De lo contrario, esta configuración no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="63b8e-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="63b8e-107">Utilice el diseño de proveedor extendido para proveedores del tipo Organización</span><span class="sxs-lookup"><span data-stu-id="63b8e-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="63b8e-108">El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="63b8e-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="63b8e-109">Creará un flujo de trabajo para cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="63b8e-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="63b8e-110">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="63b8e-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="63b8e-111">Crear proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="63b8e-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="63b8e-112">Actualizar proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="63b8e-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="63b8e-113">Actualizar proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="63b8e-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="63b8e-114">Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="63b8e-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="63b8e-115">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores en la tabla Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="63b8e-116">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-116">Then select **OK**.</span></span> <span data-ttu-id="63b8e-117">Este flujo de trabajo gestiona el escenario de creación de proveedor para la tabla **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Crear proveedores en el proceso de flujo de trabajo de la tabla Cuentas](media/create_process.png)

2. <span data-ttu-id="63b8e-119">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores en la tabla Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="63b8e-120">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-120">Then select **OK**.</span></span> <span data-ttu-id="63b8e-121">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la tabla **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="63b8e-122">Cree un proceso de flujo de trabajo para la tabla **Cuenta** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="63b8e-123">Cree un proceso de flujo de trabajo para la tabla **Cuenta** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="63b8e-124">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="63b8e-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="63b8e-125">Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Botón convertir a un flujo de trabajo en segundo plano](media/background_workflow.png)

6. <span data-ttu-id="63b8e-127">Active los flujos de trabajo que ha creado para las tablas **Cuenta** y **Proveedor** para comenzar a utilizar la tabla **Cuenta** para almacenar información de proveedores del tipo **Organización**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="63b8e-128">Utilice el diseño de proveedor extendido para proveedores del tipo Persona</span><span class="sxs-lookup"><span data-stu-id="63b8e-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="63b8e-129">El paquete de solución **Dynamics365FinanceExtended** contiene las siguientes plantillas de proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="63b8e-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="63b8e-130">Creará un flujo de trabajo para cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="63b8e-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="63b8e-131">Crear proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="63b8e-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="63b8e-132">Crear proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="63b8e-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="63b8e-133">Actualizar proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="63b8e-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="63b8e-134">Actualizar proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="63b8e-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="63b8e-135">Para crear nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="63b8e-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="63b8e-136">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Crear proveedores de tipo Persona en la tabla Contactos**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="63b8e-137">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-137">Then select **OK**.</span></span> <span data-ttu-id="63b8e-138">Este flujo de trabajo gestiona el escenario de creación de proveedor para la tabla **Contacto**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="63b8e-139">Cree un proceso de flujo de trabajo para la tabla **Proveedor** y seleccione la plantilla de proceso de flujo de trabajo **Actualizar proveedores de tipo Persona en la tabla Contactos**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="63b8e-140">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-140">Then select **OK**.</span></span> <span data-ttu-id="63b8e-141">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la tabla **Contacto**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="63b8e-142">Cree un proceso de flujo de trabajo para la tabla **Contacto** y seleccione la plantilla **Crear proveedores del tipo Persona en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="63b8e-143">Cree un proceso de flujo de trabajo para la tabla **Contacto** y seleccione la plantilla **Actualizar proveedores del tipo Persona en la tabla Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="63b8e-144">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o en segundo plano, dependiendo de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="63b8e-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="63b8e-145">Para configurar un flujo de trabajo como flujo de trabajo en segundo plano, seleccione **Convertir a un flujo de trabajo en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="63b8e-146">Active los flujos de trabajo que ha creado en las tablas **Contacto** y **Proveedor** para comenzar a utilizar la tabla **Contacto** para almacenar información de proveedores del tipo **Persona**.</span><span class="sxs-lookup"><span data-stu-id="63b8e-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]