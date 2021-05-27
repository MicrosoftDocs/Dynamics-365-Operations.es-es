---
title: Registrar los números de los certificados de concesión de TDS
description: Este tema explica cómo registrar los números de certificado de concesión de impuestos deducidos en el origen (TDS) que se emiten a los proveedores.
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
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023556"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="5efde-103">Registrar los números de los certificados de concesión de TDS</span><span class="sxs-lookup"><span data-stu-id="5efde-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5efde-104">Este tema explica cómo registrar los números de certificado de concesión de impuestos deducidos en el origen (TDS) que se emiten a los proveedores.</span><span class="sxs-lookup"><span data-stu-id="5efde-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="5efde-105">Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Concesiones de retenciones de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="5efde-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="5efde-106">En el campo **Tipo de impuesto**, seleccione **TDS** para registrar certificados de concesión para el tipo de impuesto TDS.</span><span class="sxs-lookup"><span data-stu-id="5efde-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="5efde-107">En la pestaña **Información general**, seleccione **Alt + N** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="5efde-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="5efde-108">[![Encabezado de la nueva línea](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="5efde-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="5efde-109">En el campo **Código de retención de impuestos**, seleccione el código de impuestos TDS para el que se emiten los certificados de concesión del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5efde-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="5efde-110">El campo **Nombre del código de retención de impuestos** muestra el nombre del código de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="5efde-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="5efde-111">En los campos **Fecha inicial** y **Fecha final**, defina el periodo de validez del certificado de concesión que utiliza el código de impuestos de TDS para calcular los TDS para el proveedor en condiciones favorables.</span><span class="sxs-lookup"><span data-stu-id="5efde-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="5efde-112">En el campo **Observaciones**, introduzca cualquier comentario.</span><span class="sxs-lookup"><span data-stu-id="5efde-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="5efde-113">En el campo **Sección**, introduzca el código de la sección legal bajo la cual se hace uso del certificado de concesión TDS.</span><span class="sxs-lookup"><span data-stu-id="5efde-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="5efde-114">Si el código de la sección es 197, el valor "A" aparece tanto en la columna "Razón de la no deducción/deducción más baja" en el formulario 26Q, como en la columna "Razón de la no deducción/deducción más baja/pago de impuestos (si corresponde)" en formulario 27Q.</span><span class="sxs-lookup"><span data-stu-id="5efde-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="5efde-115">Si el código de sección es 197A, el valor "B" aparece en ambos lugares.</span><span class="sxs-lookup"><span data-stu-id="5efde-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="5efde-116">Seleccione la ficha despegable **Certificado** para registrar los números de certificados de concesión de TDS para los proveedores.</span><span class="sxs-lookup"><span data-stu-id="5efde-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="5efde-117">En el campo **Cuenta del proveedor**, seleccione la cuenta del proveedor para la que se emite el certificado de concesión de TDS.</span><span class="sxs-lookup"><span data-stu-id="5efde-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="5efde-118">En los campos **Fecha inicial** y **Fecha final**, defina el periodo de validez del certificado de concesión de TDS.</span><span class="sxs-lookup"><span data-stu-id="5efde-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="5efde-119">El cálculo de TDS en condiciones favorables se basa en el periodo en el que se crea el certificado para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="5efde-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="5efde-120">En el campo **Certificado**, introduzca el número del certificado de concesión de TDS.</span><span class="sxs-lookup"><span data-stu-id="5efde-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="5efde-121">[![Ficha desplegable Certificado](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="5efde-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="5efde-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5efde-122">Close the page.</span></span>
