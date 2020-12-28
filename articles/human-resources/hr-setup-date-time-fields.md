---
title: Comprender los campos de fecha y hora
description: Comprende qué esperar al usar los campos de fecha y hora de Microsoft Dynamics 365 Human Resources. Gana claridad en qué esperar al interactuar con datos de fecha y hora en un formulario en Human Resources, un origen externo o Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 027e46d53fd9704f5483e90409be53c1510e8cd4
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529861"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="10d70-104">Comprender los campos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="10d70-104">Understand Date and Time fields</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="10d70-105">los campos **Fecha y hora** son un concepto fundamental en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="10d70-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="10d70-106">Es importante comprender cómo trabajar con los datos de **Fecha y hora** en formularios de Dynamics 365 Human Resources, Common Data Service y orígenes externos.</span><span class="sxs-lookup"><span data-stu-id="10d70-106">It's important to understand how to work with **Date and Time** data in Dynamics 365 Human Resources forms, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="10d70-107">Comprensión de la diferencia entre los tipos de datos de los campo de fecha y fecha y hora</span><span class="sxs-lookup"><span data-stu-id="10d70-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="10d70-108">Los campos **Fecha y hora** contienen información de la zona horaria, mientras que los campos **Fecha** no.</span><span class="sxs-lookup"><span data-stu-id="10d70-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="10d70-109">Los campos **Fecha** muestran la misma información en cualquier ubicación.</span><span class="sxs-lookup"><span data-stu-id="10d70-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="10d70-110">Cuando se especifica una fecha en un campo **Fecha**, Human Resources escribe esa misma fecha en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10d70-110">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="10d70-111">Al visualizar datos en un campo **Fecha y hora**, Human Resources ajusta la fecha y hora basada en función de la zona horaria del usuario establecida en el formulario **Opciones de usuario** (**Común > Configuración > Opciones de usuario**).</span><span class="sxs-lookup"><span data-stu-id="10d70-111">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="10d70-112">Puede que la información de fecha y hora que especifique en el campo no sea la misma que la información escrita en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10d70-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="10d70-113">[![Formulario de opciones de usuario](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="10d70-114">Comprensión de los campos de fecha y hora en los formularios</span><span class="sxs-lookup"><span data-stu-id="10d70-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="10d70-115">Al especificar datos en un campo **Fecha y hora**, los datos visualizados en la pantalla no son los mismos que los datos almacenados en la base de datos si la zona horaria del usuario no se establece en la hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="10d70-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="10d70-116">Los datos de campos **Fecha y hora** se almacenan siempre como UTC.</span><span class="sxs-lookup"><span data-stu-id="10d70-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="10d70-117">[![Formulario de trabajador](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="10d70-118">Comprensión de los campos de fecha y hora en la base de datos</span><span class="sxs-lookup"><span data-stu-id="10d70-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="10d70-119">Cuando Human Resources escribe un valor de **Fecha y hora** en la base de datos, almacena los datos en UTC.</span><span class="sxs-lookup"><span data-stu-id="10d70-119">When Human Resources writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="10d70-120">Esto permite a los usuarios ver los datos **Fecha y hora** en relación con la zona horaria definida en sus opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="10d70-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="10d70-121">En el ejemplo anterior, la hora de inicio es un punto en el tiempo, no una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="10d70-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="10d70-122">Al cambiar la zona horaria del usuario que ha iniciado sesión de GMT +12:00 a GMT UTC, el mismo registro terminado de crear muestra 30/04/2019 12:00:00 en lugar de 01/05/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="10d70-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="10d70-123">En el siguiente ejemplo, el empleo del empleado 000724 se activa al mismo tiempo independientemente de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="10d70-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="10d70-124">El empleado estará activo el 30/04/2019 en la zona horaria del GMT, que es lo mismo que 01/05/2019 en la zona horaria GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="10d70-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="10d70-125">Ambas hacen referencia el mismo momento dado y no a una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="10d70-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="10d70-126">[![Formulario de trabajador](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="10d70-127">Datos de fecha y hora en marco de administración de datos, Excel, Common Data Service y Power BI</span><span class="sxs-lookup"><span data-stu-id="10d70-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="10d70-128">El marco de gestión de datos, el complemento de Excel, Common Data Service, y la notificación de Power BI están diseñados para interactuar con datos directamente en el nivel de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10d70-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="10d70-129">Dado que no hay cliente para ajustar los datos **Fecha y hora** a la zona horaria del usuario, todos los valores **Fecha y hora** se muestran en UTC, lo que puede conducir a algunas suposiciones incorrectas al especificar o ver datos.</span><span class="sxs-lookup"><span data-stu-id="10d70-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="10d70-130">La base de datos asume que los datos **Fecha y hora** que se registran mediante DMF, Excel, o Common Data Service están en UTC.</span><span class="sxs-lookup"><span data-stu-id="10d70-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="10d70-131">Esto puede provocar cierta confusión cuando el valor **Fecha y hora** enviado no se muestra del modo esperado porque el usuario que ve los datos no tiene su zona horaria establecida en UTC.</span><span class="sxs-lookup"><span data-stu-id="10d70-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="10d70-132">La misma cosa puede suceder a la inversa, cuando se exportan los datos.</span><span class="sxs-lookup"><span data-stu-id="10d70-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="10d70-133">Los datos **Fecha y hora** de la entidad exportada de DMF pueden ser diferentes de lo que se presenta en el cliente de Dynamics.</span><span class="sxs-lookup"><span data-stu-id="10d70-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="10d70-134">Al usar fuentes externas como DMF para ver o crear datos, es importante tener presente que los valores **Fecha y hora** se consideran de forma predeterminada que están en UTC independientemente de la zona horaria del equipo del usuario o de los valores de la zona horaria del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="10d70-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="10d70-135">Ejemplos del mismo registro que se muestra en varias áreas del producto</span><span class="sxs-lookup"><span data-stu-id="10d70-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="10d70-136">**Human Resources con la zona horaria del usuario configurada en UTC**.</span><span class="sxs-lookup"><span data-stu-id="10d70-136">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="10d70-137">[![Formulario de trabajador](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="10d70-138">**Human Resources con la zona horaria del usuario configurada en GMT +12:00**.</span><span class="sxs-lookup"><span data-stu-id="10d70-138">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="10d70-139">[![Formulario de trabajador](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="10d70-140">**Excel mediante OData**</span><span class="sxs-lookup"><span data-stu-id="10d70-140">**Excel Via OData**</span></span>

<span data-ttu-id="10d70-141">[![Excel mediante OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="10d70-142">**Ubicación provisional de DMF**</span><span class="sxs-lookup"><span data-stu-id="10d70-142">**DMF Staging**</span></span>

<span data-ttu-id="10d70-143">[![Ubicación provisional de DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="10d70-144">**Exportar DMF**</span><span class="sxs-lookup"><span data-stu-id="10d70-144">**DMF Export**</span></span>

<span data-ttu-id="10d70-145">[![Ubicación provisional de DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="10d70-146">**Excel mediante Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="10d70-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="10d70-147">[![Excel mediante Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="10d70-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="10d70-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10d70-148">See also</span></span>

[<span data-ttu-id="10d70-149">Datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="10d70-149">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="10d70-150">Zonas horarias preferidas del usuario</span><span class="sxs-lookup"><span data-stu-id="10d70-150">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
