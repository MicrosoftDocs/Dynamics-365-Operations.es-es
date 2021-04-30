---
title: Formatos de archivo para métodos de pago
description: En este tema se describen los dos métodos para obtener los formatos de archivo que puede usar para los métodos de pago.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 895fbe2a46d99aed175676c22ba13c30d6d8b98e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894679"
---
# <a name="file-formats-for-methods-of-payment"></a><span data-ttu-id="441d4-103">Formatos de archivo para métodos de pago</span><span class="sxs-lookup"><span data-stu-id="441d4-103">File formats for methods of payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="441d4-104">En este tema se describen los dos métodos para obtener los formatos de archivo que puede usar para los métodos de pago.</span><span class="sxs-lookup"><span data-stu-id="441d4-104">This topic describes the two methods for getting file formats that you can use for methods of payment.</span></span>

<span data-ttu-id="441d4-105">Hay dos métodos que puede utilizar para obtener formatos de archivo para su uso con métodos de pago, formatos de archivo de informes electrónicos (ER) o formatos de archivo X++.</span><span class="sxs-lookup"><span data-stu-id="441d4-105">There are two methods that you can use to get file formats for use with methods of payment, electronic reporting (ER) file formats or X++ file formats.</span></span> <span data-ttu-id="441d4-106">Cuando configura un método de pago para un cliente o proveedor, indica qué formatos de archivo y estándares deben usarse para los pagos y cómo se procesarán los pagos.</span><span class="sxs-lookup"><span data-stu-id="441d4-106">When you set up a method of payment for a customer or vendor, you indicate which file formats and standards should be used for payments and how payments will be processed.</span></span> <span data-ttu-id="441d4-107">Puede seleccionar entre los siguientes tipos de formatos:</span><span class="sxs-lookup"><span data-stu-id="441d4-107">You can select from the following types of formats:</span></span>

-   <span data-ttu-id="441d4-108">Exportar</span><span class="sxs-lookup"><span data-stu-id="441d4-108">Export</span></span>
-   <span data-ttu-id="441d4-109">Importar</span><span class="sxs-lookup"><span data-stu-id="441d4-109">Import</span></span>
-   <span data-ttu-id="441d4-110">Devolución</span><span class="sxs-lookup"><span data-stu-id="441d4-110">Return</span></span>
-   <span data-ttu-id="441d4-111">Envío</span><span class="sxs-lookup"><span data-stu-id="441d4-111">Remittance</span></span>

### <a name="method-1-electronic-reporting-file-formats"></a><span data-ttu-id="441d4-112">Método 1: formatos de archivo de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="441d4-112">Method 1: Electronic reporting file formats</span></span>

<span data-ttu-id="441d4-113">Para formatos de archivo basados en configuraciones de ER, debe importar las configuraciones de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="441d4-113">For file formats that are based on ER configurations, you must import the configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="441d4-114">Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="441d4-114">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="441d4-115">Después de importar las configuraciones de informes para esos formatos de archivo, los formatos importados estarán disponibles para seleccionar en la página **Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="441d4-115">After you import reporting configurations for those file formats, the imported formats will be available to select on the **Methods of payment** page.</span></span> <span data-ttu-id="441d4-116">El proceso para importar y seleccionar formatos de archivo para Europa es similar al procedimiento para Japón.</span><span class="sxs-lookup"><span data-stu-id="441d4-116">The process for importing and selecting file formats for Europe is similar to the procedure for Japan.</span></span> <span data-ttu-id="441d4-117">Para obtener más información, consulte [Habilitar el formato de archivo de pago de JBA](tasks/jba-payment-file-format.md)</span><span class="sxs-lookup"><span data-stu-id="441d4-117">For more details, see [Enable the JBA payment file format](tasks/jba-payment-file-format.md)</span></span>

### <a name="method-2-x-file-formats"></a><span data-ttu-id="441d4-118">Método 2: formatos de archivo X++</span><span class="sxs-lookup"><span data-stu-id="441d4-118">Method 2: X++ file formats</span></span>

<span data-ttu-id="441d4-119">Para seleccionar formatos de archivo basados en código X++, siga los pasos descritos a continuación.</span><span class="sxs-lookup"><span data-stu-id="441d4-119">To select file formats that are based on X++ code, complete the following steps.</span></span>

1.  <span data-ttu-id="441d4-120">Vaya a la página **Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="441d4-120">Go to the **Methods of payment** page.</span></span>
2.  <span data-ttu-id="441d4-121">En la ficha desplegable **Formatos de archivo**, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="441d4-121">On the **File formats** FastTab, click **Setup**.</span></span>
3.  <span data-ttu-id="441d4-122">Seleccione la ficha que corresponde al tipo de formato del archivo.</span><span class="sxs-lookup"><span data-stu-id="441d4-122">Select the tab that corresponds with the file format type.</span></span>
4.  <span data-ttu-id="441d4-123">Seleccione un formato de archivo en la lista **Disponible** y muévalo a la lista **Seleccionado** con el control de flecha.</span><span class="sxs-lookup"><span data-stu-id="441d4-123">Select a file format from the **Available** list and move it to the **Selected** list with the arrow control.</span></span>
5.  <span data-ttu-id="441d4-124">Cierre la página **Formatos de archivo para métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="441d4-124">Close the **File formats for methods of payment** page.</span></span>
6.  <span data-ttu-id="441d4-125">En la ficha desplegable **Formatos de archivo**, seleccione el formato de archivo que desea utilizar para el método de pago en el campo de formato de archivo apropiado.</span><span class="sxs-lookup"><span data-stu-id="441d4-125">On the **File formats** FastTab, select the file format to use for the method of payment from the appropriate file format field.</span></span> <span data-ttu-id="441d4-126">Las opciones generales de informes electrónicos deben establecerse en **No** para formatos de archivo X++.</span><span class="sxs-lookup"><span data-stu-id="441d4-126">The General electronic reporting options should be set to **No** for X++ file formats.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]