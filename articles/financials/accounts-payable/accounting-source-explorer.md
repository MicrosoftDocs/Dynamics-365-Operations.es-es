---
title: Explorador de origen de contabilidad
description: "Este artículo proporciona información acerca del explorador del origen de contabilidad, que puede usar para análisis detallado de la información de origen detrás de asientos contables de la contabilidad general."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d5d9f7ff6b4d3ea764717240f9736a81c1aee6c1
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="accounting-source-explorer"></a><span data-ttu-id="b50c6-103">Explorador de origen de contabilidad</span><span class="sxs-lookup"><span data-stu-id="b50c6-103">Accounting source explorer</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="b50c6-104">Este artículo proporciona información acerca del explorador del origen de contabilidad, que puede usar para análisis detallado de la información de origen detrás de asientos contables de la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="b50c6-104">This article provides information about Accounting source explorer, which you can use for detailed analysis of the source information behind general ledger accounting entries.</span></span>

<span data-ttu-id="b50c6-105">El Explorador de origen de la contabilidad es una nueva página que muestra la información de origen.</span><span class="sxs-lookup"><span data-stu-id="b50c6-105">Accounting source explorer is a new page that shows source information.</span></span> <span data-ttu-id="b50c6-106">Puede usar el Explorador del origen de contabilidad como herramienta independiente o analizar los detalles detrás de asientos contables de la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="b50c6-106">You can use Accounting source explorer either as a stand-alone tool or to analyze the details behind general ledger accounting entries.</span></span> <span data-ttu-id="b50c6-107">Por ejemplo, puede usar el Explorador de origen de contabilidad para obtener la información de origen detallada para un saldo en Saldo de comprobación o para una transacción de asiento.</span><span class="sxs-lookup"><span data-stu-id="b50c6-107">For example, you can use Accounting source explorer to get the most detailed source information for a balance in Trail balance or for a voucher transaction.</span></span> <span data-ttu-id="b50c6-108">Puede usar la característica Exportar a Microsoft Excel para segmentar y desglosar la información en Microsoft Excel (por ejemplo, en una tabla dinámica o un informe de tablas dinámicas).</span><span class="sxs-lookup"><span data-stu-id="b50c6-108">You can then use the Export to MS Excel feature to further slice and dice the information in Microsoft Excel (for example, in a PivotTable or on a PivotTable report).</span></span>

<span data-ttu-id="b50c6-109">El Explorador de origen de contabilidad siempre muestra el mismo importe total por cuenta contable que muestra la Contabilidad general (por ejemplo, en un Saldo de comprobación).</span><span class="sxs-lookup"><span data-stu-id="b50c6-109">Accounting source explorer always shows the same total amount per ledger account as General ledger shows (for example, in Trial balance).</span></span> <span data-ttu-id="b50c6-110">Como en un Saldo de comprobación, puede mostrar segmentos en columnas independientes.</span><span class="sxs-lookup"><span data-stu-id="b50c6-110">As in Trial balance, you can display segments in separate columns.</span></span> <span data-ttu-id="b50c6-111">Solo tiene que seleccionar el conjunto adecuado de dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="b50c6-111">Just select the appropriate financial dimension set.</span></span> 

<span data-ttu-id="b50c6-112">Puede usar parámetros para definir un intervalo de fechas para el análisis.</span><span class="sxs-lookup"><span data-stu-id="b50c6-112">You can use parameters to define a date interval for the analysis.</span></span> <span data-ttu-id="b50c6-113">Esta funcionalidad también es similar a la funcionalidad de Saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="b50c6-113">This functionality also resembles the functionality in Trial balance.</span></span>

<span data-ttu-id="b50c6-114">Para todos los documentos que usan el marco del documento de origen, El explorador de origen de contabilidad muestra información adicional basada en las distribuciones contables y, si procede, en distribuciones contables del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b50c6-114">For all documents that use the source document framework, Accounting source explorer shows additional information, based on accounting distributions and, if applicable, project accounting distributions.</span></span> <span data-ttu-id="b50c6-115">Esta información incluye el tipo de importe monetario, el proyecto, la actividad, la categoría y la propiedad de línea.</span><span class="sxs-lookup"><span data-stu-id="b50c6-115">This information includes the monetary amount type, project, activity, category, and line property.</span></span> <span data-ttu-id="b50c6-116">A continuación se muestran algunos ejemplos del análisis que puede realizar:</span><span class="sxs-lookup"><span data-stu-id="b50c6-116">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="b50c6-117">Desviaciones entre los pedidos de compra y las facturas de proveedor, porque cada desviación está representada por un tipo de importe monetario, como la desviación de cargos</span><span class="sxs-lookup"><span data-stu-id="b50c6-117">Variances between purchase orders and vendor invoices, because each variance is represented by a monetary amount type, such as charge variance</span></span>
-   <span data-ttu-id="b50c6-118">Gastos y horas facturables frente a no facturables por proyecto, unidad de negocio y cuenta principal</span><span class="sxs-lookup"><span data-stu-id="b50c6-118">Billable versus non-billable hours and expenses per project, business unit, and main account</span></span>

<span data-ttu-id="b50c6-119">Para documentos de origen que usen el concepto de identidades de referencia de documento de origen, el Explorador de origen de contabilidad muestra incluso más detalles, como el cliente, el proveedor, el trabajador, el producto, la cantidad, el texto de unidad y las descripciones.</span><span class="sxs-lookup"><span data-stu-id="b50c6-119">For source documents that use the source document reference identities concept, Accounting source explorer shows even more details, such as the customer, vendor, worker, product, quantity, unit text, and descriptions.</span></span> <span data-ttu-id="b50c6-120">A continuación se muestran algunos ejemplos del análisis que puede realizar:</span><span class="sxs-lookup"><span data-stu-id="b50c6-120">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="b50c6-121">Los gastos de hotel por unidad de negocio y el marca de hotel para un período fiscal, en función de los informes de gastos</span><span class="sxs-lookup"><span data-stu-id="b50c6-121">Hotel expenses per business unit and hotel brand for a fiscal period, based on expense reports</span></span>
-   <span data-ttu-id="b50c6-122">Descuentos por proveedor, producto, departamento</span><span class="sxs-lookup"><span data-stu-id="b50c6-122">Discounts per vendor, product, department</span></span>

<span data-ttu-id="b50c6-123">Para estos documentos, también puede navegar hasta el documento de origen real desde el Explorador de origen de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="b50c6-123">For these documents, you can also navigate to the actual source document from Accounting source explorer.</span></span>




