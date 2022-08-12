---
title: Solucionar problemas de sincronización en vivo
description: Este artículo proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas con la sincronización en vivo.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 1211f7da15686f1c55a4c942f04c73d671e0ba6b
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111438"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Solucionar problemas de sincronización en vivo

[!include [banner](../../includes/banner.md)]



Este artículo proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Microsoft Dataverse. Proporciona información específica que puede ayudarlo a solucionar problemas con la sincronización en vivo.

> [!IMPORTANT]
> Algunos de los problemas que aborda este artículo pueden requerir la característica de administrador del sistema o las credenciales de administrador de inquilinos de Azure Active Directory (Azure AD). Cada sección para cada problema explica si se requiere un rol o credenciales específicas.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>La sincronización en vivo muestra un error al crear una fila

Es posible que reciba el siguiente mensaje de error cuando crea una fila en una aplicación de finanzas y operaciones:

*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"El usuario no es miembro de la organización.\\"}}\], El servidor remoto devolvió un error: (403) Prohibido."}}".*

Para solucionar el problema, siga los pasos en [Requisitos del sistema y requisitos previos](requirements-and-prerequisites.md). Para completar esos pasos, los usuarios de la aplicación de doble escritura que se crearon en Dataverse deben tener el rol de administrador del sistema. El equipo propietario predeterminado también debe tener el rol de administrador del sistema.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>La sincronización en vivo muestra un error cuando intenta guardar los datos de la tabla

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba el siguiente mensaje de error cuando intenta guardar datos de tabla en una aplicación de finanzas y operaciones:

*No se pueden guardar los cambios en la base de datos. La unidad de trabajo no puede confirmar la transacción. No se pueden escribir datos en la entidad uoms. Las escrituras en UnitOfMeasureEntity fallaron con el mensaje de error No se puede sincronizar con las entidades uoms.*

Para solucionar el problema, debe asegurarse de que los datos de referencia de requisitos previos existan en la aplicación de finanzas y operaciones y Dataverse. Por ejemplo, si un registro de cliente pertenece a un grupo de clientes específico, asegúrese de que el registro del grupo de clientes exista en Dataverse.

Si existen datos en ambos lugares y ha confirmado que el problema no está relacionado con los datos, siga estos pasos.

1. Abra la entidad **DualWriteProjectConfigurationEntity** usando el complemento de Excel. Para usar el complemento, habilite el modo de diseño en el complemento de Excel de finanzas y operaciones y agregue **DualWriteProjectConfigurationEntity** a una hoja de cálculo. Para obtener más información, consulte [Usar Excel para ver y actualizar datos de entidades](../../office-integration/use-excel-add-in.md).
2. Seleccione y elimine los registros que tienen problemas en el mapa y el proyecto de escritura dual. Habrá dos registros para cada asignación de escritura dual.
3. Publique los cambios mediante el complemento de Excel. Este paso es importante porque elimina los registros de la entidad y las tablas subyacentes.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Gestionar errores de privilegio de lectura o escritura cuando crea datos en una aplicación de finanzas y operaciones

Es posible que reciba el mensaje de error "Solicitud incorrecta" cuando crea datos en una aplicación de finanzas y operaciones:

![Ejemplo del mensaje de error de solicitud incorrecta.](media/error_record_id_source.png)

Para solucionar el problema, debe habilitar el privilegio que falta asignando la función de seguridad correcta al equipo de las unidades de negocio asignadas de Dynamics 365 Sales o Dynamics 365 Customer Service.

1. En la aplicación de finanzas y operaciones, busque la unidad de negocio que está asignada en el conjunto de conexión de integración de datos.

    ![Asignación de la organización.](media/mapped_business_unit.png)

2. En la aplicación Customer Engagement , inicie sesión en el entorno, vaya a **Configuración \> Seguridad** y encuentre el equipo de la unidad de negocio asignada.

    ![Equipo de la unidad de negocio asignada.](media/setting_security_page.png)

