---
title: Optimizar las consultas de tabla virtual de Dataverse
description: Optimizar y solucionar problemas de rendimiento de consultas de mesa virtual de Dataverse
author: twheeloc
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f75176781620cd6f845c002876eba6e34d5793e7
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692237"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Optimizar las consultas de tabla virtual de Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>Emitir

### <a name="overview"></a>Información general

Cuando usas tablas virtuales de Dataverse para desarrollar integraciones y otras conexiones de datos con Dynamics 365 Human Resources, puede experimentar problemas de rendimiento con consultas en las tablas virtuales. La ejecución lenta de la consulta puede ocurrir en varios clientes o interfaces. Por ejemplo, puede experimentar el problema en las siguientes circunstancias:

- Al consultar una tabla virtual a través de la API web de Dataverse
- Al crear una aplicación de energía contra una mesa virtual
- Al construir un informe de Power BI en una mesa virtual

Todas estas interfaces tienen el potencial de sacar a la luz el problema de rendimiento.

Una de las causas del rendimiento lento con tablas virtuales de Dataverse para Recursos Humanos son las columnas de clave externa de la tabla virtual relacionadas con la tabla [propiedades de navegación](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties). Cuando se crean propiedades de navegación para una tabla virtual, se agrega automáticamente una columna de clave externa a la tabla para representar el valor de la clave para la columna de clave de la tabla virtual relacionada. Por ejemplo, la columna **_mshr_fk_person_id_value** se agrega a la entidad **mshr_hcmworkerbaseentity** con la propiedad de clave externa de la entidad **mshr_dirpersonentity**. Debido a cómo se mantienen los valores de estas columnas de clave externa en una tabla, la obtención de los valores puede tener un impacto negativo en el rendimiento de una consulta en la tabla virtual.

### <a name="potential-symptoms"></a>Síntomas potenciales

Un ejemplo en el que puede ver este impacto es en las consultas contra la entidad de trabajador (**mshr_hcmworkerentity**) o trabajador de base (**mshr_hcmworkerbaseentity**). Es posible que vea que el problema de rendimiento se manifiesta de diferentes maneras:

- **Ejecución de consultas lenta**: La consulta en la tabla virtual puede devolver los resultados esperados, pero demorar más de lo esperado en completar la ejecución de la consulta.
- **Tiempo vencido de consulta**: La consulta puede agotar el tiempo de espera y devolver el siguiente error: "Se obtuvo un token para llamar Finance and Operations, pero Finance and Operations devolvió un error de tipo InternalServerError. "
- **Error inesperado**: La consulta puede devolver un tipo de error 400 con el siguiente mensaje: "Se produjo un error inesperado".

  ![Tipo de error 400 en HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType400.png)

