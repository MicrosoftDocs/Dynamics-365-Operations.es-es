---
title: Optimizar las consultas de tabla virtual de Dataverse
description: Optimizar y solucionar problemas de rendimiento de consultas de mesa virtual de Dataverse
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8026abd5c3e0f9b78e8c016731fd7785490bc945
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891111"
---
# <a name="optimize-dataverse-virtual-table-queries"></a><span data-ttu-id="08348-103">Optimizar las consultas de tabla virtual de Dataverse</span><span class="sxs-lookup"><span data-stu-id="08348-103">Optimize Dataverse virtual table queries</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="08348-104">Emitir</span><span class="sxs-lookup"><span data-stu-id="08348-104">Issue</span></span>

### <a name="overview"></a><span data-ttu-id="08348-105">Información general</span><span class="sxs-lookup"><span data-stu-id="08348-105">Overview</span></span>

<span data-ttu-id="08348-106">Cuando usas tablas virtuales de Dataverse para desarrollar integraciones y otras conexiones de datos con Dynamics 365 Human Resources, puede experimentar problemas de rendimiento con consultas en las tablas virtuales.</span><span class="sxs-lookup"><span data-stu-id="08348-106">When using Dataverse virtual tables to develop integrations and other data connections with Dynamics 365 Human Resources, you can experience performance issues with queries against the virtual tables.</span></span> <span data-ttu-id="08348-107">La ejecución lenta de la consulta puede ocurrir en varios clientes o interfaces.</span><span class="sxs-lookup"><span data-stu-id="08348-107">The slow query execution can occur across various clients or interfaces.</span></span> <span data-ttu-id="08348-108">Por ejemplo, puede experimentar el problema en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="08348-108">For example, you may experience the issue in the following circumstances:</span></span>

- <span data-ttu-id="08348-109">Al consultar una tabla virtual a través de la API web de Dataverse</span><span class="sxs-lookup"><span data-stu-id="08348-109">When querying a virtual table through the Dataverse Web API</span></span>
- <span data-ttu-id="08348-110">Al crear una aplicación de energía contra una mesa virtual</span><span class="sxs-lookup"><span data-stu-id="08348-110">When creating a Power App against a virtual table</span></span>
- <span data-ttu-id="08348-111">Al construir un informe de Power BI en una mesa virtual</span><span class="sxs-lookup"><span data-stu-id="08348-111">When building a Power BI report on a virtual table</span></span>

<span data-ttu-id="08348-112">Todas estas interfaces tienen el potencial de sacar a la luz el problema de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="08348-112">All these interfaces have the potential to surface the performance issue.</span></span>

