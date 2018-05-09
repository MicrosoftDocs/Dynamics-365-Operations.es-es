---
title: "El delimitador de plan de cuentas debe ser único"
description: "En Dynamics 365 for Finance and Operations, no puede tener el mismo delimitador para el plan de cuentas y los valores de dimensión. Debe cambiar los valores del delimitador tras la actualización."
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e12c47e4acd6aa8a92a909d490da9e590b5fcd20
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="chart-of-accounts-delimiter-must-be-unique"></a><span data-ttu-id="71285-104">El delimitador de plan de cuentas debe ser único</span><span class="sxs-lookup"><span data-stu-id="71285-104">Chart of accounts delimiter must be unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71285-105">En Microsoft Dynamics AX 2012, puede utilizar el mismo delimitador para el plan de cuentas y los valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="71285-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="71285-106">En Dynamics 365 for Finance and Operations, no puede tener el mismo delimitador para el plan de cuentas y los valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="71285-106">In Dynamics 365 for Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="71285-107">Si hay un delimitador duplicado, puede cambiarlo tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="71285-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="71285-108">Esta característica está disponible en:</span><span class="sxs-lookup"><span data-stu-id="71285-108">This feature is available in:</span></span>
- <span data-ttu-id="71285-109">Dynamics 365 for Finance and Operations versión 8.0</span><span class="sxs-lookup"><span data-stu-id="71285-109">Dynamics 365 for Finance and Operations version 8.0</span></span>
- <span data-ttu-id="71285-110">Dynamics 365 for Finance and Operations versión 7.1, KB 4094701 no puede especificar las dimensiones financieras cuando los valores de dimensión contienen el delimitador del plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="71285-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="71285-111">Dynamics 365 for Finance and Operations versión 7.2, KB 4092967 no puede elegir subproyecto como dimensión cuando el formato de subproyecto contiene el delimitador de la dimensión</span><span class="sxs-lookup"><span data-stu-id="71285-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="71285-112">Actualizar el delimitador</span><span class="sxs-lookup"><span data-stu-id="71285-112">Update delimiter</span></span>
<span data-ttu-id="71285-113">Si existe conflicto con el plan de cuentas, se puede cambiar el delimitador del plan de cuentas y el formato de id. del proyecto o del subproyecto.</span><span class="sxs-lookup"><span data-stu-id="71285-113">If there is a conflict with the Chart of Accounts, the Chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="71285-114">Ningún otro delimitador de dimensión se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="71285-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="71285-115">Puede cambiar el delimitador del plan de cuentas después de la actualización a Finance and Operations en **Parámetros de contabilidad general** > **Plan de cuentas y dimensiones** > **Cambiar delimitador**.</span><span class="sxs-lookup"><span data-stu-id="71285-115">You can change the chart of accounts delimiter after upgrade to Finance and Operations in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="71285-116">Si el único conflicto está en el formato de Id. de proyecto/subproyecto, es posible cambiar el valor en **Gestión de proyectos y parametros de contabilidad** > **General** > **Modificar el formato de subproyecto**.</span><span class="sxs-lookup"><span data-stu-id="71285-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="71285-117">Cómo determinar si el entorno requiere delimitadores actualizados</span><span class="sxs-lookup"><span data-stu-id="71285-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="71285-118">Si los delimitadores en el entorno actualizado están en conflicto, es posible que se produzca inestabilidad al especificar valores en un control de entrada segmentado o control de entrada de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="71285-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="71285-119">Esto significa que deberá usar siempre búsquedas o un menú desplegable al especificar combinaciones de cuenta y dimensión.</span><span class="sxs-lookup"><span data-stu-id="71285-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>

