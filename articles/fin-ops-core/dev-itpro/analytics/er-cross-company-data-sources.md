---
title: Orígenes de datos entre empresas en informes electrónicos (ER)
description: En este tema se explica cómo puede usar orígenes de datos entre empresas en informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: f2e6b4f20464993f736b013dde40527aba2258ed
ms.sourcegitcommit: 564aa8eec89defdbe2abaf38d0ebc4cca3e28109
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "2667653"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a><span data-ttu-id="7a168-103">Orígenes de datos entre empresas en informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="7a168-103">Cross-company data sources in Electronic reporting (ER)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7a168-104">Puede diseñar formatos de informes electrónicos (ER) para generar documentos salientes en varios formato.</span><span class="sxs-lookup"><span data-stu-id="7a168-104">You can design Electronic reporting (ER) formats to generate outgoing documents in various formats.</span></span> <span data-ttu-id="7a168-105">Cuando se genera un documento, un formato de ER denomina orígenes de datos que se configuraron en una asignación correspondiente del modelo de ER.</span><span class="sxs-lookup"><span data-stu-id="7a168-105">When a document is generated, an ER format calls data sources that were configured in a corresponding ER model mapping.</span></span> <span data-ttu-id="7a168-106">Para configurar el acceso a las tablas de la aplicación para la recuperación del registro, puede usar los orígenes de datos de ER del tipo **Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="7a168-106">To configure access to application tables for record retrieval, you can use ER data sources of the **Table records** type.</span></span> <span data-ttu-id="7a168-107">Cuando la tabla de acceso es una tabla compartida (es decir, una tabla en la que los datos se guardan sin un identificador de empresa), este origen de datos devuelve todos los registros.</span><span class="sxs-lookup"><span data-stu-id="7a168-107">When the accessing table is a shared table (that is, a table where data is saved without a company identifier), this data source returns all records.</span></span> <span data-ttu-id="7a168-108">Cuando la tabla de acceso es una tabla que depende de la empresa (es decir, una tabla en la que los datos se guardan por empresa), este origen de datos solo devuelve los registros que se han guardado para la empresa actual (es decir, el contexto de la empresa bajo la que el formato de ER se está ejecutando).</span><span class="sxs-lookup"><span data-stu-id="7a168-108">When the accessing table is a company-dependent table (that is, a table where data is saved per company), this data source returns only the records that have been saved for the current company (that is, the company context that the ER format is running under).</span></span>

<span data-ttu-id="7a168-109">Cada origen de datos del tipo **Registros de tabla** en una asignación de modelo ahora se podrá marcar como origen de datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7a168-109">Every data source of the **Table records** type in a model mapping can be now marked as a cross-company data source.</span></span> <span data-ttu-id="7a168-110">Por tanto, puede utilizar orígenes de datos del tipo **Registros de tabla** para acceder a datos entre empresas en tablas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a168-110">Therefore, you can use data sources of the **Table records** type to access cross-company data in application tables.</span></span>

<span data-ttu-id="7a168-111">Si marca un origen de datos como entre empresas, se produce el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="7a168-111">If you mark a data source as cross-company, the following behavior occurs:</span></span>

- <span data-ttu-id="7a168-112">Para un origen de datos que hace referencia a cualquier tabla compartida a excepción de CompanyInfo, el origen de datos devuelve todos los registros que existen en la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="7a168-112">For a data source that refers to any shared table except CompanyInfo, the data source returns all records that exist in the referenced table.</span></span> 
- <span data-ttu-id="7a168-113">Para un origen de datos que hace referencia a la tabla CompanyInfo, aunque CompanyInfo sea una tabla compartida, el origen de datos devuelve los registros que contienen el identificador de una empresa del ámbito definido.</span><span class="sxs-lookup"><span data-stu-id="7a168-113">For a data source that refers to the CompanyInfo table, even though CompanyInfo is a shared table, the data source returns the records that contain the identifier of a company from the defined scope.</span></span>
- <span data-ttu-id="7a168-114">Para cualquier tabla que depende de la empresa, el origen de datos devuelve los registros de la tabla de referencia que contienen el identificador de una empresa del ámbito definido.</span><span class="sxs-lookup"><span data-stu-id="7a168-114">For any company-dependent table, the data source returns the records of the referenced table that contain the identifier of a company from the defined scope.</span></span>

