---
title: Preguntas frecuentes sobre la migración de clientes de Human Resources
description: Este artículo responde a las preguntas más frecuentes sobre la migración de Microsoft Dynamics 365 Human Resources y a la infraestructura fusionada de finanzas y operaciones.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0e11d26ebe084762a8616c8aa0aa041a87306473
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734368"
---
# <a name="human-resources-customer-migration"></a>Migración de clientes de Human Resources

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>¿Cómo deberían planificar los clientes de Dynamics 365 Human Resources la migración a la infraestructura de finanzas y operaciones?

Dos categorías de clientes de Microsoft Dynamics 365 Human Resources se verán afectados y tendrán que realizar cambios para asegurarse de que están en la última infraestructura de finanzas y operaciones:

- Clientes que usan Dynamics 365 Human Resources y no tienen ninguna otra aplicación de operaciones de Dynamics 365
- Clientes que usan Dynamics 365 Human Resources y Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce o Dynamics 365 Project Operations

Independientemente de la categoría a la que pertenezcan, los clientes deberán trasladar los datos a un entorno recién creado en la infraestructura de finanzas y operaciones y validar que la fusión se haya completado con éxito.

En el futuro, la aplicación Dynamics 365 Human Resources tendrá su propio entorno de finanzas y operaciones que está separado de otras aplicaciones de operaciones. De esta forma, los clientes podrán aprovechar las opciones de extensibilidad sin tener que fusionar sus datos actuales. Microsoft proporcionará herramientas y un entorno de espacio aislado que los clientes pueden usar para probar y validar la migración de datos antes de pasar a un entorno de producción. Las herramientas permitirán un proceso casi automatizado y estarán disponibles entre agosto y noviembre de 2022.

Los clientes que utilizan otras aplicaciones en la infraestructura de finanzas y operaciones tendrán la opción de fusionar sus datos de Human Resources con un entorno existente. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>¿Cuándo pasarán los clientes a la infraestructura de finanzas y operaciones?

La transición de cada empresa dependerá de la configuración actual y la preparación de esa empresa para migrar a la nueva infraestructura de finanzas y operaciones. Recomendamos que los clientes trabajen con su socio de Microsoft para determinar el mejor camino a seguir.

- Las organizaciones que actualmente utilizan el módulo **Human Resources** de Dynamics 365 Finance podrán habilitar nuevas capacidades desde Dynamics 365 Human Resources como parte del proceso de actualización regular de One Version. Está previsto que las nuevas funciones estén disponibles de forma generalizada a partir de enero de 2022.
- Las organizaciones que utilizan Dynamics 365 Human Resources tendrán acceso a las herramientas que pueden usar para completar la fusión de la infraestructura. Microsoft trabajará con los clientes en la transición para ayudar a evitar cualquier interrupción en el servicio. Los clientes tendrán 12 meses para realizar la transición, a partir del momento en que las herramientas de migración estén disponibles.
- Las organizaciones que usan Dynamics 365 Human Resources y el módulo **Human Resources** puede mover su infraestructura de Human Resources independiente a la infraestructura de finanzas y operaciones. Otra opción es usar las herramientas de fusión para unir los entornos en un solo entorno. No hay requisitos ni plazos para fusionar los dos entornos.

