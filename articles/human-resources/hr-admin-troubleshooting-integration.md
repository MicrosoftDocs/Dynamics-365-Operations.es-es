---
title: P+F sobre la integración con Finance
description: En este tema se explica qué datos se sincronizan en una integración de Human Resources y Finance.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9b83250bdb54ea6e78709dd3a3ea434a994f6211
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694015"
---
# <a name="integration-with-finance-faq"></a>P+F sobre la integración con Finance


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tema responde a las preguntas habituales asociadas a qué datos se sincronizan cuando Dynamics 365 Human Resources se integra con Dynamics 365 Finance.

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a>¿Puedo editar el usuario de la aplicación Dynamics 365 Talent en Power Apps?

No Si edita el usuario de la aplicación Human Resources, se puede producir un error en la integración de Human Resources y Dataverse. En la siguiente tabla se muestra la configuración predeterminada para el usuario de la aplicación Talent.

| Nombre completo | Id. de la aplicación | Id. de objeto de Azure AD | URI de id. de aplicación |
| --- | --- | --- | --- |
| Dynamics 365 for Talent | f9be0c49-aa22-4ec6-911a-c5da515226ff | 27fd8129-4b3c-43f7-b1bf-47495d3a049b | f9be0c49-aa22-4ec6-911a-c5da515226ff |

