---
title: Evaluación de condiciones
description: En este tema se explica cómo crear una plantilla y un registro de evaluación de condiciones para un activo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2694b3ee51e2619a94e7ea2f4039fb52adddbbc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208924"
---
# <a name="condition-assessment"></a><span data-ttu-id="f28c5-103">Evaluación de condiciones</span><span class="sxs-lookup"><span data-stu-id="f28c5-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f28c5-104">En este tema se explica cómo crear una plantilla y un registro de evaluación de condiciones para un activo en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="f28c5-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="f28c5-105">La evaluación de condiciones se realiza a intervalos regulares, y el objetivo principal es crear y mantener datos de condiciones en activos.</span><span class="sxs-lookup"><span data-stu-id="f28c5-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="f28c5-106">Visto desde la perspectiva del mantenimiento preventivo, es importante supervisar la información esencial, como el estado actual, y el tiempo de vida restante.</span><span class="sxs-lookup"><span data-stu-id="f28c5-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="f28c5-107">Además, si realiza la evaluación de condiciones periódicamente podrá controlar y comparar las condiciones en la maquinaria de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="f28c5-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="f28c5-108">La evaluación de condiciones se puede utilizar para medir y supervisar muchas condiciones de sus equipos.</span><span class="sxs-lookup"><span data-stu-id="f28c5-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="f28c5-109">Por ejemplo, puede medir las vibraciones de la maquinaria.</span><span class="sxs-lookup"><span data-stu-id="f28c5-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="f28c5-110">Una vez que haya registrado medidas de vibración en Administración de activos para distintos tipos de equipo, puede buscar la evaluación registrada más reciente y ver medidas de vibración.</span><span class="sxs-lookup"><span data-stu-id="f28c5-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="f28c5-111">La evaluación de condiciones se crea en los activos.</span><span class="sxs-lookup"><span data-stu-id="f28c5-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="f28c5-112">Debe configurar una plantilla de la evaluación de condiciones en un tipo de activo antes de realizar el procedimiento de evaluación de condiciones.</span><span class="sxs-lookup"><span data-stu-id="f28c5-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="f28c5-113">La razón para utilizar plantillas para la evaluación de condiciones es evitar la variación de los datos de condiciones en activos similares.</span><span class="sxs-lookup"><span data-stu-id="f28c5-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="f28c5-114">La secuencia para configurar y usar la evaluación de condiciones en Administración de activos es la siguiente: primero debe configurar las plantillas necesarias de la evaluación de condiciones.</span><span class="sxs-lookup"><span data-stu-id="f28c5-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="f28c5-115">A continuación, debe asociar las plantillas con los tipos de activos del formulario **Tipos de activos**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="f28c5-116">Por último, puede crear registros de evaluación de condiciones en un activo en el formulario **Activo**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="f28c5-117">Crear una plantilla de evaluación de condiciones</span><span class="sxs-lookup"><span data-stu-id="f28c5-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="f28c5-118">Seleccione **Administración de activos** > **Configuración** > **Tipos de activos** > **Evaluación de condiciones**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="f28c5-119">Seleccionar **Nuevo** para crear una plantilla nueva.</span><span class="sxs-lookup"><span data-stu-id="f28c5-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="f28c5-120">Inserte un identificador para la plantilla en el campo **Plantilla**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="f28c5-121">Inserte un nombre para la plantilla en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="f28c5-122">En la ficha desplegable **Líneas de evaluación de condiciones**, agregue las líneas que necesita para la evaluación de condiciones, incluida la selección del tipo y la unidad de medida de la condición.</span><span class="sxs-lookup"><span data-stu-id="f28c5-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="f28c5-123">En la ficha desplegable **Tipos de activos**, agregue los tipos de activos que deben usar la plantilla de evaluación de condiciones.</span><span class="sxs-lookup"><span data-stu-id="f28c5-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="f28c5-124">En los campos **Líneas** y **Tipos de activos** del grupo **Detalles** en la parte superior de la pantalla, verá el número de líneas de evaluación y tipos de activos relacionados con la plantilla de evaluación de condiciones seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f28c5-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="f28c5-125">Crear un registro de evaluación de condiciones en un activo</span><span class="sxs-lookup"><span data-stu-id="f28c5-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="f28c5-126">Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="f28c5-127">En la lista, seleccione el activo para el que desea crear un registro de evaluación de condiciones.</span><span class="sxs-lookup"><span data-stu-id="f28c5-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="f28c5-128">En la pestaña **General**, haga clic en **Evaluación de condiciones**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="f28c5-129">Haga clic en **Nuevo** para crear un registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="f28c5-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="f28c5-130">Seleccione la fecha para la evaluación de condiciones en el campo **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="f28c5-131">Seleccione el nombre del trabajador que realizó el registro de la evaluación de condiciones en el campo **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="f28c5-132">En el campo **Líneas** verá el número de líneas de evaluación configuradas en la evaluación de condiciones.</span><span class="sxs-lookup"><span data-stu-id="f28c5-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="f28c5-133">Seleccione una plantilla para la evaluación de condiciones en el campo **Plantilla**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="f28c5-134">El nombre de la plantilla se inserta automáticamente en el campo **Nombre**, y las líneas de registro relacionadas se insertarán en la ficha desplegable **Líneas de evaluación de condiciones**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="f28c5-135">Puede insertar notas relacionadas con la evaluación de condiciones seleccionada en la ficha desplegable **Notas**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="f28c5-136">Para cada línea de la evaluación de condiciones, inserte datos de medida en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="f28c5-137">Puede insertar un comentario relacionado con la línea de registro seleccionada en la ficha desplegable **Líneas de evaluación de condiciones** > campo **Comentarios**.</span><span class="sxs-lookup"><span data-stu-id="f28c5-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="f28c5-138">Si agrega un comentario a una línea, la casilla **Comentario** se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f28c5-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="f28c5-139">Tras un registro de evaluación de condiciones en un activo, puede imprimir un informe de evaluación de condiciones.</span><span class="sxs-lookup"><span data-stu-id="f28c5-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="f28c5-140">También puede registrar la evaluación de condiciones en una orden de trabajo (**Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** >  botón **Evaluación de condiciones**.)</span><span class="sxs-lookup"><span data-stu-id="f28c5-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>
