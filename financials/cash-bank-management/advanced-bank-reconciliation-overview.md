---
title: "Visión general de conciliación bancaria avanzada"
description: "Este artículo describe el flujo del proceso avanzado de conciliación bancaria. La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 33150777222faa97af7488c59ab13cb0fb9e8e2c
ms.contentlocale: es-es
ms.lasthandoff: 06/29/2017


---

# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="c67b9-104">Visión general de conciliación bancaria avanzada</span><span class="sxs-lookup"><span data-stu-id="c67b9-104">Advanced bank reconciliation overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c67b9-105">Este artículo describe el flujo del proceso avanzado de conciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="c67b9-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="c67b9-106">La característica de conciliación bancaria avanzada le permite importar los extractos bancarios que se pueden conciliar automáticamente desde dentro de las transacciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="c67b9-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="c67b9-107">La característica avanzada de conciliación bancaria le permite importar extractos bancarios.</span><span class="sxs-lookup"><span data-stu-id="c67b9-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="c67b9-108">El extracto bancario importado se podrá conciliar automáticamente desde dentro de las transacciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="c67b9-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="c67b9-109">Estos son los pasos del flujo de conciliación bancaria avanzada.</span><span class="sxs-lookup"><span data-stu-id="c67b9-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="c67b9-110">Configure una importación de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="c67b9-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="c67b9-111">Importe extractos bancarios a través del marco de entidad de datos.</span><span class="sxs-lookup"><span data-stu-id="c67b9-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="c67b9-112">Se integran tres formatos de extracto bancario típicos: ISO20022, BAI2 y MT940.</span><span class="sxs-lookup"><span data-stu-id="c67b9-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="c67b9-113">Las funciones se pueden ampliar a cualquier formato.</span><span class="sxs-lookup"><span data-stu-id="c67b9-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="c67b9-114">Configure una secuencia numérica para usarla para conciliación bancaria avanzada y defina las reglas de coincidencia de conciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="c67b9-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="c67b9-115">Una regla de coincidencia de conciliación es un conjunto de criterios que se usan para filtrar líneas de extracto bancario y líneas de transacción bancaria de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, durante el proceso de conciliación.</span><span class="sxs-lookup"><span data-stu-id="c67b9-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations, Enterprise edition bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="c67b9-116">En función de la práctica empresarial, puede configurar más de una regla coincidente para automatizar y optimizar el proceso de conciliación.</span><span class="sxs-lookup"><span data-stu-id="c67b9-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="c67b9-117">Concilie extractos bancarios con las transacciones bancarias de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c67b9-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="c67b9-118">Realice la creación y la conciliación automáticas de diarios de conciliación.</span><span class="sxs-lookup"><span data-stu-id="c67b9-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="c67b9-119">Vea extractos bancarios y las transacciones bancarias de Microsoft Dynamics 365 for Finance and Operations en paralelo.</span><span class="sxs-lookup"><span data-stu-id="c67b9-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="c67b9-120">Registre automáticamente transacciones bancarias de Microsoft Dynamics 365 for Finance and Operations si aparecen en un extracto bancario pero no aparecen en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c67b9-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="c67b9-121">Genere un extracto de conciliación.</span><span class="sxs-lookup"><span data-stu-id="c67b9-121">Generate a reconciliation statement.</span></span>






