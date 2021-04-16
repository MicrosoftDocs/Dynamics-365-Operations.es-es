---
title: Imprimir el informe Pago de impuestos por código
description: Este tema proporciona información sobre la configuración y las acciones necesarias para imprimir el pago de impuestos por informe de código en la divisa del código contable o fiscal.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eb3ee4a12d2d29c2769f1ae22e11dc05608b47c1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815461"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="d2a6e-103">Imprimir el informe Pago de impuestos por código</span><span class="sxs-lookup"><span data-stu-id="d2a6e-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2a6e-104">Para imprimir el informe **Pago de impuestos por código**, vaya a **Impuestos** \> **Consultas e informes** \> **Informes de impuestos** \> **Pago de impuestos por código**.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="d2a6e-105">De forma predeterminada, los importes de los informes se generan en la divisa contable de la entidad jurídica para todos los códigos de informes que se configuran en la página **Códigos de informe de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="d2a6e-106">También puede generar este informe para que muestre los importes de pago de impuestos en las divisas de los códigos del impuesto para todos los códigos de informe asignados a los códigos del impuesto en la página **Códigos de impuestos** página.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="d2a6e-107">Activar la característica</span><span class="sxs-lookup"><span data-stu-id="d2a6e-107">Turn on the feature</span></span>

<span data-ttu-id="d2a6e-108">En el espacio de trabajo **Gestión de características**, active la siguiente: **Generar el pago de impuestos por informe de código en la divisa del código de los impuestos**.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="d2a6e-109">Ejecute el informe</span><span class="sxs-lookup"><span data-stu-id="d2a6e-109">Run the report</span></span>

1. <span data-ttu-id="d2a6e-110">Vaya a **Impuestos** \> **Consultas e informes** \> **Informes de impuestos** \> **Pago de impuestos por código**.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="d2a6e-111">En el campo **Informe de divisa**, seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d2a6e-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="d2a6e-112">**Divisa de contabilidad** - Imprime los importes del informe en la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="d2a6e-113">**Divisa del código de impuestos** - Imprime los importes del informe en las divisas de los códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Cuadro de diálogo pago de impuestos por código](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="d2a6e-115">La ilustración siguiente muestra un ejemplo del informe que se genera.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="d2a6e-116">El informe muestra que el código de informe **101** tiene la divisa **EUR** si el campo **Divisa de impuestos** se establece en **EUR** para el código de impuestos al que está asignado el código de informe.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Ejemplo de pago de impuestos por código de informe](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]