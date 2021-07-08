---
title: Habilitar Power BI para Contabilidad de inventario global
description: Este tema describe cómo habilitar Microsoft Power BI para la Contabilidad de inventario global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273221"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="7e8de-103">Habilitar Power BI para Contabilidad de inventario global</span><span class="sxs-lookup"><span data-stu-id="7e8de-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="7e8de-104">Puede anclar mosaicos, paneles e informes desde su cuenta de [PowerBI.com](https://powerbi.com/) a su area de trabajo de la aplicación de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="7e8de-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e8de-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7e8de-105">Prerequisites</span></span>

<span data-ttu-id="7e8de-106">Deben cumplirse los siguientes requisitos previos antes de poder habilitar informes de Power BI:</span><span class="sxs-lookup"><span data-stu-id="7e8de-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="7e8de-107">Debe ser administrador del sistema en la aplicación Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="7e8de-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="7e8de-108">Debe tener una cuenta de [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="7e8de-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="7e8de-109">Debe tener al menos un panel y un informe en su cuenta de Power BI.</span><span class="sxs-lookup"><span data-stu-id="7e8de-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="7e8de-110">Debe ser administrador de su cuenta de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7e8de-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="7e8de-111">El dominio de Azure AD debe ser el mismo que usó para su cuenta de [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="7e8de-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="7e8de-112">Configurar</span><span class="sxs-lookup"><span data-stu-id="7e8de-112">Setup</span></span>

<span data-ttu-id="7e8de-113">Para configurar la integración de Power BI, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7e8de-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="7e8de-114">Inicie sesión en [Microsoft Dynamics LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="7e8de-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="7e8de-115">Vaya a **Biblioteca de activos compartidos**, seleccione **Modelo de informe de Power BI** como tipo de activo y descargue el paquete **Contabilidad global de inventarios**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="7e8de-116">Inicie sesión en [PowerBI.com](https://app.powerbi.com/) y suba el archivo de informe de Power BI de **Contabilidad global de inventarios** siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7e8de-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="7e8de-117">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-117">Select **New**.</span></span>
    1. <span data-ttu-id="7e8de-118">Seleccione **Cargar un archivo**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="7e8de-119">Seleccione el archivo de informe de Power BI **Contabilidad global de inventarios**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="7e8de-120">Configure el informe de Power BI **Contabilidad global de inventarios** siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7e8de-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="7e8de-121">Vaya a **Mi espacio de trabajo**, busque el conjunto de datos de Contabilidad de inventario global y, a continuación, en el menú **Opciones**, seleccione **Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="7e8de-122">En **Configuración de la contabilidad de inventario global**, expanda **Parámetros** y actualice todos los parámetros según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7e8de-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="7e8de-123">Registre la aplicación como se describe en [Configurar la integración PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span><span class="sxs-lookup"><span data-stu-id="7e8de-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="7e8de-124">Integre el archivo de informe de Power BI **Contabilidad global de inventarios** en Dynamics 365 Supply Chain Management siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7e8de-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="7e8de-125">Vaya a **Administración del sistema \> Configuración \> Configuración de PowerBI.com**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="7e8de-126">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="7e8de-127">Seleccione **Habilita la integración PowerBI.Com**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="7e8de-128">En el campo **ID de aplicación**, introduzca el id. de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e8de-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="7e8de-129">En el campo **Clave de aplicación**, introduzca la clave de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e8de-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="7e8de-130">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-130">Select **Save**.</span></span>

1. <span data-ttu-id="7e8de-131">Actualice la página para que aparezca el cuadro de diálogo de inicio de sesión de Power BI.</span><span class="sxs-lookup"><span data-stu-id="7e8de-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="7e8de-132">En la pestaña **Opciones**, seleccione **Abrir catálogo de informes** y luego seleccione el archivo de informe de Power BI **Contabilidad global de inventarios** que cargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e8de-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="7e8de-133">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="7e8de-133">Refresh the page.</span></span> <span data-ttu-id="7e8de-134">Debería ver que se ha agregado su informe.</span><span class="sxs-lookup"><span data-stu-id="7e8de-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="7e8de-135">En **Informes de Power BI**, seleccione el vínculo **Contabilidad global de inventarios**.</span><span class="sxs-lookup"><span data-stu-id="7e8de-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="7e8de-136">Para obtener más información, consulte [Configurar la integración de PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="7e8de-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>
