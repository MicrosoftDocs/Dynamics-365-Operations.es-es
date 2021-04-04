---
title: Parámetros de adquisición y abastecimiento para el coste descargado
description: Este tema describe cómo configurar los parámetros de Adquisición y abastecimiento relevantes cuando utiliza el módulo Costo de entrega.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 49e046a1437917cfa866f690511789496fac2c53
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500751"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="39abc-103">Parámetros de adquisición y abastecimiento para el coste descargado</span><span class="sxs-lookup"><span data-stu-id="39abc-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="39abc-104">La página **Parámetros de adquisición y abastecimiento** tiene algunas configuraciones que son especialmente relevantes cuando usa el módulo **Coste de aterrizaje**.</span><span class="sxs-lookup"><span data-stu-id="39abc-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="39abc-105">Utilice el cuadro de diálogo **Actualizar líneas de pedido** que se abre desde la página **Parámetros de adquisición y abastecimiento** para especificar si las líneas de la orden de compra deben actualizarse automáticamente cuando se realizan cambios en el encabezado de la orden de compra.</span><span class="sxs-lookup"><span data-stu-id="39abc-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="39abc-106">Para completar esta configuración de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39abc-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="39abc-107">Vaya a **Adquisición y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="39abc-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="39abc-108">Sobre la pestaña **General**, seleccione el enlace **Actualizar líneas de pedido**.</span><span class="sxs-lookup"><span data-stu-id="39abc-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="39abc-109">El cuadro de diálogo **Actualizar líneas de pedido** enumera los campos en el encabezado del pedido que también pueden aplicar actualizaciones automáticas a los campos relacionados en las líneas del pedido.</span><span class="sxs-lookup"><span data-stu-id="39abc-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="39abc-110">Establezca cada campo de la lista en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="39abc-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="39abc-111">**Siempre** - Las líneas del pedido se actualizan automáticamente cuando se actualiza el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="39abc-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="39abc-112">**Nunca** - Las líneas del pedido nunca se actualizan automáticamente cuando se actualiza el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="39abc-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="39abc-113">**Inmediato** - Se le pedirá al usuario que seleccione si las líneas de pedido deben actualizarse.</span><span class="sxs-lookup"><span data-stu-id="39abc-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