3. Abra la página del equipo para editarla y luego seleccione **Gestionar roles**.

    ![Botón de administrar roles.](media/manage_team_roles.png)

4. En el cuadro de diálgoo **Gestionar roles de equipo**, asigne el rol que tiene el privilegio de lectura / escritura para las tablas relevantes, y luego seleccione **Aceptar**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Solucione problemas de sincronización en un entorno que ha cambiado recientemente el entorno Dataverse

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba el siguiente mensaje de error cuando crea datos en una aplicación de finanzas y operaciones:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**No se puede generar la carga útil para la entidad CustCustomerV3Entity**","logDateTime":" 2019-08-27T18:51:52.5843124Z","verboseError":"Error en la creación de la carga útil con error URI no válido: el URI está vacío".}\], isErrorCountUpdated":true}*

Así es como se ve el mensaje error en la aplicación Customer Engagement:

> Error inesperado de código de ISV. (ErrorType = ClientError) Excepción inesperada del complemento (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: no se pudo procesar la cuenta de la entidad - (Un intento de conexión falló porque la parte conectada no respondió correctamente después de un período de tiempo, o la conexión establecida falló porque el anfitrión conectado no pudo responder).

Este error ocurre si el entorno de Dataverse se restablece incorrectamente cuando intenta crear datos en la aplicación de finanzas y operaciones.

> [!IMPORTANT]
> Si ha vuelto a vincular los entornos, debe detener todos los mapas de entidades antes de continuar con los pasos de mitigación.

Para solucionar el problema, debe completar los pasos en Dataverse y la aplicación de finanzas y operaciones.

1. En la aplicación de finanzas y operaciones, siga estos pasos:

    1. Abra la entidad **DualWriteProjectConfigurationEntity** usando el complemento de Excel. Para usar el complemento, habilite el modo de diseño en el complemento de Excel de finanzas y operaciones y agregue **DualWriteProjectConfigurationEntity** a una hoja de cálculo. Para obtener más información, consulte [Usar Excel para ver y actualizar datos de entidades](../../office-integration/use-excel-add-in.md).
    2. Seleccione y elimine los registros que tienen problemas en el mapa y el proyecto de escritura dual. Habrá dos registros para cada asignación de escritura dual.
    3. Publique los cambios mediante el complemento de Excel. Este paso es importante porque elimina los registros de la entidad y las tablas subyacentes.
    4. Para ayudar a prevenir errores al volver a vincular los entornos de finanzas y operaciones o Dataverse, asegúrese de que no queden configuraciones de escritura dual.

2. En Dataverse, siga estos pasos:

    1. Inicie sesión en su entorno de Dataverse (por ejemplo, `https://*****.crm.dynamics.com/`).
    2. Vaya a **Ajustes avanzados** \> **Búsqueda avanzada**.
    3. Seleccione **Configuración de tiempo de ejecución de DualWrite**.
    4. Seleccione la columna para ver.
    5. Seleccione **Resultados** para ver las configuraciones.
    6. Elimine todas las instancias.

3. En la aplicación de finanzas y operaciones, siga estos pasos:

    1. Abra la entidad **DualWriteProjectConfigurationEntity** usando el complemento de Excel. Para usar el complemento, habilite el modo de diseño en el complemento de Excel de finanzas y operaciones y agregue **DualWriteProjectConfigurationEntity** a una hoja de cálculo. Para obtener más información, consulte [Usar Excel para ver y actualizar datos de entidades](../../office-integration/use-excel-add-in.md).
    2. Seleccione y elimine los registros que tienen problemas en el mapa y el proyecto de escritura dual. Habrá dos registros para cada asignación de escritura dual.
    3. Publique los cambios mediante el complemento de Excel. Este paso es importante porque elimina los registros de la entidad y las tablas subyacentes.
    4. Para ayudar a prevenir errores al volver a vincular los entornos de finanzas y operaciones o Dataverse, asegúrese de que no queden configuraciones de escritura dual.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Error de sincronización en vivo después de hacer una copia completa de la base de datos

Es posible que reciba el siguiente mensaje de error después de ejecutar una copia completa de la base de datos de un sistema a otro y luego intentar ejecutar una operación de base de datos:

*La organización SecureConfig (???) no coincide con la organización CRM real (???).*

El mensaje de error se muestra desde el complemento de tiempo de ejecución de escritura dual para garantizar que la configuración de escritura dual que está configurada en un sistema no se pueda utilizar en otro sistema.

Para solucionar el problema, elimine todos los registros de la tabla **msdyn_dualwriteruntimeconfig** después de restaurar la base de datos. Para más información, vea [Desvincular y volver a vincular entornos de escritura dual](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Problemas de sincronización en vivo causados por una sintaxis de filtro de consulta incorrecta en los mapas de escritura dual

Aunque la expresión de consulta para un filtro de mapa de escritura dual es sintácticamente correcta, es posible que no funcione como se esperaba. La expresión de filtro está en una entidad, no en una fuente de datos individual de un objeto de consulta. Por lo tanto, la consulta SQL que se genera no devuelve los resultados esperados.

He aquí un ejemplo.

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Es de esperar que se filtren los proyectos que no tienen padre. Sin embargo, el filtro no funciona porque se traduce a una consulta que se parece al siguiente ejemplo.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

El resultado real es que el campo `parentProject` se evalúa como `null`. Sin embargo, `null` no es lo mismo que la cadena vacía. Debido a esta discrepancia, el filtro de consulta no devuelve resultados válidos.

Para arreglar el problema, siga estos pasos.

1. Agregue una columna calculada que se pueda agregar en un modelo de extensión y que esté respaldada por una lógica que convierta `null` en la cadena vacía.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Utilice el filtro en la nueva columna calculada en lugar de la columna predeterminada.

Para evaluar el filtro en un entorno de desarrollo, puede utilizar el siguiente código X ++ para validar los resultados. Ejecute este código como un programa independiente. Puede usarlo para evaluar diferentes tipos de filtros que son aplicables para una entidad antes de usar esos filtros en mapas de escritura dual. La consulta se puede ejecutar en la base de datos para evaluar discrepancias.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>Los datos de las aplicaciones de finanzas y operaciones no se sincronizan con Dataverse

Durante la sincronización en vivo, puede encontrar un problema en el que solo se sincroniza una parte de los datos desde aplicaciones de finanzas y operaciones para Dataverse o los datos no están sincronizados en absoluto.

> [!NOTE]
> Debe solucionar este problema durante el desarrollo.

Antes de comenzar a solucionar el problema, revise los siguientes requisitos previos:

+ Asegúrese de que sus cambios personalizados estén escritos en un solo alcance de transacción.
+ Los eventos empresariales y el marco de escritura dual no se manejan operaciones `doinsert()`, `doUpdate()` y `recordset()`, o registros donde `skipBusinessEvents(true)` está marcado. Si su código está dentro de estas funciones, no se activará la escritura dual.
+ Los eventos comerciales deben registrarse para la fuente de datos que se asigna. Algunas fuentes de datos pueden usar una combinación externa y pueden estar marcadas como de solo lectura en aplicaciones de finanzas y operaciones. No se realiza un seguimiento de estas fuentes de datos.
+ Los cambios se activarán solo si las modificaciones están en los campos mapeados. Las modificaciones de campo no mapeadas no activarán la escritura dual.
+ Asegúrese de que las evaluaciones de los filtros proporcionen un resultado válido.

### <a name="troubleshooting-steps"></a>Pasos de solución de problemas

1. Revise las asignaciones de campos en la página de administración de escritura dual. Si un campo no se asigna de las aplicaciones de finanzas y operaciones a Dataverse, no se rastreará. Por ejemplo, en la siguiente ilustración, el campo **Descripción** se rastrea desde Dataverse, pero no desde las aplicaciones de finanzas y operaciones. No se rastrearán los cambios en ese campo en las aplicaciones de finanzas y operaciones.

    ![Campo seguido.](media/live-sync-troubleshooting-1.png)

2. Determine si se realiza un seguimiento de la fuente de datos en la definición de eventos empresariales. Por ejemplo, en la siguiente ilustración, no se realizará un seguimiento de ningún campo de la tabla **DefaultDimensionDAVs** y las tablas subyacentes para detectar cambios. No se realiza un seguimiento de las fuentes de datos que utilizan una combinación externa y que están marcadas como de solo lectura.

    ![Campo que no se rastrea.](media/live-sync-troubleshooting-2.png)

3. Determine si los campos de la tabla asignada aparecen en la tabla **DEFINICIÓN DE EVENTOS DE NEGOCIOS**, como se muestra en la siguiente ilustración. Si no encuentra el campo que está buscando en el resultado de la consulta, no se activará mediante escritura dual.

    ![Campo seguido en la tabla.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Escenario de ejemplo

En las aplicaciones de finanzas y operaciones, hay una actualización de la dirección para un registro de contacto, pero el cambio de dirección no está sincronizado con Dataverse. Este escenario ocurre porque no hay registro en la tabla **NegociosEventosDefinición** tiene la combinación de la tabla afectada y la entidad. Específicamente, la tabla **LogisticsPostalAddress** no es la fuente de datos directa para la entidad **smmContactpersonCDSV2Entity**. La entidad **smmContactpersonCDSV2Entity** tiene **smmContactPersonV2Entity** como origen de datos y **smmContactPersonV2Entity**, a su vez, tiene **LogisticsPostalAddressBaseEntity** com origen de datos. La tabla **LogisticsPostalAddress** es la fuente de datos para **LogisticsPostalAddressBaseEntity**.

Una situación similar puede ocurrir en algunos patrones no estándar, como los casos en los que la tabla que se está modificando en las aplicaciones de finanzas y operaciones obviamente no está vinculada a la entidad que las contiene. Por ejemplo, los datos de la dirección principal se calculan en la entidad **smmContactPersonCDSV2Entity**. El marco de escritura dual intenta determinar cómo un cambio en una tabla subyacente se asigna a las entidades. Por lo general, este enfoque es suficiente. Sin embargo, en algunos casos, el vínculo es tan complejo que debe ser específico. Debe asegurarse de que el **RecId** de la tabla relacionada está directamente disponible en la entidad. Luego agregue un método estático para monitorear la tabla en busca de cambios.

Por ejemplo, revise el método **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()**. **CustCustomerV3entity** y **VendVendorV2Entity** han sido modificados para manejar esta situación.

Para arreglar el problema, siga estos pasos.

1. Agrega un campo **PrimaryPostalAddressRecId** a la entidad **smmContactPersonV2Entity**. Hágalo interno.

    ![Campo agregado a la entidad smmContactPersonV2Entity.](media/Troubleshoot_live_sync_issue_1.png)

2. Agregue el mismo campo a al entiddad **smmContactPersonCDSV2Entity**.

    ![Campo agregado a la entidad smmContactPersonCDSV2Entity.](media/Troubleshoot_live_sync_issue_2.png)

3. Agregue el siguiente método a la clase **smmContactPersonCDSV2Entity**.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Sincronice la base de datos y cree la aplicación.
5. Detenga todos los mapas de escritura dual que se crean en la entidad **smmContactPersonCDSV2Entity**.
6. Inicie el mapa. Debería ver la nueva tabla (**LogisticsPostalAddress** en este ejemplo) que ha comenzado a rastrear usando la columna **RefTableName** para la fila donde el valor **refentityname** es igual a **smmContactPersonCDSV2Entity** en la tabla **NegociosEventosDefinición**.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Error al crear un registro donde se envían varios registros desde una aplicación de finanzas y operaciones para Dataverse en el mismo lote

Para cualquier transacción, una aplicación de finanzas y operaciones crea datos en un lote y los envía como lote a Dataverse. Si se crean dos registros como parte de la misma transacción y hacen referencia entre sí, es posible que reciba un mensaje de error similar al siguiente ejemplo en la aplicación de finanzas y operaciones:

*No se pueden escribir datos en la entidad aaa_fundingsources. No se puede buscar ebecsfs_contracts con valores {PC00...}. No se puede buscar aaa_fundingsources con valores {PC00...}. Las escrituras en aaa_fundingsources fallaron con el mensaje de error Mensaje de excepción: El servidor remoto devolvió un error: (400) Solicitud incorrecta.*

Para solucionar el problema, cree relaciones de entidad en la app de finanzas y operaciones para indicar que las dos entidades están relacionadas entre sí y que los registros relacionados se manejan en la misma transacción.

## <a name="enable-verbose-logging-of-error-messages"></a>Habilitar el registro detallado de mensajes de error

En una aplicación de finanzas y operaciones, es posible que encuentre errores relacionados con el entorno de Dataverse. Es posible que el mensaje de error no contenga el texto completo del mensaje u otros datos relevantes. Para obtener más información, puede habilitar el registro detallado configurando el indicador **IsDebugMode** que está presente en la entidad **DualWriteProjectConfigurationEntity** en todas las configuraciones del proyecto en aplicaciones de finanzas y operaciones.

1. Abra la entidad **DualWriteProjectConfigurationEntity** usando el complemento de Excel. Para usar el complemento, habilite el modo de diseño en el complemento de Excel de finanzas y operaciones y agregue **DualWriteProjectConfigurationEntity** a una hoja de cálculo. Para obtener más información, consulte [Usar Excel para ver y actualizar datos de entidades](../../office-integration/use-excel-add-in.md).
2. Estableza el indiecador **IsDebugMode** en **Sí** en el proyecto.
3. Ejecute el escenario.
4. Los registros detallados están disponibles en la tabla **DualWriteErrorLog**. Para buscar datos mediante el navegador de tablas, utilice la siguiente URL: `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. Para capturar más registros en modo de depuración, instale la actualización en [KB 4595434 (Corrección de la propagación de valores en blanco en la sincronización en vivo de escritura dual)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Error al agregar una dirección para un cliente o contacto

Es posible que reciba el siguiente mensaje de error cuando intente agregar una dirección para un cliente o contacto en aplicaciones de finanzas y operaciones o Dataverse:

*No se pueden escribir datos en la entidad msdyn_partypostaladdresses.Writes to DirPartyPostalAddressLocationCDSEntity falló con mensaje de error Solicitud fallida con código de estado BadRequest y código de error CDS: 0x80040265 mensaje de respuesta: Se produjo un error en el complemento. Ya existe un registro que tiene los valores de atributo ID de ubicación. La clave de entidad Clave de ID de ubicación requiere que este conjunto de atributos contenga valores únicos. Seleccione valores únicos y vuelva a intentarlo.*

Para solucionar el problema, instale la versión del paquete de orquestación de escritura dual (2.2.2.60), de modo que las claves en la tabla **Dirección** se definen como se muestra en la siguiente tabla.

| Propiedad | Valor |
|---|---|
| Nombre para mostrar | **Clave de ubicación** |
| Nombre | **msdyn_locationkey** |
| Campos | **msdyn_locationid**, **parentid** |
| Estado | **Activa** |
| Trabajo del sistema | En blanco |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Error al agregar un cliente en Dataverse

Es posible que reciba el siguiente mensaje de error cuando intenta agregar un cliente en Dataverse:

*"RecordError0": "Error de escritura para la entidad Clientes V3 con excepción desconocida - No se encontró el registro de parte para el tipo de parte 'Organización'"}.*

Cuando se crea un cliente en Dataverse, se genera un nuevo número de partido. El mensaje de error se muestra cuando el registro del cliente, junto con la parte, se sincroniza con aplicaciones de finanzas y operaciones, pero ya existe un registro de cliente que tiene un número de parte diferente.

Para solucionar el problema, busque al cliente mediante la búsqueda de grupo. Si el cliente no existe, cree un nuevo registro de cliente. Si el cliente existe, use la parte existente para crear el nuevo registro de cliente.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Error al crear un nuevo cliente, proveedor o contacto en Dataverse

Es posible que reciba el siguiente mensaje de error cuando intente crear un nuevo cliente, proveedor o contacto en Dataverse:

*No se puede actualizar el tipo de una fiesta de 'DirOrganization' a 'DirPerson'; en su lugar, se debe eliminar la fiesta existente seguida de una inserción con el nuevo tipo.*

En Dataverse, hay una secuencia numérica en la tabla **msdyn_party**. Cuando se crea una cuenta en Dataverse, se crea un nuevo partido (por ejemplo **Fiesta-001** del tipo **Organización**). Estos datos se envían a la aplicación de finanzas y operaciones. Si el entorno de Dataverse se restablece, o el entorno de finanzas y operaciones está vinculado a un entorno de Dataverse, y luego se crea un nuevo registro de contacto en Dataverse, se cera un nuevo valor de fiesta que comienza con **Fiesta-001**. Esta vez, el registro de fiesta que se crea será **Fiesta-001** del tipo **Persona**. Cuando se sincronizan estos datos, las aplicaciones de finanzas y operaciones muestran el mensaje de error anterior, porque el registro de la fiesta **Fiesta-001** de tipo **Organización** ya existe.

Para solucionar el problema, cambie la secuencia numérica automática del campo **msdyn_partynumber** de la tabla **msdyn_party** en Dataverse a una secuencia numérica automática diferente.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Problema de rendimiento con asignaciones de clientes o contactos

Es posible que pueda mejorar ligeramente el rendimiento de la sincronización en vivo para clientes y contactos personalizando el método **getEntityDataSourceToFieldMapping** (en la entidad **CustCustomerV3Entity**) y el método **getEntityDataSourceToFieldMapping** (en la entidad **smmContactPersonCDSV2Entity**). Estas personalizaciones reducen el número de registros en la tabla **BusinessEventsDefinition**. Esta reducción en el número de registros, a su vez, reduce el número de eventos que se generan.

El método **getEntityDataSourceToFieldMapping** de la entidad **CustCustomerV3Entity** se asegura de que una actualización de la dirección electrónica o la dirección postal del cliente desencadene eventos comerciales, por lo que los datos actualizados se enviarán a Dataverse. Si no usa todos los campos y no necesita la información en escritura dual, comente las líneas apropiadas en el método. Cada campo y tabla rastreados que se agregan en este método agrega un registro en la tabla **NegociosEventosDefinición** para la combinación de la tabla rastreada y la entidad rastreada.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

De forma similar, el método **getEntityDataSourceToFieldMapping** de la entidad **smmContactPersonCDSV2Entity** se asegura de que cualquier actualización de la dirección electrónica del contacto o la dirección postal del cliente desencadene eventos comerciales, por lo que los datos actualizados se enviarán a Dataverse. En el método, puede comentar las líneas de cualquier campo que no use.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

Después de actualizar los métodos, siga estos pasos.

1. Sincronice la base de datos y cree la aplicación.
2. Detenga todos los mapas de escritura dual que se crean en las entidades **smmContactPersonCDSV2Entity** y **CustCustomerV3Entity**.
3. Inicie los mapas. Debería ver menos registros en las entidaddes **smmContactPersonCDSV2Entity** y **CustCustomerV3Entity** y la tabla **NegociosEventosDefinición**, y el rendimiento podría mejorar marginalmente.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

