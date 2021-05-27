---
title: Editar dimensiones financieras para transacciones minoristas
description: En este tema se describe cómo editar dimensiones financieras para transacciones minoristas en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 381d8bb0939f6c4c163477990e49382201487375
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019916"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="49793-103">Editar dimensiones financieras para transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="49793-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49793-104">En este tema se describe cómo editar dimensiones financieras para transacciones minoristas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="49793-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="49793-105">Editar dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="49793-105">Edit financial dimensions</span></span>

<span data-ttu-id="49793-106">Para editar dimensiones financieras para transacciones minoristas en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="49793-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="49793-107">Abra la página **Configuración de dimensiones financieras para la integración de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="49793-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="49793-108">Seleccione el registro **Integración de dimensiones predeterminadas** activo.</span><span class="sxs-lookup"><span data-stu-id="49793-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="49793-109">En la ficha desplegable **Dimensiones financieras**, asegúrese de que todas las dimensiones que desea editar en la hoja de cálculo de Excel estén presentes en la lista **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="49793-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="49793-110">Para obtener más información, consulte [Entidades de datos](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).</span><span class="sxs-lookup"><span data-stu-id="49793-110">For more information, see [Data entities](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).</span></span>
1. <span data-ttu-id="49793-111">Descargue y abra el archivo de Excel en la página **Extractos**, la página **Transacciones comerciales** o el icono **Errores de validación de transacciones** en el espacio de trabajo **Operaciones financieras de tienda**.</span><span class="sxs-lookup"><span data-stu-id="49793-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="49793-112">Para cambiar la dimensión financiera de la transacción, seleccione **Diseño** y, a continuación, el símbolo del lápiz junto a la fila **Transacción (auditable)**.</span><span class="sxs-lookup"><span data-stu-id="49793-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="49793-113">Busque y seleccione el campo **FinancialDimensionDisplayValue**, elija una celda en la parte del encabezado de la hoja de cálculo de Excel y luego seleccione **Agregar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="49793-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="49793-114">Seleccione una celda debajo de la celda que seleccionó en el paso anterior, elija **Agregar valor** y, a continuación, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="49793-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="49793-115">Las dimensiones financieras se agregan a la hoja de cálculo de Excel y luego se pueden editar y publicar.</span><span class="sxs-lookup"><span data-stu-id="49793-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="49793-116">Para cambiar las dimensiones en las líneas de transacción, seleccione la fila **Transacciones de ventas (auditables)**, seleccione el símbolo del lápiz y luego repita los pasos 6 y 7.</span><span class="sxs-lookup"><span data-stu-id="49793-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="49793-117">Para cambiar las dimensiones en las líneas de pago, seleccione la fila **Transacciones de pago (auditables)**, elija el símbolo del lápiz y luego repita los pasos 6 y 7.</span><span class="sxs-lookup"><span data-stu-id="49793-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="49793-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="49793-118">Additional resources</span></span>

[<span data-ttu-id="49793-119">Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio</span><span class="sxs-lookup"><span data-stu-id="49793-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="49793-120">Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea</span><span class="sxs-lookup"><span data-stu-id="49793-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="49793-121">Crear un libro de trabajo de Excel para editar transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="49793-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="49793-122">Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="49793-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]