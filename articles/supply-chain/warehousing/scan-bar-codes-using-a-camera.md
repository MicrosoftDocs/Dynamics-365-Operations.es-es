---
title: Digitalizar códigos de barras mediante una cámara en la aplicación de almacén
description: Este tema explica cómo configurar la aplicación de almacén para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: fd4818ab936e1c93000793da756c97df6d05b2a9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436646"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a><span data-ttu-id="cc921-103">Digitalizar códigos de barras mediante una cámara en la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="cc921-103">Scan bar codes using a camera in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc921-104">Este tema explica cómo configurar la aplicación de almacén para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="cc921-104">This topic explains how to set up the warehouse app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cc921-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cc921-105">Prerequisites</span></span>
<span data-ttu-id="cc921-106">Para utilizar esta característica, debe tener instalada la versión 1.2.0.0 de la aplicación de almacén y su dispositivo debe tener una cámara.</span><span class="sxs-lookup"><span data-stu-id="cc921-106">To use this feature, you need to have version 1.2.0.0 of the warehouse app installed, and your device must have a camera.</span></span> <span data-ttu-id="cc921-107">Cuando abra la aplicación después de actualizarla, se le solicitará que permita a la aplicación usar la cámara.</span><span class="sxs-lookup"><span data-stu-id="cc921-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="cc921-108">Si su dispositivo no tiene cámara, no se mostrará ningún mensaje y no podrá utilizar una cámara como escáner.</span><span class="sxs-lookup"><span data-stu-id="cc921-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="cc921-109">Configurar</span><span class="sxs-lookup"><span data-stu-id="cc921-109">Setup</span></span>
<span data-ttu-id="cc921-110">En la configuración de visualización de la aplicación de almacén, puede seleccionar si la cámara debe utilizarse para la digitalización de códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="cc921-110">In the Display settings of the warehouse application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="cc921-111">Si habilita la opción **Usar la cámara como escáner**, puede usar la cámara en cada campo de entrada que tenga el modo de entrada preferido establecido en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="cc921-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="cc921-112">Para controlar si un campo de entrada debe ser escaneable, en la página **Nombres de campo de aplicación Warehouse**, establezca **Modo de entrada preferido** en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="cc921-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="cc921-113">Cuando se selecciona esta opción, se puede usar una cámara para escanear en la aplicación de almacén.</span><span class="sxs-lookup"><span data-stu-id="cc921-113">When this option is selected, a camera can be used for scanning in the warehouse app.</span></span> <span data-ttu-id="cc921-114">Para obtener información sobre cómo configurar nombres de campo en Warehousing, consulte [Configurar nombres de campo de aplicación en la aplicación de almacén](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="cc921-114">For information about how to configure app field names in Warehousing, see [Configure app field names in warehouse app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="cc921-115">Formatos de códigos de barras admitidos</span><span class="sxs-lookup"><span data-stu-id="cc921-115">Supported bar code formats</span></span>
<span data-ttu-id="cc921-116">Se admiten los formatos de códigos de barras más comúnes, incluido el Código 128, el Código 39, el Código 93, EAN-8, EAN-13, UPC-E, UPC-A y códigos QR.</span><span class="sxs-lookup"><span data-stu-id="cc921-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="cc921-117">Navegación</span><span class="sxs-lookup"><span data-stu-id="cc921-117">Navigation</span></span>
<span data-ttu-id="cc921-118">La página de la cámara se iniciará en cada página donde el campo de entrada tenga el modo de entrada preferido establecido en Exploración, cuando se encuentre en la página Cámara, use las siguientes opciones para navegar:</span><span class="sxs-lookup"><span data-stu-id="cc921-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="cc921-119">Haga clic en el botón Atrás para volver a la página de tarea y detalles.</span><span class="sxs-lookup"><span data-stu-id="cc921-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="cc921-120">Haga clic en el lápiz en la página de tarea y detalles para pasar a la página donde puede escribir la entrada manualmente.</span><span class="sxs-lookup"><span data-stu-id="cc921-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="cc921-121">Haga clic en la cámara en la página de tarea y detalles para volver a la página Cámara.</span><span class="sxs-lookup"><span data-stu-id="cc921-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="cc921-122">Página de tarea y detalles</span><span class="sxs-lookup"><span data-stu-id="cc921-122">Task and details page</span></span> | <span data-ttu-id="cc921-123">Página de la cámara</span><span class="sxs-lookup"><span data-stu-id="cc921-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Página de detalles de tarea de ejemplo de escaneo de cámara](./media/camera-scanning-example-task-detail-page50.png)          | ![Ejemplo de escaneo de cámara, página de cámara más pequeña](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="cc921-126">En la página de la cámara, al hacer clic en el botón Cámara, aparecerá atenuada mientras trata de identificar un código de barras.</span><span class="sxs-lookup"><span data-stu-id="cc921-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="cc921-127">Si no se identifica un código de barras en menos de 5 segundos, el proceso se pondrá en tiempo de espera y el botón Cámara volverá a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="cc921-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="cc921-128">A continuación, podrá intentar escanear de nuevo un código de barras.</span><span class="sxs-lookup"><span data-stu-id="cc921-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="cc921-129">Cuando apunte la cámara a un código de barras, mantenga el código de barras alineado entre los corchetes para lograr un mejor resultado.</span><span class="sxs-lookup"><span data-stu-id="cc921-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="cc921-130">Cuando un código de barras se digitaliza correctamente, el resultado se procesará y pasará al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="cc921-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="cc921-131">Si el siguiente paso contiene otro campo de entrada con el modo de entrada preferido establecido en Exploración, la página de la cámara se volverá a iniciar.</span><span class="sxs-lookup"><span data-stu-id="cc921-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="cc921-132">Si el paso siguiente no es un campo de exploración, la página de la cámara no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="cc921-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>

