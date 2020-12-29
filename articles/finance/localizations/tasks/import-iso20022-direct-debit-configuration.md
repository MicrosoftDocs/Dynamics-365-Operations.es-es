---
title: Importación de la configuración de domiciliación bancaria ISO20022
description: Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de cliente.
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
ms.openlocfilehash: e5d4256b155d3e06d63e425fab63b4025ef2577f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447649"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="ee3a1-103">Importación de la configuración de domiciliación bancaria ISO20022</span><span class="sxs-lookup"><span data-stu-id="ee3a1-103">Import ISO20022 direct debit configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee3a1-104">Este procedimiento muestra cómo importar una configuración de informes electrónicos de pagos de cliente.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="ee3a1-105">Este procedimiento usa el formato de débito directo ISO 20022 como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="ee3a1-106">Este procedimiento se creó con la empresa de datos de demostración DEMF pero puede usar cualquier empresa de datos de demostración para este fin.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="ee3a1-107">Este es el primero de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="ee3a1-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="ee3a1-109">En la lista de proveedores de configuración disponibles, seleccione Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee3a1-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="ee3a1-110">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-110">Click Set active.</span></span>
4. <span data-ttu-id="ee3a1-111">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-111">Click Repositories.</span></span>
5. <span data-ttu-id="ee3a1-112">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-112">Click Open.</span></span>
6. <span data-ttu-id="ee3a1-113">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-113">Click Show filters.</span></span>
7. <span data-ttu-id="ee3a1-114">Aplique los siguientes filtros: especifique un valor de filtro de "Domiciliación bancaria ISO20022 (DE)" en el campo "Nombre de configuración" mediante el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="ee3a1-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="ee3a1-115">Opcionalmente, puede encontrar la configuración en la lista, seleccionarla y omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="ee3a1-116">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-116">Click Import.</span></span>
    * <span data-ttu-id="ee3a1-117">Si el botón Importar no está disponible, es que la configuración ya se ha importado.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="ee3a1-118">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="ee3a1-118">Click Yes.</span></span>