<span data-ttu-id="08348-113">Una de las causas del rendimiento lento con tablas virtuales de Dataverse para Recursos Humanos son las columnas de clave externa de la tabla virtual relacionadas con la tabla [propiedades de navegación](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span><span class="sxs-lookup"><span data-stu-id="08348-113">One cause of slow performance with Dataverse virtual tables for Human Resources is the foreign key columns of the virtual table related to the table's [navigation properties](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span></span> <span data-ttu-id="08348-114">Cuando se crean propiedades de navegación para una tabla virtual, se agrega automáticamente una columna de clave externa a la tabla para representar el valor de la clave para la columna de clave de la tabla virtual relacionada.</span><span class="sxs-lookup"><span data-stu-id="08348-114">When navigation properties are created for a virtual table, a foreign key column is automatically added to the table to represent the value of the key for the related virtual table's key column.</span></span> <span data-ttu-id="08348-115">Por ejemplo, la columna **_mshr_fk_person_id_value** se agrega a la entidad **mshr_hcmworkerbaseentity** con la propiedad de clave externa de la entidad **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="08348-115">For example, the **_mshr_fk_person_id_value** column is added to the **mshr_hcmworkerbaseentity** entity with the foreign key property from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="08348-116">Debido a cómo se mantienen los valores de estas columnas de clave externa en una tabla, la obtención de los valores puede tener un impacto negativo en el rendimiento de una consulta en la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="08348-116">Because of how the values for these foreign key columns are maintained in a table, fetching the values can have a negative impact on the performance of a query against the virtual table.</span></span>

### <a name="potential-symptoms"></a><span data-ttu-id="08348-117">Síntomas potenciales</span><span class="sxs-lookup"><span data-stu-id="08348-117">Potential symptoms</span></span>

<span data-ttu-id="08348-118">Un ejemplo en el que puede ver este impacto es en las consultas contra la entidad de trabajador (**mshr_hcmworkerentity**) o trabajador de base (**mshr_hcmworkerbaseentity**).</span><span class="sxs-lookup"><span data-stu-id="08348-118">An example where you may see this impact is in queries against the Worker (**mshr_hcmworkerentity**) or Base worker (**mshr_hcmworkerbaseentity**) entity.</span></span> <span data-ttu-id="08348-119">Es posible que vea que el problema de rendimiento se manifiesta de diferentes maneras:</span><span class="sxs-lookup"><span data-stu-id="08348-119">You may see the performance issue manifest itself in a few different ways:</span></span>

- <span data-ttu-id="08348-120">**Ejecución de consultas lenta**: La consulta en la tabla virtual puede devolver los resultados esperados, pero demorar más de lo esperado en completar la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="08348-120">**Slow query execution**: The query against the virtual table may return the expected results, but take longer than expected to complete execution of the query.</span></span>
- <span data-ttu-id="08348-121">**Tiempo vencido de consulta**: La consulta puede agotar el tiempo de espera y devolver el siguiente error: "Se obtuvo un token para llamar Finance and Operations, pero Finance and Operations devolvió un error de tipo InternalServerError. "</span><span class="sxs-lookup"><span data-stu-id="08348-121">**Query timeout**: The query may time out and return the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type InternalServerError."</span></span>
- <span data-ttu-id="08348-122">**Error inesperado**: La consulta puede devolver un tipo de error 400 con el siguiente mensaje: "Se produjo un error inesperado".</span><span class="sxs-lookup"><span data-stu-id="08348-122">**Unexpected error**: The query may return an error type 400 with the following message: "An unexpected error occurred."</span></span>

  ![Tipo de error 400 en HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType400.png)

- <span data-ttu-id="08348-124">**Estrangulamiento**: La consulta puede hacer un uso excesivo de los recursos del servidor y quedar sujeta a limitaciones.</span><span class="sxs-lookup"><span data-stu-id="08348-124">**Throttling**: The query may overuse server resources, and become subject to throttling.</span></span> <span data-ttu-id="08348-125">En este caso, la consulta devuelve el siguiente error: "Se obtuvo un token para llamar Finance and Operations, pero Finance and Operations devolvió un error de tipo 429."</span><span class="sxs-lookup"><span data-stu-id="08348-125">In this case, the query returns the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type 429."</span></span> <span data-ttu-id="08348-126">Para obtener más información sobre la limitación de recursos humanos, consulte [Preguntas frecuentes sobre la limitación](./hr-admin-integration-throttling-faq.md).</span><span class="sxs-lookup"><span data-stu-id="08348-126">For more information in throttling in Human Resources, see [Throttling FAQ](./hr-admin-integration-throttling-faq.md).</span></span>

  ![Tipo de error 429 en HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a><span data-ttu-id="08348-128">Resolución</span><span class="sxs-lookup"><span data-stu-id="08348-128">Resolution</span></span>

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a><span data-ttu-id="08348-129">Limite la cantidad de columnas incluidas en su consulta de datos</span><span class="sxs-lookup"><span data-stu-id="08348-129">Limit the number of columns included in your data query</span></span>

<span data-ttu-id="08348-130">Con las tablas virtuales, uno de los métodos con mayor potencial para mejorar el rendimiento de la consulta es limitar el número de columnas seleccionadas en la consulta.</span><span class="sxs-lookup"><span data-stu-id="08348-130">With virtual tables, one of the methods with the greatest potential to improve query performance is to limit the number of columns selected in the query.</span></span> <span data-ttu-id="08348-131">La guía general para optimizar el rendimiento de la consulta es limitar las columnas devueltas en su consulta solo a las propiedades que necesita.</span><span class="sxs-lookup"><span data-stu-id="08348-131">The general guidance for optimizing query performance is to limit the columns returned in your query to only those properties that you need.</span></span> <span data-ttu-id="08348-132">Esto es particularmente cierto con las columnas de clave externa en tablas virtuales.</span><span class="sxs-lookup"><span data-stu-id="08348-132">This is particularly true with the foreign key columns on virtual tables.</span></span> <span data-ttu-id="08348-133">Si no necesita los valores en las columnas de clave externa para su integración o informe, entonces estructura la consulta para seleccionar solo las columnas que necesita, excluyendo las columnas de clave externa.</span><span class="sxs-lookup"><span data-stu-id="08348-133">If you don't need the values in the foreign key columns for your integration or report, then structure the query to select only the columns you need, excluding the foreign key columns.</span></span>

#### <a name="selecting-columns-in-an-odata-query"></a><span data-ttu-id="08348-134">Seleccionar columnas en una consulta de OData</span><span class="sxs-lookup"><span data-stu-id="08348-134">Selecting columns in an OData query</span></span>

<span data-ttu-id="08348-135">Al consultar una tabla virtual a través de API web de Dataverse, puede limitar el número de columnas incluidas en la consulta mediante la opción de consulta del sistema **$select** y defina las columnas para las que necesita que se devuelvan los resultados.</span><span class="sxs-lookup"><span data-stu-id="08348-135">When querying a virtual table through the Dataverse Web API, you can limit the number of columns included in the query by using the **$select** system query option, and define the columns for which you need results returned.</span></span> <span data-ttu-id="08348-136">Para maximizar el rendimiento, excluya las columnas de clave externa (aquellas con el prefijo **_mshr_FK_**) de la consulta.</span><span class="sxs-lookup"><span data-stu-id="08348-136">To maximize performance, exclude foreign key columns (those with the **_mshr_FK_** prefix) from the query.</span></span>

<span data-ttu-id="08348-137">Por ejemplo, la siguiente consulta contra la entidad **mshr_hcmworkerbaseentity** incluirá solo las columnas incluidas en la cláusula **$select** de opción de consulta, excluyendo los valores de clave externa.</span><span class="sxs-lookup"><span data-stu-id="08348-137">For example, the following query against the **mshr_hcmworkerbaseentity** entity will include only the columns included in the **$select** query option clause, excluding foreign key values.</span></span> <span data-ttu-id="08348-138">Esto proporciona mejoras significativas en el rendimiento con respecto a una consulta que incluye todas las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="08348-138">This provides significant improvements in performance over a query that includes all table columns.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="08348-139">La recomendación de limitar el número de columnas seleccionadas también se aplica cuando se utiliza la opción de consulta **$expand** para expandir la consulta a tablas virtuales relacionadas a través de las propiedades de navegación.</span><span class="sxs-lookup"><span data-stu-id="08348-139">The recommendation to limit the number of columns selected also applies when using the **$expand** query option to expand the query to related virtual tables through navigation properties.</span></span> <span data-ttu-id="08348-140">Por ejemplo, la siguiente consulta incluye columnas de la entidad **mshr_hcmworkerbaseentity** con columnas expandidas de la entidad **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="08348-140">For example, the following query includes columns from the **mshr_hcmworkerbaseentity** entity with expanded columns from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="08348-141">Tenga en cuenta que la opción de consulta **$select** también se incluye en la cláusula de opción de consulta **$expand**.</span><span class="sxs-lookup"><span data-stu-id="08348-141">Note that the **$select** query option is also included in the **$expand** query option clause.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="08348-142">Cuando utilice este método de recuperar datos con la opción de consulta **$select** en la cláusula de opción de consulta **$expand**, normalmente verá mayores mejoras de rendimiento cuando la propiedad de navegación entre las entidades es una relación de varios a uno.</span><span class="sxs-lookup"><span data-stu-id="08348-142">When using this method of retrieving data with the **$select** query option in the **$expand** query option clause, you will typically see greater performance improvements when the navigation property between the entities is a many-to-one relationship.</span></span> <span data-ttu-id="08348-143">Es posible que no vea la misma disminución en el tiempo de ejecución de la consulta al expandir una relación de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="08348-143">You may not see the same decrease in query execution time when expanding a one-to-many relationship.</span></span> <span data-ttu-id="08348-144">Para obtener más información sobre la definición de relación para talbas virtuales de Dataverse, ver [Relaciones de mesa](/powerapps/maker/data-platform/create-edit-entity-relationships).</span><span class="sxs-lookup"><span data-stu-id="08348-144">For more information on relationship definition for Dataverse virtual tables, see [Table relationships](/powerapps/maker/data-platform/create-edit-entity-relationships).</span></span>

<span data-ttu-id="08348-145">Para obtener más información sobre el uso de las opciones de consulta del sistema **$select** y **$expand** en la API web de Dataverse, consulte [Recuperar registros de entidades relacionados con una consulta](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span><span class="sxs-lookup"><span data-stu-id="08348-145">For more information on using the **$select** and **$expand** system query options in the Dataverse Web API, see [Retrieve related entity records with a query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span></span>

#### <a name="selecting-columns-in-power-bi"></a><span data-ttu-id="08348-146">Seleccionar columnas en Power BI</span><span class="sxs-lookup"><span data-stu-id="08348-146">Selecting columns in Power BI</span></span>

<span data-ttu-id="08348-147">Si experimenta alguno de los indicios antes mencionados de rendimiento lento al construir un informe de Power BI contra una tabla virtual de Dataverse, puede mejorar el rendimiento excluyendo columnas de clave externa de las columnas seleccionadas de la tabla para el informe.</span><span class="sxs-lookup"><span data-stu-id="08348-147">If you experience any of the aforementioned indications of slow performance when building a Power BI report against a Dataverse virtual table, you can improve the performance by excluding foreign key columns from the columns selected from the table for the report.</span></span> <span data-ttu-id="08348-148">Por ejemplo, si está utilizando Power BI Desktop para crear un informe contra la entidad **mshr_hcmworkerbaseentity**, puede utilizar los siguientes pasos para seleccionar las columnas que desea incluir en la consulta del informe.</span><span class="sxs-lookup"><span data-stu-id="08348-148">For example, if you are using Power BI Desktop to create a report against the **mshr_hcmworkerbaseentity** entity, you can use the following steps to select the columns you want included in the report query.</span></span>

1. <span data-ttu-id="08348-149">En Power BI Desktop, seleccione **Más...** desde la lista **Obtener datos** desplegable en la cinta de acciones.</span><span class="sxs-lookup"><span data-stu-id="08348-149">In Power BI Desktop, select **More...** from the **Get data** drop-down list on the action ribbon.</span></span>
2. <span data-ttu-id="08348-150">En la ventana **Obtener datos**, entrar **Common Data Service** en el cuadro de búsqueda, seleccione el conector **Common Data Service** y seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="08348-150">In the **Get Data** window, enter **Common Data Service** in the search box, select the **Common Data Service** connector, and select **Connect**.</span></span>
3. <span data-ttu-id="08348-151">En el campo **URL del servidor** de la ventana Common Data Service, ingrese el URI de la organización para su entorno de Dataverse y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08348-151">In the **Server Url** field of the Common Data Service window, enter the organization URI for your Dataverse environment, and select **OK**.</span></span>
  
   ![Escriba el URI para su entorno Dataverse](./media/PowerBIDataverseURLSetup.png)
  
4. <span data-ttu-id="08348-153">En la ventana del navegador, expanda el nodo **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="08348-153">In the Navigator window, expand the **Entities** node.</span></span>
5. <span data-ttu-id="08348-154">En el cuadro de búsqueda, ingrese **mshr_hcmworkerbaseentity** y seleccione la entidad.</span><span class="sxs-lookup"><span data-stu-id="08348-154">In the search box, enter **mshr_hcmworkerbaseentity**, and select the entity.</span></span>
6. <span data-ttu-id="08348-155">Seleccione **Transformar datos**.</span><span class="sxs-lookup"><span data-stu-id="08348-155">Select **Transform Data**.</span></span>
7. <span data-ttu-id="08348-156">En la ventana del Editor de Power Query, seleccione **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="08348-156">In the Power Query Editor window, select **Advanced Editor**.</span></span>
8. <span data-ttu-id="08348-157">En la ventana **Editor avanzado**, actualice la consulta para que se vea como la siguiente, agregando o quitando cualquier columna a la matriz según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="08348-157">In the **Advanced Editor** window, update the query to look like the below, adding or removing any columns to the array as needed.</span></span>

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Actualice la consulta en el Editor avanzado para Power Query Editor](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. <span data-ttu-id="08348-159">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="08348-159">Select **Done**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08348-160">Si anteriormente recibió un error de tipo 429 de la consulta antes de la actualización, es posible que deba esperar el período de reintento antes de actualizar la consulta para que se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="08348-160">If you previously received an error of type 429 from the query prior to updating, you may need to wait for the retry period prior to refreshing the query for it to complete successully.</span></span>

10. <span data-ttu-id="08348-161">Hacer clic en **Cerrar y aplicar** en la cinta de acciones del Editor de Power Query.</span><span class="sxs-lookup"><span data-stu-id="08348-161">Click **Close & Apply** on the Power Query Editor action ribbon.</span></span>

<span data-ttu-id="08348-162">Entonces puede comenzar a construir su informe de Power BI contra las columnas seleccionadas de la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="08348-162">You're then able to begin building your Power BI report against the columns selected from the virtual table.</span></span>

#### <a name="selecting-columns-in-power-apps"></a><span data-ttu-id="08348-163">Seleccionar columnas en Power Apps</span><span class="sxs-lookup"><span data-stu-id="08348-163">Selecting columns in Power Apps</span></span>

<span data-ttu-id="08348-164">Similar a las consultas de API web de Dataverse y Power BI, puede mejorar el rendimiento de las consultas para Power Apps basandose en las tablas virtuales de Dataverse al excluir columnas de tablas relacionadas de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="08348-164">Similar to Dataverse Web API queries and Power BI, you can improve query performance for Power Apps based on Dataverse virtual tables by excluding columns of related tables from your app.</span></span> <span data-ttu-id="08348-165">Si alguna columna de una tabla relacionada se ha incluido en una página, la URL de solicitud construida para obtener los datos incluirá las propiedades de clave externa de la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="08348-165">If any columns from a related table have been included on a page, then the request URL constructed to fetch the data will include foreign key properties of the related table.</span></span> <span data-ttu-id="08348-166">Esto, como en los ejemplos de [Seleccionar columnas en una consulta OData](#selecting-columns-in-power-apps), reduce el rendimiento al provocar búsquedas de datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="08348-166">This, as in the examples of [Selecting columns in an OData Query](#selecting-columns-in-power-apps) above, reduces performance by causing additional data lookups.</span></span>

<span data-ttu-id="08348-167">Para solucionar este problema, puede validar que no se hayan incluido campos de datos de tablas relacionadas en ningún formulario de datos de su Power App.</span><span class="sxs-lookup"><span data-stu-id="08348-167">To work around this, you can validate that no data fields from related tables have been included on any data form of your Power App.</span></span>

1. <span data-ttu-id="08348-168">En el panel de vista de árbol, seleccione el formulario de datos para la pantalla.</span><span class="sxs-lookup"><span data-stu-id="08348-168">In the Tree view pane, select the data form for the screen.</span></span>
2. <span data-ttu-id="08348-169">En el panel **Propiedades**, seleccione **Editar** en la propiedad **Campos**.</span><span class="sxs-lookup"><span data-stu-id="08348-169">In the **Properties** pane, select **Edit** on the **Fields** property.</span></span>
3. <span data-ttu-id="08348-170">En el panel **Datos**, verifique que ninguno de los campos seleccionados sean campos de la tabla virtual de la fuente de datos.</span><span class="sxs-lookup"><span data-stu-id="08348-170">In the **Data** pane, verify that none of the selected fields are fields of the virtual table of the data source.</span></span>

<span data-ttu-id="08348-171">Por ejemplo, si uno de los campos de datos incluidos en una página de la aplicación hace referencia a otra tabla, como **ThisItem.Worker.Name**, dónde **Worker** es la tabla relacionada, existe la posibilidad de que se reduzca el rendimiento al obtener los datos.</span><span class="sxs-lookup"><span data-stu-id="08348-171">For example, if one of the data fields included on a page in the app references another table, such as **ThisItem.Worker.Name**, where **Worker** is the related table, there is a potential for reduced performance in fetching the data.</span></span>

<span data-ttu-id="08348-172">Puedes usar el [Monitor de Power Apps](/powerapps/maker/monitor-overview) para asegurarse de que solo se incluyan en la consulta las columnas que necesita para obtener los datos de la aplicación Power.</span><span class="sxs-lookup"><span data-stu-id="08348-172">You can use the [Power Apps Monitor](/powerapps/maker/monitor-overview) to ensure that only the columns you need are being included in the query to get the data for the Power App.</span></span> <span data-ttu-id="08348-173">Puede ver la URL construida para la operación getRows para asegurarse de que las columnas que ha seleccionado para su aplicación sean óptimas para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="08348-173">You can view the URL constructed for the getRows operation to ensure the columns you have selected for your app will be optimal for retrieving the data.</span></span>

![Usar el Monitor de Power Apps para analizar la operación getData](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a><span data-ttu-id="08348-175">Filtrar la consulta de datos</span><span class="sxs-lookup"><span data-stu-id="08348-175">Filtering the data query</span></span>

<span data-ttu-id="08348-176">Otro método para mejorar el rendimiento de la ejecución de consultas es limitar el número de registros devueltos en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="08348-176">Another method for improving query execution performance is to limit the number of records returned in the query results.</span></span> <span data-ttu-id="08348-177">Puede hacer esto filtrando los resultados para asegurarse de que solo recibe los registros que necesita.</span><span class="sxs-lookup"><span data-stu-id="08348-177">You can do this by filtering the results to ensure that you are only receiving the records you need.</span></span>

<span data-ttu-id="08348-178">Ver [Filtrar Resultados](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) para obtener más información sobre el filtrado de datos de consultas.</span><span class="sxs-lookup"><span data-stu-id="08348-178">See [Filter results](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) for more information on filtering query data.</span></span>

### <a name="limiting-the-page-size-of-the-query"></a><span data-ttu-id="08348-179">Limitar el tamaño de página de la consulta</span><span class="sxs-lookup"><span data-stu-id="08348-179">Limiting the page size of the query</span></span>

<span data-ttu-id="08348-180">Si está trabajando con grandes conjuntos de datos, puede dividir los resultados de la consulta en varias páginas agregando el encabezado de preferencia `odata.maxpagesize` para consultas de datos.</span><span class="sxs-lookup"><span data-stu-id="08348-180">If you're working with large data sets, you can divide query results into multiple pages by adding the `odata.maxpagesize` preference header to data queries.</span></span>

<span data-ttu-id="08348-181">Para obtener más información sobre la paginación, consulte [Especificar el número de entidades que se devolverán en una página](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span><span class="sxs-lookup"><span data-stu-id="08348-181">For more information on paging, see [Specify the number of entities to return in a page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span></span>

## <a name="see-also"></a><span data-ttu-id="08348-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08348-182">See also</span></span>

- [<span data-ttu-id="08348-183">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="08348-183">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)
- [<span data-ttu-id="08348-184">Preguntas frecuentes sobre tablas virtuales de Human Resources</span><span class="sxs-lookup"><span data-stu-id="08348-184">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)
- [<span data-ttu-id="08348-185">Preguntas frecuentes sobre limitación</span><span class="sxs-lookup"><span data-stu-id="08348-185">Throttling FAQ</span></span>](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]