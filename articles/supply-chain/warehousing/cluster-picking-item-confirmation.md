---
title: Confirmación de producto para picking de clústeres
description: Este tema describe cómo se establece la verificación de artículos junto con el picking en clúster.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d2ce787e6a7d677bc997bff363f34850ff9899b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568223"
---
[!include [banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="58544-103">Confirmación de producto para picking de clústeres</span><span class="sxs-lookup"><span data-stu-id="58544-103">Product confirmation for cluster picking</span></span>
<span data-ttu-id="58544-104">El picking en clúster le permite elegir los artículos para varios pedidos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="58544-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="58544-105">Cuando se aplica el picking en clúster, es esencial la confirmación del artículo para comprobar que los artículos se agregan a los clústeres.</span><span class="sxs-lookup"><span data-stu-id="58544-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="58544-106">Puede comprobar los artículos del picking en clúster durante el proceso de picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="58544-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="58544-107">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="58544-107">Where it applies</span></span>
<span data-ttu-id="58544-108">La comprobación de artículos para trabajos de picking en clúster funcional del mismo modo que cuando se comprueban artículos en un proceso que no es de picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="58544-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="58544-109">La configuración se basa en la configuración del código de barras del producto.</span><span class="sxs-lookup"><span data-stu-id="58544-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="58544-110">Establecer la comprobación de artículos con picking en clúster</span><span class="sxs-lookup"><span data-stu-id="58544-110">Set up item verification with cluster picking</span></span>
1.  <span data-ttu-id="58544-111">En un elemento de menú del dispositivo móvil, abra el formulario de configuración para la confirmación del trabajo: **Gestión de almacenes** > **Gestión de almacenes** > **Configuración** > **Dispositivo móvil** > **Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="58544-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
2.  <span data-ttu-id="58544-112">En el elemento de menú del dispositivo móvil, abra **Configuración de la confirmación de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="58544-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="58544-113">Opción</span><span class="sxs-lookup"><span data-stu-id="58544-113">Option</span></span>        |                                    <span data-ttu-id="58544-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="58544-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="58544-115">Confirmación del producto</span><span class="sxs-lookup"><span data-stu-id="58544-115">Product confirmation</span></span> | <span data-ttu-id="58544-116">Permite que se compruebe cada pieza de inventario desde el dispositivo móvil cuando se escanea.</span><span class="sxs-lookup"><span data-stu-id="58544-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |

