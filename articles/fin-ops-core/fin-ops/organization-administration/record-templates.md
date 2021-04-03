---
title: Visión general de las plantillas de registro
description: Este artículo presenta el concepto de las plantillas de registro y explica cómo se pueden usar para crear registros que comparten información.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a37b4875fd2bf6e981cbe6ee2cc7e999be7b5f36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559902"
---
# <a name="record-templates-overview"></a><span data-ttu-id="89780-103">Visión general de las plantillas de registro</span><span class="sxs-lookup"><span data-stu-id="89780-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89780-104">Este artículo presenta el concepto de las plantillas de registro y explica cómo se pueden usar para crear registros que comparten información.</span><span class="sxs-lookup"><span data-stu-id="89780-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="89780-105">Las plantillas de registro ayudan a crear los registros más rápidamente, aunque sólo se pueden crear plantillas de registro para algunos tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="89780-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="89780-106">Por ejemplo, imagínese que está introduciendo información de alquiler para un negocio de alquiler de coches ubicado en Valladolid.</span><span class="sxs-lookup"><span data-stu-id="89780-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="89780-107">Dado que es probable que la mayoría de los clientes sean de la zona de Valladolid, estaría bien que se rellenasen automáticamente los valores para los campos de **Provincia**, **País** y **Ciudad** en el formulario de alquiler.</span><span class="sxs-lookup"><span data-stu-id="89780-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="89780-108">Solo se pueden aplicar plantillas para las áreas a las que se tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="89780-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="89780-109">Sin embargo, todos los títulos de plantilla están visibles para el usuario actual cuando se crea un registro nuevo, así como a los demás usuarios si se crean plantillas que estarán disponibles a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="89780-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="89780-110">Asegúrese de tener esto en cuenta al asignar nombres a las plantillas.</span><span class="sxs-lookup"><span data-stu-id="89780-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="89780-111">Por ejemplo, evite usar nombres que incluyan palabras como "comisión" en caso de que sea confidencial que algunos empleados de la empresa tengan salarios basados en comisiones.</span><span class="sxs-lookup"><span data-stu-id="89780-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="89780-112">Cuando una o varias plantillas a las que tiene acceso se han creado para un formulario específico e intenta crear un nuevo registro en el formulario, se mostrará la página **Seleccionar una plantilla para...** .</span><span class="sxs-lookup"><span data-stu-id="89780-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="89780-113">Al seleccionar una plantilla de la lista, se crea un registro nuevo que contiene la información predeterminada que se basa en la plantilla que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="89780-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="89780-114">Si no desea utilizar plantillas al crear registros nuevos, active la casilla de verificación **No volver a hacer esta pregunta** en la página **Seleccionar una plantilla para**.</span><span class="sxs-lookup"><span data-stu-id="89780-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="89780-115">Para volver a mostrar el cuadro de diálogo de selección de plantilla, haga clic en **Información de registro** y después en **Mostrar la selección de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="89780-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]