Para obtener la información actualizada, consulte periódicamente los [Planes de lanzamiento](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>¿Seguirán necesitando los clientes integraciones personalizadas entre Dynamics 365 Human Resources y el módulo Human Resources?

- Los clientes que tienen Dynamics 365 Human Resources y otros entornos de infraestructura de finanzas y operaciones que están integrados actualmente tendrán que continuar integrando los dos entornos después de la fusión.
- Los clientes que optan por mantener su entorno de Dynamics 365 Human Resources independiente de su entorno de aplicaciones de finanzas y operaciones existente tendrá que continuar integrando los entornos para que los datos estén disponibles en ambos entornos.
- Los clientes pueden seguir usando el integrador de datos para copiar datos entre los dos entornos. Los clientes que combinen datos en un solo entorno después de la migración ya no tendrán que integrar los datos, pues todos los datos estarán en una sola base de datos.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>¿Migrarán automáticamente las soluciones ISV de clientes?

La experiencia de migración para cada solución de proveedor de software independiente (ISV) variará, según el método de integración de la solución. Microsoft trabajará en estrecha colaboración con los ISV para ayudar a realizar una transición sin problemas a la nueva infraestructura de finanzas y operaciones. Muchas soluciones de ISV se basan en Dataverse mediante el uso de capacidades de Microsoft Power Platform. Estas soluciones dependen de la integración de Dataverse entre el entorno de Dynamics 365 Human Resources y el entorno de Dataverse. La integración de Dataverse está en desuso como parte de la fusión de infraestructura. En la infraestructura de finanzas y operaciones se planean nuevos mapas de doble escritura para reemplazar la funcionalidad de la integración de Dataverse.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>¿Cómo se verá afectado el integrador de datos que mueve datos entre Dynamics 365 Human Resources y otras aplicaciones de Dynamics 365?

Cuando los clientes pasen a la infraestructura de finanzas y operaciones, deberán continuar integrando datos entre los dos entornos. Los clientes pueden seguir usando el integrador de datos para realizar estas tareas de migración de datos. Los clientes que planean mantener su entorno de Dynamics 365 Human Resources independiente de su entorno de aplicaciones de finanzas y operaciones existente tendrá que continuar integrando los datos entre los dos entornos. Para los clientes que fusionen los dos entornos en un solo entorno, ya no será necesaria la integración entre los dos entornos.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>¿Cómo se moverán los datos entre Dynamics 365 Human Resources en la infraestructura de finanzas y operaciones y Dataverse después de la migración?

La integración de Dataverse actual entre Dynamics 365 Human Resources y Dataverse está dejando en desuso como parte de la infraestructura de finanzas y operaciones. Hay planes para introducir mapas de doble escritura para asignar las entidades de finanzas y operaciones a las tablas de Dataverse. Los clientes tendrán que decidir qué mapas de doble escritura se requieren para su implementación. Recomendamos que se utilicen tablas virtuales para integraciones y soluciones de ISV, a menos que exista una necesidad empresarial específica de que los datos se dupliquen en Dataverse para ejecutar lógica de negocios.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>¿Cómo afecta la migración a las extensiones de Dataverse para Dynamics 365 Human Resources?

Los clientes deberán migrar a un entorno de espacio aislado antes de migrar su entorno de producción. Cuando los clientes migren su entorno de espacio aislado, tendrán que crear una copia de su entorno de Dataverse para conectarse al nuevo entorno migrado de finanzas y operaciones. Recomendamos que un cliente copie tanto los datos como las soluciones para el entorno, de modo que coincidan con el entorno de producción actual del cliente.

Cuando los clientes estén listos para migrar su entorno de Dynamics 365 Human Resources de producción, Microsoft migrará automáticamente la base de datos y el almacenamiento de Azure Blob. La base de datos y el almacenamiento migrados apuntarán el nuevo entorno en la infraestructura de finanzas y operaciones al mismo entorno de Dataverse de producción. Antes de que los datos puedan seguir copiándose en Dataverse, los clientes deberán habilitar cualquier mapa de doble escritura que se requiera para sus integraciones, extensiones y soluciones ISV que se basan en Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>¿Funcionarán automáticamente los componentes de Microsoft Power Platform que se crearon para Dynamics 365 Human Resources después de que se complete la migración de la infraestructura?

Las aplicaciones que se crean en Power Apps, los flujos que se crean en Power Automate y otras personalizaciones de Microsoft Power Platform son como extensiones de Dataverse. Durante la migración de los entornos de producción del cliente, no hay impacto en entornos de Dataverse, incluidas las extensiones. En este caso, aplicaciones, flujos y otras personalizaciones de Power Microsoft Platform deberán seguir funcionando sin necesidad de configuración adicional.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>¿Qué pasará con las entidades de tablas virtuales de Dataverse para Dynamics 365 Human Resources durante la migración?

Cuando los clientes migran su entorno de Dynamics 365 Human Resources a la infraestructura de finanzas y operaciones, el entorno permanecerá conectado al entorno de Dataverse que está conectado actualmente a Dynamics 365 Human Resources. Las tablas virtuales de Dataverse que se hayan generado en el entorno seguirán funcionando sin necesidad de configuración adicional. Es posible que las tablas virtuales deban volver a generarse en el entorno de Dataverse que está conectado con el entorno de finanzas y operaciones existente de un cliente.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>¿Cómo funcionará una integración que utiliza la API del sistema de seguimiento de candidatos (ATS), la API de nómina, tablas virtuales de Dataverse para Dynamics 365 Human Resources u otras entidades de la API web de Dataverse cuando se complete la fusión de la infraestructura?

Cuando los clientes migran su entorno de Dynamics 365 Human Resources a la infraestructura de finanzas y operaciones, el entorno permanecerá conectado al entorno de Dataverse que está conectado actualmente a Dynamics 365 Human Resources. Todas las integraciones que se desarrollaron con la API web de Dataverse seguirán funcionando después de que se complete la migración.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>Nuestra organización ha configurado seguridad personalizada en Dynamics 365 Human Resources. ¿Seguirá aplicándose después de que se complete la migración de la infraestructura?

Sí, se incluirán configuraciones de seguridad personalizadas en la migración de datos.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>¿Se migrarán automáticamente los flujos de trabajo de Dynamics 365 Human Resources?

Sí, se migrarán las configuraciones de flujo de trabajo, el historial de flujo de trabajo y los flujos de trabajo actuales en proceso a la infraestructura fusionada.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>¿Se migrarán automáticamente las vistas guardadas de Dynamics 365 Human Resources?

Sí, las vistas guardadas se migrarán a la infraestructura fusionada.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>¿Las características que están habilitadas en Dynamics 365 Human Resources estarán disponibles automáticamente después de la fusión de la infraestructura?

- Para los clientes que utilizan el módulo **Human Resources**, las características que solo están disponibles en Dynamics 365 Human Resources se gestionarán a través de Administración de características. Por lo general, estas funciones no estarán habilitadas de forma predeterminada. Se documentará cualquier característica que deba habilitarse de forma predeterminada.
- Para los clientes que usan Dynamics 365 Human Resources, las características estarán disponibles en la infraestructura. Cualquier característica que no esté disponible será documentada. Todas las claves de Administración de características que estén habilitadas en el entorno de Dynamics 365 Human Resources actual se habilitarán en la infraestructura fusionada. Para más información, consulte [Resumen de administración de características](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>¿Qué sucede con las bases de datos BYOD durante la migración?

Las configuraciones de importación y exportación para traer su propia base de datos (BYOD) se migrarán a la infraestructura de finanzas y operaciones.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>¿Hay algún impacto en la región de Azure cuando se migra el entorno del cliente?

El entorno de Dynamics 365 Human Resources permanecerá en la misma región de Azure para la migración. Si existe el requisito de mover un entorno a una región de Azure diferente, los clientes deberán seguir los pasos estándar para migrar a una nueva región una vez que se complete la migración.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>¿Qué sucede con mi Azure Data Lakes durante la migración?

Cualquier exportación que esté configurada actualmente para Azure Data Lake Storage en aplicaciones de finanzas y operaciones mantendrá la misma configuración después de la migración.

> [!NOTE]
> Los mapas de doble escritura deberán estar habilitados para continuar escribiendo datos del entorno de Human Resources en Dataverse.

Los clientes que deseen exportar datos de Human Resources al lago de datos pueden habilitar esta característica una vez que se complete la migración a la infraestructura de finanzas y operaciones. Para más información, vea [Lagos de datos - Azure Architecture Center](/azure/architecture/data-guide/scenarios/data-lake).

Los clientes pueden vincular múltiples entornos de finanzas y operaciones al mismo lago de datos. Sin embargo, cada entorno apuntará a una carpeta y un contenedor diferentes. Los clientes que planean fusionar entornos más adelante deben planificar cuidadosamente su enfoque.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>¿Qué migración será necesaria si un cliente está utilizando actualmente el módulo Human Resources?

Los clientes que utilizan el módulo **Human Resources** tendrán la nueva funcionalidad de la característica de Dynamics 365 Human Resources aplicada a su entorno a través del proceso de actualización estándar de One Version. Los clientes pueden esperar ver la nueva funcionalidad en su entorno a medida que esté disponible en cada actualización. Los clientes pueden utilizar Administración de características para habilitar las características. Los clientes deben planificar la validación de estas nuevas características mediante el uso de los procesos que ya tienen y utilizarlos para validar otras actualizaciones en su entorno.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>¿Qué pasará con las integraciones personalizadas con sistemas externos?

Los clientes tendrán que migrar sus integraciones al entorno de finanzas y operaciones. Debido a que el punto de conexión de este entorno es diferente, es posible que los clientes deban actualizar o cambiar las integraciones para que apunten al nuevo entorno. Esta tarea será principalmente un proceso manual y los cambios necesarios dependerán de la arquitectura de la integración. Los clientes deben trabajar con su socio de Microsoft para determinar el mejor enfoque para mover integraciones.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>¿Qué pasará con las extensiones de Microsoft Power Platform (Dataverse) si los clientes fusionan un entorno de Dynamics 365 Human Resources con un entorno de finanzas y operaciones existente?

Si los clientes deciden fusionar un entorno de Dynamics 365 Human Resources y un entorno de finanzas y operaciones existente en una sola instancia de Dataverse después de la migración, sus los entornos de Dataverse deben combinarse como parte del proceso de fusión. Esta tarea requerirá que cualquier aplicación que se cree utilizando Power Apps y cualquier otra personalización se volverán a implementar en el nuevo entorno.

## <a name="what-will-happen-to-documents-during-the-migration"></a>¿Qué pasará con los documentos durante la migración?

Cuando los clientes migran su entorno de Dynamics 365 Human Resources a la infraestructura de finanzas y operaciones, los documentos permanecerán en el almacenamiento de documentos existente y se asignarán automáticamente al nuevo entorno en la infraestructura de finanzas y operaciones.

En una versión futura, se proporcionarán nuevas entidades de datos. Después de realizar ese cambio, los clientes que elijan fusionar su entorno de Dynamics 365 Human Resources con un entorno de finanzas y operaciones existente podrán exportar documentos y moverlos al entorno existente.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Después de la migración, ¿qué sucede con los trabajos por lotes que se configuraron en Dynamics 365 Human Resources?

Los trabajos por lotes deberán reconfigurarse en el entorno de finanzas y operaciones. Los clientes deberán evaluar cada trabajo por lotes y compararlo con la lista actual de trabajos por lotes en el entorno de finanzas y operaciones. Los clientes también deben analizar la programación por lotes general cuando fusionan los dos conjuntos de trabajos por lotes, para determinar si se deben realizar cambios en la programación de lotes, las prioridades o los grupos de lotes.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>¿Cómo afectará la migración al proyecto LCS para Dynamics 365 Human Resources?

Los clientes deberán crear un nuevo proyecto de Microsoft Dynamics Lifecycle Service (LCS), y tendrán que seleccionar aplicaciones de finanzas y operaciones como producto e **Implementación** como tipo de proyecto. Además, un nuevo campo para el tipo de subproyecto está disponible cuando se crea un proyecto LCS. Los clientes tendrán que seleccionar la opción de migración de Dynamics 365 Human Resources para migrar un proyecto Human Resources LCS existente a la infraestructura de finanzas y operaciones.

Las características de los proyectos LCS de finanzas y operaciones difieren de las características de los proyectos de Human Resources LCS.

Para publicar, los nuevos clientes deberán completar las siguientes tareas:

- Completar la incorporación del proyecto.
- Completar la metodología.
- Rellenar un calculador de suscripción.
- Complete el proceso de preparación para la puesta en marcha.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>¿Cómo se migrará el Modelador de procesos empresariales?

Los clientes deberán exportar su biblioteca del Modelador de procesos empresariales del proyecto de Human Resources LCS e importarlo al proyecto LCS de finanzas y operaciones. Además, los clientes deberán actualizar la configuración de la Ayuda en la aplicación para que apunte al nuevo proyecto LCS.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>¿Cómo afectará la migración al proceso de actualización del servicio?

Después de la migración, los clientes tendrán mucha más flexibilidad para la administración del ciclo de vida de la aplicación (ALM) y actualizaciones de servicio. Las actualizaciones de servicio ya no se aplicarán automáticamente a los entornos de Human Resources. En su lugar, el servicio seguirá los procesos y la funcionalidad de actualización del servicio One Version, y se habilitarán opciones de configuración para actualizaciones a través de LCS.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>¿Los clientes serán elegibles para la asistencia FastTrack con la fusión de infraestructura?

Microsoft aún está definiendo qué herramientas y recursos estarán disponibles en FastTrack para ayudar con la fusión.

## <a name="licensing-impact"></a>Impacto de las licencias

Para obtener más información sobre cómo se verán afectadas las licencias, consulte [Fusión de infraestructuras de Dynamics 365 Human Resources](hr-infrastructure-merge.md#licensing).
