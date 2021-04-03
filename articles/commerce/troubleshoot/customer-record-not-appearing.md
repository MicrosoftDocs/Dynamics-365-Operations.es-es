---
title: Los registros de clientes no aparecen en la sede de Commerce
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los registros de los clientes no aparecen inmediatamente en la sede de Commerce.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 790468ac244f1647c07024604886c65d22feca24
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585518"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="a4656-103">Los registros de clientes no aparecen en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="a4656-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4656-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los registros de los clientes no aparecen inmediatamente en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a4656-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="a4656-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4656-105">Description</span></span>

<span data-ttu-id="a4656-106">Cuando crea un nuevo registro de cliente mediante el flujo de registro en el escaparate de comercio electrónico, el registro de cliente correspondiente no aparece inmediatamente en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a4656-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="a4656-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="a4656-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="a4656-108">Deshabilitar la creación de clientes en modo asíncrono</span><span class="sxs-lookup"><span data-stu-id="a4656-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4656-109">Si deshabilita la creación de clientes asincrónica, el rendimiento del sistema podría verse afectado, porque la creación de cada registro producirá una solicitud en tiempo real a la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a4656-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="a4656-110">Además, si la sede de Commerce está inactiva (por ejemplo, durante los flujos de servicio), cualquier flujo de creación de nuevos clientes producirá errores.</span><span class="sxs-lookup"><span data-stu-id="a4656-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="a4656-111">Para deshabilitar la creación de clientes en modo asíncrono en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a4656-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a4656-112">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de tienda en línea \> Perfiles de funcionalidad**.</span><span class="sxs-lookup"><span data-stu-id="a4656-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="a4656-113">Si aún no está utilizando un perfil de funcionalidad para su canal en línea, cree uno.</span><span class="sxs-lookup"><span data-stu-id="a4656-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="a4656-114">Asegúrese de que la opción **Crear cliente en modo asíncrono** está configurada en **No**.</span><span class="sxs-lookup"><span data-stu-id="a4656-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="a4656-115">Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.</span><span class="sxs-lookup"><span data-stu-id="a4656-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="a4656-116">Seleccione la tienda en línea para la que deshabilitar la creación de clientes asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a4656-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="a4656-117">En la pestaña **General**, asegúrese de que el campo **Perfil de funcionalidad** está configurado para el perfil de funcionalidad que está utilizando para su canal en línea.</span><span class="sxs-lookup"><span data-stu-id="a4656-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4656-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a4656-118">Additional resources</span></span>

[<span data-ttu-id="a4656-119">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="a4656-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
