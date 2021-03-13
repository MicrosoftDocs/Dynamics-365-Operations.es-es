---
title: Crear una cuenta de almacenamiento en Azure y un almacén de claves
description: Este tema explica cómo crear una cuenta de almacenamiento de Azure y un almacén de claves.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d076aa5230437d1ef90f6b46d49ee4dea526db24
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104238"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="74c26-103">Crear una cuenta de almacenamiento en Azure y un almacén de claves</span><span class="sxs-lookup"><span data-stu-id="74c26-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="74c26-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="74c26-104">Prerequisites</span></span>

<span data-ttu-id="74c26-105">Antes de que pueda completar los pasos de este tema, debe asegurarse de que se han completado las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="74c26-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="74c26-106">Crear un recurso de almacén de claves en Azure.</span><span class="sxs-lookup"><span data-stu-id="74c26-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="74c26-107">Para obtener información, vea [Acerca de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="74c26-107">For more information, see [About Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="74c26-108">Cree una cuenta de Azure Storage (Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="74c26-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="74c26-109">Para más información, vea [Mantenimiento de la cuenta de Azure Storage](https://docs.microsoft.com/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="74c26-109">For more information, see [Maintaining Azure Storage Account](https://docs.microsoft.com/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="74c26-110">Información general</span><span class="sxs-lookup"><span data-stu-id="74c26-110">Overview</span></span>

<span data-ttu-id="74c26-111">En este tema, completará dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="74c26-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="74c26-112">Configure la cuenta de almacenamiento de Azure para obtener el URI de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74c26-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="74c26-113">Configure el almacén de claves para almacenar el URI de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74c26-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="74c26-114">Configure la cuenta de almacenamiento de Azure para obtener el URI de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="74c26-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="74c26-115">Abra la cuenta de almacenamiento que planea usar con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="74c26-115">Open the storage account that you plan to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="74c26-116">Ir **Servicio blob** \> **Contenedores** y cree un nuevo contenedor.</span><span class="sxs-lookup"><span data-stu-id="74c26-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="74c26-117">Introduzca un nombre para el contenedor y establezca el campo **Nivel de acceso público** en **Privado (sin acceso anónimo)**.</span><span class="sxs-lookup"><span data-stu-id="74c26-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="74c26-118">Abra el contenedor y vaya a **Configuraciones \> Directiva de acceso**.</span><span class="sxs-lookup"><span data-stu-id="74c26-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="74c26-119">Seleccione **Agregar política** para agregar una política de acceso almacenada.</span><span class="sxs-lookup"><span data-stu-id="74c26-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="74c26-120">Seleccione los campos **Identificador** y **Permisos** según corresponda.</span><span class="sxs-lookup"><span data-stu-id="74c26-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="74c26-121">En el campo **Permisos**, debe seleccionar todos los permisos.</span><span class="sxs-lookup"><span data-stu-id="74c26-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Otorgar permiso de almacenamiento de blobs](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="74c26-123">Ingrese las fechas de inicio y vencimiento.</span><span class="sxs-lookup"><span data-stu-id="74c26-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="74c26-124">La fecha de caducidad debería ser futura.</span><span class="sxs-lookup"><span data-stu-id="74c26-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="74c26-125">Seleccione **Aceptar** para guardar la política y luego guardar los cambios en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="74c26-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="74c26-126">Regrese a la cuenta de almacenamiento y abra **Explorador de almacenamiento (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="74c26-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="74c26-127">Haga clic con el botón derecho en el contenedor y luego seleccione **Obtener firma de acceso compartido**.</span><span class="sxs-lookup"><span data-stu-id="74c26-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="74c26-128">En el cuadro de diálogo **Firma de acceso compartido**, copie y almacene el valor en el campo **URI**.</span><span class="sxs-lookup"><span data-stu-id="74c26-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="74c26-129">Este valor se utilizará en el siguiente procedimiento y se denominará *URI de firma de acceso compartido*.</span><span class="sxs-lookup"><span data-stu-id="74c26-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Seleccionar y copiar el valor de URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="74c26-131">Configure el almacén de claves para almacenar el URI de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="74c26-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="74c26-132">Abra el almacén de claves que tiene intención de usar con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="74c26-132">Open the key vault that you intend to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="74c26-133">Ir **Configuraciones** \> **Misterios** y luego seleccione **Generar/Importar** para crear un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="74c26-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="74c26-134">En la página **Crea un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="74c26-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="74c26-135">Permite escribir el nombre del secreto.</span><span class="sxs-lookup"><span data-stu-id="74c26-135">Enter the name of the secret.</span></span> <span data-ttu-id="74c26-136">Este nombre se utilizará durante la configuración del servicio en el Servicio de configuración reguladora (RCS) y se denominará el *nombre secreto del almacén de claves*.</span><span class="sxs-lookup"><span data-stu-id="74c26-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="74c26-137">En el campo **Valor**, seleccione **URI de firma de acceso compartido** y luego seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="74c26-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="74c26-138">Configure la política de acceso para otorgar al complemento de facturación electrónica el nivel correcto de acceso seguro al secreto que creó.</span><span class="sxs-lookup"><span data-stu-id="74c26-138">Set up the access policy to grant the Electronic invoicing add-on the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="74c26-139">Ir **Configuraciones \> Política de acceso** y seleccione **Agregar política de acceso**.</span><span class="sxs-lookup"><span data-stu-id="74c26-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="74c26-140">Establezca los permisos secretos para las operaciones **Obtener** y **Lista**.</span><span class="sxs-lookup"><span data-stu-id="74c26-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Otorgar acceso al servicio](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="74c26-142">Establezca los permisos de certificado para las operaciones **Obtener** y **Lista**.</span><span class="sxs-lookup"><span data-stu-id="74c26-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Otorgar permiso de certificado](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="74c26-144">En el cuadro de diálogo **Principal**, seleccione el principal agregando **Complemento de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="74c26-144">In the **Principal** dialog box, select the principal by adding **Electronic invoicing add-on**.</span></span>
10. <span data-ttu-id="74c26-145">Seleccione **Agregar** y luego seleccione **Guardar cambios de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="74c26-145">Select **Add**, and then select **Save Key Vault changes**.</span></span>
11. <span data-ttu-id="74c26-146">En la página **Visión de conjunto**, copie el valor **Nombre DNS** para el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="74c26-146">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="74c26-147">Este valor se utilizará durante la configuración del servicio en RCS y se denominará *URI del almacén de claves*.</span><span class="sxs-lookup"><span data-stu-id="74c26-147">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>
