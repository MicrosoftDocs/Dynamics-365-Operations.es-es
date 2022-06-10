---
title: Preguntas frecuentes de la fusión de infraestructura de Dynamics 365 Human Resources
description: Este tema responde a las preguntas más frecuentes sobre la combinación de infraestructura para aplicaciones Microsoft Dynamics 365 Human Resources y Finanzas y oepraciones.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 766ee49c17749841d8acac6637a0262e87e52e92
ms.sourcegitcommit: d38d2fe85dc2497211ba5731617f590029d07145
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809624"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Preguntas frecuentes de la fusión de infraestructura de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tema responde a las preguntas más frecuentes sobre la combinación de infraestructura para aplicaciones Microsoft Dynamics 365 Human Resources y Finanzas y oepraciones.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>¿Qué es la fusión de infraestructura de Dynamics 365 Human Resources?

Dynamics 365 Human Resources es una aplicación independiente que utiliza una infraestructura diferente a la de otras aplicaciones de Finanzas y Operaciones, como Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce y Dynamics 365 Project Operations. La fusión de infraestructura introduce Dynamics 365 Human Resources en la misma infraestructura que otras aplicaciones de Finanzas y operaciones.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>El valor y los beneficios de la infraestructura se fusionan

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>Mi organización usa Dynamics 365 Human Resources para gestionar sus operaciones de recursos humanos. ¿Qué beneficios veremos de estos cambios?

- Estos cambios eliminan la confusión causada por varios conjuntos de capacidades de recursos humanos (RR.HH.) en Dynamics 365.
- Proporcionan tanto extensibilidad de Microsoft Power Platform como una forma de ampliar la lógica empresarial y las opciones de funciones.
- Añaden consistencia entre Dynamics 365 Human Resources y otras aplicaciones de Finanzas y operaciones en términos de gestión del ciclo de vida de las aplicaciones (ALM), Microsoft Dynamics Lifecycle Services (LCS), disponibilidad geográfica, extensibilidad y más.
- Le permiten aprovechar las herramientas y los servicios compartidos y ayudan a reducir los costes.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>Mi organización usa el módulo de Recursos Humanos en Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. ¿Qué beneficios veremos de estos cambios?

Las capacidades e inversiones que se han realizado en Dynamics 365 Human Resources ahora estarán disponibles para los clientes que utilizan el módulo de RR.HH. en Dynamics 365 Finance. Algunas de estas capacidades incluyen la gestión de bajas y ausencias, la gestión de beneficios y la gestión de tareas.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>¿Perderé las funciones o capacidades que utilizo actualmente?

