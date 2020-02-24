---
title: Elegir una tecnología de integración de datos
description: Este artículo proporciona orientación sobre varias opciones para integrarse con datos administrados por Recursos Humanos, describiendo las características de diferentes tecnologías de integración para que los integradores puedan tomar decisiones informadas sobre qué tecnologías se adaptan mejor a sus necesidades.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029897"
---
# <a name="choose-a-data-integration-technology"></a>Elegir una tecnología de integración de datos

Dynamics 365 Human Resources gestiona datos empresariales que son útiles en una variedad de procesos de negocio. Este artículo proporciona orientación sobre varias opciones para integrarse con datos administrados por Recursos Humanos, describiendo las características de diferentes tecnologías de integración para que los integradores puedan tomar decisiones informadas sobre qué tecnologías se adaptan mejor a sus necesidades.

## <a name="data-integration-vision"></a>Visión de integración de datos

Microsoft ve los datos comerciales como un activo clave que hace que su empresa sea única. Los datos de su negocio son muy valiosos. Los datos recopilados y mantenidos por una parte de la empresa se relacionan con los datos recopilados por otra parte de la empresa, y estas relaciones pueden utilizarse para mejorar los procesos empresariales y la inteligencia empresarial en toda su organización. Proporcionar un acceso fácil, seguro y estable a los datos de su empresa, independientemente de qué sistema "posea" los datos, es un principio clave de la visión que tenemos para la integración de datos con Recursos Humanos.

