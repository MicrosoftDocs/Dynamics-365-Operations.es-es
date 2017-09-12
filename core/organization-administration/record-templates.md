---
title: Crear plantillas de registro
description: "Este artículo presenta el concepto de las plantillas de registro y explica cómo se pueden usar para crear registros que comparten información."
author: pvillads
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 9b184800ce845fa046e0cae38392e07141378dbb
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="create-record-templates"></a><span data-ttu-id="878ba-103">Crear plantillas de registro</span><span class="sxs-lookup"><span data-stu-id="878ba-103">Create record templates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="878ba-104">Este artículo presenta el concepto de las plantillas de registro y explica cómo se pueden usar para crear registros que comparten información.</span><span class="sxs-lookup"><span data-stu-id="878ba-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="878ba-105">Las plantillas de registro pueden ayudarle a crear registros más rápidamente en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="878ba-105">Record templates can help you to create records more quickly in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="878ba-106">Puede crear plantillas de registro solo para parte de los tipos de registro de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="878ba-106">You can create record templates for only some of the record types in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="878ba-107">Por ejemplo, **** imagínese que está introduciendo información de alquiler para un negocio de alquiler de coches ubicado en Valladolid.</span><span class="sxs-lookup"><span data-stu-id="878ba-107">For example, **** imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="878ba-108">Dado que es probable que la mayoría de los clientes sean de la zona de Valladolid, estaría bien que se rellenasen automáticamente los valores para los campos de **Provincia**, **País** y **Ciudad** en el formulario de alquiler.</span><span class="sxs-lookup"><span data-stu-id="878ba-108">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span> <span data-ttu-id="878ba-109">**Nota:** solo se pueden aplicar plantillas para las áreas de Finance and Operations a las que se tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="878ba-109">**Note:** You can apply templates only for the areas of Finance and Operations that you have access to.</span></span> <span data-ttu-id="878ba-110">Sin embargo, todos los títulos de plantilla están visibles para el usuario actual cuando se crea un registro nuevo, así como a los demás usuarios si se crean plantillas que estarán disponibles a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="878ba-110">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="878ba-111">Asegúrese de tener esto en cuenta al asignar nombres a las plantillas.</span><span class="sxs-lookup"><span data-stu-id="878ba-111">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="878ba-112">Por ejemplo, evite usar nombres que incluyan palabras como "comisión" en caso de que sea confidencial que algunos empleados de la empresa tengan salarios basados en comisiones.</span><span class="sxs-lookup"><span data-stu-id="878ba-112">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span> <span data-ttu-id="878ba-113">Cuando una o varias plantillas a las que tiene acceso se han creado para un formulario específico e intenta crear un nuevo registro en el formulario, se mostrará la página **Seleccionar una plantilla para...** .</span><span class="sxs-lookup"><span data-stu-id="878ba-113">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="878ba-114">Al seleccionar una plantilla de la lista, se crea un registro nuevo que contiene la información predeterminada que se basa en la plantilla que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="878ba-114">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="878ba-115">Si no desea utilizar plantillas al crear registros nuevos, active la casilla de verificación **No volver a hacer esta pregunta** en la página **Seleccionar una plantilla para**.</span><span class="sxs-lookup"><span data-stu-id="878ba-115">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="878ba-116">Para volver a mostrar el cuadro de diálogo de selección de plantilla, haga clic en **Información de registro** y después en **Mostrar la selección de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="878ba-116">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>




