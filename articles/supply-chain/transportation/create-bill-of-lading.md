---
title: Crear un conocimiento de embarque
description: Este tema describe cómo crear un conocimiento de embarque al utilizar procesos de gestión de almacenes.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd014f5804681936920b47e999709f153def11bc
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437272"
---
# <a name="create-a-bill-of-lading"></a><span data-ttu-id="e4504-103">Crear un conocimiento de embarque</span><span class="sxs-lookup"><span data-stu-id="e4504-103">Create a bill of lading</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4504-104">Este tema describe cómo crear un conocimiento de embarque al utilizar procesos de gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="e4504-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="e4504-105">Un conocimiento de embarque es un documento legal entre la empresa que envía los artículos y el transportista.</span><span class="sxs-lookup"><span data-stu-id="e4504-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="e4504-106">El documento acompaña a los artículos enviados y sirve como recepción de envío cuando los artículos se entregan en el destino.</span><span class="sxs-lookup"><span data-stu-id="e4504-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="e4504-107">Si utiliza la gestión de almacenes, hay dos maneras de generar un conocimiento de embarque:</span><span class="sxs-lookup"><span data-stu-id="e4504-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="e4504-108">Cree el informe manualmente, mediante la página **Conocimiento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="e4504-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="e4504-109">Genere el informe desde el **Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="e4504-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="e4504-110">Si genera el conocimiento de embarque desde el **Área de trabajo de planificación de la carga**, el estado de carga debe ser **Enviados**.</span><span class="sxs-lookup"><span data-stu-id="e4504-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="e4504-111">Si hay más de un envío en la carga, se crea un conocimiento de embarque para cada envío.</span><span class="sxs-lookup"><span data-stu-id="e4504-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="e4504-112">Una vez que se ha creado un conocimiento de embarque, puede realizar cambios en él en la página **Conocimiento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="e4504-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="e4504-113">Conocimiento de embarque maestro</span><span class="sxs-lookup"><span data-stu-id="e4504-113">Master bill of lading</span></span>
<span data-ttu-id="e4504-114">Si hay más de un envío en la carga, puede generar un conocimiento de embarque maestro.</span><span class="sxs-lookup"><span data-stu-id="e4504-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="e4504-115">Esto tiene el mismo diseño e información que un conocimiento de embarque, pero contiene el contenido resumido para todos los envíos.</span><span class="sxs-lookup"><span data-stu-id="e4504-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="e4504-116">Si la opción **Crear un conocimiento de embarque maestro cuando exista más de un envío en una carga** se establece en **Sí** en la página **Parámetros de administración de transporte**, se genera automáticamente un conocimiento de embarque maestro si crea un conocimiento de embarque en **Área de trabajo de planificación de la carga** y hay más de un envío.</span><span class="sxs-lookup"><span data-stu-id="e4504-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="e4504-117">También puede obtener una lista de los conocimientos de embarque haciendo clic en **Información relacionada** &gt; **Conocimiento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="e4504-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="e4504-118">Si está creando conocimientos de embarque manualmente, puede crear un conocimiento de embarque maestro en la página **Conocimiento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="e4504-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>



