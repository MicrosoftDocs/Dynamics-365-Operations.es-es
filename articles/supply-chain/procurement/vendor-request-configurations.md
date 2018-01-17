---
title: Configuraciones de solicitud de proveedor
description: Este tema describe los campos que hay que rellenar en una nueva solicitud del proveedor.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 57297a5798004f959a53513b88750866083beee7
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---

# <a name="vendor-request-configurations"></a><span data-ttu-id="9ebfc-103">Configuraciones de solicitud de proveedor</span><span class="sxs-lookup"><span data-stu-id="9ebfc-103">Vendor request configurations</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="9ebfc-104">Para completar una solicitud del proveedor, una persona de contacto del proveedor debe completar el asistente de registro del proveedor potencial.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="9ebfc-105">En el formulario **Configuraciones de la solicitud del proveedor**, puede crear perfiles que especifiquen campos necesarios y campos visibles en el asistente de registro del proveedor potencial.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="9ebfc-106">El asistente de registro del proveedor comenzará por preguntar al usuario del proveedor potencial en qué país/región opera el proveedor.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="9ebfc-107">Esta información determina la configuración aplicable.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="9ebfc-108">Si no se define ninguna configuración específica para un país o región, se usará una configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="9ebfc-109">Establecer la configuración de la solicitud del proveedor</span><span class="sxs-lookup"><span data-stu-id="9ebfc-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="9ebfc-110">De forma predeterminada, hay una configuración del proveedor disponible en el formulario Configuraciones de la solicitud del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="9ebfc-111">No es posible selecionar el país/regiones para la configuración predeterminada, por lo que la sección **Países o regiones** no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1.  <span data-ttu-id="9ebfc-112">Haga click en **Adquisición y abastecimiento** > **Configuración** > **Proveedores** y, a continuación haga click en **Configuraciones de la solicitud del proveedor**.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="9ebfc-113">Haga clic en la pestaña **Campos** para establecer el estado de los campos mencionados.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
-   <span data-ttu-id="9ebfc-114">Oculto (no visible)</span><span class="sxs-lookup"><span data-stu-id="9ebfc-114">Hidden (Not visible)</span></span>
-   <span data-ttu-id="9ebfc-115">Se muestra (visible pero no obligatorio)</span><span class="sxs-lookup"><span data-stu-id="9ebfc-115">Displayed (Visible but not mandatory)</span></span>
-   <span data-ttu-id="9ebfc-116">Necesario (visible y obligatorio)</span><span class="sxs-lookup"><span data-stu-id="9ebfc-116">Required (Visible and mandatory)</span></span>
3.  <span data-ttu-id="9ebfc-117">Haga clic en la pestaña **Contenido** para especificar si el texto se va a mostrar en el asistente y si debe haber una confirmación que el usuario del proveedor potencial deba aceptar antes de ir al paso siguiente del asistente.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="9ebfc-118">Se solicitará la aceptación de los términos y condiciones para que el usuario pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="9ebfc-119">También puede introducir un mensaje de confirmación que se mostrará cuando concluya el asistente y puede agregar uno o varios cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="9ebfc-120">Creación de una configuración de proveedor para un país o región específicos</span><span class="sxs-lookup"><span data-stu-id="9ebfc-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="9ebfc-121">Haga click en **Adquisición y abastecimiento** > **Configuración** > **Proveedores** y, a continuación haga click en **Configuraciones de la solicitud del proveedor**.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="9ebfc-122">Haga click en **Nuevo** para crear una nueva configuración y proporcione un nombre para la configuración.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="9ebfc-123">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-123">Click **Save**.</span></span>
4.  <span data-ttu-id="9ebfc-124">Abra la pestaña **País/regiones** para seleccionar el país/región para el que se usará la configuración.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="9ebfc-125">Complete la configuración siguiendo las directrices para la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ebfc-125">Complete the configuration by following the guidelines for the default configuration.</span></span>