Históricamente, la integración de datos entre múltiples sistemas ha sido difícil.
Microsoft está tomando medidas para facilitar la integración de datos, y se logra un gran paso hacia ese objetivo a través de [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

En el futuro, Human Resources va a hacer que Common Data Service sea la interfaz pública preferida para los datos de recursos humanos. Con el tiempo, esperamos que todos los datos más importantes administrados por Human Resources se expongan en Common Data Service. Nosotros recomendamos Common Data Service como la tecnología elegida para la mayoría de las aplicaciones integradoras. Si bien nos damos cuenta de que no todos los datos que puede requerir su aplicación están actualmente presentes en Common Data Service, y que los plazos de su proyecto pueden requerir una tecnología alternativa, infórmenos cuándo Common Data Service no cumpla con sus necesidades de integración.

## <a name="integration-technologies"></a>Tecnologías de integración

Las siguientes secciones describen las diferentes tecnologías de integración de datos disponibles para su uso con Human Resources.

### <a name="common-data-service-entities"></a>Entidades de Common Data Service

Common Data Service es la interfaz de datos pública preferida para Human Resources. Common Data Service está construido sobre una plataforma madura, que ha surgido de la plataforma "XRM" de Dynamics 365, sobre la cual se crean las soluciones de [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement).

Common Data Service proporciona una plataforma para entidades de datos y una API para acceder a esas entidades. Cuando se implementa Human Resources en su organización, Human Resources se conecta a una instancia de Common Data Service y las entidades que mantienen los datos de Human Resources se implementan en esa instancia de Common Data Service, haciendo que las entidades y los datos estén disponibles para cualquier aplicación que pueda conectarse a la instancia de Common Data Service. Dependiendo de qué aplicaciones de Human Resources esté utilizando, Human Resources realiza operaciones de datos directamente en las entidades de Common Data Service (es el caso de Attract y Onboard) o sincroniza los datos a/desde las entidades de Common Data Service.

Una vez que las entidades de datos que exponen los datos que requieren sus aplicaciones integradoras estén presentes en Common Data Service, puede hacer uso completo de [Common Data Service y las API que admite](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Entre las API compatibles se encuentra la [API web de Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), que proporciona una implementación de OData para acceder a los datos de Common Data Service.

Las entidades de Common Data Service y las API asociadas son la mejor opción para acceder a los datos de Human Resources desde aplicaciones web, servicios web/API y desde cualquier otra aplicación que se conecte a fuentes de OData.

> [!NOTE]
> Como la decisión de convertir Common Data Service en la interfaz de datos preferida para Human Resources es relativamente reciente, es posible que las entidades de datos de Human Resources que necesita para su integración aún no estén disponibles en Common Data Service<sup>1</sup> Si las entidades de Human Resources requeridas para su integración aún no están disponibles, deberá esperar a que las entidades de datos estén disponibles o deberá utilizar una de las otras tecnologías de integración que se describen a continuación.
> 
> De forma predeterminada, la integración de Common Data Service se desactiva en los entornos nuevos que no incluyen los datos proporcionados de prueba. De forma predeterminada, está activado en los entornos nuevos que incluyen datos de demostración y la sincronización de datos en los entornos empieza cuando se aprovisionan. Después de que el entorno esté listo para sincronizar datos, puede activar la integración.

<sup>1</sup>Para obtener una lista de entidades de Human Resources disponibles en Common Data Service, vea [Human Resources y Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities). Para Attract y Onboard, todas las entidades están disponibles en Common Data Service.

### <a name="dmfdixf-entities"></a>Entidades DMF/DIXF

Human Resources, creado principalmente en la misma plataforma que las aplicaciones de Finance and Operations, proporciona un [marco de gestión de datos (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), a veces también conocido como Marco de importación y exportación de datos o DIXF y un conjunto de entidades de datos que se pueden usar para importar/exportar datos a/desde Human Resources. Mientras las entidades de Common Data Service sean la interfaz de integración de datos preferida para Human Resources, las entidades DMF seguirán siendo útiles en algunas circunstancias, como:

- Las entidades de Common Data Service aún no están disponibles.

- La integración requiere funcionalidad de importación/exportación masiva de datos de alto rendimiento.

Las entidades de DMF actualmente proporcionan la cobertura de datos más completa para los datos de Human Resources.

DMF no es apropiado para integraciones en tiempo real (como cuando se requieren comentarios inmediatos del usuario en una interfaz de usuario), porque las operaciones de paquetes son trabajos por lotes programados, y a menudo tendrán un mínimo de 1-2 minutos de latencia antes de que el servicio por lotes seleccione el trabajo para la ejecución, más el tiempo requerido para completar la operación de importación/exportación.

DMF puede ser la mejor opción cuando se requiere un alto rendimiento (como una importación/exportación programada por la noche de muchos miles de registros).

> [!NOTE]
> DMF no está disponible para Attract y Onboard.

### <a name="dmf-package-rest-api"></a>API REST de paquetes DMF

El DMF proporciona una [API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) para manipular paquetes de datos. Esta API se puede utilizar para interactuar mediante programación con el DMF, permitiendo acciones como:

- Importar un paquete de datos

- Exportar un paquete de datos

- Comprobar el estado de una operación de importación/exportación

La API REST de paquetes DMF es totalmente compatible con Human Resources: Core HR.

### <a name="azure-sql-db-byod"></a>Azure SQL DB (BYOD)

DMF también proporciona una característica potente (generalmente conocida como [Bring Your Own Database](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) o BYOD) que permite a Human Resources exportar datos a su propia instancia de Microsoft Azure SQL Database. Esto proporciona una gran flexibilidad, porque cuando los datos están presentes en su propia base de datos SQL, puede utilizar cualquier aplicación o middleware que pueda conectarse a un almacén de datos SQL.

BYOD generalmente debe considerarse una solución de solo lectura. Si bien puede manipular y almacenar los datos que desee en la base de datos SQL de Azure (como para mashups de datos), los datos almacenados en la base de datos SQL de Azure no se sincronizarán de nuevo con Human Resources.

BYOD es apropiado para soluciones de informes, integraciones de datos, mashups de datos, como origen de datos para una canalización de [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> BYOD no está disponible para Attract y Onboard.

### <a name="odata-enabled-entities"></a>Entidades habilitadas para OData

La mayoría de las entidades DMF también están habilitadas para acceder a través del servicio de datos de Human Resources (OData). La documentación proporcionada para el [servicio OData de Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) generalmente también se aplica a Human Resources, aunque no se aplicará la documentación sobre la creación de sus propias entidades expuestas a OData.

Aunque se prefieren Common Data Service y la implementación de OData proporcionada por Common Data Service (a través de la [API web de Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) frente al servicio de datos de Human Resources, el servicio de datos de Human Resources actualmente tiene una cobertura de entidad más completa para los datos de Human Resources.

### <a name="excel-add-in"></a>Complemento de Excel

El [complemento de Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) utiliza entidades habilitadas para OData bajo la superficie. Proporciona una manera conveniente para que un usuario final recupere y modifique datos de Recursos Humanos a través de la familiar IU de Excel.

El complemento de Excel es apropiado para la importación/exportación de datos ad-hoc por expertos en dominios comerciales. Para una integración de datos recurrente que requiere automatización programática, otra tecnología de integración será más apropiada.

### <a name="data-integrator"></a>Integrador de datos

La experiencia del administrador de Common Data Service proporciona un [servicio integrador de datos](https://docs.microsoft.com/powerapps/administrator/data-integrator) que puede usarse para integraciones de datos a/desde Common Data Service. El integrador de datos se puede utilizar para definir proyectos de integración (a menudo basados en plantillas predefinidas que los desarrolladores de aplicaciones han diseñado para integraciones específicas). Los proyectos de integración pueden programarse para ejecutarse automáticamente en un horario recurrente o ejecutarse manualmente.

Los proyectos de Data Integrator son apropiados para integraciones por lotes de Common Data Service y son una excelente opción para integraciones entre la familia de aplicaciones de Dynamics 365. Como ejemplo, Microsoft proporciona una plantilla de Integrador de datos lista para usar que se puede utilizar para integrar datos de Human Resources en Dynamics 365 Finance. Para obtener más información, consulte [Integración de Dynamics 365 Human Resources en Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

El integrador de datos también es compatible con [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) (a través de su [función de consulta avanzada](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)).
Power Query proporciona filtros y transformación de datos potentes y flexibles, incluido el rico lenguaje de fórmulas M, y probablemente sea familiar para aquellos que tienen experiencia en el desarrollo de informes de Power BI.

## <a name="deciding-on-an-integration-technology"></a>Decidir sobre una tecnología de integración

Con tantas tecnologías de integración diferentes disponibles, decidir qué enfoque de integración usar a veces puede ser abrumador. Con el tiempo, y particularmente a medida que la cobertura de datos en Common Data Service avance, la decisión será más fácil, ya que Common Data Service será la interfaz de datos preferida en la mayoría de los casos. Pero hasta entonces, puede encontrar que Common Data Service aún no satisface sus necesidades. La siguiente tabla ayuda a resumir algunas de las características clave de las diversas opciones de tecnología de integración.

| Tecnología/Herramienta/API    | Integraciones periódicas                   | Sincrónico/Asincrónico                    | Acceso programático a través de una API        | Volúmenes de datos apropiados                                   | Cobertura de datos                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Entidades de Common Data Service           | Sí, usando el integrador de datos o middleware | Sinc., Asinc., por lotes (a través del integrador de datos) | Sí, a través de la API web de Dynamics 365 (OData) | Varía según el caso de uso (admite paginación para uso interactivo) | Mejorando<sup>2</sup>                       |
| Entidades DMF           | Sí, programado a través de middleware        | Asinc., por lotes                                | Sí, a través de la API REST de paquetes DMF         | Alto (cientos de miles de registros)                    | Alta                                |
| API REST de paquetes DMF   | Sí, programado a través de middleware        | Asinc., por lotes                                | Sí                                       | Alto (cientos de miles de registros)                    | La API admite todas las entidades DMF       |
| BYOD                   | Sí, programado por el administrador en Human Resources        | Asinc., por lotes                                | No<sup>3</sup>                                    | Alto (cientos de miles de registros)                    | Admite todas las entidades DMF           |
| Entidades habilitadas para OData | Sí, usando middleware                    | Sincronizar                                        | Sí, a través del Servicio de datos de Human Resources (OData)  | Varía según el caso de uso (admite paginación para uso interactivo) | Alta                                |
| Complemento de Excel           | No                                       | Sincronizar                                        | No                                        | Mediano (decenas de miles de registros)                      | Admite todas las entidades habilitadas para OData |
| Integrador de datos        | Sí, programado en el integrador de datos        | Asinc., por lotes                                | No                                        | Varía según el caso de uso                                       | Admite todas las entidades de Common Data Service           |

<sup>2</sup>Microsoft está invirtiendo fuertemente en aumentar la cobertura de datos para las entidades de Common Data Service y recomienda Common Data Service como la interfaz de datos preferida cuando hay cobertura disponible. Actualmente, la cobertura de datos de Common Data Service es baja en relación con las entidades habilitadas para DMF y OData.

<sup>3</sup>Se puede acceder a la base de datos SQL mediante programación.

## <a name="summary"></a>Resumen

Los datos de su empresa son un activo valioso, pero su valor puede verse muy disminuido si resulta difícil utilizar los datos para sus propósitos específicos (como informes, mashups de datos o aplicaciones personalizadas). Dynamics 365 Human Resources proporciona varias tecnologías para trabajar con sus datos fuera de la interfaz de usuario (UI) de la aplicación de Recursos Humanos, lo que permite integrar el acceso de las aplicaciones a los datos. Este tema ha descrito las tecnologías de integración disponibles y algunas de sus características clave. Esta información debería ayudarlo a tomar mejores decisiones sobre qué enfoques aprovechar para sus proyectos de integración.

