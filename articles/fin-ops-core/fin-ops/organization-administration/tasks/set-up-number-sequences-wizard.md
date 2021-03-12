---
title: Configurar secuencias numéricas mediante un asistente
description: En ese tema se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 684983d1ea54264cc378ded8e9dca3cf9ec2c901
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799041"
---
# <a name="set-up-number-sequences-using-a-wizard"></a><span data-ttu-id="f7500-103">Configurar secuencias numéricas mediante un asistente</span><span class="sxs-lookup"><span data-stu-id="f7500-103">Set up number sequences using a wizard</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7500-104">Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan.</span><span class="sxs-lookup"><span data-stu-id="f7500-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="f7500-105">El registro de datos maestros o de transacciones que necesita un identificador se denomina referencia.</span><span class="sxs-lookup"><span data-stu-id="f7500-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="f7500-106">Para poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia.</span><span class="sxs-lookup"><span data-stu-id="f7500-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="f7500-107">En ese tema se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente.</span><span class="sxs-lookup"><span data-stu-id="f7500-107">This topic explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="f7500-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="f7500-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="f7500-109">Vaya a **Navegación > Módulos > Administración de la organización > Secuencias numéricas > Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="f7500-109">Go to **Navigation > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="f7500-110">Seleccione **Generar**.</span><span class="sxs-lookup"><span data-stu-id="f7500-110">Select **Generate**.</span></span>
3. <span data-ttu-id="f7500-111">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7500-111">Select **Next**.</span></span>

   - <span data-ttu-id="f7500-112">En esta página, puede modificar el código de identificación, el valor más bajo y el valor más alto.</span><span class="sxs-lookup"><span data-stu-id="f7500-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="f7500-113">Además, puede indicar si la secuencia numérica debe ser continua.</span><span class="sxs-lookup"><span data-stu-id="f7500-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
   - <span data-ttu-id="f7500-114">No seleccione la opción **Continuo** si debe preasignar números para la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="f7500-114">Do not select the **Continuous** option if you must preallocate numbers for the number sequence.</span></span> <span data-ttu-id="f7500-115">Para agregar un segmento de ámbito al formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, seleccione **Incluir ámbito en el formato**.</span><span class="sxs-lookup"><span data-stu-id="f7500-115">To add a scope segment to the format of a number sequence, select the format in the list, and then select **Include scope in format**.</span></span> <span data-ttu-id="f7500-116">Para quitar un segmento de ámbito del formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, seleccione **Quitar ámbito del formato**.</span><span class="sxs-lookup"><span data-stu-id="f7500-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then select **Remove scope from format**.</span></span> <span data-ttu-id="f7500-117">Para excluir una secuencia numérica de la generación automática, seleccione la secuencia numérica en la lista y, a continuación, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f7500-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then select **Delete**.</span></span>  

4. <span data-ttu-id="f7500-118">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7500-118">Select **Next**.</span></span>
5. <span data-ttu-id="f7500-119">Seleccione **Fin**.</span><span class="sxs-lookup"><span data-stu-id="f7500-119">Select **Finish**.</span></span>