<span data-ttu-id="7a168-115">En el cuadro de diálogo de consulta del sistema, cuando la opción **Pedir consulta** está activada para cualquier origen de datos que esté marcada como entre empresas, puede seleccionar manualmente una o más empresas para incluirlas en la pestaña **Intervalo de empresas** .</span><span class="sxs-lookup"><span data-stu-id="7a168-115">In the system query dialog box, when the **Ask for query** option is turned on for any data source that is marked as cross-company, you can manually select one or more companies to include on the **Company range** tab.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a168-116">Como otros filtros, el filtro de empresa se conserva como un valor utilizado por última vez para consultas cuando ejecute un formato de ER.</span><span class="sxs-lookup"><span data-stu-id="7a168-116">Like other filters, the company filter is persisted as a last-used value for queries when you run an ER format.</span></span> <span data-ttu-id="7a168-117">El filtro no se modifica automáticamente si cambia el valor entre empresas para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7a168-117">The filter isn't automatically changed if you change the cross-company value for a data source.</span></span> <span data-ttu-id="7a168-118">Para utilizar un valor entre empresas diferente para otro origen de datos, elimine la correspondiente selección específica del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a168-118">To use a different cross-company value for another data source, delete the corresponding user-specific selection.</span></span>

<span data-ttu-id="7a168-119">Para cada origen de datos que esté marcado como entre empresas, puede seleccionar los registros que desee utilizando las funciones **FILTRO** y **DONDE** en expresiones de ER.</span><span class="sxs-lookup"><span data-stu-id="7a168-119">For every data source that is marked as cross-company, you can select the records that you want by using the **FILTER** and **WHERE** functions in ER expressions.</span></span> <span data-ttu-id="7a168-120">El campo **dataAreaID** se puede usar como un identificador de empresa.</span><span class="sxs-lookup"><span data-stu-id="7a168-120">The **dataAreaID** field can also be used as a company identifier.</span></span> <span data-ttu-id="7a168-121">Actualmente, el campo **dataAreaID** se limita a los siguientes tipos de condiciones cuando se utiliza la función **FILTRO**:</span><span class="sxs-lookup"><span data-stu-id="7a168-121">Currently, the **dataAreaID** field is limited to the following types of conditions when the **FILTER** function is used:</span></span>

- <span data-ttu-id="7a168-122">Solo se admiten las condiciones que tienen una única comparación del campo **dataAreaID**.</span><span class="sxs-lookup"><span data-stu-id="7a168-122">Only conditions that have a single **dataAreaID** field comparison are supported.</span></span>
- <span data-ttu-id="7a168-123">Solo se permiten las comparaciones con expresiones que no dependen de elementos de la lista de registros.</span><span class="sxs-lookup"><span data-stu-id="7a168-123">Only comparisons that have expressions that don't depend on records list items are allowed.</span></span>

<span data-ttu-id="7a168-124">Por tanto, la siguiente expresión es válida.</span><span class="sxs-lookup"><span data-stu-id="7a168-124">Therefore, the following expression is valid.</span></span>

