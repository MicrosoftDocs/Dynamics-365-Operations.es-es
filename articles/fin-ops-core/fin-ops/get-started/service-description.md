---
title: Descripción del servicio para aplicaciones de Finance and Operations
description: Este tema proporciona la descripción del servicio para aplicaciones de Finance and Operations.
author: tomhig
ms.date: 09/29/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: a1547f0cc6c6f705cd0e2ff6e5be751cb97b946a
ms.sourcegitcommit: 79d19924ed736c9210fa9ae4e0d4c41c53c27eb5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "7581825"
---
# <a name="service-description-for-finance-and-operations-apps"></a>Descripción del servicio para aplicaciones de Finance and Operations

[!include[banner](../includes/banner.md)]

Las aplicaciones de Finance and Operations son ofertas de software como servicio (SaaS) de planificación de recursos empresariales (ERP) que se basan en y para [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/). El servicio Finance and Operations brinda a las organizaciones la funcionalidad ERP que respalda sus requisitos únicos y les ayuda a adaptarse a entornos comerciales en constante cambio, sin necesidad de que administren la infraestructura. Las aplicaciones Finance and Operations pueden incluir una o más de las siguientes áreas de solución:

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Junto con [Inteligencia de negocio](/power-bi/fundamentals/power-bi-service-overview), [infraestructura](https://azure.microsoft.com/global-infrastructure/), [proceso](/azure/service-fabric/service-fabric-overview) y [servicios de base de datos](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/), estas aplicaciones permiten a las organizaciones ejecutar procesos comerciales operativos y específicos de la industria. Con el apoyo de su socio de implementación, los clientes determinan la configuración de la lógica de la aplicación empresarial que mejor se adapta a sus procesos empresariales únicos. La funcionalidad y los procesos comerciales se pueden aumentar o ampliar a través de una o una combinación de las siguientes soluciones:

- [Experiencia de personalización](personalize-user-experience.md) integrada
- Herramientas de [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)
- [Kit de desarrollo de software (SDK) de Finance and Operations](../../dev-itpro/dev-tools/developer-home-page.md) basado en [Visual Studio](https://visualstudio.microsoft.com) y [automatización de compilación de Azure DevOps](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- Soluciones de proveedores de software independientes (ISV) de [AppSource](https://appsource.microsoft.com/partners)

Según los requisitos, los clientes eligen su enfoque de solución. Trabajan con su socio de implementación para definir, desarrollar y probar su solución utilizando las herramientas y las mejores prácticas que se proporcionan en [Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md). Hay cuatro escenarios comunes:

- Configuración de aplicaciones "lista para usar" estándar de Finance and Operations (sin extensiones)
- Configuración de aplicaciones de Finance and Operations que incluye una o más soluciones ISV
- Configuración de aplicaciones de Finance and Operations que incluye una o más extensiones específicas del cliente
- Configuración de aplicaciones de Finance and Operations que incluye una combinación de extensiones específicas del cliente y una o más soluciones ISV

Las organizaciones pueden igualar el crecimiento de su negocio agregando fácilmente usuarios y procesos comerciales a través de un modelo de suscripción simple y transparente. Para obtener más información, consulte la [Guía de licencias de Dynamics 365](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365).

## <a name="operating-model"></a>Modelo de operación

El modelo operativo de las apps de Finance and Operations define roles y responsabilidades específicos para el cliente, el socio de implementación y Microsoft a lo largo del ciclo de vida del servicio. Para más información, vea [Operaciones y servicios en la nube](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Actividades de cliente

Los clientes trabajan con su socio y [Microsoft FastTrack](/dynamics365/fasttrack/) siguiendo el marco de [Success by Design](/dynamics365/fasttrack/success-by-design-overview) y usando herramientas y plantillas de mejores prácticas proporcionadas en [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) para implementar su solución. Las actividades comunes incluyen:

- Gestión de seguridad e identidad de usuario
- Definir, desarrollar y operar procesos comerciales
- Definir, desarrollar, probar y operar extensiones
- Supervisar y administrar implementaciones que no sean de producción
- Gestionar actualizaciones de aplicaciones y validar extensiones
- Administrar soluciones de ISV e integraciones de terceros

### <a name="microsoft-responsibilities"></a>Responsabilidades de Microsoft

Microsoft gestiona el servicio Finance and Operations mediante la implementación, la supervisión activa y el servicio de entornos de producción y sandbox del cliente en la suscripción de Microsoft SaaS. Esta gestión incluye la asignación de la infraestructura del sistema necesaria para ejecutar el servicio y comunicarse de forma proactiva con los clientes sobre el estado del servicio. Incluye responsabilidades:

**Gestión de infraestructura**
- Seguridad y aislamiento
- Sistemas operativos y virtualización
- Servidores, almacenamiento y redes
- Energía, redes, refrigeración del centro de datos

**Administración de la plataforma de aplicaciones**
- Monitoreo y notificaciones de aplicaciones 24/7
- Diagnósticos, actualizaciones de plataforma, parches, actualizaciones de servicios
- Enrutamiento de aplicaciones, equilibrio de carga, replicación de sitios
- Aprovisionamiento y gestión del medio ambiente
- Gestión de bases de datos, alta disponibilidad (HA) / recuperación ante desastres (DR), escala, operaciones
- Computa la implementación, escala hacia arriba, escala hacia abajo

## <a name="system-configuration"></a>Configuración del sistema

Las aplicaciones de Finance and Operations escalan según el volumen de transacciones y la carga de usuarios. Cada implementación de cliente produce una solución única que consta de los siguientes elementos:

- **Composición de datos** - Un conjunto único de parámetros que controlan el comportamiento, el diseño de la organización, la estructura de los datos maestros (como las dimensiones financieras y de inventario) y la granularidad del seguimiento de transacciones.
- **Ampliación y configuración** - Mecanismos de extensión que utilizan extensiones de código, soluciones ISV y configuraciones únicas que incluyen flujos de trabajo, integraciones y configuraciones de informes.
- **Patrones de uso** - Una combinación única de uso en línea y por lotes, junto con la capacidad de integrarse con sistemas ascendentes y descendentes para un flujo de datos unificado y la capacidad de diferenciar según las vistas de información que los clientes utilizan en sus procesos comerciales.

Microsoft configura entornos de producción de clientes que están dimensionados para manejar los volúmenes de transacciones y la concurrencia de usuarios. Microsoft es responsable de las siguientes tareas:

- Asignar correctamente los recursos de los entornos de producción, en función de la información de perfil del cliente en el [Estimador de suscripción LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- Monitorear y diagnosticar continuamente la disponibilidad del servicio de los entornos de producción
- Analizar y solucionar problemas de rendimiento del sistema con aplicaciones de Finance and Operations

Para asegurarse de que una implementación esté configurada para un alto rendimiento, los clientes deben completar estas tareas:

- Proporcionar información de uso precisa sobre la implementación de Finance and Operations en el [Estimador de suscripción LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Cree y pruebe extensiones para el rendimiento y la escala.
- Pruebe adecuadamente las configuraciones de datos para determinar el rendimiento.
- Asegure la escalabilidad haciendo [pruebas de rendimiento](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) antes de la puesta en marcha.

## <a name="onboarding-and-implementation"></a>Incorporación e implementación

La siguiente tabla muestra los eventos típicos de incorporación e implementación.

| Solicitud | Acción esperada de Microsoft | Acción esperada del cliente / socio de implementación |
|---|---|---|
| Compra de oferta inicial | Un proyecto LCS se crea después de la compra de la oferta, en base a un evento que desencadena el cliente. | Pasar por el acuerdo empresarial (EA) o el [proceso comercial](before-you-buy.md) del proveedor de soluciones en la nube (CSP). El socio crea un inquilino para el cliente, si corresponde. |
| Compra adicional | Otorgue al cliente acceso al complemento seleccionado durante la implementación. | No aplicable |
| Planificación y análisis de la implementación | Proporcionar herramientas relevantes en LCS, como el [Modelador de procesos de negocio (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md) e [interoperabilidad con Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md). | Haga la planificación del proyecto, configure Azure DevOps, integración completa del sistema y configuración de cuentas de administrador. |

Para más información, vea [Incorporación de un proyecto de implementación](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalización

Las aplicaciones de Finance and Operations se sirven desde varias regiones de Azure en todo el mundo. Las aplicaciones de Finance and Operations brindan funcionalidad para admitir diferentes países / regiones e idiomas nativos. Para más información, vea [Características normativas y de localización](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Consdieraciones específicas del país o región

- Los clientes de la industria regulada u organizaciones comerciales que hacen negocios con entidades en Francia que requieren la residencia de datos local deben revisar [Finance and Operations en Francia](../../dev-itpro/deployment/france-local-deployment.md).
- Los clientes que tienen operaciones en China deben revisar [Finance and Operations operado por 21Vianet en China](../../dev-itpro/deployment/china-local-deployment.md).
- Los clientes que tienen operaciones en Rusia deben revisar la [Ley rusa de localización de datos personales](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia).

### <a name="general-data-protection-regulation-gdpr"></a>Reglamento general de protección de datos (RGPD)

Para las aplicaciones de Finance and Operations, Microsoft actúa como procesador. Como procesador de datos, Finance and Operations proporciona procesos y funciones que ayudan a los clientes a cumplir con las obligaciones de GDPR como controlador de datos. Para obtener más información, consulte [Visión general del RGPD](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Entorno y administración de datos

Esta sección describe algunos eventos típicos de administración de datos y entorno que ocurren en el servicio.

### <a name="environment-and-data-management-events-for-production-instances"></a>Eventos de gestión de datos y entorno para instancias de producción

LCS proporciona [herramientas de autoservicio](../../dev-itpro/deployment/infrastructure-stack.md) y [operaciones de movimiento de base de datos](../../dev-itpro/database/dbmovement-operations.md) que se utilizan para realizar tareas de gestión de datos y entorno. A continuación, encontrará algunos ejemplos:

**Evento:** [Solicitando una instancia de producción](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- Completar la [Lista de verificación de puesta en marcha](../imp-lifecycle/prepare-go-live.md) y envíela al equipo de [Microsoft FastTrack](/dynamics365/fasttrack/).
- Completar el [Estimador de suscripción LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md) antes de solicitar una instancia de producción.
- Completar todas las tareas de implementación que se especifican en la [Metodología LCS](../../dev-itpro/lifecycle-services/create-methodology.md).

**Evento:** [Copiar una base de datos de espacio aislado en una instancia de producción](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Realizado para una puesta en marcha simulada o una transición de puesta en marcha real.

**Evento:** [Modo de mantenimiento](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Active el modo de mantenimiento en LCS.
2. Complete el mantenimiento requerido.
3. Desactive el modo de mantenimiento en LCS.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Eventos de gestión de datos y entorno para instancias de no producción

LCS proporciona [aprovisionamiento de autoservicio](../../dev-itpro/deployment/infrastructure-stack.md) y [operaciones de movimiento de base de datos](../../dev-itpro/database/dbmovement-operations.md) que se utilizan para realizar tareas de gestión de datos y entorno. A continuación, encontrará algunos ejemplos:

**Evento:** [Implementar una nueva instancia de espacio aislado](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Asegúrese de que todas las instancias requeridas hayan sido [planificadas](../imp-lifecycle/environment-planning.md) y que se han comprado las ofertas complementarias correspondientes.
- Ejecute el proceso de implementación en LCS.
- Completar todas las tareas de implementación que se especifican en las listas de comprobación de LCS.
    
>[!NOTE]
>Un entorno de pruebas de desarrollo es una máquina virtual (VM) que se [implementa en la suscripción de Azure del cliente](../../dev-itpro/dev-tools/access-instances.md) y gestionado por el cliente.

**Evento:** [Copiar una base de datos de configuración Oro del espacio aislado a producción](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Realizado para una puesta en marcha simulada o una transición de puesta en marcha real.

**Evento:** [Restaurar una copia de seguridad de un punto en el tiempo de producción en una instancia que no es de producción](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Ejecute la opción [Actualizar base de datos](../../dev-itpro/database/database-refresh.md) en LCS.
- Copia posterior: elimine u oculte datos confidenciales mediante scripts, ajuste las configuraciones de aplicaciones específicas del entorno (como puntos finales de integración) y habilite o agregue usuarios. Tenga en cuenta que estos cambios se realizan aplicando un [paquete de datos](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package).

**Evento:** [Restauración puntual de la base de datos de instancias que no son de producción](../../dev-itpro/database/database-point-in-time-restore.md)

- Acepte que el proceso no se puede deshacer.
- Ejecute la operación de restauración a un momento dado en LCS.

**Evento:** Copiar una base de datos de zona de pruebas de nivel 2 a una zona de pruebas de desarrollo para solucionar problemas y [depuración](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Ejecute la operación de exportación de la base de datos en LCS en el entorno de zona de pruebas de nivel 2.
- Importe y actualice la base de datos en el entorno de desarrollo.

## <a name="data-backup-and-retention"></a>Copia de seguridad y retención de datos

Bases de datos para los entornos de Finance and Operations de la suscripción SaaS están protegidos por copias de seguridad automáticas. Para los entornos de producción, las copias de seguridad automáticas se retienen durante 28 días, a menos que Microsoft realice una reversión. Para los entornos sandbox (Tier 2+), se conservan durante siete días. Se puede realizar una reversión del entorno de producción si se produce una falla durante cualquier actualización de mantenimiento planificada.

Para obtener más información sobre las copias de seguridad automáticas, consulte [Copias de seguridad automatizadas: Azure SQL Database & SQL Managed Instance](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Responsabilidades de actividad de servicio

La siguiente tabla describe algunos escenarios y actividades típicos para el servicio. También indica si Microsoft, el cliente o tanto Microsoft como el cliente son responsables de las actividades.

| Actividad | Responsabilidad de Microsoft | Responsabilidad del cliente |
|---|---|---|
| **Aprovisionamiento de inquilinos iniciales** | | |
| Mida la carga proyectada en LCS utilizando la herramienta de estimación de suscripción y solicite que se aprovisionen entornos específicos. | | X |
| Aprovisione todas las instancias de producción y las instancias de no producción. | X | |
| Valide las instancias de producción implementadas y las instancias de no producción. | | X |
| **Actualizaciones de servicio** | |
| Aplica actualizaciones de servicio a instancias designadas de producción y no producción. | X | |
| Aplique manualmente actualizaciones de servicio de LCS a instancias de espacio aislado. Defina, desarrolle, pruebe la actualización y proporcione el paquete de actualización de código a LCS. | | X |
| Solicite y programe que las actualizaciones de la extensión se apliquen a la instancia de producción. | | X |
| Cree una copia de seguridad de código y datos para la instancia de producción antes de que se apliquen las actualizaciones. | X | |
| En caso de que se produzca algún error, retrotraiga la instancia de producción al código y la copia de seguridad de los datos. | X | |
| **Gestión de datos (copia de seguridad, restauración y actualización)** | | |
| Realice una copia de seguridad de la base de datos. | X | |
| Determine la alta disponibilidad y un plan de recuperación ante desastres. | X | |
| Supervisar el rendimiento de la base de datos de la instancia de producción. | X | |
| Regule el rendimiento de la base de datos de la instancia de producción. | X | |
| Realice una actualización puntual de la base de datos de la instancia de producción en una instancia que no sea de producción. | | X |
| **Actualizar la infraestructura** | | |
| Programe actualizaciones periódicas de la infraestructura. | X | |
| **Escalar hacia arriba y hacia abajo (usuarios, almacenamiento e instancias)** | | |
| Adquiera usuarios adicionales y complementos que no sean de producción. | | X |
| Actualice los cambios de uso en la herramienta de estimación de suscripción LCS. | | X |
| Informe cualquier problema de rendimiento significativo que afecte el uso del servicio. | | X |
| Gestione de forma proactiva los recursos necesarios para el servicio correspondiente. | X | |
| Investigar y solucionar incidentes. | X | |
| **Seguridad (acceso de usuarios)** | | |
| Proporcionar acceso de usuario al servicio. | | X |
| Proporcione acceso al proyecto LCS para la administración y operación de instancias que se implementaron a través de LCS. | | X |
| **Monitoreo de instancias de producción** | | |
| Monitoreo de instancias de producción 24/7. | X | |
| Notifique de forma proactiva al cliente sobre las incidencias que involucren a la instancia de producción. | X | |
| **Administrar y monitorear instancias que no son de producción** | | |
| Administre instancias que no sean de producción mediante LCS. | | X |
| Monitoreo de instancias de no producción. | | X |

## <a name="service-update-strategy"></a>Estrategia de actualización del servicio

De acuerdo con la [política del ciclo de vida del software](../../dev-itpro/migration-upgrade/versions-update-policy.md), las aplicaciones de Finance and Operations siguen la [Política de ciclo de vida moderna](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) de Microsoft, que cubre los productos que reciben servicio y soporte de forma continua. 

Microsoft lanza ocho actualizaciones de servicio para aplicaciones de Finance and Operations cada año en los siguientes meses:

- Enero
- Febrero
- Abril
- May
- Julio
- Agosto
- Octubre
- Noviembre

>[!NOTE]
>Abril y octubre son las principales olas de lanzamiento de funciones. Los clientes pueden pausar una actualización de servicio individual por hasta tres ciclos de actualización consecutivos.

Para obtener más información, revise los siguientes temas:

- [Información general de las actualizaciones del servicio de One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Configurar actualizaciones de servicio a través de LCS](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Pausar actualizaciones de servicio a través de LCS](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Recibir notificaciones acerca de las actualizaciones de servicio a través de LCS](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Herramientas de prueba de regresión para validar las actualizaciones del servicio](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Hoja de ruta de Dynamics 365 y oleadas de versiones](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Seguridad y acceso administrativo

El acceso administrativo a un entorno de producción de Finance and Operations está estrictamente controlado y registrado. Los datos del cliente se tratan de acuerdo con los [Términos de los servicios en línea de Microsoft](https://www.microsoft.com/licensing/terms/productoffering). 

### <a name="customer-administrative-access"></a>Acceso administrativo del cliente

El administrador de inquilinos del cliente puede acceder a instancias de producción o instancias de no producción, como se describe en la siguiente tabla:

| Tipo de entorno | Propósito | Nivel de acceso del cliente |
|---|---|---|
| **No producción**<br>Espacio aislado de nivel 1 | Un entorno de no producción que los clientes implementan con fines de desarrollo, demostración o capacitación. | Un espacio aislado de nivel 1 (también denominado entorno alojado en la nube) es una máquina virtual administrada por el cliente que se implementa en la suscripción de Azure del cliente desde LCS. Debido a que es una máquina virtual en la suscripción de Azure del cliente, el cliente tiene acceso administrativo completo al entorno a través de Escritorio remoto. |
| **No producción**<br>Sandbox de nivel 2 (o superior) | Un entorno de no producción que los clientes implementan para pruebas de aceptación de usuarios, pruebas de integración, capacitación, puesta en escena o cualquier otro escenario de preproducción. | Los entornos sandbox de nivel 2 y superiores se implementan en la suscripción SaaS de Finance and Operations. El acceso a las bases de datos de Azure SQL que están asociadas con el entorno de no producción se otorga a través del [acceso justo a tiempo](../../dev-itpro/database/database-just-in-time-jit-access.md). El acceso a Escritorio remoto no está disponible. |
| **Producción** | Un entorno de producción se implementa cuando el proyecto está [listo para la puesta en marcha inicial](/imp-lifecycle/environment-planning.md#production-system-readiness). | Los entornos de producción se implementan en la suscripción SaaS. Todo el acceso se realiza a través del navegador, los puntos finales de servicio o LCS. |

### <a name="microsoft-administrative-access"></a>Acceso administrativo de Microsoft

La siguiente tabla muestra los diferentes niveles de acceso para diferentes administradores de Microsoft:

| Administrador | Datos del cliente |
|---|---|
| Equipo de respuestas de operaciones<br>(Limitado solo al personal clave) | El acceso se otorga mediante un ticket de soporte. El acceso está auditado y limitado a la duración de la actividad de soporte. |
| Servicios de soporte al cliente de Microsoft (CSS) | Sin acceso directo. El cliente puede usar la pantalla compartida para trabajar con el personal de soporte para depurar problemas. |
| Ingeniería | Sin acceso directo. El equipo de respuesta de operaciones puede utilizar la pantalla compartida para trabajar con ingenieros para depurar problemas. |
| Otros en Microsoft | No hay acceso. |

## <a name="monitoring"></a>Supervisión

Microsoft ha invertido en un extenso conjunto de herramientas para monitorear y diagnosticar las instancias de producción de los clientes. Microsoft supervisa los entornos de producción de los clientes las 24 horas del día, los 7 días de la semana. Para más información, vea [Soporte y seguimiento a la producción](../imp-lifecycle/production-support-monitoring.md).

| Responsabilidades de Microsoft | Responsabilidades del cliente |
|---|---|
| <ul><li>Monitorear la disponibilidad del servicio.</li><li>Supervise y alerte continuamente a través de métricas de salud y controles de componentes críticos como Application Object Server (AOS), Batch, Data Import / Export Framework (DIXF), Commerce y Management Reporter.</li><li>Supervise la degradación del rendimiento causada por los servicios de infraestructura (como Azure Active Directory \[Azure AD\] y Azure SQL).</li><li>Si Microsoft determina que un solo proceso o trabajo por lotes está causando aberraciones, ese proceso o trabajo se terminará después de la comunicación con el cliente.</li></ul> | <ul><li>Supervise los cambios en las configuraciones y extensiones de la aplicación que pueden causar problemas funcionales y de rendimiento.</li><li>Los errores de aplicación deben diagnosticarse utilizando las herramientas de supervisión. Utilice estas herramientas para diagnosticar las aberraciones de rendimiento informadas por los usuarios.</li><li>Informe a Microsoft si hay una carga esperada en el sistema más allá del uso máximo proyectado.</li><li>Si el servicio aplicable no está disponible en la instancia de producción, el cliente puede usar LCS para informar una [interrupción de la producción](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

Al enviar solicitudes de soporte en línea, a través de LCS, los clientes permiten que Microsoft brinde experiencia técnica rápida y profunda de la manera más efectiva y eficiente. Aunque hay una opción de teléfono disponible, solo debe usarse si la opción en línea no está disponible. Para obtener más información, consulte [Opciones de soporte de teléfono](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Administración de incidentes

Microsoft responde y corrige los incidentes según los niveles de gravedad. Los niveles de gravedad de los incidentes de Microsoft se pueden cambiar durante la evaluación inicial del incidente y a medida que se disponga de más información sobre el impacto y el alcance. Si el incidente se mitiga, la gravedad del incidente permanece sin cambios.

Para obtener más información sobre los niveles de gravedad, consulte [esta tabla de gravedad](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Continuidad empresarial mediante alta disponibilidad y recuperación ante desastres 

Microsoft proporciona continuidad empresarial y recuperación ante desastres para instancias de producción de aplicaciones de Finance and Operations en caso de interrupciones en toda la región de Azure. Para más información, vea [Continuidad empresarial y recuperación ante desastres](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Alta disponibilidad** - La funcionalidad HA proporciona formas de evitar el tiempo de inactividad causado por la falla de un solo nodo en un centro de datos de Azure. La arquitectura en la nube de cada servicio usa conjuntos de disponibilidad de Azure para el nivel de proceso a fin de evitar eventos de punto único de falla. HA para bases de datos se proporciona a través de [Características de Azure SQL HA](/azure/azure-sql/database/high-availability-sla).
- **Recuperación de desastres** - Las [Características de recuperación ante desastres de Azure](/azure/best-practices-availability-paired-regions) protegen cada servicio contra interrupciones que afecten ampliamente a todo un centro de datos de Azure. Estas son algunas de estas características:

    - Replicación geo-activa de Azure SQL para la base de datos principal (base de datos empresarial).
    - Copias con redundancia geográfica de Azure Blob Storage (que contiene documentos adjuntos) en otras regiones de Azure.
    - Región secundaria para las replicaciones de Azure SQL y Azure Blob Storage.

Los almacenes de datos primarios son compatibles con la replicación. Por lo tanto, los componentes de cada servicio, como Management Reporter y el almacén de entidades, utilizan datos transformados de la base de datos principal. Estos datos deben generarse después de que se haya configurado el sitio de recuperación y se haya iniciado el servicio. Los artefactos de código del cliente y los almacenes de datos recuperados se utilizan para volver a implementar el sitio. La redistribución permite la replicación del estado de los nodos informáticos, junto con la red y otros componentes, para utilizar los almacenes de datos recuperados para configurar el sitio secundario. Si se utiliza la recuperación ante desastres para recuperar la instancia de producción del cliente, Microsoft y el cliente cumplirán con sus responsabilidades de [administracion de incidentes](service-description.md#incident-management).

Los planes y procedimientos de recuperación ante desastres de Microsoft se examinan periódicamente a través de auditorías de controles de sistemas y organizaciones (SOC). Estas auditorías de cumplimiento dan fe del proceso técnico y de procedimiento de la DR de Microsoft, que incluye aplicaciones de Dynamics 365 Finance and Operations. Los informes de auditoría de [cumplimiento de SOC](/compliance/regulatory/offering-soc-2) y todos los demás informes de cumplimiento están disponibles en [Ofertas de cumplimiento de Microsoft Trust Center](/compliance/regulatory/offering-home).

| Responsabilidades de Microsoft | Responsabilidades del cliente |
|---|---|
| Microsoft aprovisiona un entorno secundario en el centro de datos emparejado de Azure cuando se implementa la instancia de producción principal. Para obtener más información, consulte [Continuidad empresarial y recuperación ante desastres (BCDR): regiones emparejadas de Azure](/azure/best-practices-availability-paired-regions). | None |
| Microsoft habilita la redundancia geográfica de Azure SQL y Azure Blob Storage cuando se implementa la instancia de producción principal. | None |
| Microsoft habilita la copia de seguridad automática en las bases de datos de Azure SQL. | None |
| <p>Cuando ocurre una interrupción, Microsoft determina si se debe realizar una conmutación por error para el cliente y si habrá pérdida de datos. La pérdida de datos puede durar hasta cinco segundos. Para más información, vea [Restauración geográfica de Azure SQL Database](https://azure.microsoft.com/blog/azure-sql-database-geo-restore).</p><p>En caso de pérdida de datos, Microsoft solicitará la aprobación del cliente para una conmutación por error.</p> | En caso de pérdida de datos, es posible que el cliente deba proporcionar una autorización por escrito para activar la conmutación por error. |
| Cuando se produce una conmutación por error, el servicio aplicable funciona en modo limitado. El mantenimiento de la actualización no se puede activar en el modo de conmutación por error. | El cliente no puede solicitar implementaciones de paquetes u otras solicitudes de mantenimiento regulares en modo de conmutación por error. |
| Cuando el centro de datos se vuelve operativo, Microsoft vuelve a la instancia de producción en la región principal de Azure. Se reanudan las operaciones normales. | Es posible que el cliente tenga que cerrar sesión en la conmutación por recuperación a la instancia de producción en la región principal de Azure. |

## <a name="finance-and-operations-support-offerings"></a>Ofertas de soporte de Finance and Operations

El soporte técnico está disponible en los mercados donde se ofrecen servicios de Finance and Operations. Las [experiencias de soporte](../../dev-itpro/lifecycle-services/lcs-support.md) se proporcionan en LCS o en las aplicaciones de Finance and Operations. A continuación, encontrará algunos ejemplos:

- [Búsqueda de temas](../../dev-itpro/lifecycle-services/issue-search-lcs.md) en LCS
- [Soporte técnico integrado](../../dev-itpro/lifecycle-services/support-experience.md) en aplicaciones de Finance and Operations
- [Compatibilidad impulsada por la nube](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) en LCS

Microsoft ofrece a los clientes de Finance and Operations tres planes de soporte: Premier, Professional Direct y el soporte que se incluye en la suscripción. El nivel de soporte varía según el plan. La siguiente tabla muestra una comparación de los tres planes.

| Característica de soporte | Premier | Professional directo | Suscripción |
|---|---|---|---|
| Envío ilimitado de incidentes de rotura/reparación | Sí | Sí | Sí |
| Acceso 24/7 a través de LCS | Sí | Sí | Sí |
| Tiempo de respuesta ante incidentes | Menos de una hora | Menos de una hora | Siguiente día de negocios |
| Horas de asesoramiento | Las piscinas se adquieren por contrato. | N.º | N.º |
| Gerente de cuenta de soporte dedicado | Sí | N.º | N.º |
| Ingeniero de soporte dedicado | Comprometido bajo un acuerdo separado | N.º | N.º |

Para obtener más información, consulte [Resumen de soporte](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Proceso para involucrar el apoyo

En caso de incidencias que involucren aplicaciones de Finance and Operations, los clientes envían tickets de soporte a Microsoft a través de LCS. CSS maneja los incidentes, según el plan de soporte del cliente y la gravedad del incidente según lo designado por CSS.

### <a name="service-level-agreement"></a>Acuerdo de nivel de servicio

Microsoft está comprometido con una tasa de disponibilidad del 99,9 por ciento por mes del servicio. Si Microsoft no logra y no mantiene el nivel de servicio para el servicio aplicable como se describe en el acuerdo de nivel de servicio (SLA), el cliente puede ser elegible para un crédito para una parte de sus tarifas de servicio mensuales para ese servicio. Para obtener información sobre cómo iniciar un crédito de servicio, consulte la sección "Reclamaciones" del [SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

## <a name="important-resources"></a>Recursos importantes

- **[Centro de confianza](https://www.microsoft.com/trust-center)** - Obtenga información sobre dónde se almacenan los datos de Finance and Operations, además de información adicional sobre procedimientos de privacidad, cumplimiento y seguridad.
- **[Términos de licencia y documentación](https://www.microsoftvolumelicensing.com/)** - Acceda rápidamente a los términos, condiciones e información complementaria de la licencia que sea relevante para el uso de productos y servicios con licencia a través de los programas de licencias por volumen de Microsoft.
- **[Términos de licencia](https://www.microsoft.com/licensing/product-licensing/)** - Los recursos de esta página definen los términos y condiciones del software y los productos de servicios en línea que compra a través de los programas de licencias comerciales de Microsoft.
- **[Política de ciclo de vida de Microsoft](/lifecycle/)** - Esta página proporciona pautas coherentes y predecibles para la disponibilidad de soporte durante la vida útil de un producto.
- **[Guía de licencias](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** - Utilice esta guía para obtener más información sobre cómo obtener una licencia de Dynamics 365.
- **[Atención al cliente](https://dynamics.microsoft.com/support/)** - Obtenga soporte líder en la industria para sus aplicaciones de Dynamics 365.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** - Administre el ciclo de vida de su aplicación y avance hacia implementaciones predecibles, repetibles y de alta calidad.

## <a name="definitions"></a>Definiciones

### <a name="azure-region"></a>[Región de Azure](/azure/availability-zones/az-overview#regions)

Una región geográfica donde existen uno o más centros de datos de Azure. Los ejemplos incluyen EE. UU. Y Europa.

### <a name="business-process-modeler-bpm"></a>[Modelador de procesos empresariales (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

Una herramienta en LCS que ayuda a completar un análisis de brechas de ajuste para una implementación determinada mediante el uso de definiciones de procesos comerciales de American Productivity & Quality Center (APQC) que son compatibles con aplicaciones de Finance and Operations.

### <a name="cloud-solution-provider"></a>Proveedor de soluciones en la nube

Un socio que forma parte del programa Microsoft Cloud Solution Provider (CSP) y que brinda a los clientes servicios en la nube de valor agregado, soporte, una sola factura y administración de clientes a escala.

### <a name="customer"></a>Cliente 

Una entidad empresarial que consume aplicaciones de Finance and Operations y está representado por un inquilino en Office 365.

### <a name="development-environment"></a>Entorno de desarrollo

Un entorno de pruebas de no producción que se utiliza para desarrollar extensiones. Los clientes implementan este entorno en su propia suscripción de Azure desde LCS. Este entorno también se puede utilizar para demostraciones, formación u otras tareas de prueba. También se conoce como [espacio aislado de nivel 1](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher).

### <a name="downtime"></a>Tiempo de inactividad

Cualquier período en el que los usuarios no pueden iniciar sesión o acceder a su inquilino activo debido a una falla en la plataforma no vencida o en la infraestructura del servicio, según lo determine Microsoft a partir del monitoreo de salud automatizado y los registros del sistema. El tiempo de inactividad no incluye el tiempo de inactividad programado, la falta de disponibilidad de funciones complementarias del servicio, la imposibilidad de acceder al servicio debido a sus modificaciones al servicio o los períodos en los que se excede la capacidad de la unidad de báscula.

### <a name="implementation-partner"></a>Partner de implementación

El socio que el cliente selecciona para personalizar, configurar, implementar y administrar sus soluciones de Finance and Operations.

### <a name="incident"></a>Incidente

Un problema que los clientes encuentran mientras usan el servicio de Finance and Operations, y que envían un ticket a través de LCS.

### <a name="microsoft-customer-support-services-css"></a>Servicios de soporte al cliente de Microsoft (CSS)

El equipo de soporte global de Microsoft que se dedica a brindar un servicio de calidad para aplicaciones de Finance and Operations.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

El portal administrativo para la gestión del ciclo de vida de las aplicaciones de Finance and Operations desde la prueba hasta la implementación, la gestión y el soporte de posproducción. Para obtener más información, consulte [Recursos de Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Instancia de no producción

Cualquiera de las siguientes instancias de un servicio que el cliente utiliza para validar extensiones y realizar otras tareas de desarrollo:

- **Nivel 1 de espacio aislado** - Instancia de desarrollador (alojada por el cliente)
- **Nivel 2 de espacio aislado** - Instancia de prueba de aceptación estándar
- **Niveles 3 a 5 de espacio aislado** - Espacios aislados adicionales

Para obtener más información sobre los niveles 2 a 5, consulte [Seleccionar el entorno correcto de Nivel 2 o superior](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Instancia de producción

Un entorno de Finance and Operations que el cliente utiliza para gestionar sus transacciones y procesos comerciales diarios "en vivo".

### <a name="sandbox-environment"></a>Entorno de espacio aislado

Un entorno de no producción que el cliente utiliza para demostraciones, capacitación, pruebas de aceptación del usuario, validación de extensiones y otras tareas de prueba.

### <a name="service"></a>Servicio

Cualquiera de los servicios básicos que se incluyen en las aplicaciones de Finance and Operations.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Acuerdo de nivel de servicio (SLA) para servicios en línea de Microsoft

El SLA se aplica a los servicios en línea de Microsoft. Para obtener más información, vea [Acuerdos de nivel de servicio](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Actualización del servicio

Microsoft presta servicio a los entornos de Finance and Operations de forma coherente a través de actualizaciones de servicio. Los clientes establecen su propio calendario de actualización de servicios, en función de sus necesidades comerciales. Para obtener más información, consulte [Actualizaciones del servicio de una versión](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="user"></a>Usuario

Una sola persona que usa entornos de Finance and Operations y quién está asociado con el inquilino de un cliente.
