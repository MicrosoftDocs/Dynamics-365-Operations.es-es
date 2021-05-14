---
title: Configurar un entorno para la búsqueda de datos maestros
description: Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924163"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="d3f73-103">Configurar un entorno para la búsqueda de datos maestros</span><span class="sxs-lookup"><span data-stu-id="d3f73-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3f73-104">Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="d3f73-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="d3f73-105">Configure la integración de Power Platform en Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d3f73-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="d3f73-106">Para obtener más información, consulte [Integración de Microsoft Power Platform - Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3f73-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="d3f73-107">Configuración de Dynamics 365 Finance y Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d3f73-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="d3f73-108">Para más información, vea [Obteniendo la solución](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) y [Autenticacion y autorizacion](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="d3f73-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="d3f73-109">Configure las entidades siguientes.</span><span class="sxs-lookup"><span data-stu-id="d3f73-109">Set up the following entities.</span></span> <span data-ttu-id="d3f73-110">Para obtener más información, consulte [Habilitar entidades virtuales](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="d3f73-110">For more information, see [Enabling virtual entities](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).</span></span>
      - <span data-ttu-id="d3f73-111">CompanyInfoEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-111">CompanyInfoEntity</span></span>
      - <span data-ttu-id="d3f73-112">CurrencyEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-112">CurrencyEntity</span></span>
      - <span data-ttu-id="d3f73-113">CustCustomerV3Entity</span><span class="sxs-lookup"><span data-stu-id="d3f73-113">CustCustomerV3Entity</span></span>
      - <span data-ttu-id="d3f73-114">DeliveryTermsEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-114">DeliveryTermsEntity</span></span>
      - <span data-ttu-id="d3f73-115">EcoResProductCategoryEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-115">EcoResProductCategoryEntity</span></span>
      - <span data-ttu-id="d3f73-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="d3f73-116">EcoResReleasedProductV2Entity</span></span>
      - <span data-ttu-id="d3f73-117">LogisticsAddressCityEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-117">LogisticsAddressCityEntity</span></span>
      - <span data-ttu-id="d3f73-118">LogisticsAddressCountryRegionTranslationEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-118">LogisticsAddressCountryRegionTranslationEntity</span></span>
      - <span data-ttu-id="d3f73-119">LogisticsAddressStateEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-119">LogisticsAddressStateEntity</span></span>
      - <span data-ttu-id="d3f73-120">PurchProcurementChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-120">PurchProcurementChargeCDSEntity</span></span>
      - <span data-ttu-id="d3f73-121">SalesChargeCDSEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-121">SalesChargeCDSEntity</span></span>
      - <span data-ttu-id="d3f73-122">TaxGroupEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-122">TaxGroupEntity</span></span>
      - <span data-ttu-id="d3f73-123">TaxItemGroupHeadingEntity</span><span class="sxs-lookup"><span data-stu-id="d3f73-123">TaxItemGroupHeadingEntity</span></span>
      - <span data-ttu-id="d3f73-124">VendVendorV2Entity</span><span class="sxs-lookup"><span data-stu-id="d3f73-124">VendVendorV2Entity</span></span>
4. <span data-ttu-id="d3f73-125">Configure Regulatory Configuration Service (RCS) de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d3f73-125">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="d3f73-126">Cree una solicitud de servicio para que Microsoft habilite la distribución de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="d3f73-126">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="d3f73-127">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="d3f73-127">ERCdsFeature</span></span>
      - <span data-ttu-id="d3f73-128">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="d3f73-128">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="d3f73-129">Vaya al espacio de trabajo **Administración de funciones** y habilite las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3f73-129">Go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="d3f73-130">(Vista previa) Compatibilidad con orígenes de datos de Informes electrónicos de Dataverse</span><span class="sxs-lookup"><span data-stu-id="d3f73-130">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="d3f73-131">(Versión preliminar) Soporte para orígenes de datos de Dataverse del servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="d3f73-131">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="d3f73-132">Características de globalización (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d3f73-132">(Preview) Globalization features</span></span>

5. <span data-ttu-id="d3f73-133">Inicie sesión en RCS con una cuenta de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d3f73-133">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="d3f73-134">Ir a **Informes electrónicos** > **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="d3f73-134">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="d3f73-135">Seleccione **Nuevo** para agregar un registro e ingrese la siguiente información de campo.</span><span class="sxs-lookup"><span data-stu-id="d3f73-135">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="d3f73-136">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="d3f73-136">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="d3f73-137">En el campo **Tipo**, seleccione **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="d3f73-137">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="d3f73-138">En el campo **Aplicación**, introduzca la URL de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d3f73-138">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="d3f73-139">En el campo **Inquilino**, ingrese su inquilino.</span><span class="sxs-lookup"><span data-stu-id="d3f73-139">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="d3f73-140">En el campo **URL personalizada**, ingrese su URL de Dataverse y adjúntela con "/api/data/v9.1".</span><span class="sxs-lookup"><span data-stu-id="d3f73-140">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="d3f73-141">Seleccione **Verificar la conexión** y finalice el proceso de conexión.</span><span class="sxs-lookup"><span data-stu-id="d3f73-141">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="d3f73-142">[![Compruebe el botón de conexión](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="d3f73-142">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="d3f73-143">Ir a **Informes electrónicos** > **Configuraciones de impuestos** e importar configuraciones de impuestos desde [Configuraciones de impuestos](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="d3f73-143">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="d3f73-144">[![Página de configuraciones de impuestos, árbol del modelo de datos de impuestos](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="d3f73-144">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="d3f73-145">Ve a **Mapeo del modelo de documento imponible** o **Mapeo de modelos de Dataverse** si está utilizando una configuración de Microsoft y, en el campo **Aplicación conectada**, seleccione el registro que creó en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="d3f73-145">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="d3f73-146">Establezca **Predeterminado para la asignación de modelo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d3f73-146">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="d3f73-147">[![Página de asignación de modelos](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="d3f73-147">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
