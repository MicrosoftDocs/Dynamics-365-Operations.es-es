---
title: Orden de ejecución para la sincronización inicial de Finance and Operations y Common Data Service
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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797307"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="29ada-103">Orden de ejecución para la sincronización inicial de Finance and Operations y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="29ada-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="29ada-104">Antes de usar la integración de datos, debe crear los datos iniciales necesarios para clientes, proveedores y los contactos.</span><span class="sxs-lookup"><span data-stu-id="29ada-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="29ada-105">Por ejemplo, si desea crear un nuevo elemento **Grupo de proveedores** y establecer sus **Condiciones de pago** como **Net30**, antes de intentar crear el elemento **Grupo de proveedores** necesita asegurarse de que exista **Net30** en Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="29ada-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="29ada-106">(En el futuro, lanzaremos al mercado una funcionalidad de plataforma de escritura dual denominada **Sincronización inicial**. Hará una única sincronización de datos entre Finance and Operations y Common Data Service como parte de la configuración de la escritura dual).</span><span class="sxs-lookup"><span data-stu-id="29ada-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="29ada-107">Sugerencias: Estamos lanzando al mercado una asignación de escritura dual para todos los datos de referencia, incluidas las **Condiciones de pago**.</span><span class="sxs-lookup"><span data-stu-id="29ada-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="29ada-108">Si ya tiene los datos iniciales en un sistema, una pequeña operación de actualización de un registro puede activar la escritura dual en dicho registro.</span><span class="sxs-lookup"><span data-stu-id="29ada-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="29ada-109">Debe seguir el siguiente orden de prioridad y asegurarse de que los datos iniciales están disponibles en Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="29ada-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="29ada-110">Proveedor</span><span class="sxs-lookup"><span data-stu-id="29ada-110">Vendor</span></span>

<span data-ttu-id="29ada-111">El orden de ejecución para el proveedor es:</span><span class="sxs-lookup"><span data-stu-id="29ada-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="29ada-112">Cliente (Organización)</span><span class="sxs-lookup"><span data-stu-id="29ada-112">Customer (Organization)</span></span>

<span data-ttu-id="29ada-113">El orden de ejecución para el cliente es:</span><span class="sxs-lookup"><span data-stu-id="29ada-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="29ada-114">Contacto (Persona)</span><span class="sxs-lookup"><span data-stu-id="29ada-114">Contact (Person)</span></span>

<span data-ttu-id="29ada-115">El orden de ejecución para el contacto es:</span><span class="sxs-lookup"><span data-stu-id="29ada-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
