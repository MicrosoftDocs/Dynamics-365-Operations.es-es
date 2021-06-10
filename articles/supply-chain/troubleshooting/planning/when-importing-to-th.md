---
title: Se le solicitará que guarde la configuración de cobertura del artículo aunque no haya realizado cambios
description: Se le solicitará que guarde la configuración de cobertura del artículo aunque no haya realizado cambios.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049488"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="4cb8e-103">Se le solicitará que guarde la configuración de cobertura del artículo aunque no haya realizado cambios</span><span class="sxs-lookup"><span data-stu-id="4cb8e-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="4cb8e-104">Número de KB: 4615588</span><span class="sxs-lookup"><span data-stu-id="4cb8e-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="4cb8e-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="4cb8e-105">Symptoms</span></span>

<span data-ttu-id="4cb8e-106">En algunos escenarios, es posible que reciba el siguiente mensaje cuando abra la página **Cobertura de artículos** después de importar elementos a través de la entidad *Cobertura de artículo V2*:</span><span class="sxs-lookup"><span data-stu-id="4cb8e-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="4cb8e-107">¿Desea guardar los cambios antes de cerrar?</span><span class="sxs-lookup"><span data-stu-id="4cb8e-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="4cb8e-108">Recibe este mensaje aunque no haya realizado ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="4cb8e-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="4cb8e-109">Resolution</span></span>

<span data-ttu-id="4cb8e-110">La página **Cobertura de artículos** incluye una lógica predeterminada compleja que puede hacer que el mensaje se muestre después de que se hayan realizado cambios directos en la base de datos, como a través de la importación de entidades.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="4cb8e-111">Por ejemplo, el campo de entidad `AREGENERALSETTINGSOVERRIDDEN` está configurado en *No*, pero importa un archivo que proporciona valores nuevos o modificados para campos como `PRODUCTCOVERAGEGROUPID` y / o `VENDORACCOUNTNUMBER`.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="4cb8e-112">En este caso, debido a que el campo `AREGENERALSETTINGSOVERRIDDEN` está configurado en *No*, los valores se borran automáticamente de los campos cuando abre la página **Cobertura de artículos** por primera vez después de la importación.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="4cb8e-113">Si guarda los cambios como lo indica el cuadro de mensaje, se almacenan en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="4cb8e-114">De lo contrario, recibirá el mismo mensaje la próxima vez que abra la página.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="4cb8e-115">Para evitar este comportamiento, pero también incluir valores para campos como `PRODUCTCOVERAGEGROUPID` a través de la importación de la entidad, establezca `AREGENERALSETTINGSOVERRIDDEN` a *Sí* cuando importe.</span><span class="sxs-lookup"><span data-stu-id="4cb8e-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
