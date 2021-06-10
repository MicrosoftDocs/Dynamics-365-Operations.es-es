---
title: Comprender los campos de fecha y hora
description: Comprende qué esperar al usar los campos de fecha y hora de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b7e5726f7e4beea1584b9a8e142212531ba1db56
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051746"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="b082c-103">Comprender campos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="b082c-103">Understand Date and Time fields</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b082c-104">los campos **Fecha y hora** son un concepto fundamental en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b082c-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b082c-105">Es importante comprender cómo trabajar con los datos de **Fecha y hora** en formularios, Dataverse y orígenes externos.</span><span class="sxs-lookup"><span data-stu-id="b082c-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="b082c-106">Comprensión de la diferencia entre los tipos de datos de los campo de fecha y fecha y hora</span><span class="sxs-lookup"><span data-stu-id="b082c-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="b082c-107">Los campos **Fecha y hora** contienen información de la zona horaria, mientras que los campos **Fecha** no.</span><span class="sxs-lookup"><span data-stu-id="b082c-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="b082c-108">Los campos **Fecha** muestran la misma información en cualquier ubicación.</span><span class="sxs-lookup"><span data-stu-id="b082c-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="b082c-109">Cuando se especifica una fecha en un campo **Fecha**, Human Resources escribe esa misma fecha en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b082c-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="b082c-110">Al visualizar datos en un campo **Fecha y hora**, Human Resources ajusta la fecha y hora basada en función de la zona horaria del usuario establecida en el formulario **Opciones de usuario** (**Común > Configuración > Opciones de usuario**).</span><span class="sxs-lookup"><span data-stu-id="b082c-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="b082c-111">Puede que la información de fecha y hora que especifique en el campo no sea la misma que la información escrita en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b082c-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="b082c-112">[![Formulario de opciones de usuario](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="b082c-113">Comprensión de los campos de fecha y hora en los formularios</span><span class="sxs-lookup"><span data-stu-id="b082c-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="b082c-114">Los datos de **Fecha y hora** que se muestran en pantalla no serán los mismos que los datos almacenados en la base de datos si la zona horaria del usuario no se establece en la hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="b082c-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="b082c-115">Los datos de campos **Fecha y hora** se almacenan siempre como UTC.</span><span class="sxs-lookup"><span data-stu-id="b082c-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="b082c-116">[![UTC en formulario de trabajador](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="b082c-117">Comprensión de los campos de fecha y hora en la base de datos</span><span class="sxs-lookup"><span data-stu-id="b082c-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="b082c-118">Cuando Human Resources escribe un valor de **Fecha y hora** en la base de datos, almacena los datos en UTC.</span><span class="sxs-lookup"><span data-stu-id="b082c-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="b082c-119">Esto permite a los usuarios ver los datos **Fecha y hora** en relación con la zona horaria definida en sus opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="b082c-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="b082c-120">En el ejemplo anterior, la hora de inicio es un punto en el tiempo, no una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="b082c-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="b082c-121">Al cambiar a GMT UTC la zona horaria del usuario que inició sesión en GMT+12:00, el mismo registro muestra 30/04/2019 12:00:00 en lugar de 01/05/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="b082c-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="b082c-122">En el siguiente ejemplo, el empleo del empleado 000724 se activa al mismo tiempo independientemente de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b082c-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="b082c-123">El empleado estará activo el 30/04/2019 en la zona horaria del GMT, que es lo mismo que 01/05/2019 en la zona horaria GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="b082c-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="b082c-124">Ambas hacen referencia el mismo momento dado y no a una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="b082c-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="b082c-125">[![GMT en formulario de trabajador](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="b082c-126">Datos de fecha y hora en marco de administración de datos, Excel, Dataverse y Power BI</span><span class="sxs-lookup"><span data-stu-id="b082c-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="b082c-127">El marco de gestión de datos, el complemento de Excel, Dataverse, y la notificación de Power BI están diseñados para interactuar con datos directamente en el nivel de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b082c-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="b082c-128">Dado que no hay cliente para ajustar los datos de **Fecha y hora** a la zona horaria del usuario, todos los valores **Fecha y hora** se muestran en UTC, lo que puede conducir a algunas suposiciones incorrectas al especificar o ver datos.</span><span class="sxs-lookup"><span data-stu-id="b082c-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="b082c-129">La base de datos asume que los datos **Fecha y hora** enviados mediante DMF, Excel, o Dataverse están en UTC.</span><span class="sxs-lookup"><span data-stu-id="b082c-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="b082c-130">Esto puede provocar cierta confusión cuando el valor **Fecha y hora** enviado no se muestra del modo esperado porque el usuario que ve los datos no tiene su zona horaria establecida en UTC.</span><span class="sxs-lookup"><span data-stu-id="b082c-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="b082c-131">La misma cosa puede suceder a la inversa, cuando se exportan los datos.</span><span class="sxs-lookup"><span data-stu-id="b082c-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="b082c-132">Los datos de **Fecha y hora** de la entidad exportada de DMF pueden ser diferentes de lo que se presenta en el cliente de Dynamics.</span><span class="sxs-lookup"><span data-stu-id="b082c-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="b082c-133">Al usar orígenes externos como DMF para ver o crear datos, es importante tener presente que, de forma predeterminada, se consideran que los valores de **Fecha y hora** están en UTC, con independencia de la zona horaria del equipo del usuario o de los valores de la zona horaria del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b082c-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="b082c-134">Ejemplos del mismo registro que se muestra en varias áreas del producto</span><span class="sxs-lookup"><span data-stu-id="b082c-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="b082c-135">**Human Resources con la zona horaria del usuario configurada en UTC**.</span><span class="sxs-lookup"><span data-stu-id="b082c-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="b082c-136">[![Formulario de trabajador en UTC](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="b082c-137">**Human Resources con la zona horaria del usuario configurada en GMT +12:00**.</span><span class="sxs-lookup"><span data-stu-id="b082c-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="b082c-138">[![Formulario de trabajador en GMT](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="b082c-139">**Excel mediante OData**</span><span class="sxs-lookup"><span data-stu-id="b082c-139">**Excel Via OData**</span></span>

<span data-ttu-id="b082c-140">[![Excel mediante OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="b082c-141">**Ubicación provisional de DMF**</span><span class="sxs-lookup"><span data-stu-id="b082c-141">**DMF Staging**</span></span>

<span data-ttu-id="b082c-142">[![Ubicación provisional de DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="b082c-143">**Exportar DMF**</span><span class="sxs-lookup"><span data-stu-id="b082c-143">**DMF Export**</span></span>

<span data-ttu-id="b082c-144">[![Exportación de DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="b082c-145">**Excel mediante Dataverse**</span><span class="sxs-lookup"><span data-stu-id="b082c-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="b082c-146">[![Excel mediante Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="b082c-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="b082c-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b082c-147">See also</span></span>

[<span data-ttu-id="b082c-148">Datos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="b082c-148">Date and time data</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="b082c-149">Zonas horarias preferidas del usuario</span><span class="sxs-lookup"><span data-stu-id="b082c-149">User preferred time zones</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]