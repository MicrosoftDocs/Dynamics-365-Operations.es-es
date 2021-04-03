---
title: Faltan productos y categorías después de la copia del entorno
description: Este tema proporciona una guía de resolución de problemas que puede ayudar cuando faltan productos y categorías después de que un sitio se copia entre entornos o dentro del mismo entorno.
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
ms.openlocfilehash: 35f2cbd98a91149395f40bf821c1d5d7e58eaf77
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585527"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="f7ff2-103">Faltan productos y categorías después de la copia del entorno</span><span class="sxs-lookup"><span data-stu-id="f7ff2-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7ff2-104">Este tema proporciona una guía de resolución de problemas que puede ayudar cuando faltan productos y categorías después de que un sitio se copia entre entornos o dentro del mismo entorno.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="f7ff2-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7ff2-105">Description</span></span>

<span data-ttu-id="f7ff2-106">Después de que un sitio se copia de un entorno a otro, o dentro del mismo entorno, faltan los productos y las categorías del sitio.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="f7ff2-107">Los productos y categorías faltarán en el escaparate de la tienda de comercio electrónico y en la pestaña **Productos** del creador de sitios de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="f7ff2-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="f7ff2-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="f7ff2-109">Asigne el número de unidad operativa del canal a un sitio recién copiado en el creador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="f7ff2-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="f7ff2-110">Para asignar el número de unidad operativa del canal (OUN) a un sitio recién copiado en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f7ff2-111">Seleccione el sitio recién copiado.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="f7ff2-112">En **Configuración del sitio**, seleccione **Canales**.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="f7ff2-113">Junto al nombre del canal, seleccione los puntos suspensivos (**...**) y luego seleccione **Cambiar el canal de la tienda en línea**.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="f7ff2-114">En el cuadro de diálogo **Cambiar el canal de la tienda en línea**, seleccione el canal a asignar al sitio recién copiado, y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="f7ff2-115">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="f7ff2-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7ff2-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f7ff2-116">Additional resources</span></span>

[<span data-ttu-id="f7ff2-117">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="f7ff2-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
