---
title: Configurar un entorno para la búsqueda de datos maestros
description: Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.
author: kai-cloud
ms.date: 03/31/2021
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
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869097"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a><span data-ttu-id="0385d-103">Configurar un entorno para la búsqueda de datos maestros</span><span class="sxs-lookup"><span data-stu-id="0385d-103">Set up an environment for master data lookup</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="0385d-104">Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="0385d-104">This topic explains how to set up your environment to use the Tax Calculation master data lookup functionality.</span></span>

1. <span data-ttu-id="0385d-105">Configure la integración de Power Platform en Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0385d-105">Set up power platform integration in Lifecycle Services (LCS).</span></span> <span data-ttu-id="0385d-106">Para obtener más información, consulte [Integración de Microsoft Power Platform - Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0385d-106">For more information, see [Microsoft Power Platform integration - Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).</span></span>
2. <span data-ttu-id="0385d-107">Configuración de Dynamics 365 Finance y Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0385d-107">Set up Dynamics 365 Finance and Microsoft Dataverse.</span></span> <span data-ttu-id="0385d-108">Para más información, vea [Obteniendo la solución](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) y [Autenticacion y autorizacion](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span><span class="sxs-lookup"><span data-stu-id="0385d-108">For more information, see [Getting the solution](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) and [Authentication and authorization](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).</span></span>
3. <span data-ttu-id="0385d-109">Importe la *Solución de entidad virtual de servicio fiscal de requisito previo* desde [Entidad virtual de servicio tributario](https://go.microsoft.com/fwlink/?linkid=2158160).</span><span class="sxs-lookup"><span data-stu-id="0385d-109">Import the *Prerequisite tax service virtual entity solution* from the [Tax service virtual entity](https://go.microsoft.com/fwlink/?linkid=2158160).</span></span>
4. <span data-ttu-id="0385d-110">Configure Regulatory Configuration Service (RCS) de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0385d-110">Set up the Dynamics 365 Regulatory Configuration Service (RCS).</span></span> 
5. <span data-ttu-id="0385d-111">Cree una solicitud de servicio para que Microsoft habilite la distribución de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="0385d-111">Create a service request for Microsoft to enable flighting of the following features:</span></span>

      - <span data-ttu-id="0385d-112">ERCdsFeature</span><span class="sxs-lookup"><span data-stu-id="0385d-112">ERCdsFeature</span></span>
      - <span data-ttu-id="0385d-113">TaxServiceCDSFeature</span><span class="sxs-lookup"><span data-stu-id="0385d-113">TaxServiceCDSFeature</span></span>

6. <span data-ttu-id="0385d-114">En Finance, vaya al espacio de trabajo **Administración de funciones** y habilite las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="0385d-114">In Finance, go to the **Feature management** workspace, and enable the following features:</span></span>

      - <span data-ttu-id="0385d-115">(Vista previa) Compatibilidad con orígenes de datos de Informes electrónicos de Dataverse</span><span class="sxs-lookup"><span data-stu-id="0385d-115">(Preview) Electronic reporting Dataverse datasources support</span></span>
      - <span data-ttu-id="0385d-116">(Versión preliminar) Soporte para orígenes de datos de Dataverse del servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="0385d-116">(Preview) Tax Service Dataverse datasources support</span></span>
      - <span data-ttu-id="0385d-117">Características de globalización (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0385d-117">(Preview) Globalization features</span></span>

5. <span data-ttu-id="0385d-118">Inicie sesión en RCS con una cuenta de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="0385d-118">Sign in to RCS using a tenant admin account.</span></span>
6. <span data-ttu-id="0385d-119">Ir a **Informes electrónicos** > **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="0385d-119">Go to **Electronic reporting** > **Connected applications**.</span></span> 
7. <span data-ttu-id="0385d-120">Seleccione **Nuevo** para agregar un registro e ingrese la siguiente información de campo.</span><span class="sxs-lookup"><span data-stu-id="0385d-120">Select **New** to add a record, and enter the following field information.</span></span> 

   - <span data-ttu-id="0385d-121">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="0385d-121">In the **Name** field, enter a name.</span></span>
   - <span data-ttu-id="0385d-122">En el campo **Tipo**, seleccione **Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="0385d-122">In the **Type** field, select **Dataverse**.</span></span>
   - <span data-ttu-id="0385d-123">En el campo **Aplicación**, introduzca la URL de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0385d-123">In the **Application** field, enter your Dataverse URL.</span></span>
   - <span data-ttu-id="0385d-124">En el campo **Inquilino**, ingrese su inquilino.</span><span class="sxs-lookup"><span data-stu-id="0385d-124">In the **Tenant** field, enter your tenant.</span></span>
   - <span data-ttu-id="0385d-125">En el campo **URL personalizada**, ingrese su URL de Dataverse y adjúntela con "/api/data/v9.1".</span><span class="sxs-lookup"><span data-stu-id="0385d-125">In the **Custom URL** field, enter your Dataverse URL and append it with "/api/data/v9.1".</span></span>

8. <span data-ttu-id="0385d-126">Seleccione **Verificar la conexión** y finalice el proceso de conexión.</span><span class="sxs-lookup"><span data-stu-id="0385d-126">Select **Check connection**, and finish the connection process.</span></span> 

   <span data-ttu-id="0385d-127">[![Compruebe el botón de conexión](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span><span class="sxs-lookup"><span data-stu-id="0385d-127">[![Check connection button](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)</span></span>

9. <span data-ttu-id="0385d-128">Ir a **Informes electrónicos** > **Configuraciones de impuestos** e importar configuraciones de impuestos desde [Configuraciones de impuestos](https://go.microsoft.com/fwlink/?linkid=2158352).</span><span class="sxs-lookup"><span data-stu-id="0385d-128">Go to **Electronic reporting** > **Tax configurations**, and import tax configurations from [Tax configurations](https://go.microsoft.com/fwlink/?linkid=2158352).</span></span>

   <span data-ttu-id="0385d-129">[![Página de configuraciones de impuestos, árbol del modelo de datos de impuestos](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span><span class="sxs-lookup"><span data-stu-id="0385d-129">[![Tax configurations page, Tax data model tree](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)</span></span>

10. <span data-ttu-id="0385d-130">Ve a **Mapeo del modelo de documento imponible** o **Mapeo de modelos de Dataverse** si está utilizando una configuración de Microsoft y, en el campo **Aplicación conectada**, seleccione el registro que creó en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="0385d-130">Go to the **Taxable document model mapping**, or **Dataverse Model Mapping** if you are using a Microsoft configuration, and in the **Connected application** field, select the record that you created in step 7.</span></span>
11. <span data-ttu-id="0385d-131">Establezca **Predeterminado para la asignación de modelo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0385d-131">Set **Default for model mapping** to **Yes**.</span></span>

   <span data-ttu-id="0385d-132">[![Página de asignación de modelos](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span><span class="sxs-lookup"><span data-stu-id="0385d-132">[![Model mapping page](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
