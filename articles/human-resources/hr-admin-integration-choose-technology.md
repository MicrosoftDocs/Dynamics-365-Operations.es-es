---
title: Elegir una tecnología de integración de datos
description: Este artículo proporciona información sobre la integración con datos administrados por Human Resources. Describe diferentes tecnologías de integración para ayudarlo a decidir qué tecnologías se adaptan mejor a sus necesidades.
author: andreabichsel
manager: tfehr
ms.date: 02/28/2020
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
ms.openlocfilehash: ee394172fb531e7aecc1be411f9adf2dd184d15e
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114196"
---
# <a name="choose-a-data-integration-technology"></a>Elegir una tecnología de integración de datos

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo proporciona información para la integración con datos administrados por Dynamics 365 Human Resources. Describe diferentes tecnologías de integración para ayudarlo a decidir qué tecnologías se adaptan mejor a sus necesidades.

## <a name="data-integration-background"></a>Trasfondo de integración de datos

Los datos comerciales son un activo clave que hace que su empresa sea única. Los datos de su negocio son muy valiosos. Puede utilizar las relaciones entre los datos recopilados en toda su empresa para mejorar los procesos empresariales y la inteligencia empresarial en toda su organización. Nos esforzamos por proporcionar un acceso fácil, seguro y estable a los datos de su empresa, independientemente del sistema del que provengan.

