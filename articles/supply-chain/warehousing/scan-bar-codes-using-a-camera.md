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
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 28a49736f43bd2d3bfd4c6856f2f87079a005ba2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239311"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a><span data-ttu-id="d9dfa-103">Digitalizar códigos de barras mediante una cámara en la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="d9dfa-103">Scan bar codes using a camera in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9dfa-104">Este tema explica cómo configurar la aplicación de almacén para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-104">This topic explains how to set up the warehouse app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d9dfa-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d9dfa-105">Prerequisites</span></span>
<span data-ttu-id="d9dfa-106">Para utilizar esta característica, debe tener instalada la versión 1.2.0.0 de la aplicación de almacén y su dispositivo debe tener una cámara.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-106">To use this feature, you need to have version 1.2.0.0 of the warehouse app installed, and your device must have a camera.</span></span> <span data-ttu-id="d9dfa-107">Cuando abra la aplicación después de actualizarla, se le solicitará que permita a la aplicación usar la cámara.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="d9dfa-108">Si su dispositivo no tiene cámara, no se mostrará ningún mensaje y no podrá utilizar una cámara como escáner.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="d9dfa-109">Configurar</span><span class="sxs-lookup"><span data-stu-id="d9dfa-109">Setup</span></span>
<span data-ttu-id="d9dfa-110">En la configuración de visualización de la aplicación de almacén, puede seleccionar si la cámara debe utilizarse para la digitalización de códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-110">In the Display settings of the warehouse application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="d9dfa-111">Si habilita la opción **Usar la cámara como escáner**, puede usar la cámara en cada campo de entrada que tenga el modo de entrada preferido establecido en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="d9dfa-112">Para controlar si un campo de entrada debe ser escaneable, en la página **Nombres de campo de aplicación Warehouse**, establezca **Modo de entrada preferido** en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="d9dfa-113">Cuando se selecciona esta opción, se puede usar una cámara para escanear en la aplicación de almacén.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-113">When this option is selected, a camera can be used for scanning in the warehouse app.</span></span> <span data-ttu-id="d9dfa-114">Para obtener información sobre cómo configurar nombres de campo en Warehousing, consulte [Configurar nombres de campo de aplicación en la aplicación de almacén](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="d9dfa-114">For information about how to configure app field names in Warehousing, see [Configure app field names in warehouse app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="d9dfa-115">Formatos de códigos de barras admitidos</span><span class="sxs-lookup"><span data-stu-id="d9dfa-115">Supported bar code formats</span></span>
<span data-ttu-id="d9dfa-116">Se admiten los formatos de códigos de barras más comúnes, incluido el Código 128, el Código 39, el Código 93, EAN-8, EAN-13, UPC-E, UPC-A y códigos QR.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="d9dfa-117">Navegación</span><span class="sxs-lookup"><span data-stu-id="d9dfa-117">Navigation</span></span>
<span data-ttu-id="d9dfa-118">La página de la cámara se iniciará en cada página donde el campo de entrada tenga el modo de entrada preferido establecido en Exploración, cuando se encuentre en la página Cámara, use las siguientes opciones para navegar:</span><span class="sxs-lookup"><span data-stu-id="d9dfa-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="d9dfa-119">Haga clic en el botón Atrás para volver a la página de tarea y detalles.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="d9dfa-120">Haga clic en el lápiz en la página de tarea y detalles para pasar a la página donde puede escribir la entrada manualmente.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="d9dfa-121">Haga clic en la cámara en la página de tarea y detalles para volver a la página Cámara.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="d9dfa-122">Página de tarea y detalles</span><span class="sxs-lookup"><span data-stu-id="d9dfa-122">Task and details page</span></span> | <span data-ttu-id="d9dfa-123">Página de la cámara</span><span class="sxs-lookup"><span data-stu-id="d9dfa-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Página de detalles de tarea de ejemplo de escaneo de cámara](./media/camera-scanning-example-task-detail-page50.png)          | ![Ejemplo de escaneo de cámara, página de cámara más pequeña](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="d9dfa-126">En la página de la cámara, al hacer clic en el botón Cámara, aparecerá atenuada mientras trata de identificar un código de barras.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="d9dfa-127">Si no se identifica un código de barras en menos de 5 segundos, el proceso se pondrá en tiempo de espera y el botón Cámara volverá a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="d9dfa-128">A continuación, podrá intentar escanear de nuevo un código de barras.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="d9dfa-129">Cuando apunte la cámara a un código de barras, mantenga el código de barras alineado entre los corchetes para lograr un mejor resultado.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="d9dfa-130">Cuando un código de barras se digitaliza correctamente, el resultado se procesará y pasará al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="d9dfa-131">Si el siguiente paso contiene otro campo de entrada con el modo de entrada preferido establecido en Exploración, la página de la cámara se volverá a iniciar.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="d9dfa-132">Si el paso siguiente no es un campo de exploración, la página de la cámara no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="d9dfa-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]