```
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

<span data-ttu-id="7a168-125">De forma predeterminada, el ámbito incluye todas las empresas de la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="7a168-125">By default, the scope includes all companies of the current application.</span></span> <span data-ttu-id="7a168-126">Sin embargo, puede estar limitado.</span><span class="sxs-lookup"><span data-stu-id="7a168-126">However, it can be restricted.</span></span> <span data-ttu-id="7a168-127">Para limitar el ámbito de acceso a datos entre empresas para un único formato de ER, asigne una jerarquía organizativa específica para el formato.</span><span class="sxs-lookup"><span data-stu-id="7a168-127">To restrict the scope of cross-company data access for a single ER format, assign a specific organization hierarchy to the format.</span></span> <span data-ttu-id="7a168-128">Cuando una jerarquía se define para un formato de ER, solo se devuelven los registros para las entidades jurídicas que están presentes en la jerarquía asignada, aunque el formato llama a orígenes de datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7a168-128">When a hierarchy is defined for an ER format, only records for legal entities that are presented in the assigned hierarchy are returned, even though the format calls cross-company data sources.</span></span> <span data-ttu-id="7a168-129">Cuando se define una referencia a una jerarquía que ya no existe para un formato de ER, se aplica el ámbito predeterminado y el formato llama a orígenes de datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7a168-129">When a reference to a hierarchy that no longer exists is defined for an ER format, the default scope is applied, and the format calls cross-company data sources.</span></span> <span data-ttu-id="7a168-130">En esta situación, se devuelven los registros para todas las empresas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a168-130">In this situation, records for all application companies are returned.</span></span>

<span data-ttu-id="7a168-131">Tenga en cuenta que cuando se activa la opción **Usar borrador** para lo asignado a una única jerarquía organizativa del formato de ER, las entidades jurídicas de la versión de borrador de esta jerarquía se utilizarán para identificar el ámbito para orígenes de datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7a168-131">Note that when the **Use draft** option is turned on for the assigned to a single ER format organization hierarchy, the legal entities from the draft version of this hierarchy will be used to identify the scope for cross-company data sources.</span></span> <span data-ttu-id="7a168-132">Si no existe la versión de borrador, las entidades jurídicas de la última versión publicada de esta jerarquía organizativa se utilizarán para esto.</span><span class="sxs-lookup"><span data-stu-id="7a168-132">If the draft version does not exist, the legal entities from the last published version of this organization hierarchy will be used for this.</span></span>

<span data-ttu-id="7a168-133">Tenga en cuenta que cuando se desactiva la opción **Usar borrador** para lo asignado a una única jerarquía organizativa del formato de ER, las entidades jurídicas de la última versión publicada de esta jerarquía organizativa se utilizarán para identificar el ámbito para orígenes de datos entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7a168-133">Note that when the **Use draft** option is turned off for the assigned to a single ER format organization hierarchy, the legal entities from the last published version of this organization hierarchy will be used to identify the scope for cross-company data sources.</span></span> <span data-ttu-id="7a168-134">La efectividad de la fecha de jerarquías organizativas no se admite aún en el marco de ER.</span><span class="sxs-lookup"><span data-stu-id="7a168-134">Date effectiveness of organization hierarchies is not supported yet in the ER framework.</span></span>

<span data-ttu-id="7a168-135">La jerarquía se puede asignar a un formato en una página específica a la que se puede acceder desde el espacio de trabajo de ER o mediante el elemento de menú **Administración de la organización \> Informes electrónicos \> Filtro de entidad jurídica para formatos**.</span><span class="sxs-lookup"><span data-stu-id="7a168-135">The hierarchy can be assigned to a format in a specific page that can be accessed from the ER workspace or by using the **Organization administration \> Electronic reporting \> Legal entity filter for formats** menu item.</span></span> <span data-ttu-id="7a168-136">Para acceder a la página, debe concederse al usuario el privilegio **Mantener filtros de la entidad jurídica para formatos** (ERMaintainFormatMappingLegalEntityFilters).</span><span class="sxs-lookup"><span data-stu-id="7a168-136">To access the page, the **Maintain legal entity filters for format** privilege (ERMaintainFormatMappingLegalEntityFilters) must be granted to a user.</span></span> <span data-ttu-id="7a168-137">Se aplica la restricción del ámbito de las entidades jurídicas basadas en jerarquías para el formato, además de la restricción que el usuario puede especificar manualmente en el cuadro de diálogo de consulta del sistema.</span><span class="sxs-lookup"><span data-stu-id="7a168-137">The scope restriction of hierarchy-based legal entities for the format is applied in addition to the restriction that the user can manually specify in the system query dialog box.</span></span> <span data-ttu-id="7a168-138">La intersección de estas restricciones se utiliza cuando se ejecuta el formato.</span><span class="sxs-lookup"><span data-stu-id="7a168-138">The intersection of these restrictions is used when the format is run.</span></span>

<span data-ttu-id="7a168-139">Para obtener más información acerca de esta función, reproduzca la guía de tareas **ER Acceder a registros de tablas que dependen de la empresa en modo entre empresas**, que forma parte del proceso empresarial 7.5.4.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10677) y puede descargarse del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="7a168-139">To learn more about this feature, play the task guide, **ER Access records of company dependent tables in cross-company mode**, which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process, and can be downloaded from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span> <span data-ttu-id="7a168-140">Esta guía de tareas le guía por el proceso de configurar una asignación del modelo de ER y el formato de ER para acceder a las tablas de la aplicación en modo entre empresas.</span><span class="sxs-lookup"><span data-stu-id="7a168-140">This task guide walks you through the process of configuring an ER model mapping and ER format to access application tables in cross-company mode.</span></span>

<span data-ttu-id="7a168-141">Descargue los siguientes archivos para completar la guía de tareas:</span><span class="sxs-lookup"><span data-stu-id="7a168-141">Download the following files to complete the task guide:</span></span>

- [<span data-ttu-id="7a168-142">Configuración del modelo de ER - CrossCompanyDataAccessModel.xml</span><span class="sxs-lookup"><span data-stu-id="7a168-142">ER model configuration - CrossCompanyDataAccessModel.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111)
- [<span data-ttu-id="7a168-143">Configuración del formato de ER - CrossCompanyDataAccessFormat.xml</span><span class="sxs-lookup"><span data-stu-id="7a168-143">ER format configuration - CrossCompanyDataAccessFormat.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111)