Históricamente, la integración de datos entre múltiples sistemas ha sido difícil.
Microsoft está tomando medidas para facilitar la integración de datos, y se logra un gran paso hacia ese objetivo a través de [Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Human Resources va a hacer que Dataverse sea la interfaz pública preferida para los datos de Human Resources. Con el tiempo, esperamos que todos los datos más importantes administrados por Human Resources se expongan en Dataverse. Nosotros recomendamos Dataverse como la tecnología elegida para la mayoría de las aplicaciones integradoras.

Nos damos cuenta que es posible que Dataverse aún no contenga todos los datos que requiere su aplicación. También nos damos cuenta de que el cronograma de su proyecto puede requerir una tecnología alternativa. Asegúrese de informarnos cuándo Dataverse no cumple con sus necesidades de integración.

## <a name="integration-technologies"></a>Tecnologías de integración

Las siguientes secciones describen las diferentes tecnologías de integración de datos disponibles para su uso con Human Resources.

### <a name="dataverse-tables"></a>Tablas de Dataverse

Dataverse es la interfaz de datos pública preferida para Human Resources. Surgió de la plataforma Dynamics 365 XRM, que es utilizada por soluciones [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement).

Dataverse proporciona una plataforma y API para tablas de datos. Cuando implementa Human Resources, se conecta a una instancia de Dataverse. Las entidades para los datos de Human Resources se implementan en esa instancia de Dataverse. Las tablas y sus datos están disponibles para cualquier aplicación que pueda conectarse a la instancia de Dataverse. Human Resources sincroniza datos hacia y desde las tablas de Dataverse.

> [!NOTE]
> Las entidades de Human Resources se corresponden con tablas de Dataverse. Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Cuando las tablas de datos requeridas por las aplicaciones integradoras están en Dataverse, puede usar completamente [Dataverse y las API compatibles](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Entre las API compatibles se encuentra la [API web de Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), que proporciona una implementación de OData para acceder a los datos de Dataverse.

Las tablas de Dataverse y sus API asociadas son la mejor opción para acceder a los datos de Human Resources desde aplicaciones web, servicios web/API y desde cualquier otra aplicación que se conecte a fuentes de OData.

> [!NOTE]
> Como la decisión de convertir Dataverse en la interfaz de datos preferida para Human Resources es relativamente reciente, es posible que las entidades de datos de Human Resources que necesita para su integración aún no estén disponibles en Dataverse.
> </br>
> Para obtener una lista de entidades de Human Resources disponibles en Dataverse, vea [Human Resources y Dataverse](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Si las entidades de Human Resources requeridas para su integración aún no están disponibles, deberá esperar a que las entidades de datos estén disponibles o deberá utilizar una de las otras tecnologías de integración que se describen a continuación.
> </br>
> De forma predeterminada, la integración de Dataverse se desactiva en los entornos nuevos que no incluyen los datos proporcionados de prueba. De forma predeterminada, está activado en los entornos nuevos que incluyen datos de demostración y la sincronización de datos en los entornos empieza cuando se aprovisionan. Después de que el entorno esté listo para sincronizar datos, puede activar la integración.

### <a name="dmfdixf-entities"></a>Entidades DMF/DIXF

Human Resources, construido principalmente en la misma plataforma que las aplicaciones Finance and Operations, proporciona un [Marco de gestión de datos (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json). DMF también se conoce como el Marco de importación y exportación de datos (DIXF). Human Resources proporciona un conjunto de entidades de datos que puede usar para importar y exportar datos de Human Resources. Aunque las tablas de Dataverse son la interfaz de integración de datos preferida para Human Resources, las entidades de DMF siguen siendo útiles en algunas circunstancias, como:

- Cuando las tablas de Dataverse aún no están disponibles.

- La integración requiere funcionalidad de importación/exportación masiva de datos de alto rendimiento.

> [!NOTE]
> Las entidades de Human Resources se corresponden con tablas de Dataverse. Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Actualmente las entidades de DMF proporcionan la cobertura de datos más completa para los datos de Human Resources.

DMF no es apropiado para integraciones en tiempo real, como cuando necesita comentarios inmediatos del usuario en una interfaz de usuario. Las operaciones de paquete son trabajos por lotes programados y, a menudo, tienen una latencia mínima de 1-2 minutos antes de que el servicio por lotes recoja el trabajo para su ejecución, más el tiempo que sea necesario para completar la operación de importación / exportación.

DMF puede ser la mejor opción cuando se requiere un alto rendimiento (como una importación/exportación programada por la noche de muchos miles de registros).

> [!NOTE]
> DMF no está disponible para Attract y Onboard.

### <a name="dmf-package-rest-api"></a>API REST de paquetes DMF

El DMF proporciona una [API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) para manipular paquetes de datos. Esta API se puede utilizar para interactuar mediante programación con el DMF, permitiendo acciones como:

- Importar un paquete de datos

- Exportar un paquete de datos

- Comprobar el estado de una operación de importación/exportación

Human Resources ofrece toda la API REST de paquetes de DMF.

### <a name="azure-sql-db-byod"></a>Azure SQL DB (BYOD)

DMF también proporciona una característica potente (conocida como [Bring Your Own Database](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) o BYOD) que permite a Human Resources exportar datos a su propia instancia de Microsoft Azure SQL Database. Esta capacidad proporciona una tremenda flexibilidad. Cuando los datos están presentes en su propia base de datos SQL, puede utilizar cualquier aplicación o middleware que pueda conectarse a un almacén de datos SQL.

BYOD es principalmente una solución de solo lectura. Si bien puede manipular y almacenar los datos que desee en la base de datos SQL de Azure (como para mashups de datos), los datos almacenados en la base de datos SQL de Azure no se sincronizarán de nuevo con Human Resources.

BYOD es apropiado para soluciones de informes, integraciones de datos, mashups de datos, como origen de datos para una canalización de [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> BYOD no está disponible para Attract y Onboard.

### <a name="odata-enabled-entities"></a>Entidades habilitadas para OData

La mayoría de las entidades DMF también están habilitadas para acceder a través del servicio de datos de Human Resources (OData). La documentación proporcionada para el [Servicio OData de Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) se aplica a Human Resources, excepto para crear sus propias entidades expuestas a OData.

Aunque se prefieren Dataverse y la implementación de OData proporcionada por Dataverse (a través de la [API web de Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) frente al servicio de datos de Human Resources, el servicio de datos de Human Resources actualmente tiene una cobertura de entidad más completa para los datos de Human Resources.

### <a name="excel-add-in"></a>Complemento de Excel

El [complemento de Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) utiliza entidades habilitadas para OData bajo la superficie. Proporciona una manera conveniente para que un usuario final recupere y modifique datos de Recursos Humanos a través de la familiar IU de Excel.

El complemento de Excel es apropiado para la importación/exportación de datos ad-hoc por expertos en dominios comerciales. Para una integración de datos recurrente que requiere automatización programática, otra tecnología de integración será más apropiada.

### <a name="data-integrator"></a>Integrador de datos

Puedes usar el [Servicio integrador de datos](https://docs.microsoft.com/powerapps/administrator/data-integrator) para integrar datos hacia y desde Dataverse. El integrador de datos le permite definir proyectos de integración, a menudo basados en plantillas predefinidas que los desarrolladores de aplicaciones han diseñado para integraciones específicas. Los proyectos de integración pueden programarse para ejecutarse automáticamente en un horario recurrente o ejecutarse manualmente.

Los proyectos de Data Integrator son apropiados para integraciones por lotes de Dataverse. Son una excelente opción para integraciones entre la familia de aplicaciones Dynamics 365. Por ejemplo, Microsoft proporciona una plantilla de Integrador de datos que se puede utilizar para integrar datos de Human Resources en Dynamics 365 Finance. Puede obtener más información sobre la plantilla en [Integración desde Dynamics 365 Human Resources a Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

El integrador de datos es compatible con [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) a través de su [Función de consulta avanzada](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). Power Query proporciona filtros y transformación de datos potentes y flexibles, incluido el rico lenguaje de fórmulas M. Power Query probablemente le sea familiar si ha desarrollado informes Power BI.

## <a name="deciding-on-an-integration-technology"></a>Decidir sobre una tecnología de integración

Con tantas tecnologías de integración diferentes disponibles, decidir qué enfoque de integración usar a veces puede ser abrumador. A medida que la cobertura de datos en Dataverse avance, la decisión será más fácil, ya que Dataverse será la interfaz de datos preferida en la mayoría de los casos. Pero hasta entonces, puede encontrar que Dataverse aún no satisface sus necesidades. La siguiente tabla resume algunas de las características clave de las diversas opciones de tecnología de integración.

| Tecnología/Herramienta/API    | Integraciones periódicas                   | Sincrónico/Asincrónico                    | Acceso programático a través de una API        | Volúmenes de datos apropiados                                   | Cobertura de datos                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Tablas de Dataverse           | Sí, usando el integrador de datos o middleware | Sinc., Asinc., por lotes (a través del integrador de datos) | Sí, a través de la API web de Dynamics 365 (OData) | Varía según el caso de uso (admite paginación para uso interactivo) | Mejorando<sup>2</sup>                       |
| Entidades DMF           | Sí, programado a través de middleware        | Asinc., por lotes                                | Sí, a través de la API REST de paquetes DMF         | Alto (cientos de miles de registros)                    | Alta                                |
| API REST de paquetes DMF   | Sí, programado a través de middleware        | Asinc., por lotes                                | Sí                                       | Alto (cientos de miles de registros)                    | La API admite todas las entidades DMF       |
| BYOD                   | Sí, programado por el administrador en Human Resources        | Asinc., por lotes                                | No<sup>3</sup>                                    | Alto (cientos de miles de registros)                    | Admite todas las entidades DMF           |
| Entidades habilitadas para OData | Sí, usando middleware                    | Sincronizar                                        | Sí, a través del Servicio de datos de Human Resources (OData)  | Varía según el caso de uso (admite paginación para uso interactivo) | Alta                                |
| Complemento de Excel           | No                                       | Sincronizar                                        | No                                        | Mediano (decenas de miles de registros)                      | Admite todas las entidades habilitadas para OData |
| Integrador de datos        | Sí, programado en el integrador de datos        | Asinc., por lotes                                | N.º                                        | Varía según el caso de uso                                       | Admite todas las tablas de Dataverse           |

<sup>2</sup>Microsoft está realizando un gran esfuerzo por aumentar la cobertura de datos para tablas de Dataverse. Recomendamos usar Dataverse cuando hay cobertura disponible. Actualmente, la cobertura de datos de Dataverse es baja en comparación con las entidades habilitadas para DMF y OData.

<sup>3</sup>Se puede acceder a la base de datos SQL mediante programación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]