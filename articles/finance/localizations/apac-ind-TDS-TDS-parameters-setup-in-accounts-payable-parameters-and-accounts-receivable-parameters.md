---
title: Configurar los parámetros de TDS en proveedores y clientes
description: Este tema explica cómo establecer parámetros en proveedores y clientes para que sean compatibles con las deducciones de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023568"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="e7adf-103">Configurar los parámetros de TDS en proveedores y clientes</span><span class="sxs-lookup"><span data-stu-id="e7adf-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7adf-104">Este tema explica cómo establecer parámetros en proveedores y clientes para que sean compatibles con las deducciones de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="e7adf-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="e7adf-105">Vaya a **Impuesto \> Configuración \> Parámetros \> Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="e7adf-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="e7adf-106">En la pestaña **Actualizaciones**, seleccione **Actualizar líneas de pedido** para abrir el cuadro de diálogo **Actualizar líneas de pedido**.</span><span class="sxs-lookup"><span data-stu-id="e7adf-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="e7adf-107">En la sección **Grupo de TDS**, en el campo **Actualizar grupo de TDS**, especifique el método que se utilizará para actualizar el grupo de TDS en el nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="e7adf-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="e7adf-108">Esta configuración se utiliza cuando el grupo de TDS se actualiza en un encabezado de pedido.</span><span class="sxs-lookup"><span data-stu-id="e7adf-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="e7adf-109">Las siguientes opciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="e7adf-109">The following options are available:</span></span>

    - <span data-ttu-id="e7adf-110">**Nunca**: el grupo de TDS no se actualiza en las líneas de pedido cuando se actualiza en el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="e7adf-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="e7adf-111">**Siempre**: el grupo de TDS se actualiza automáticamente en las líneas de pedido cuando se actualiza en el encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="e7adf-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="e7adf-112">**Bajo petición**: los usuarios reciben un mensaje que les pide que actualicen el grupo de TDS en las líneas de pedido.</span><span class="sxs-lookup"><span data-stu-id="e7adf-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="e7adf-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7adf-113">Select **OK**.</span></span>

    <span data-ttu-id="e7adf-114">[![Cuadro de diálogo de actualizar líneas de pedido](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="e7adf-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="e7adf-115">Vaya a **Impuesto \> Configuración \> Parámetros \> Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="e7adf-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="e7adf-116">En la pestaña **General**, en la ficha desplegable **Dividir según la información de entrega**, establezca la opción **Recepción del producto** a **Sí** para registrar y dividir una recepción de producto que tiene diferentes direcciones de entrega y números de cuenta de impuestos (TAN).</span><span class="sxs-lookup"><span data-stu-id="e7adf-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="e7adf-117">Si esta opción se establece en **No**, no puede registrar un albarán de compra que tenga diferentes direcciones de entrega y TAN.</span><span class="sxs-lookup"><span data-stu-id="e7adf-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="e7adf-118">Establezca la opción **Factura** a **Sí** para registrar y dividir una factura de compra que tiene diferentes direcciones de entrega y TAN.</span><span class="sxs-lookup"><span data-stu-id="e7adf-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="e7adf-119">[![Ficha desplegable Dividir según la información de entrega](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="e7adf-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="e7adf-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e7adf-120">Close the page.</span></span>
