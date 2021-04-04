---
title: Sincronizar fecha y hora en trabajos de importación
description: Utilice las zonas horarias UTC en los trabajos de importación para evitar problemas con las conversiones de zona horaria.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce3bf39e8342d3fe19a253f6d17684b2bd0aec0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570490"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="301c3-103">Sincronizar fecha y hora en trabajos de importación</span><span class="sxs-lookup"><span data-stu-id="301c3-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="301c3-104">Es importante establecer la zona horaria de su trabajo de importación en la hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="301c3-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="301c3-105">Es posible que vea fechas y horas inesperadas en sus datos importados si usa una configuración diferente.</span><span class="sxs-lookup"><span data-stu-id="301c3-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="301c3-106">Sin la configuración correcta, el proceso de importación convierte la fecha UTC al formato local y, después, la configuración del sistema la convierte nuevamente.</span><span class="sxs-lookup"><span data-stu-id="301c3-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="301c3-107">Esta conversión dual hace que las fechas cambien entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="301c3-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="301c3-108">Por ejemplo, la conversión dual podría hacer que la fecha de inicio de un empleado sea diferente entre Dynamics 365 Human Resources y Dynamics 365 Finance debido a las diferencias en las zonas horarias locales.</span><span class="sxs-lookup"><span data-stu-id="301c3-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="301c3-109">Establecer el trabajo de importación en UTC resuelve este problema.</span><span class="sxs-lookup"><span data-stu-id="301c3-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="301c3-110">En Dynamics 365 Finance and Operations, seleccione **Administración de datos**.</span><span class="sxs-lookup"><span data-stu-id="301c3-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="301c3-111">Seleccione **Importar proyectos** y luego seleccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="301c3-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="301c3-112">En **Formato de fecha de origen**, seleccione **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="301c3-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="301c3-113">[![Cambiar el formato de la fecha de origen a UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="301c3-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="301c3-114">Cambie la **Zona horaria** a **Zona horaria universal coordinada**, y cambie **Idioma** a **En-US**.</span><span class="sxs-lookup"><span data-stu-id="301c3-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]