- **Estrangulamiento**: La consulta puede hacer un uso excesivo de los recursos del servidor y quedar sujeta a limitaciones. En este caso, la consulta devuelve el siguiente error: "Se obtuvo un token para llamar Finance and Operations, pero Finance and Operations devolvió un error de tipo 429." Para obtener más información sobre la limitación de recursos humanos, consulte [Preguntas frecuentes sobre la limitación](./hr-admin-integration-throttling-faq.md).

  ![Tipo de error 429 en HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Resolución

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Limite la cantidad de columnas incluidas en su consulta de datos

Con las tablas virtuales, uno de los métodos con mayor potencial para mejorar el rendimiento de la consulta es limitar el número de columnas seleccionadas en la consulta. La guía general para optimizar el rendimiento de la consulta es limitar las columnas devueltas en su consulta solo a las propiedades que necesita. Esto es particularmente cierto con las columnas de clave externa en tablas virtuales. Si no necesita los valores en las columnas de clave externa para su integración o informe, entonces estructura la consulta para seleccionar solo las columnas que necesita, excluyendo las columnas de clave externa.

#### <a name="selecting-columns-in-an-odata-query"></a>Seleccionar columnas en una consulta de OData

Al consultar una tabla virtual a través de API web de Dataverse, puede limitar el número de columnas incluidas en la consulta mediante la opción de consulta del sistema **$select** y defina las columnas para las que necesita que se devuelvan los resultados. Para maximizar el rendimiento, excluya las columnas de clave externa (aquellas con el prefijo **_mshr_FK_**) de la consulta.

Por ejemplo, la siguiente consulta contra la entidad **mshr_hcmworkerbaseentity** incluirá solo las columnas incluidas en la cláusula **$select** de opción de consulta, excluyendo los valores de clave externa. Esto proporciona mejoras significativas en el rendimiento con respecto a una consulta que incluye todas las columnas de la tabla.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

La recomendación de limitar el número de columnas seleccionadas también se aplica cuando se utiliza la opción de consulta **$expand** para expandir la consulta a tablas virtuales relacionadas a través de las propiedades de navegación. Por ejemplo, la siguiente consulta incluye columnas de la entidad **mshr_hcmworkerbaseentity** con columnas expandidas de la entidad **mshr_dirpersonentity**. Tenga en cuenta que la opción de consulta **$select** también se incluye en la cláusula de opción de consulta **$expand**.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Cuando utilice este método de recuperar datos con la opción de consulta **$select** en la cláusula de opción de consulta **$expand**, normalmente verá mayores mejoras de rendimiento cuando la propiedad de navegación entre las entidades es una relación de varios a uno. Es posible que no vea la misma disminución en el tiempo de ejecución de la consulta al expandir una relación de uno a varios. Para obtener más información sobre la definición de relación para talbas virtuales de Dataverse, ver [Relaciones de mesa](/powerapps/maker/data-platform/create-edit-entity-relationships).

Para obtener más información sobre el uso de las opciones de consulta del sistema **$select** y **$expand** en la API web de Dataverse, consulte [Recuperar registros de entidades relacionados con una consulta](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Seleccionar columnas en Power BI

Si experimenta alguno de los indicios antes mencionados de rendimiento lento al construir un informe de Power BI contra una tabla virtual de Dataverse, puede mejorar el rendimiento excluyendo columnas de clave externa de las columnas seleccionadas de la tabla para el informe. Por ejemplo, si está utilizando Power BI Desktop para crear un informe contra la entidad **mshr_hcmworkerbaseentity**, puede utilizar los siguientes pasos para seleccionar las columnas que desea incluir en la consulta del informe.

1. En Power BI Desktop, seleccione **Más...** desde la lista **Obtener datos** desplegable en la cinta de acciones.
2. En la ventana **Obtener datos**, entrar **Common Data Service** en el cuadro de búsqueda, seleccione el conector **Common Data Service** y seleccione **Conectar**.
3. En el campo **URL del servidor** de la ventana Common Data Service, ingrese el URI de la organización para su entorno de Dataverse y seleccione **Aceptar**.
  
   ![Escriba el URI para su entorno Dataverse.](./media/PowerBIDataverseURLSetup.png)
  
4. En la ventana del navegador, expanda el nodo **Entidades**.
5. En el cuadro de búsqueda, ingrese **mshr_hcmworkerbaseentity** y seleccione la entidad.
6. Seleccione **Transformar datos**.
7. En la ventana del Editor de Power Query, seleccione **Editor avanzado**.
8. En la ventana **Editor avanzado**, actualice la consulta para que se vea como la siguiente, agregando o quitando cualquier columna a la matriz según sea necesario.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Actualice la consulta en el Editor avanzado para Power Query Editor.](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. Seleccione **Listo**.

   > [!NOTE]
   > Si anteriormente recibió un error de tipo 429 de la consulta antes de la actualización, es posible que deba esperar el período de reintento antes de actualizar la consulta para que se complete correctamente.

10. Hacer clic en **Cerrar y aplicar** en la cinta de acciones de Power Query Editor.

Entonces puede comenzar a construir su informe de Power BI contra las columnas seleccionadas de la tabla virtual.

#### <a name="selecting-columns-in-power-apps"></a>Seleccionar columnas en Power Apps

Similar a las consultas de API web de Dataverse y Power BI, puede mejorar el rendimiento de las consultas para Power Apps basandose en las tablas virtuales de Dataverse al excluir columnas de tablas relacionadas de su aplicación. Si alguna columna de una tabla relacionada se ha incluido en una página, la URL de solicitud construida para obtener los datos incluirá las propiedades de clave externa de la tabla relacionada. Esto, como en los ejemplos de [Seleccionar columnas en una consulta OData](#selecting-columns-in-power-apps), reduce el rendimiento al provocar búsquedas de datos adicionales.

Para solucionar este problema, puede validar que no se hayan incluido campos de datos de tablas relacionadas en ningún formulario de datos de su Power App.

1. En el panel de vista de árbol, seleccione el formulario de datos para la pantalla.
2. En el panel **Propiedades**, seleccione **Editar** en la propiedad **Campos**.
3. En el panel **Datos**, verifique que ninguno de los campos seleccionados sean campos de la tabla virtual de la fuente de datos.

Por ejemplo, si uno de los campos de datos incluidos en una página de la aplicación hace referencia a otra tabla, como **ThisItem.Worker.Name**, dónde **Worker** es la tabla relacionada, existe la posibilidad de que se reduzca el rendimiento al obtener los datos.

Puedes usar el [Monitor de Power Apps](/powerapps/maker/monitor-overview) para asegurarse de que solo se incluyan en la consulta las columnas que necesita para obtener los datos de la aplicación Power. Puede ver la URL construida para la operación getRows para asegurarse de que las columnas que ha seleccionado para su aplicación sean óptimas para recuperar los datos.

![Usar el Monitor de Power Apps para analizar la operación getData.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Filtrar la consulta de datos

Otro método para mejorar el rendimiento de la ejecución de consultas es limitar el número de registros devueltos en los resultados de la consulta. Puede hacer esto filtrando los resultados para asegurarse de que solo recibe los registros que necesita.

Ver [Filtrar Resultados](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) para obtener más información sobre el filtrado de datos de consultas.

### <a name="limiting-the-page-size-of-the-query"></a>Limitar el tamaño de página de la consulta

Si está trabajando con grandes conjuntos de datos, puede dividir los resultados de la consulta en varias páginas agregando el encabezado de preferencia `odata.maxpagesize` para consultas de datos.

Para obtener más información sobre la paginación, consulte [Especificar el número de entidades que se devolverán en una página](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Consulte también

- [Configurar tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
- [Preguntas frecuentes sobre tablas virtuales de Human Resources](hr-admin-virtual-entity-faq.md)
- [Preguntas frecuentes sobre limitación](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
