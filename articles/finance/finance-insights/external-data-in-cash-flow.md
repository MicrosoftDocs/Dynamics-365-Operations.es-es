---
title: Utilizar datos externos en las previsiones de flujo de efectivo (versión preliminar)
description: Este tema describe los pasos de configuración que debe completar para que los datos externos se puedan introducir o importar en los pronósticos de flujo de efectivo.
author: rcarlson
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ddfc0670a5fca24d996e9ab605e267f9f3f26f19
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897897"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="b4e42-103">Utilizar datos externos en las previsiones de flujo de efectivo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b4e42-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b4e42-104">Los datos externos se pueden introducir o importar en forma de pronósticos de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="b4e42-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="b4e42-105">Este tema describe los pasos de configuración que son específicos para el uso de datos externos y que permiten que los datos externos se incluyan en una previsión de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="b4e42-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="b4e42-106">Configuración de datos externos</span><span class="sxs-lookup"><span data-stu-id="b4e42-106">External data setup</span></span>

<span data-ttu-id="b4e42-107">Utilice la pestaña **Fuente externa** de la página **Configuración de pronóstico de flujo de efectivo** (**Gestión de efectivo y banco \> Previsión de flujo de efectivo**) para introducir configuraciones que admitan el uso de datos externos en las previsiones de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="b4e42-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="b4e42-108">Para obtener más información sobre la configuración, consulte [Previsión de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md).</span><span class="sxs-lookup"><span data-stu-id="b4e42-108">For more information about the setup, see [Cash flow forecasting](../cash-bank-management/cash-flow-forecasting.md).</span></span>

<span data-ttu-id="b4e42-109">Para introducir datos externos para pronósticos de flujo de efectivo, puede usar la experiencia Abrir en Excel para introducir y modificar datos externos.</span><span class="sxs-lookup"><span data-stu-id="b4e42-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="b4e42-110">Seleccione el botón **Datos externos** y luego seleccione **Agregar datos externos** o **Editar datos externos existentes**.</span><span class="sxs-lookup"><span data-stu-id="b4e42-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="b4e42-111">Cuando se abre el archivo de Microsoft Excel, puede introducir información en los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="b4e42-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="b4e42-112">**Id. de entrada**</span><span class="sxs-lookup"><span data-stu-id="b4e42-112">**Entry ID**</span></span>
- <span data-ttu-id="b4e42-113">**Descripción** (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4e42-113">**Description** (optional)</span></span>
- <span data-ttu-id="b4e42-114">**Nombre de fuente externa**: seleccione uno de los valores de la lista que definió al configurar Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="b4e42-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="b4e42-115">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="b4e42-115">**Legal Entity**</span></span>
- <span data-ttu-id="b4e42-116">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="b4e42-116">**Date**</span></span>
- <span data-ttu-id="b4e42-117">**Importe en divisa de transacción**</span><span class="sxs-lookup"><span data-stu-id="b4e42-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="b4e42-118">**Código de divisa**</span><span class="sxs-lookup"><span data-stu-id="b4e42-118">**Currency Code**</span></span>
- <span data-ttu-id="b4e42-119">**Dimensión predeterminada** (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4e42-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="b4e42-120">**Número del Documento** (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4e42-120">**Document number** (optional)</span></span>
- <span data-ttu-id="b4e42-121">**Número de cuenta** (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4e42-121">**Account number** (optional)</span></span>
- <span data-ttu-id="b4e42-122">**Nombre de cuenta** (opcional)</span><span class="sxs-lookup"><span data-stu-id="b4e42-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="b4e42-123">Importación de datos externos mediante el marco Administración de datos</span><span class="sxs-lookup"><span data-stu-id="b4e42-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="b4e42-124">Puede importar datos externos para las previsiones de flujo de efectivo mediante el espacio de trabajo **Administración de datos** y la entidad que se denomina **Entrada de fuente externa de pronóstico de flujo de efectivo**.</span><span class="sxs-lookup"><span data-stu-id="b4e42-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="b4e42-125">Además, si debe mover los datos de configuración de un entorno a otro, las siguientes entidades están disponibles para las tablas de configuración necesarias:</span><span class="sxs-lookup"><span data-stu-id="b4e42-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="b4e42-126">Configuración de origen externo de previsión de flujo de efectivo</span><span class="sxs-lookup"><span data-stu-id="b4e42-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="b4e42-127">Configuración de entidad jurídica de origen externo de previsión de flujo de efectivo</span><span class="sxs-lookup"><span data-stu-id="b4e42-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="b4e42-128">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="b4e42-128">Privacy notice</span></span>
<span data-ttu-id="b4e42-129">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="b4e42-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]