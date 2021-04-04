---
title: Hacer único el delimitador del plan de cuentas
description: Este tema explica cómo no puede tener el mismo delimitador para el plan contable y los valores de dimensión. Debe cambiar los valores del delimitador tras la actualización.
author: panolte
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 183980651a811ef30a49461ff5a5f649d94b079c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565271"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="35edd-104">Hacer único el delimitador del plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="35edd-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35edd-105">En Microsoft Dynamics AX 2012, puede utilizar el mismo delimitador para el plan de cuentas y los valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="35edd-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="35edd-106">En las versiones actuales de Finance and Operations, no puede tener el mismo delimitador para el plan de cuentas y los valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="35edd-106">In current versions of Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="35edd-107">Si hay un delimitador duplicado, puede cambiarlo tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="35edd-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="35edd-108">Esta función está disponible en las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="35edd-108">This feature is available in the following versions:</span></span>
- <span data-ttu-id="35edd-109">Finance and Operations versión 8.0</span><span class="sxs-lookup"><span data-stu-id="35edd-109">Finance and Operations version 8.0</span></span>
- <span data-ttu-id="35edd-110">Finance and Operations versión 7.1, KB 4094701 no puede especificar las dimensiones financieras cuando los valores de dimensión contienen el delimitador del plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="35edd-110">Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="35edd-111">Finance and Operations versión 7.2, KB 4092967 no puede elegir subproyecto como dimensión cuando el formato de subproyecto contiene el delimitador de la dimensión</span><span class="sxs-lookup"><span data-stu-id="35edd-111">Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="35edd-112">Actualizar el delimitador</span><span class="sxs-lookup"><span data-stu-id="35edd-112">Update delimiter</span></span>
<span data-ttu-id="35edd-113">Si existe conflicto con el plan de cuentas, se puede cambiar el delimitador del plan de cuentas y el formato de id. del proyecto o del subproyecto.</span><span class="sxs-lookup"><span data-stu-id="35edd-113">If there is a conflict with the chart of accounts, the chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="35edd-114">Ningún otro delimitador de dimensión se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="35edd-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="35edd-115">Puede cambiar el delimitador del plan de cuentas después de la actualización en **Parámetros de contabilidad general** > **Plan de cuentas y dimensiones** > **Cambiar delimitador**.</span><span class="sxs-lookup"><span data-stu-id="35edd-115">You can change the chart of accounts delimiter after upgrade in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="35edd-116">Si el único conflicto está en el formato de Id. de proyecto/subproyecto, es posible cambiar el valor en **Gestión de proyectos y parametros de contabilidad** > **General** > **Modificar el formato de subproyecto**.</span><span class="sxs-lookup"><span data-stu-id="35edd-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="35edd-117">Cómo determinar si el entorno requiere delimitadores actualizados</span><span class="sxs-lookup"><span data-stu-id="35edd-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="35edd-118">Si los delimitadores en el entorno actualizado están en conflicto, es posible que se produzca inestabilidad al especificar valores en un control de entrada segmentado o control de entrada de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="35edd-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="35edd-119">Esto significa que deberá usar siempre búsquedas o un menú desplegable al especificar combinaciones de cuenta y dimensión.</span><span class="sxs-lookup"><span data-stu-id="35edd-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]