![Configuración predeterminada para el usuario de la aplicación Talent.](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>¿Se sincronizan todos los datos o solo algunas entidades de datos?

Un subconjunto de los datos se sincroniza. Para ver una lista de todas las entidades, consulte [Integración con Dynamics 365 Finance](hr-admin-integration-finance.md).

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a>¿Por qué no veo los datos sincronizados con Dataverse?

De forma predeterminada, la integración de Dataverse se desactiva en los entornos nuevos que no incluyen los datos proporcionados de prueba. De forma predeterminada, está activado en los entornos nuevos que incluyen datos de demostración, y la sincronización de datos empieza cuando se aprovisiona el entorno. Después de que el entorno esté listo para sincronizar datos, puede activar la integración. Para obtener más información, consulte la sección [Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md).

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>¿Puedo crear una nueva asignación sin usar plantillas?

Las plantillas son el punto de partida. Puede crear su propia plantilla, pero una plantilla siempre es necesaria cuando se crea un proyecto de integración. Para obtener más información acerca del integrador de datos (DI), las plantillas y los proyectos, consulte [Integrar los datos en Microsoft Dataverse](/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>¿Puedo asignar dimensiones financieras para transferir entre Human Resources y Finance?

Las dimensiones financieras no están actualmente en Dataverse y como consecuencia no forman parte de la plantilla predeterminada. Esta entidad se planifica, pero no hay una escala de tiempo de liberación disponible.

Para los datos que residen en Finance pero no existen en Human Resources, enlace los dos sistemas usando **Configurar vínculos** en Human Resources.

![Distribuir dimensiones financieras.](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>A veces cuando importo empleados, van a empleados inactivos en Finance. ¿Por qué?

Puede obtener este error si los empleados no tienen un registro de detalle activo de empleo en Human Resources. Para solucionarlo, vaya a **Dirección de personal \> Empleados \> Historial de empleo \> Administrador de fechas**, y compruebe que hay un registro activo de detalles del empleo.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Si selecciono asignar solo un subconjunto de campos, ¿los cambios realizados en los campos no asignados desencadenarán una sincronización?

La sincronización de datos sigue la programación de ejecución. La integración cogerá un registro si cualquier campo del registra cambia, con independencia de si el campo forma parte de asignación de integración.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>¿Cómo puedo enviar únicamente cambios de trabajadores activos y no los registros finalizados?

Con el uso de la "consulta avanzada”, puede filtrar y volver a dar forma a datos de origen antes de pasarlos al destino.

![Consulta avanzada de trabajadores activos.](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>¿Puedo especificar qué campos debo enviar a Finance para una entidad específica?

Los campos se pueden agregar o quitar de la tarea de integración. No todos los campos de datos que existen en la tabla de Dataverse se rellenarán desde Human Resources.
Los datos adicionales se pueden rellenar mediante Power Apps.

![Añadir o eliminar campos a y desde una tarea de integración.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Configuro la integración como un trabajo por lotes, pero Human Resources ha perdido la conexión con el sistema de destino. ¿Cómo puedo enviar al mismo conjunto de cambios al sistema de destino?

No se requiere ninguna configuración especial para el control de excepciones. El integrador de datos automáticamente cogerá e informará de los errores que se producen en el origen y destino y permitirá intentos manuales. Sin embargo, no permite la corrección manual de los datos. Si las actualizaciones de datos son necesarias, deben producirse en el origen o el destino.

## <a name="can-i-set-up-bi-directional-integration"></a>¿Puedo configurar la integración bidireccional?

No, la integración es actualmente unidireccional (de Human Resources a Finance and Operations). Sin embargo, existe una plantilla predeterminada disponible para enviar datos desde Human Resources a Finance.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>¿Puedo permitir la eliminación de registros como parte de mi integración?

No, el integrador de los datos no capturará los registros eliminados para la transferencia de datos. Únicamente la configuración y las actualizaciones (UPSERT) de los datos se incluyen actualmente.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>¿Puedo volver a ejecutar la ejecución con errores? En caso afirmativo, ¿se enviará un archivo completo o solo los cambios?

La primera ejecución del integrador de datos es una siempre una ejecución completa. Las ejecuciones posteriores se basan en seguimiento de cambios. Cuando se ejecuta una ejecución de errores, se extraen los registros en el ámbito de la ejecución y se envían los cambios más recientes de Dataverse.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>Cuando guardo el proyecto, obtengo el error: "El proyecto tiene errores de asignación.” ¿Qué hago?

Compruebe la configuración de las claves de integración, realice los cambios necesarios en la configuración, y actualice las entidades del proyecto.

Cuando se usa la plantilla predeterminada, las claves de integración automáticamente serán importadas. Este problema puede producirse cuando las tareas nuevas se agregan a la plantilla existente.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Si tengo un número de N de entidades jurídicas en las que los trabajadores tienen empleos, ¿necesito crear una asignación para cada uno de ellos?

Sí, para cada entidad jurídica en Finance, necesitará un proyecto de integración individual en la integración de datos.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Necesito transferir los datos que no son parte de la plantilla predeterminada proporcionada por Microsoft. ¿Puedo hacer esto?

Sí, los campos se pueden agregar o quitar de la plantilla existente. La plantilla se puede modificar para incluir datos adicionales de otras tablas de Dataverse. La entidad debe estar en Dataverse para que se incluya en la plantilla. 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Acabo de crear nuevos entornos de Finance y Human Resources y recibo el error "El valor de los datos infringe las restricciones de integridad”. ¿Por qué?

Los motivos de este error pueden ser:

- La transferencia de datos produjo una extracción de registros duplicada en el origen (Dataverse).

- La transferencia de datos tiene valores nulos para campos que son necesarios en Finance and Operations. Compruebe que los datos que están en Dataverse y cumplen con los requisitos de Finance and Operations.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Si hay errores de la ejecución y el identificador de empleado no se sincroniza ¿cómo encuentro el trabajo del historial que tiene el registro de empleado con errores?

El integrador de los datos creará varios proyectos en Finance. La relación entre la tarea del integrador de datos y el proyecto de Finance es de uno a uno.

Haga un seguimiento del tiempo del historial de la ejecución del integrador de datos y busque el proyecto de índice -1 en Finance. Si el número de la tarea es 9 en el integrador de los datos, el índice en Finance es 8.

1. Obtenga el índice de la tarea del integrador de datos (en este ejemplo es “9 ").

    ![Captura del índice de la tarea desde el integrador de datos.](media/CaptureTaskIndex.png)

2. Realice un seguimiento del tiempo de ejecución del proyecto.

    ![Seguimiento del tiempo de ejecución del proyecto.](media/CaptureTimeOfExecution.png)

3. En Finance, identifique el índice. - 1. En este ejemplo, el proyecto con el sufijo "8 "y el tiempo de ejecución de índice "0 "coincide con el tiempo de ejecución del paso 2.

    ![Identificar el índice.](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>Después de integrar Human Resources y Finance, no veo mis datos de Human Resources en Finance. ¿Qué hago?

La integración en Finance es un proceso de dos pasos. En primer lugar, compruebe que los datos de Human Resources estén actualizados y disponibles en Dataverse. Esto es una sincronización prácticamente en tiempo real y se puede comprobar en Power Apps buscando los datos en las tablas de datos.

![Datos en Dataverse.](media/DataInCDS.png)

Si los datos no aparecen como se esperaba en Dataverse, compruebe que la entidad se admita en la integración. Para incluir datos adicionales en Dataverse, se necesitará un cambio en el lado de Microsoft.

Si admite la entidad y los datos están disponibles en Dataverse, compruebe que la asignación sea correcta en el integrador de los datos. Si la asignación del integrador parece aceptable, compruebe que los trabajos de gestión de datos se hayan ejecutado correctamente. Los errores pueden producirse durante la ejecución de los trabajos por lotes. Para obtener más información sobre la administración de datos, vea [Administración de datos](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>Las direcciones de mis empleados son incorrectas después de que las importe a Finance. ¿Qué hago?

La secuencia numérica para **Identificador de la ubicación** usa el mismo patrón en Human Resources y en Finance. La secuencia numérica tiene que ser única en ambos lados para que no haya colisiones de dirección al integrar datos de Dataverse en Finance and Operations.

Durante la implementación de Human Resources, compruebe que las secuencias numéricas no sean iguales en Human Resources y Finance and Operations. Valide que todas las secuencias numéricas no sean idénticas donde los datos se puedan mantener en ambos sistemas.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Al crear mi conjunto de conexiones, no puedo ver la conexión en la lista desplegable de conexiones. ¿Qué hago?

Asegúrese de que al crear sus conexiones, elija Dynamics 365 Finance y Dataverse.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Al sincronizar los empleos, obtengo los errores “CompanyInfo_FK no existe“o “el valor “12/31/2154 11:59: pm" del campo "Fecha final del empleo" no se encuentra en la tabla "Empleo" relacionada.” ¿Qué debo hacer?

Asegúrese de que está realizando asignaciones a las entidades jurídicas correctas. La sincronización de entidades jurídicas no es parte de la plantilla predeterminada, por lo que se espera que cada entidad jurídica que está presente en Human Resources y Dataverse también esté en Finance. Además, asegúrese de que está seleccionando las entidades jurídicas correctas para el conjunto de conexiones asociado.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>Después de configurar mi proyecto, la asignación de campos para Finance parece estar vacía. ¿Qué hago?

Actualice las entidades de datos en Finance en **Administración de datos \> Parámetros del marco \> Configuración de entidad \> Actualizar lista de entidades.** Esto debe necesitar un par de minutos para completarse, luego deberá ver las asignaciones. Este error ocurre cuando se crean nuevos proyectos.

![Falta asignación de campos.](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Recursos adicionales

- Integrador de datos (DI): 

  - [Integrar datos en Microsoft Dataverse](/powerapps/administrator/data-integrator)

  - [Administración y solución de problemas de errores del integrador de datos](/powerapps/administrator/data-integrator-error-management)

  - [Respuesta a solicitudes de DSR para registros generados por el sistema en Power Apps, Microsoft Power Automate y Dataverse](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Administración de datos:

  - [Administración de datos](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
