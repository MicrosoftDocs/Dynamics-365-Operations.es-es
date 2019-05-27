---
title: Autorizar previsión de la demanda ajustada
description: No todos los datos de previsión se deben autorizar inmediatamente. Este artículo se explica cómo puede especificar el período para el que una previsión está autorizada. También explica cómo puede autorizar la previsión para empresas y modelos de previsión específicos.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c397329993bd3014b608cdc50d5002dcd5ed6a4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547087"
---
# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="70279-105">Autorizar previsión de la demanda ajustada</span><span class="sxs-lookup"><span data-stu-id="70279-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70279-106">No todos los datos de previsión se deben autorizar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="70279-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="70279-107">Este artículo se explica cómo puede especificar el período para el que una previsión está autorizada.</span><span class="sxs-lookup"><span data-stu-id="70279-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="70279-108">También explica cómo puede autorizar la previsión para empresas y modelos de previsión específicos.</span><span class="sxs-lookup"><span data-stu-id="70279-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="70279-109">No todos los datos de previsión se deben autorizar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="70279-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="70279-110">Puede especificar las fechas de inicio y fin del período para el que la previsión está autorizada.</span><span class="sxs-lookup"><span data-stu-id="70279-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="70279-111">Esta función le permite congelar los cubos específicos.</span><span class="sxs-lookup"><span data-stu-id="70279-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="70279-112">Las fechas de inicio y fin que especifique deben corresponder a las fechas de inicio y fin del depósito en que se genera la previsión.</span><span class="sxs-lookup"><span data-stu-id="70279-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="70279-113">El sistema aplica esta restricción y ajusta automáticamente las fechas, si se requiere el ajuste.</span><span class="sxs-lookup"><span data-stu-id="70279-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="70279-114">En la pestaña **Detalles** de la página **Autorización**, puede ver los detalles acerca de la previsión que se generó recientemente.</span><span class="sxs-lookup"><span data-stu-id="70279-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="70279-115">Puede seleccionar las empresas y los modelos de previsión para autorizar la programación para el uso.</span><span class="sxs-lookup"><span data-stu-id="70279-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="70279-116">De forma predeterminada, la cuadrícula incluye a todas las empresas para la que la demanda prevista se ha creado.</span><span class="sxs-lookup"><span data-stu-id="70279-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="70279-117">Para cada empresa, se rellena previamente el modelo de previsión que corresponde al plan de previsión actual que está configurado en los parámetros de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="70279-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="70279-118">Sin embargo, puede cambiar este modelo de previsión a cualquier modelo de previsión que pertenezca a dicha empresa.</span><span class="sxs-lookup"><span data-stu-id="70279-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="70279-119">Si no se han generado datos de la demanda prevista para una empresa seleccionada, recibirá un mensaje de advertencia en el momento de la importación.</span><span class="sxs-lookup"><span data-stu-id="70279-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="70279-120">Es muy importante que entienda cómo funciona la casilla **Guardar los ajustes manuales realizados en la previsión de la demanda de la línea base**.</span><span class="sxs-lookup"><span data-stu-id="70279-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="70279-121">Si ha realizado ajustes manuales a la previsión estadística de línea base, los valores ajustados están autorizados para su uso, incluso si esta casilla está desactivada.</span><span class="sxs-lookup"><span data-stu-id="70279-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="70279-122">Sin embargo, los cambios se descartan después de la autorización.</span><span class="sxs-lookup"><span data-stu-id="70279-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="70279-123">Por lo tanto, la próxima vez que se genera una previsión, esa previsión solo es una previsión estadística y no tiene invalidación manual, incluso si selecciona **Transferir ajustes manuales a la previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="70279-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="70279-124">Por lo tanto, puede considerar la casilla **Guardar los ajustes manuales realizados en la previsión de la demanda de la línea base** un mecanismo que le permite conservar o descartar todos los cambios manuales.</span><span class="sxs-lookup"><span data-stu-id="70279-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="additional-resources"></a><span data-ttu-id="70279-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="70279-125">Additional resources</span></span>
--------

[<span data-ttu-id="70279-126">Realización de ajustes manuales realizados en la previsión de línea base</span><span class="sxs-lookup"><span data-stu-id="70279-126">Making manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="70279-127">Supervisión de la precisión de previsión</span><span class="sxs-lookup"><span data-stu-id="70279-127">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)



