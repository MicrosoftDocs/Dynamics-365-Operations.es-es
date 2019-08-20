---
title: Importación de la configuración de transferencia de crédito ISO20022
description: Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de proveedor.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee7e69611d31d2577ebafdfc059b0936aef0520b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848800"
---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="9d651-103">Importación de la configuración de transferencia de crédito ISO20022</span><span class="sxs-lookup"><span data-stu-id="9d651-103">Import ISO20022 credit transfer configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d651-104">Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="9d651-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="9d651-105">El formato alemán de transferencia de crédito ISO 20022 se usa como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9d651-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="9d651-106">Este procedimiento se puede utilizar para otro formato de informes electrónicos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9d651-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="9d651-107">Esta tarea se creó con la empresa de datos de demostración DEMF pero puede usar cualquier empresa de datos de demostración para completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="9d651-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="9d651-108">Esta es la primera de cinco tareas que conjuntamente muestran el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9d651-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="9d651-109">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9d651-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="9d651-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9d651-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9d651-111">En la lista de proveedores de configuración disponibles, seleccione Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d651-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="9d651-112">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="9d651-112">Click Set active.</span></span>
4. <span data-ttu-id="9d651-113">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="9d651-113">Click Repositories.</span></span>
5. <span data-ttu-id="9d651-114">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="9d651-114">Click Open.</span></span>
6. <span data-ttu-id="9d651-115">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="9d651-115">Click Show filters.</span></span>
7. <span data-ttu-id="9d651-116">Aplique los siguientes filtros: especifique un valor de filtro de "Transferencia de crédito ISO20022 (DE)" en el campo "Nombre de configuración" mediante el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="9d651-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="9d651-117">De forma alternativa, puede buscar la configuración en la lista, seleccionarla y trasladarla a la tarea de importación.</span><span class="sxs-lookup"><span data-stu-id="9d651-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="9d651-118">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="9d651-118">Click Import.</span></span>
    * <span data-ttu-id="9d651-119">Si el botón Importar no está disponible, es que la configuración ya se ha importado.</span><span class="sxs-lookup"><span data-stu-id="9d651-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="9d651-120">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="9d651-120">Click Yes.</span></span>

