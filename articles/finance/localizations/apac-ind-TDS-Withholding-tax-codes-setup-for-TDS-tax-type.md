---
title: Configurar códigos de retención de impuestos para tipos de impuestos de TDS
description: Este tema explica cómo configurar códigos de impuestos de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: d56a23f7af7633e1761a8a7c48f71381d6f14df2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023580"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a><span data-ttu-id="3d89c-103">Configurar códigos de retención de impuestos para tipos de impuestos de TDS</span><span class="sxs-lookup"><span data-stu-id="3d89c-103">Set up withholding tax codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d89c-104">Este tema explica cómo configurar códigos de impuestos de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="3d89c-104">This topic explains how to set up tax codes for Tax Deducted at Source (TDS).</span></span>

1. <span data-ttu-id="3d89c-105">Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Códigos de retenciones de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="3d89c-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax codes**.</span></span>

    <span data-ttu-id="3d89c-106">[![Página Códigos de retenciones de impuestos](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span><span class="sxs-lookup"><span data-stu-id="3d89c-106">[![Withholding tax codes page](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span></span>

2. <span data-ttu-id="3d89c-107">En el panel de acciones, seleccione **Nuevo** para crear un código de retención de impuestos para TDS e introduzca los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="3d89c-107">On the Action Pane, select **New** to create a withholding tax code for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="3d89c-108">En la ficha desplegable **General**, en el campo **Tipo de impuesto**, seleccione **TDS** para categorizar el código de impuestos como un código de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-108">On the **General** FastTab, in the **Tax type** field, select **TDS** to categorize the tax code as a TDS tax code.</span></span>
4. <span data-ttu-id="3d89c-109">En el campo **Periodo de liquidación**, seleccione el periodo de liquidación para el código de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-109">In the **Settlement period** field, select the TDS settlement period for the TDS tax code.</span></span>
5. <span data-ttu-id="3d89c-110">En el campo **Cuenta principal**, seleccione la cuenta contable en la que se debe registrar el importe de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-110">In the **Main account** field, select the ledger account that the TDS amount should be posted to.</span></span>
6. <span data-ttu-id="3d89c-111">En el campo **Cliente**, seleccione el cliente en la que se debe contabilizar el importe de TDS que se deduce en las transacciones de ventas.</span><span class="sxs-lookup"><span data-stu-id="3d89c-111">In the **Receivable account** field, select the receivable account that the TDS amount that is deducted in sales transactions should be posted to.</span></span>

    <span data-ttu-id="3d89c-112">El campo **Origen** se establece automáticamente en **Porcentaje del importe bruto** y el valor no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="3d89c-112">The **Origin** field is automatically set to **Percentage of gross amount**, and the value can't be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d89c-113">No puede establecer el origen en **Porcentaje del importe neto** para códigos de impuestos del tipo de impuesto de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-113">You can't set the origin to **Percentage of net amount** for tax codes of the TDS tax type.</span></span>

7. <span data-ttu-id="3d89c-114">En el campo **Componente de retención de impuestos**, seleccione el grupo de componentes de impuestos de TDS para el código de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-114">In the **Withholding tax component** field, select the TDS tax component for the TDS tax code.</span></span>
8. <span data-ttu-id="3d89c-115">Seleccione **Valores** en el Panel de acciones para abrir la página **Valores de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="3d89c-115">On the Action Pane, select **Values** to open the **Withholding tax values** page.</span></span>
9. <span data-ttu-id="3d89c-116">En el campo **Fecha inicial**, introduzca al fecha inicial para el valor de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-116">In the **From date** field, enter the start date for the TDS value.</span></span> <span data-ttu-id="3d89c-117">En el campo **Fecha final**, escriba la fecha final.</span><span class="sxs-lookup"><span data-stu-id="3d89c-117">In the **To date** field, enter the end date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d89c-118">Los campo **Límite mínimo**, **Límite superior** y **Excluir %** no están disponibles para códigos de impuestos del tipo de impuesto de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-118">The **Minimum limit**, **Upper limit**, and **Exclude %** fields aren't available for tax codes of the TDS tax type.</span></span>

10. <span data-ttu-id="3d89c-119">En el campo **Valor**, especifique el porcentaje de TDS para el código de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-119">In the **Value** field, enter the percentage of TDS for the TDS tax code.</span></span>
11. <span data-ttu-id="3d89c-120">Cierre la página **Valores de retención de impuestos** para volver a la página **Códigos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="3d89c-120">Close the **Withholding tax values** page to return to the **Withholding tax codes** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d89c-121">El botón **Límites** en la página **Códigos de retención de impuestos** no está disponible para códigos de impuestos del tipo de impuesto de TDS.</span><span class="sxs-lookup"><span data-stu-id="3d89c-121">The **Limits** button on the **Withholding tax codes** page isn't available for tax codes of the TDS tax type.</span></span>

12. <span data-ttu-id="3d89c-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3d89c-122">Close the page.</span></span>
