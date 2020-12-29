---
title: Analizar documentos de entrada en formato de Excel
description: Este tema proporciona información sobre el diseño de los formatos de informes electrónicos (ER) que analizan el contenido de los archivos de Microsoft Excel de entrada.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 6e27806d3b94eb485705cec539a4849b81fbba91
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685796"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="f2e7d-103">Analizar documentos de entrada en formato de Excel</span><span class="sxs-lookup"><span data-stu-id="f2e7d-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f2e7d-104">Puede diseñar los formatos de informes electrónicos de (ER) para analizar archivos de Microsoft Excel de entrada que representan datos en los libros de Microsoft Excel (archivos en formato de XLSX).</span><span class="sxs-lookup"><span data-stu-id="f2e7d-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="f2e7d-105">Puede usar el contenido de estos archivos para actualizar datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="f2e7d-106">Esto resulta útil si:</span><span class="sxs-lookup"><span data-stu-id="f2e7d-106">This is useful if you:</span></span>

- <span data-ttu-id="f2e7d-107">Diseña un modelo y un formato nuevos y los desea probar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="f2e7d-108">En este caso, Excel simulará los datos de la aplicación reales.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="f2e7d-109">Gestiona los datos más allá de la aplicación en Excel y desea importar estos datos para mostrar un informe específico.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="f2e7d-110">Para obtener más información acerca de esta función, reproduzca las guías de tareas **Datos de importación de ER de un archivo de Microsoft Excel (Parte 1: Formato de diseño)** y **Datos de importación de ER de un archivo de Microsoft Excel (Parte 2: Datos de la importación)** (partes del proceso empresarial 7.5.4.3 Acquire/servicio Develop IT/componentes de la solución (10677)).</span><span class="sxs-lookup"><span data-stu-id="f2e7d-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="f2e7d-111">Estas guías de la tarea le enseñan cómo el archivo de Excel de entrada se puede analizar mediante el formato de ER para importar la información de documentos de entrada y actualizar datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="f2e7d-112">Puede descargar los archivos de la guía de tareas del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="f2e7d-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="f2e7d-113">Descargue los siguientes archivos para completar la guía de tareas mencionadas arriba.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="f2e7d-114">Descripción del contenido</span><span class="sxs-lookup"><span data-stu-id="f2e7d-114">Content description</span></span>                         | <span data-ttu-id="f2e7d-115">Archivo</span><span class="sxs-lookup"><span data-stu-id="f2e7d-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="f2e7d-116">Archivo de entrada en el formato .XLSX - plantilla</span><span class="sxs-lookup"><span data-stu-id="f2e7d-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="f2e7d-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="f2e7d-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="f2e7d-118">Archivo de entrada en el formato .XLSX - datos de muestra</span><span class="sxs-lookup"><span data-stu-id="f2e7d-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="f2e7d-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="f2e7d-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="f2e7d-120">Si aún no ha reproducido la guía de tareas siguiente, [ER Crear las configuraciones necesarias para importar datos desde un archivo externo](./tasks/er-required-configurations-import-data.md) en la aplicación actual Finance and Operations, descargue el siguiente archivo.</span><span class="sxs-lookup"><span data-stu-id="f2e7d-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Finance and Operations application, download the following file.</span></span>

| <span data-ttu-id="f2e7d-121">Descripción del contenido</span><span class="sxs-lookup"><span data-stu-id="f2e7d-121">Content description</span></span>    | <span data-ttu-id="f2e7d-122">Archivo</span><span class="sxs-lookup"><span data-stu-id="f2e7d-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="f2e7d-123">Configuración del modelo de ER</span><span class="sxs-lookup"><span data-stu-id="f2e7d-123">ER model configuration</span></span> | [<span data-ttu-id="f2e7d-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="f2e7d-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