Habrá paridad funcional entre Dynamics 365 Human Resources y el módulo de RRHH en aplicaciones de Finanzas y operaciones. Dynamics 365 Human Resources tendrá prioridad para características similares. Para más información, consulte [Resumen de administración de funciones](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>¿Cambiará la experiencia de mis usuarios?

Las nuevas capacidades de recursos humanos se gestionarán a través de la gestión de funciones. Los clientes decidirán si quieren adquirirlos. En algunos casos, las capacidades pueden modificarse. En esos casos, se proporcionará documentación.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>¿Cómo me afecta este cambio si soy un cliente existente y utilizo ambos módulos de recursos humanos en la infraestructura de Finanzas y operaciones y Dynamics 365 Human Resources a través de integraciones personalizadas?

Las integraciones personalizadas entre Dynamics 365 Human Resources y el módulo de RR.HH. en Dynamics 365 Finance ya no serán necesarias. Todos los datos de recursos humanos residirán en la misma base de datos que otras aplicaciones de Finance and Operations.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Migración de Dynamics 365 Human Resources a las aplicaiones de Finanzas y operaciones

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Mi organización usa Dynamics 365 Human Resources para gestionar operaciones de recursos humanos. ¿Qué tenemos que planificar para migrar a la nueva experiencia?

Si su organización usa Dynamics 365 Human Resources pero no usa ningún otra aplicación , su entorno de aplicaciones de Finanzas y operaciones se migrará a la nueva infraestructura. Gran parte de este proceso de migración se automatizará. Se implementarán procesos para migrar su base de datos y sincronizarla con la nueva infraestructura.

Además, se implementarán herramientas para que pueda probar el proceso de migración y validar sus datos y experiencia antes de migrar su entorno de producción.

Si su organización usa tanto Dynamics 365 Human Resources como otras aplicaciones de Finanzas y operaciones, debe planificar más tiempo para la validación para asegurarse de que sus datos se migren correctamente al nuevo entorno. La migración a la nueva infraestructura fusionará los datos de su entorno de Recursos Humanos con su entorno Finance and Operations. La existencia de datos en conflicto requerirá la participación del usuario para determinar cómo se debe resolver el conflicto. Los usuarios y administradores deberán gestionar las asignaciones de datos donde haya conflictos y probar la migración en entornos de espacio aislado antes de migrar los entornos de producción.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Mi organización usa el módulo de Recursos Humanos en Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. ¿Qué tenemos que planificar para migrar a la nueva experiencia?

Para organizaciones que utilizan el módulo de recursos humanos en aplicaciones de Finanzas y operaciones, la nueva función de Dynamics 365 Human Resources se aplicará a su entorno a través del proceso de actualización estándar de una versión. Puede esperar ver la nueva funcionalidad en su entorno a medida que esté disponible en cada actualización. Puede utilizar la administración de prestaciones para activar nuevas funciones; sin embargo, debe planificar la validación de estas funciones. Siga los procesos que tiene implementados para validar otras actualizaciones de su entorno. Para obtener más información sobre cómo se aplican las actualizaciones a aplicaciones Finance and Operations, vea [Resumen de una versión](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>¿Cuándo se migrará mi organización?

La migración de cada organización dependerá de su configuración actual y su preparación para migrar a la nueva infraestructura. Estas fechas están sujetas a cambios.

- Organizaciones que actualmente utilizan el módulo de RRHH en las aplicaciones de Finanzas y operaciones recibirán la funcionalidad de recursos humanos para Dynamics 365 Human Resources como parte del proceso de actualización regular de One Version. Está previsto que las nuevas funciones estén disponibles de forma generalizada a partir de enero de 2022.
- Las organizaciones que solo usan Dynamics 365 Human Resources tendrán acceso a herramientas de migración para que puedan comenzar a realizar pruebas e iniciar la migración a partir de mediados de 2022. Aún no se ha determinado la fecha en la que debe completarse la migración a la nueva infraestructura. Sin embargo, será al menos un año después de la fecha en que las herramientas de migración estén disponibles.
- Organizaciones que actualmente usan tanto Dynamics 365 Human Resources como otras aplicaciones de Finanzas y operaciones tendrán acceso a las herramientas de migración para que puedan comenzar a realizar pruebas y comenzar la migración a finales de 2022. Aún no se ha determinado la fecha en la que debe completarse la migración a la nueva infraestructura. Sin embargo, será al menos un año después de la fecha en que las herramientas de migración estén disponibles.

Para obtener más información sobre las nuevas funciones de Dynamics 365 Human Resources, vea [Qué hay de nuevo o cambiado en Recursos Humanos](./hr-admin-whats-new.md).

### <a name="my-organization-has-not-yet-gone-live-on-dynamics-365-human-resources-should-we-go-live-with-the-human-resources-module-in-the-finance-and-operations-apps-or-with-the-dynamics-365-human-resources-app-on-the-legacy-infrastructure"></a>Mi organización aún no se ha puesto en funcionamiento en Dynamics 365 Human Resources. ¿Deberíamos poner en funcionamiento el módulo Human Resources en las aplicaciones de Finanzas y operaciones o la aplicación de Dynamics 365 Human Resources en la infraestructura heredada?

Hay que tener en cuenta elementos importantes como qué funcionalidad de recursos humanos se necesita y cuándo estará disponible esa funcionalidad en la nueva infraestructura. Si la organización necesita la funcionalidad básica para la gestión de personal, que está disponible actualmente en el módulo de recursos humanos de las aplicaciones de Finanzas y operaciones en la nueva infraestructura. Se espera que exista paridad de funciones entre el módulo de recursos humanos de las aplicaciones de Finanzas y operaciones y la aplicación Dynamics 365 Human Resources en la versión 10.0.25, cuya disponibilidad de forma generalizada está programada para marzo de 2022. Funciones de integración como la aplicación Teams y las integraciones de entidades Dataverse estarán disponibles en versiones posteriores.

Si las necesidades de funcionalidad de recursos humanos de la organización estarán disponibles en la nueva infraestructura dentro del período de tiempo en el que la organización entrará en funcionamiento, puede ser más fácil ponerlo en marcha en el módulo Human Resources en las aplicaciones de Finanzas y operaciones. De esta forma la migración será más fácil, ya que será una actualización de la aplicación estándar a la aplicación Dynamics 365 Human Resources y el cliente ya estará en la nueva infraestructura. Si la organización decide hacer la puesta en marcha en la aplicación Dynamics 365 Human Resources en la infraestructura heredada, será necesario migrar el entorno para pasar a la nueva infraestructura. Esto se puede evitar si la puesta en marcha se hace en la nueva infraestructura.

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Estoy usando nuevas capacidades que solo están disponibles en Dynamics 365 Human Resources (tal como **Baja y ausencia** y **Administración de beneficios**). ¿Estarán ahora disponibles estas capacidades en el módulo de Recursos Humanos en la infraestructura Finance and Operations?

Sí, todos los módulos de Dynamics 365 Human Resources funcionarán tal cual en aplicaciones de Finanzas y operaciones y habrá una paridad de funciones del 100 por ciento. Como parte de la estrategia de migración general para los clientes que actualmente usan estas capacidades en RR.HH., los datos de los clientes se migrarán para que continúen trabajando en la infraestructura Finance and Operations.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>Yo uso las nuevas capacidades de administración de beneficios de Dynamics 365 Human Resources. He creado integraciones personalizadas con el módulo de recursos humanos en la infraestructura Finance and Operations para poder aprovechar las capacidades de nómina mediante el uso de datos de beneficios. ¿Se requerirán estas integraciones personalizadas en el futuro?

Como parte de la fusión de la infraestructura, los datos de RR.HH. se incorporan a la misma base de datos que otras aplicaciones Finance and Operations. La integración entre módulos en aplicaciones Finance and Operations ya no será necesaria.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>Mi organización utiliza una o más soluciones ISV con Dynamics 365 Human Resources. ¿Nuestras soluciones ISV se migrarán automáticamente?

La experiencia de migración para cada solución de proveedor de software independiente (ISV) variará, según el método de integración de la solución. Microsoft trabajará en estrecha colaboración con los ISV para garantizar una transición sin problemas a la nueva infraestructura.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>Mi organización utiliza la integración de LinkedIn Talent Hub con Dynamics 365 Human Resources. ¿Continuará funcionando esta integración después de que se complete el cambio de infraestructura?

No, la integración de LinkedIn Talent Hub no funcionará tras la migración a la nueva infraestructura. El servicio para la integración de LinkedIn Talent Hub se retirará con la infraestructura de Dynamics 365 Human Resources heredada.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Mi organización usa la aplicación Recursos humanos para Teams. ¿Continuará funcionando esta aplicación después de que se complete el cambio de infraestructura?

Sí, la integración de la aplicación Human Resources para Teams seguirá funcionando después de la migración a la nueva infraestructura.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Mi organización ha configurado seguridad personalizada en Dynamics 365 Human Resources. ¿Seguirá aplicándose nuestra seguridad personalizada después de que se complete el cambio de infraestructura?

Sí, se incluirán configuraciones de seguridad personalizadas en la migración de datos a la nueva infraestructura.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Estamos utilizando el integrador de datos para mover datos entre Dynamics 365 Human Resources y aplicaciones de Finanzas y operaciones. ¿Cómo se verán afectados los datos que se están integrando actualmente?

Los datos de recursos humanos que están actualmente en Dynamics 365 Human Resources se sincronizan con Dataverse. El integrador de datos se puede utilizar para la sincronización unidireccional con aplicaciones Finance and Operations. Después de la migración a la nueva infraestructura, los datos de RR.HH. serán nativos de aplicaciones de Finanzas y operaciones. El integrador de datos ya no será necesario para sincronizar los datos entre aplicaciones Finance and Operations y recursos humanos.

Las tablas de datos nativas actuales de Dataverse para Recursos Humanos continuarán sincronizando los datos del entorno en la nueva infraestructura. Las entidades se convertirán para admitir escritura dual. Cualquier otra integración de datos que se configure a través del Integrador de datos en estas tablas para otras aplicaciones de Dynamics 365 continuarán funcionando como están configuradas actualmente.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>Estamos usando escritura dual para mover datos de recursos humanos entre Dataverse y otras aplicaciones de Finanzas y operaciones. ¿Cómo se verán afectados los datos que se están integrando actualmente por la migración a la nueva infraestructura?

Los datos de RRHH serán nativos en las aplicaciones Finance and Operations en el entorno de la nueva infraestructura. Se utilizará la doble escritura para mover los datos de recursos humanos entre el nuevo entorno y el entorno de Dataverse.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Hemos construido integraciones personalizadas a partir de Dynamics 365 Human Resources a uno o más sistemas externos. ¿Tendremos que desarrollar nuevas integraciones después de que el cambio de infraestructura se complete?

Depende del punto final de integración. Para obtener más información sobre las tecnologías de integración que están disponibles en aplicaciones Finance and Operations y cómo elegir la mejor tecnología de integración, consulte [Descripción general de la integración](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Hemos extendido Dataverse para Dynamics 365 Human Resources. ¿Se migrarán automáticamente estas extensiones?

Si los entornos de Dynamics 365 Human Resources y Finanzas y operaciones que se unirán en el entorno de la nueva infraestructura están conectados al mismo entorno de Dataverse, las dos aplicaciones seguirán conectadas al mismo entorno de Dataverse después de la migración. No será necesario realizar la migración para ninguna extensión de Dataverse.

Sin embargo, si los entornos de Dynamics 365 Human Resources y Finanzas y operaciones están actualmente conectados a entornos de Dataverse distintos, los dos entornos de Dataverse deberán combinarse para que estén conectados a un solo entorno de la nueva infraestructura. Para esta migración de Dataverse, las tablas Dataverse que son estándar para las soluciones de Recursos Humanos se pueden conectar y resincronizar con el nuevo entorno de Dataverse. Las extensiones del entorno de Dataverse no se migrarán automáticamente, sino que se deben volver a implementar en el nuevo entorno. Le recomendamos que utilice soluciones gestionadas para gestionar sus extensiones de Dataverse. Para más información, vea [Introducción a las soluciones](/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-utilized-the-custom-field-functionality-within-dynamics-365-human-resources-will-those-custom-fields-migrate-automatically"></a>Hemos utilizado la funcionalidad de campo personalizado en Dynamics 365 Human Resources, ¿esos campos personalizados se migrarán automáticamente?
Sí, los campos personalizados que se agregaron se migrarán a la nueva infraestructura.

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Hemos configurado flujos Microsoft Power Automate y / o Microsoft Power Apps para trabajar con Dynamics 365 Human Resources. ¿Se migrarán estos componentes Microsoft Power Platform y funcionarán automáticamente después de que se complete el cambio de infraestructura?

Los flujos Power Apps, Power Automate y otras personalizaciones Microsoft Power Platform son similares a extensiones Dataverse. Que funcionen automáticamente después de la migración a la nueva infraestructura depende de si la aplicación de Recursos Humanos y las aplicaciones Finanzas y operaciones están conectadas al mismo entorno de Power Apps antes de la migración.

Si las aplicaciones están actualmente conectadas al mismo entorno Power Apps, seguirán conectadas a ese entorno Power Apps después de la migración a la nueva infraestructura. En este caso, Power Apps, flujos Power Automate y otras personalizaciones de Microsoft Power Platform seguirán funcionando sin ninguna configuración adicional. Le recomendamos que utilice soluciones gestionadas para gestionar sus extensiones aplicación en el Dataverse. Para más información, vea [Introducción a las soluciones](/powerapps/developer/data-platform/introduction-solutions).

Sin embargo, si la aplicación de Recursos Humanos y las aplicaciones Finanzas y operaciones están conectadas a entornos de Power Apps distintos, deberán combinarse como parte de la migración. Esta tarea requerirá que cualquier Power Apps y otras personalizaciones se volverán a implementar en el nuevo entorno.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Hemos habilitado tablas virtuales de Dataverse para Dynamics 365 Human Resources. ¿Qué pasará con estas tablas durante la migración?

Después de la migración, si el entorno de la nueva infraestructura permanece conectado al entorno Dataverse que está actualmente conectado a Dynamics 365 Human Resources, las tablas virtuales Dataverse que se han generado en ese entorno seguirán funcionando sin ninguna configuración adicional.

Sin embargo, si el entorno de la nueva infraestructura está conectado a un entorno Dataverse diferente después de la migración, las tablas virtuales deberán regenerarse en el nuevo entorno de Dataverse.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Hemos desarrollado una integración utilizando la API del Sistema de seguimiento de candidatos (ATS), la API de nómina, tablas virtuales de Dataverse para Dynamics 365 Human Resources u otras entidades en la API web de Dataverse. ¿Continuarán funcionando estas integraciones después de que se complete el cambio de infraestructura?

Después de la migración, si el entorno de la nueva infraestructura permanece conectado al entorno Dataverse que está actualmente conectado a Dynamics 365 Human Resources, cualquier integración que se haya desarrollado contra la API web de Dataverse seguirá funcionando tras completar la migración.

Sin embargo, si el entorno de la nueva infraestructura está conectado a un entorno Dataverse distinto tras la migración, cualquier integración desarrollada contra la API web de Dataverse tendrá que reconfigurarse para que pueda conectarse al nuevo entorno Dataverse.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>¿Hay algún impacto en la región de Azure cuando se migra mi entorno?

Se espera que su entorno de recursos humanos permanezca normalmente en la misma región de Azure durante la migración. La única excepción es si el entorno de Recursos Humanos se fusionará con un entorno Finanzas y operaciones que se encuentra en una región diferente. En este caso, el entorno de Recursos Humanos se migrará a la región de Azure del entorno de Finance and Operations.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>Mi organización depende de los flujos de trabajo en Dynamics 365 Human Resources para uno o más procesos comerciales. ¿Se migrarán automáticamente estos flujos de trabajo?

Sí, se migrarán las configuraciones de flujo de trabajo, el historial de flujo de trabajo y los flujos de trabajo actuales en proceso.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>¿Qué capacitación y recursos estarán disponibles para ayudar con el proceso de migración?

Se proporcionará documentación completa para describir cada paso del proceso de migración en detalle. También pueden estar disponibles recursos de capacitación adicionales, como videos y talleres, según las necesidades.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>Mi organización ha creado vistas guardadas en Dynamics 365 Human Resources para mejorar la usabilidad de la interfaz. ¿Se migrarán automáticamente estas vistas guardadas?

Sí, las vistas guardadas se migrarán a la nueva infraestructura.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Estamos usando Ceridian con Dynamics 365 Human Resources. ¿La integración con Ceridian estará disponible tras completar el cambio de infraestructura? 

La integración con Ceridian se migrará a la integración basada en la API de nómina. La integración basada en archivos que existe actualmente en Dynamics 365 Human Resources no se migrará a la infraestructura de Finanzas y operaciones. Para más información, vea [Introducción a la API de nóminas](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>¿Cómo afectará la migración al proceso de actualización del servicio?

Después de la migración, los clientes tendrán mucha más flexibilidad en términos de ALM y actualizaciones de servicios. Las actualizaciones del servicio ya no se aplicarán automáticamente a los entornos de recursos humanos. En cambio, el servicio seguirá los procesos y la funcionalidad de actualización del servicio One Version. Por lo tanto, las opciones de configuración para las actualizaciones estarán disponibles a través de LCS. Para obtener más información, consulte [Vista general de One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>¿Cómo afectará la migración a mi proyecto LCS para Dynamics 365 Human Resources?

La migración a la nueva infraestructura moverá la gestión de sus entornos de Dynamics 365 Human Resources a un proyecto de implementación de Finanzas y operaciones en LCS. Si la migración fusiona Dynamics 365 Human Resources con un entorno existente de Finanzas y operaciones, su proyecto LCS de Recursos Humanos se fusionará con el proyecto de implementación de LCS para la aplicación de Finanzas y operaciones. Si actualmente usa solo Dynamics 365 Human Resources, se creará un nuevo proyecto de implementación de LCS y su proyecto de LCS de Recursos Humanos existente se migrará al nuevo proyecto.

El nuevo proyecto será el mismo tipo de proyecto que usan las aplicaciones Finance and Operations. Tendrá las mismas características y funcionalidad para la gestión del entorno. Para obtener más información, consulte [Recursos de Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Hemos vinculado nuestras grabaciones de tareas al Business Process Modeler en Recursos Humanos. ¿Cómo se migrará el Business Process Modeler y se fusionará con LCS?

Las bibliotecas de procesos comerciales para el proyecto LCS se migrarán al nuevo proyecto LCS para Recursos Humanos.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>Actualmente, mi organización solo usa Dynamics 365 Human Resources. ¿Qué recursos están disponibles para que podamos aprender más sobre las capacidades de desarrollo después de que se complete el cambio de infraestructura?

Tanto las opciones de extensibilidad de Microsoft Power Platform como de Finanzas y operaciones estarán disponibles y se pueden utilizar para el desarrollo. Para más información, vea [Desarrollar y personalizar la página de inicio](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Hemos habilitado funciones en Dynamics 365 Human Resources. ¿Se habilitarán estas funciones automáticamente durante la migración?

Si una función se habilita automáticamente en la nueva infraestructura se determinará individualmente para cada función. Esta información se incluirá en la documentación de funciones.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>¿Qué sucede con mi base de datos BYOD durante la migración?

Las configuraciones de importación y exportación para traer su propia base de datos (BYOD) se migrarán a la nueva infraestructura.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>¿Qué sucede con mi Azure Data Lake durante la migración?

Cualquier exportación que esté configurada actualmente para Azure Data Lake Storage en aplicaciones de Finanzas y operaciones mantendrá la misma configuración después de la migración.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Actualmente estamos usando Dynamics AX 2012. ¿Se utilizarán las herramientas de actualización que están disponibles actualmente para actualizar el módulo de recursos humanos en AX 2012 a Dynamics 365 Human Resources?

Sí. Dynamics 365 Human Resources se incluirá en la base de código fusionada y la infraestructura para aplicaciones de Finanzas y operaciones. Una actualización de Dynamics AX 2012 a Dynamics 365 Human Resources utilizará la misma ruta de actualización y las mismas herramientas que se utilizan para actualizar a la última versión de aplicaciones de Finanzas y operaciones.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Usamos el manejo de documentos con Dynamics 365 Human Resources. ¿Qué pasará con los documentos durante la migración?

Los documentos permanecerán en el almacenamiento de documentos existente. Se reasignarán al entorno en la nueva infraestructura.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>¿Qué sucede con los trabajos por lotes que hemos configurado en Dynamics 365 Human Resources después de la migración?

Los trabajos por lotes aplicables se migrarán automáticamente a la nueva infraestructura.

## <a name="licensing-impact"></a>Impacto de las licencias

Esta documentación no reemplaza ni reemplaza ninguna de la documentación legal que cubre los derechos de uso.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>Mi organización usa Dynamics 365 Human Resources para gestionar sus operaciones de recursos humanos. ¿Cambian nuestras licencias o nuestros costes?

Los clientes que han comprado licencias Dynamics 365 Human Resources no se verán afectados. No hay migración de licencias para estos clientes. La unidad de mantenimiento de existencias (SKU) de la zona de pruebas adicional que era específica para Recursos humanos ya no será aplicable. En cambio, los clientes pueden optar por comprar un espacio aislado de aplicaciones Finance and Operations de nivel 2 a un coste ligeramente menor. Los clientes existentes que hayan comprado un espacio aislado de recursos humanos se migrarán a un espacio aislado de aplicaciones Finance and Operations de nivel 2 sin coste adicional.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>Mi organización usa el módulo de Recursos Humanos en Dynamics 365 Finance, Supply Chain Management, Commerce, o Project Operations. ¿Cambian mis licencias o costes?

Usuarios existentes de aplicaciones de Dynamics 365 y usuarios independientes Dynamics 365 Finance, Supply Chain Management, Commerce y Project Operations pueden acceder a Recursos humanos como parte de esas licencias hasta febrero de 2025 o hasta que expire el acuerdo de licencia actual, lo que ocurra primero. Puede optar por pasar a las licencias de Recursos Humanos antes si esto le ayuda a lograr mejores ahorros de costes. A partir de febrero de 2025, todos los clientes existentes de CSP y EA deben abandonar el módulo de recursos humanos y comprar licencias de recursos humanos para aprovechar las nuevas capacidades que se están incorporando a las aplicaciones Finance and Operations.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>Mi organización está en directo con Dynamics 365 Finance, Supply Chain Management, Commerce o Project Operations. ¿Se nos pedirá que compremos un entorno adicional para respaldar la fusión de la infraestructura?

No se requieren entornos adicionales para respaldar el cambio de infraestructura.

