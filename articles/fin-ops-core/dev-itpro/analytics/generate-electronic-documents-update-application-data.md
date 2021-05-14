---
title: Generar documentos electrónicos y actualizar datos de aplicación utilizando ER
description: Puede diseñar los formatos de informes electrónicos (ER) que se pueden usar en la aplicación para generar documentos electrónicos salientes.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f66a173c7d66f915a7802e42caf1a36f661eea1
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944326"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="1b868-103">Generar documentos electrónicos y actualizar datos de aplicaciones mediante ER</span><span class="sxs-lookup"><span data-stu-id="1b868-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b868-104">Puede diseñar los formatos de informes electrónicos (ER) que se pueden usar en la aplicación para generar documentos electrónicos salientes.</span><span class="sxs-lookup"><span data-stu-id="1b868-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="1b868-105">También puede diseñar formatos de ER que analizan los documentos electrónicos entrantes y usan el contenido en esos documentos para actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b868-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="1b868-106">Con esta funcionalidad, un único formato de ER se puede usar para generar documentos electrónicos salientes y actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b868-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="1b868-107">Esta función también se puede en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b868-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="1b868-108">Para evitar el uso repetido de datos de la aplicación en procesos posteriores puede marcar un dato de aplicación inmediatamente después que se usa para generar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1b868-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="1b868-109">Por ejemplo, puede marcar transacciones de pago como ya procesadas inmediatamente después de que se hayan incluido en un mensaje de pago generado.</span><span class="sxs-lookup"><span data-stu-id="1b868-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="1b868-110">Para archivar los detalles del procesamiento de los documentos electrónicos que se han generado mediante la lógica de ER.</span><span class="sxs-lookup"><span data-stu-id="1b868-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="1b868-111">Por ejemplo, una identificación única del mensaje de pago que se genera mediante la expresión de ER.</span><span class="sxs-lookup"><span data-stu-id="1b868-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="1b868-112">La expresión se basa en la información especificada al cuadro de diálogo de ER cuando el formato de ER se ejecuta para generar documentos.</span><span class="sxs-lookup"><span data-stu-id="1b868-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="1b868-113">Para obtener más información acerca de esta función, reproduzca el conjunto de documentos Generar ER con las guías de tareas de actualización de los datos de la aplicación (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)), que describen los detalles de la generación de informes y el archivado de intrastat.</span><span class="sxs-lookup"><span data-stu-id="1b868-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="1b868-114">Los archivos siguientes son necesarios para completar determinados pasos en estas guías de tareas.</span><span class="sxs-lookup"><span data-stu-id="1b868-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="1b868-115">Descargue y guardar estos archivos en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="1b868-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="1b868-116">Configuración del modelo de datos de ER: intrastat (modelo)</span><span class="sxs-lookup"><span data-stu-id="1b868-116">ER data model configuration: Intrastat (model)</span></span>](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [<span data-ttu-id="1b868-117">Configuración de la asignación del modelo de ER: intrastat (asignación)</span><span class="sxs-lookup"><span data-stu-id="1b868-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [<span data-ttu-id="1b868-118">Configuración del formato de ER: intrastat (formato)</span><span class="sxs-lookup"><span data-stu-id="1b868-118">ER format configuration: Intrastat (format)</span></span>](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
