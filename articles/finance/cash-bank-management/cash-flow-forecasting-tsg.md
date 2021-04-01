---
title: Solucionar problemas de configuración de pronóstico de flujo de efectivo
description: Este tema ofrece respuestas a preguntas que puede que tenga al configurar la previsión de flujo de efectivo. Aborda las preguntas frecuentes (FAQ) sobre la configuración del flujo de efectivo, las actualizaciones del flujo de efectivo y el flujo de efectivo de Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1cde9321259753bd0cacab3706c7f8455598ff3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232498"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="92f0e-104">Solucionar problemas de configuración de pronóstico de flujo de efectivo</span><span class="sxs-lookup"><span data-stu-id="92f0e-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92f0e-105">Este tema ofrece respuestas a preguntas que puede que tenga al configurar la previsión de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="92f0e-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="92f0e-106">Aborda las preguntas frecuentes (FAQ) sobre la configuración del flujo de efectivo, las actualizaciones del flujo de efectivo y el flujo de efectivo de Power BI.</span><span class="sxs-lookup"><span data-stu-id="92f0e-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="92f0e-107">¿Por qué se muestra el flujo de efectivo para una sola entidad legal?</span><span class="sxs-lookup"><span data-stu-id="92f0e-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="92f0e-108">La previsión de flujo de caja se configura y calcula por entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="92f0e-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="92f0e-109">Los informes de Power BI y la capacidad de pronóstico de flujo de efectivo en Finance Insights muestran los resultados.</span><span class="sxs-lookup"><span data-stu-id="92f0e-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="92f0e-110">La previsión de flujo de efectivo debe configurarse para cada entidad jurídica para la que desee ver una previsión.</span><span class="sxs-lookup"><span data-stu-id="92f0e-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="92f0e-111">Revise la configuración de la previsión de flujo de caja en todas sus entidades legales.</span><span class="sxs-lookup"><span data-stu-id="92f0e-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="92f0e-112">Alternativamente, revise la configuración de todas las entidades legales para la previsión de flujo de efectivo y asegúrese de que estén configuradas según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="92f0e-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="92f0e-113">¿Por qué Power BI no muestra todos los datos de flujo de caja?</span><span class="sxs-lookup"><span data-stu-id="92f0e-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="92f0e-114">Se deben completar varios pasos para que los pronósticos de flujo de efectivo puedan aparecer en las vistas de Power BI.</span><span class="sxs-lookup"><span data-stu-id="92f0e-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="92f0e-115">Revise la siguiente lista de comprobación y asegúrese de que se hayan completado todos los pasos:</span><span class="sxs-lookup"><span data-stu-id="92f0e-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="92f0e-116">Configure el flujo de caja para cada entidad legal.</span><span class="sxs-lookup"><span data-stu-id="92f0e-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="92f0e-117">En los parámetros de contabilidad general, configure la divisa del sistema y el tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="92f0e-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="92f0e-118">Configure la divisa de contabilidad general y el tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="92f0e-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="92f0e-119">Introduzca los tipos de cambio entre la divisa de transacción y la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="92f0e-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="92f0e-120">Introduzca los tipos de cambio entre la divisa contable y la divisa del sistema.</span><span class="sxs-lookup"><span data-stu-id="92f0e-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="92f0e-121">Introduzca los tipos de cambio entre la divisa contable y cada divisa de banco.</span><span class="sxs-lookup"><span data-stu-id="92f0e-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="92f0e-122">¿Por qué el flujo de caja de Power BI funciona en versiones anteriores pero ahora está en blanco?</span><span class="sxs-lookup"><span data-stu-id="92f0e-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="92f0e-123">Verifique que se hayan configurado las medidas de "Medida de flujo de efectivo V2" y "LedgerCovLiquidityMeasurement" del almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="92f0e-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="92f0e-124">Para obtener más información sobre cómo trabajar con datos en , consulte [Integración de Power BI con el almacén de entidades](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verifique que todos los pasos necesarios para ver el contenido de Power BI se hayan completado.</span><span class="sxs-lookup"><span data-stu-id="92f0e-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="92f0e-125">Para obtener más información, consulte [Contenido de Power BI de visión general de efectivo](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="92f0e-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="92f0e-126">¿Se han actualizado las entidades del almacén de entidades?</span><span class="sxs-lookup"><span data-stu-id="92f0e-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="92f0e-127">Debe actualizar periódicamente sus entidades para asegurarse de que los datos estén actualizados y sean precisos.</span><span class="sxs-lookup"><span data-stu-id="92f0e-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="92f0e-128">Para actualizar manualmente una entidad específica, vaya a **Administración del sistema \> Configurar \> Almacén de entidades**, seleccione la entidad y luego seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="92f0e-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="92f0e-129">Los datos también se pueden actualizar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="92f0e-129">The data can also be updated automatically.</span></span> <span data-ttu-id="92f0e-130">En la página **Almacén de entidades**, configure la opción **Actualización automática habilitada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="92f0e-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]