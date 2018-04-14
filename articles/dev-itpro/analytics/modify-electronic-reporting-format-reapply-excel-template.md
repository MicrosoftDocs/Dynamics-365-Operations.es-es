---
title: "Modificar un formato de informe electrónico al aplicar de nuevo una plantilla de Microsoft Excel"
description: "Este tema proporciona información acerca de cómo puede modificar el formato de informes electrónicos (ER) que se usa para generar documentos empresariales reaplicando una plantilla de Excel modificada."
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: eb0a37acebb61c7f4f06724bf0234211072f1e98
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="modify-an-electronic-reporting-format-by-reapplying-a-microsoft-excel-template"></a><span data-ttu-id="eb687-103">Modificar un formato de informe electrónico al aplicar de nuevo una plantilla de Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="eb687-103">Modify an Electronic reporting format by reapplying a Microsoft Excel template</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="eb687-104">La herramienta de informes electrónicos (ER) se usa para generar documentos empresariales en formato electrónico.</span><span class="sxs-lookup"><span data-stu-id="eb687-104">The Electronic reporting (ER) tool is used to generate business documents in an electronic format.</span></span> <span data-ttu-id="eb687-105">Para generar un documento empresarial, debe crear un formato de ER, y luego usar el diseñador de ER para definir el diseño de documento empresarial y especificar los datos que se deben incluir en él.</span><span class="sxs-lookup"><span data-stu-id="eb687-105">To generate a business document, you must create an ER format, and then use the ER designer to define the layout of the business document and specify the data that should be included in it.</span></span> <span data-ttu-id="eb687-106">A continuación puede ejecutar el formato de ER para generar el documento empresarial.</span><span class="sxs-lookup"><span data-stu-id="eb687-106">You can then run the ER format to generate the business document.</span></span>

<span data-ttu-id="eb687-107">La herramienta de ER se puede usar para generar documentos empresariales como archivos de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="eb687-107">The ER tool can be used to generate business documents as Microsoft Excel files.</span></span> <span data-ttu-id="eb687-108">Puede usar un documento de Excel como plantilla para estos documentos.</span><span class="sxs-lookup"><span data-stu-id="eb687-108">You can use an Excel document as a template for these documents.</span></span> <span data-ttu-id="eb687-109">Para definir el diseño de documento en el diseñador de ER, puede importar el contenido del documento de Excel que desea utilizar como plantilla en el formato definido de ER.</span><span class="sxs-lookup"><span data-stu-id="eb687-109">To define the document layout in the ER designer, you can import the contents of the Excel document that you want to use as a template into the defined ER format.</span></span> <span data-ttu-id="eb687-110">Para más detalles y practicar este escenario, reproduzca la guía de tareas **Diseñar una configuración ER para generar informes en formato OPENXML** (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)).</span><span class="sxs-lookup"><span data-stu-id="eb687-110">For more details, and to practice this scenario, play the task guide **ER Design a configuration for generating reports in OPENXML format** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span>

<span data-ttu-id="eb687-111">Si edita el documento de Excel que se usa como plantilla para un documento empresarial, la nueva funcionalidad de ER permite reaplicar la plantilla actualiza al formato de ER.</span><span class="sxs-lookup"><span data-stu-id="eb687-111">If you edit the Excel document that is used as a template for a business document, new ER functionality lets you reapply the updated template to the ER format.</span></span> <span data-ttu-id="eb687-112">El formato de ER se actualiza a continuación para ajustarse a la plantilla actualizada.</span><span class="sxs-lookup"><span data-stu-id="eb687-112">The ER format is then updated so that it adheres to the updated template.</span></span> <span data-ttu-id="eb687-113">Para más detalles sobre esta funcionalidad, reproduzca la guía de tareas **Modificar un formato de ER reaplicando una plantilla de Excel** (parte del proceso empresarial 7.5.5.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10683)).</span><span class="sxs-lookup"><span data-stu-id="eb687-113">For more details about this functionality, play the task guide **ER Modify a format by reapplying an Excel template** (part of the 7.5.5.3 Acquire/Develop IT service/solution components (10683) business process).</span></span> <span data-ttu-id="eb687-114">En el paso de la guía de tareas donde importa una plantilla actualizada, utilice plantilla modificada del archivo de Excel de informe de pago, SampleVendPaymWsReport2, como plantilla.</span><span class="sxs-lookup"><span data-stu-id="eb687-114">In the task guide step where you import an updated template, use the modified template of the Payment Report Excel file, SampleVendPaymWsReport2, as a template.</span></span>

