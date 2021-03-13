---
title: Retención de impuestos global
description: Este tema proporciona información sobre la funcionalidad de retención de impuestos global y cómo configurarla. La funcionalidad de retención de impuestos global se ha mejorado para las transacciones de proveedores y clientes, de modo que la retención de impuestos se calcula a nivel de artículo.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 17ed1dcae97f6cd28175c483be5ca3ce96d59e05
ms.sourcegitcommit: 053f4cda6862fbcd9e3aa6e9cb009e7de833beac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "5075747"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="a78eb-104">Retención de impuestos global</span><span class="sxs-lookup"><span data-stu-id="a78eb-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a78eb-105">Este tema proporciona información sobre la funcionalidad de retención de impuestos global y explica cómo configurarla.</span><span class="sxs-lookup"><span data-stu-id="a78eb-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="a78eb-106">La nueva funcionalidad está disponible en las versiones 10.0.17 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="a78eb-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="a78eb-107">La funcionalidad de retención de impuestos global se ha mejorado para las transacciones de proveedores y clientes, de modo que la retención de impuestos se calcula a nivel de artículo.</span><span class="sxs-lookup"><span data-stu-id="a78eb-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="a78eb-108">El saldo en la cuenta de retención de impuestos de las transacciones de compra se puede liquidar ejecutando el trabajo de pago de retención de impuestos en la cuenta de liquidación de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a78eb-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="a78eb-109">La retención de impuestos global no respalda la función **Mantener cargos** función en las páginas de pedidos de compra, facturas de proveedor y pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a78eb-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="a78eb-110">Activar la retención de impuestos global</span><span class="sxs-lookup"><span data-stu-id="a78eb-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="a78eb-111">En el espacio de trabajo **Administración de características**, seleccione **Retención de impuestos global** y luego seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="a78eb-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="a78eb-112">Vaya a **Impuesto \> Configuración \> Parámetros \> Parámetros del libro mayor**, y luego, en la pestaña **Retención de impuestos**, configure la opción **Habilitar la retención de impuestos global** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a78eb-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="a78eb-113">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a78eb-113">Select **Save**.</span></span>
4. <span data-ttu-id="a78eb-114">Actualice la página en su navegador web.</span><span class="sxs-lookup"><span data-stu-id="a78eb-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="a78eb-115">La funcionalidad de retención de impuestos global no se puede activar para países o regiones donde ya existen soluciones de retención de impuestos localizadas.</span><span class="sxs-lookup"><span data-stu-id="a78eb-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="a78eb-116">Estas áreas incluyen, entre otras, India, Brasil, Tailandia, Arabia Saudí, Irlanda, Gran Bretaña y Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="a78eb-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>
