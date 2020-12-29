---
title: Visión general de pago positivo
description: Este artículo proporciona información acerca del pago positivo, que se usa para generar una lista electrónica de cheques que se pueden presentar a un banco.
author: panolte
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f64b2bc6c336ba833cbd95f83596fe516bce8b56
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447560"
---
# <a name="positive-pay-overview"></a><span data-ttu-id="83791-103">Visión general de pago positivo</span><span class="sxs-lookup"><span data-stu-id="83791-103">Positive pay overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83791-104">Este artículo proporciona información acerca del pago positivo, que se usa para generar una lista electrónica de cheques que se pueden presentar a un banco.</span><span class="sxs-lookup"><span data-stu-id="83791-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="83791-105">El pago positivo se usa para generar una lista electrónica de cheques que se pueden presentar a un banco.</span><span class="sxs-lookup"><span data-stu-id="83791-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="83791-106">Los archivos de pago positivo pueden ayudar a los bancos a evitar fraude de cheques.</span><span class="sxs-lookup"><span data-stu-id="83791-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="83791-107">Configure los pagos positivos para generar una lista electrónica de cheques cada vez que se impriman cheques.</span><span class="sxs-lookup"><span data-stu-id="83791-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="83791-108">A continuación, cuando un cheque se envía al banco, el banco compara el cheque con la lista de cheques que envió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="83791-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="83791-109">Si el cheque coincide con un cheque de la lista, el banco lo compensa.</span><span class="sxs-lookup"><span data-stu-id="83791-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="83791-110">Si el cheque no coincide con un cheque en la lista, el banco lo retiene para su revisión.</span><span class="sxs-lookup"><span data-stu-id="83791-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="83791-111">El pago positivo también se conoce como Pago seguro.</span><span class="sxs-lookup"><span data-stu-id="83791-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="83791-112">Los archivos de pago positivo pueden contener información confidencial acerca de los beneficiarios y los importes del cheque.</span><span class="sxs-lookup"><span data-stu-id="83791-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="83791-113">Por lo tanto, asegúrese de usar medidas de seguridad adecuadas desde el momento en que los archivos se generan, hasta que los reciba el banco.</span><span class="sxs-lookup"><span data-stu-id="83791-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="83791-114">Los archivos de pago positivo se descargan en función de las instrucciones de descarga para el explorador web.</span><span class="sxs-lookup"><span data-stu-id="83791-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="83791-115">Los archivos de pago positivo se crean mediante entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="83791-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="83791-116">Para generar un archivo de pago positivo, debe configurar los formatos de transformación para el XML que traduce los datos en un formato que el banco puede usar.</span><span class="sxs-lookup"><span data-stu-id="83791-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="83791-117">Para cada cuenta bancaria para la que desea generar información de pago positivo, debe asignar el formato de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="83791-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="83791-118">Tras generar pagos, puede generar un archivo de pago positivo para una única entidad jurídica y una única cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="83791-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="83791-119">También puede generar archivos de pago positivo para varias entidades jurídicas y cuentas bancarias al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="83791-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="83791-120">Después de que se hayan pagado los cheques que aparecen en un archivo de pago positivo, recibirá un número de confirmación del banco.</span><span class="sxs-lookup"><span data-stu-id="83791-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="83791-121">A continuación, puede confirmar el archivo de pago positivo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="83791-121">You can then confirm the positive pay file in the system.</span></span> 

<span data-ttu-id="83791-122">Si debe cambiar un archivo de pago positivo, puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="83791-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="83791-123">A continuación, para cada cheque del archivo de pago positivo, se restablece el campo que indica si el cheque se ha incluido en un archivo de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="83791-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="83791-124">Para obtener más información, consulte [Configurar y generar archivos de pago positivo](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="83791-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>



