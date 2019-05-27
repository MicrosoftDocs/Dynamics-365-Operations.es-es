---
title: Digitalizar códigos de barras mediante una cámara en Dynamics 365 for Finance and Operations - Warehousing
description: Este tema explica cómo configurar Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: e78d0a82d3ca66a6912ea1a9517296ca241edf1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559056"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-for-finance-and-operations--warehousing"></a><span data-ttu-id="dfccd-103">Digitalizar códigos de barras mediante una cámara en Dynamics 365 for Finance and Operations - Warehousing</span><span class="sxs-lookup"><span data-stu-id="dfccd-103">Scan bar codes using a camera in Dynamics 365 for Finance and Operations – Warehousing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfccd-104">Este tema explica cómo configurar Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="dfccd-104">This topic explains how to set up Dynamics 365 for Finance and Operations – Warehousing to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="dfccd-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dfccd-105">Prerequisites</span></span>
<span data-ttu-id="dfccd-106">Para utilizar esta función, debe tener instalada la versión 1.2.0.0 de Warehousing y su dispositivo debe tener una cámara.</span><span class="sxs-lookup"><span data-stu-id="dfccd-106">To use this feature, you need to have version 1.2.0.0 of Warehousing installed, and your device must have a camera.</span></span> <span data-ttu-id="dfccd-107">Cuando abra la aplicación después de actualizarla, se le solicitará que permita a la aplicación Dynamics 365 for Finance and Operations – Warehousing usar la cámara.</span><span class="sxs-lookup"><span data-stu-id="dfccd-107">When you open the app after updating, you will be prompted to allow the Dynamics 365 for Finance and Operations – Warehousing application to use the camera.</span></span> <span data-ttu-id="dfccd-108">Si su dispositivo no tiene cámara, no se mostrará ningún mensaje y no podrá utilizar una cámara como escáner.</span><span class="sxs-lookup"><span data-stu-id="dfccd-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="dfccd-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="dfccd-109">Setup</span></span>
<span data-ttu-id="dfccd-110">En la configuración de visualización de la aplicación Warehousing, puede seleccionar si la cámara debe utilizarse para la digitalización de códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="dfccd-110">In the Display settings of the Warehousing application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="dfccd-111">Si habilita la opción **Usar la cámara como escáner**, puede usar la cámara en cada campo de entrada que tenga el modo de entrada preferido establecido en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="dfccd-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="dfccd-112">Para controlar si un campo de entrada debe ser escaneable, en la página **Nombres de campo de aplicación Warehouse** en Dynamics 365 for Finance and Operations, establezca **Modo de entrada preferido** en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="dfccd-112">To control whether an input field should be scannable, on the **Warehouse app field names** page in Dynamics 365 for Finance and Operations, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="dfccd-113">Cuando se selecciona esta opción, se puede usar una cámara para escanear en la aplicación Warehousing.</span><span class="sxs-lookup"><span data-stu-id="dfccd-113">When this option is selected, a camera can be used for scanning in the Warehousing app.</span></span> <span data-ttu-id="dfccd-114">Para obtener información sobre cómo configurar nombres de campo en Warehousing, consulte [Configurar nombres de campo de aplicación en la aplicación Warehousing](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="dfccd-114">For information about how to configure app field names in Warehousing, see [Configure app field names in Warehousing app](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="dfccd-115">Formatos de códigos de barras admitidos</span><span class="sxs-lookup"><span data-stu-id="dfccd-115">Supported bar code formats</span></span>
<span data-ttu-id="dfccd-116">Se admiten los formatos de códigos de barras más comúnes, incluido el Código 128, el Código 39, el Código 93, EAN-8, EAN-13, UPC-E, UPC-A y códigos QR.</span><span class="sxs-lookup"><span data-stu-id="dfccd-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="dfccd-117">Navegación</span><span class="sxs-lookup"><span data-stu-id="dfccd-117">Navigation</span></span>
<span data-ttu-id="dfccd-118">La página de la cámara se iniciará en cada página donde el campo de entrada tenga el modo de entrada preferido establecido en Exploración, cuando se encuentre en la página Cámara, use las siguientes opciones para navegar:</span><span class="sxs-lookup"><span data-stu-id="dfccd-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="dfccd-119">Haga clic en el botón Atrás para volver a la página de tarea y detalles.</span><span class="sxs-lookup"><span data-stu-id="dfccd-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="dfccd-120">Haga clic en el lápiz en la página de tarea y detalles para pasar a la página donde puede escribir la entrada manualmente.</span><span class="sxs-lookup"><span data-stu-id="dfccd-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="dfccd-121">Haga clic en la cámara en la página de tarea y detalles para volver a la página Cámara.</span><span class="sxs-lookup"><span data-stu-id="dfccd-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="dfccd-122">Página de tarea y detalles</span><span class="sxs-lookup"><span data-stu-id="dfccd-122">Task and details page</span></span> | <span data-ttu-id="dfccd-123">Página de la cámara</span><span class="sxs-lookup"><span data-stu-id="dfccd-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![camera-scanning-example-task-detail-page](./media/camera-scanning-example-task-detail-page50.png)          | ![camera-scanning-example-camera-page-smaller](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="dfccd-126">En la página de la cámara, al hacer clic en el botón Cámara, aparecerá atenuada mientras trata de identificar un código de barras.</span><span class="sxs-lookup"><span data-stu-id="dfccd-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="dfccd-127">Si no se identifica un código de barras en menos de 5 segundos, el proceso se pondrá en tiempo de espera y el botón Cámara volverá a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="dfccd-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="dfccd-128">A continuación, podrá intentar escanear de nuevo un código de barras.</span><span class="sxs-lookup"><span data-stu-id="dfccd-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="dfccd-129">Cuando apunte la cámara a un código de barras, mantenga el código de barras alineado entre los corchetes para lograr un mejor resultado.</span><span class="sxs-lookup"><span data-stu-id="dfccd-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="dfccd-130">Cuando un código de barras se digitaliza correctamente, el resultado se procesará y pasará al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="dfccd-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="dfccd-131">Si el siguiente paso contiene otro campo de entrada con el modo de entrada preferido establecido en Exploración, la página de la cámara se volverá a iniciar.</span><span class="sxs-lookup"><span data-stu-id="dfccd-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="dfccd-132">Si el paso siguiente no es un campo de exploración, la página de la cámara no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="dfccd-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>

