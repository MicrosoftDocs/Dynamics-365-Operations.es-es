---
title: Orden de ejecución para la sincronización inicial de aplicaciones de Finance and Operations y Common Data Service
description: Este tema especifica el orden de sincronización que debe seguir para crear datos de inicio.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: befe4e12a10f4a39b90bcb4faba6431a063a40e2
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020000"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="34d5d-103">Orden de ejecución para la sincronización inicial de aplicaciones de Finance and Operations y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="34d5d-103">Execution order for initial synchronization of Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="34d5d-104">Antes de usar la integración de datos, debe crear los datos iniciales necesarios para clientes, proveedores y los contactos.</span><span class="sxs-lookup"><span data-stu-id="34d5d-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="34d5d-105">Por ejemplo, va a crear un nuevo elemento **Grupo de proveedores** y establece su valor **Condiciones de pago** en **Net30**.</span><span class="sxs-lookup"><span data-stu-id="34d5d-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="34d5d-106">En este caso, antes de que se intente crear el elemento **Grupo de proveedores**, debe asegurarse de que exista **Net30** tanto en la aplicación como en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34d5d-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both the application and Common Data Service.</span></span> <span data-ttu-id="34d5d-107">(En el futuro, Microsoft lanzará al mercado una funcionalidad de plataforma de escritura dual denominada Sincronización inicial. Hará una única sincronización de datos entre la aplicación y Common Data Service como parte de la configuración de la escritura dual).</span><span class="sxs-lookup"><span data-stu-id="34d5d-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between the application and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="34d5d-108">Microsoft va a lanzar al mercado una asignación de escritura dual para todos los datos de referencia, incluidas las **Condiciones de pago** (condiciones de pago).</span><span class="sxs-lookup"><span data-stu-id="34d5d-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="34d5d-109">Si ya tiene los datos iniciales en un sistema, una pequeña operación de actualización de un registro puede activar la escritura dual en dicho registro.</span><span class="sxs-lookup"><span data-stu-id="34d5d-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="34d5d-110">Debe seguir el siguiente orden de prioridad y asegurarse de que los datos iniciales están disponibles en la aplicación y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34d5d-110">You must follow the following order of precedence and make sure that the initial data is available in the application and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="34d5d-111">Proveedor</span><span class="sxs-lookup"><span data-stu-id="34d5d-111">Vendor</span></span>

<span data-ttu-id="34d5d-112">A continuación se indica el orden de la ejecución para la entidad **Proveedor**:</span><span class="sxs-lookup"><span data-stu-id="34d5d-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="34d5d-113">Grupo de proveedores</span><span class="sxs-lookup"><span data-stu-id="34d5d-113">Vendor group</span></span>

    1. <span data-ttu-id="34d5d-114">Condiciones de pago</span><span class="sxs-lookup"><span data-stu-id="34d5d-114">Terms of payment</span></span>

        1. <span data-ttu-id="34d5d-115">Días de pago y líneas</span><span class="sxs-lookup"><span data-stu-id="34d5d-115">Payment day and lines</span></span>
        2. <span data-ttu-id="34d5d-116">Multivencimientos</span><span class="sxs-lookup"><span data-stu-id="34d5d-116">Payment schedule</span></span>

2. <span data-ttu-id="34d5d-117">Método de pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="34d5d-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="34d5d-118">Cliente (Organización)</span><span class="sxs-lookup"><span data-stu-id="34d5d-118">Customer (Organization)</span></span>

<span data-ttu-id="34d5d-119">A continuación se indica el orden de la ejecución para la entidad **Cliente**:</span><span class="sxs-lookup"><span data-stu-id="34d5d-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="34d5d-120">Grupo de clientes</span><span class="sxs-lookup"><span data-stu-id="34d5d-120">Customer group</span></span>

    1. <span data-ttu-id="34d5d-121">Condiciones de pago</span><span class="sxs-lookup"><span data-stu-id="34d5d-121">Terms of payment</span></span>

        1. <span data-ttu-id="34d5d-122">Días de pago y líneas</span><span class="sxs-lookup"><span data-stu-id="34d5d-122">Payment day and lines</span></span>
        2. <span data-ttu-id="34d5d-123">Pago</span><span class="sxs-lookup"><span data-stu-id="34d5d-123">Payment</span></span> 

2. <span data-ttu-id="34d5d-124">Método de pago de cliente</span><span class="sxs-lookup"><span data-stu-id="34d5d-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="34d5d-125">Contacto (Persona)</span><span class="sxs-lookup"><span data-stu-id="34d5d-125">Contact (Person)</span></span>

<span data-ttu-id="34d5d-126">A continuación se indica el orden de la ejecución para la entidad **Contacto**:</span><span class="sxs-lookup"><span data-stu-id="34d5d-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="34d5d-127">Cliente </span><span class="sxs-lookup"><span data-stu-id="34d5d-127">Customer</span></span>
2. <span data-ttu-id="34d5d-128">Proveedor</span><span class="sxs-lookup"><span data-stu-id="34d5d-128">Vendor</span></span>
