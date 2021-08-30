---
title: Comparación de las características en la nube y locales
description: En este tema se muestran qué características se admiten en la nube y en local.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 68082ad0ae264b76a852d8d12412af8c4ad917703441c41e67743d1b499a8d73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736231"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Comparación de características locales y en la nube

[!include [banner](../includes/banner.md)]

En este tema se muestra una comparación de las características disponibles en la nube frente a local para las siguientes aplicaciones:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

También se incluye información sobre las [características de desarrollo y administración](cloud-prem-comparison.md#development-and-administration-features).

Las tablas siguientes muestran las áreas de la aplicación. El soporte en la nube y local se muestra en la característica como un conjunto. Si las características específicas difieren de la totalidad del área, se indican en una línea aparte de la columna Característica.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Área**             | **Característica**                | **Nube** | **Local** |
|---------------------|-----------------------------|-----------|-----------------|
| Cumplimiento y certificaciones        |                                                                                           | Sí       | Sí             |
|                                      | Certificación SOC 1 de tipo 1                                                                | Sí       | No              |
| Administración de datos e integración      |                                                                                           | Sí       | Sí             |
|                                      | Exportar datos a su propio almacén de datos                                                    | Sí       | Sí             |
|                                      | Habilitar la exportación de actualizaciones incrementales a una entidad de datos                                 | Sí       | Sí             |
|                                      | Integraciones de datos                                                                         | Sí       | Sí             |
| Administración de documentos                  |                                                                                           | Sí       | Sí             |
| Administración financiera                 |                                                                                           | Sí       | Sí             |
| Ayuda                                 |                                                                                           | Sí       | N.º              |
| Recursos humanos                      |                                                                                           | Sí       | Sí             |
| Inteligencia                         |                                                                                           | Sí       | Sí             |
|                                      | Informes electrónicos (ER)                                                                 | Sí       | Sí             |
|                                      | ER: integración con LCS                                                                  | Sí       | No              |
|                                      | ER: integración con SharePoint                                                           | Sí       | No              |
|                                      | ER: Integración con Regulatory Configuration Services (RCS)                              | Sí       | No              |
|                                      | ER: permite usar el sistema de archivos local como almacenamiento de las configuraciones de ER accesibles mediante los repositorios de ER | N.º        | Sí             |
|                                      | Integración con PowerBI.com                                                              | Sí       | N.º              |
|                                      | Integración con PowerBI Desktop                                                          | N.º        | Sí             |
|                                      | Espacios de trabajo analíticos                                                                     | Sí       | N.º              |
|                                      | Proceso empresarial inteligente: recomendaciones                                             | Sí       | Nº              |
|                                      | Creación de informes de Power BI con OData mediante el escritorio de Power BI o herramientas de Excel PowerQuery    | Sí       | Nº              |
|                                      | SQL Server Reporting Services (SSRS) admite el escalado                                 | Sí       | Sí             |
|                                      | La telemetría se transfiere a la nube                                                   | Sí       | N.º              |
| Servicios de Lifecycle                   |                                                                                           | Sí       | Sí             |
|                                      | Procesos empresariales configurables                                                           | Sí       | No              |
| Localizaciones                        |                                                                                           | Sí       | Sí             |
| Aplicaciones móviles, espacios de trabajos y plataforma |                                                                                           | Sí       | Sí             |
| Integración con Office                   |                                                                                           | Sí       | Sí             |
| Administración de la organización          |                                                                                           | Sí       | Sí             |
| Nómina                              |                                                                                           | Sí       | Sí             |
|                                      | Depósito directo                                                                            | Sí       | No              |
| Gestión y contabilidad de proyectos    |                                                                                           | Sí       | Sí             |
| Seguridad                             |                                                                                           | Sí       | Sí             |
| Gestión de servicio                   |                                                                                           | Sí       | Sí             |
| Cliente web                           |                                                                                           | Sí       | Sí             |
|                                      | Grabador de tareas: guarde o cargue grabaciones de tareas desde la biblioteca de BPM                         | Sí       | N.º              |
| Soporte                              |                                                                                           | Sí       | Sí             |
|                                      | Acceso al soporte a través del menú de ayuda y servicio técnico                                             | Sí       | No              |
|                                      | Eventos de negocio                                                                           | Sí       | Sí (se requiere conectividad a Internet o se deben implementar puntos finales personalizados para enviar/recibir eventos de negocios dentro de la intranet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Área**                | **Característica**             | **Nube** | **Local** |
|-------------------------|-------------------|-----------|-----------------|
| Administración de activos                     |                                                                                           | Sí       | Sí             |
| Cumplimiento y certificaciones        |                                                                                           | Sí       | Sí             |
|                                      | Certificación SOC 1 de tipo 1                                                                | Sí       | Nº              |
| Contabilidad de costes                      |                                                                                           | Sí       | Sí             |
|                                      | Paquete de contenido de contabilidad de costes para Power BI                                                 | Sí       | Nº              |
|                                      | Área de trabajo de la contabilidad de costes para aplicaciones móviles                                                  | Sí       | Nº              |
| Gestión de costes                      |                                                                                           | Sí       | Sí             |
|                                      | Paquete de contenido gestión de costes para Power BI                                                 | Sí       | Nº              |
| Administración de datos e integración      |                                                                                           | Sí       | Sí             |
|                                      | Extensión diseñada según la configuración                                                            | Sí       | N.º              |
|                                      | Exportar datos a su propio almacén de datos                                                    | Sí       | Sí             |
|                                      | Habilitar la exportación de actualizaciones incrementales a una entidad de datos                                 | Sí       | Sí             |
|                                      | Integraciones de datos                                                                         | Sí       | Sí             |
| Administración de documentos                  |                                                                                           | Sí       | Sí             |
| Ayuda                                 |                                                                                           | Sí       | No              |
| Inteligencia                         |                                                                                           | Sí       | Sí             |
|                                      | Informes electrónicos (ER)                                                                 | Sí       | Sí             |
|                                      | ER: integración con LCS                                                                  | Sí       | No              |
|                                      | ER: integración con SharePoint                                                           | Sí       | No              |
|                                      | ER: Integración con Regulatory Configuration Services (RCS)                              | Sí       | No              |
|                                      | ER: permite usar el sistema de archivos local como almacenamiento de las configuraciones de ER accesibles mediante los repositorios de ER | N.º        | Sí             |
|                                      | Integración con PowerBI.com                                                              | Sí       | N.º              |
|                                      | Integración con PowerBI Desktop                                                          | N.º        | Sí             |
|                                      | Espacios de trabajo analíticos                                                                     | Sí       | N.º              |
|                                      | Proceso empresarial inteligente: recomendaciones                                             | Sí       | Nº              |
|                                      | Creación de informes de Power BI con OData mediante el escritorio de Power BI o herramientas de Excel PowerQuery    | Sí       | Nº              |
|                                      | SQL Server Reporting Services (SSRS) admite el escalado                                 | Sí       | Sí             |
|                                      | La telemetría se transfiere a la nube                                                   | Sí       | N.º              |
| Gestión de inventarios                 |                                                                                           | Sí       | Sí             |
| Servicios de Lifecycle                   |                                                                                           | Sí       | Sí             |
|                                      | Procesos empresariales configurables                                                           | Sí       | N.º              |
| Localizaciones                        |                                                                                           | Sí       | Sí             |
| Fabricación                        |                                                                                           | Sí       | Sí             |
| Previsión y planificación maestra      |                                                                                           | Sí       | Sí             |
| Optimización de planificación                |                                                                                           | Sí       | N.º              |
| Aplicaciones móviles, espacios de trabajos y plataforma |                                                                                           | Sí       | Sí             |
| Integración con Office                   |                                                                                           | Sí       | Sí             |
| Administración de la organización          |                                                                                           | Sí       | Sí             |
| Adquisición y abastecimiento             |                                                                                           | Sí       | Sí             |
|                                      | Catálogo externo en línea de la solicitud de compra                                   | Sí       | Nº              |
|                                      | Análisis de compras e informes de gastos Power BI                                                  | Sí       | Nº              |
| Gestión de información de productos       |                                                                                           | Sí       | Sí             |
| Datos del producto principal                  |                                                                                           | Sí       | Sí             |
| Producción                           |                                                                                           | Sí       | Sí             |
|                                      | Informes de rendimiento de producción de Power BI                                                   | Sí       | Nº              |
| Gestión de proyectos y contabilidad    |                                                                                           | Sí       | Sí             |
| Ventas                                |                                                                                           | Sí       | Sí             |
|                                      | Informes de rendimiento de ventas y rentabilidad de Power BI                                      | Sí       | Nº              |
| Seguridad                             |                                                                                           | Sí       | Sí             |
| Gestión de servicio                   |                                                                                           | Sí       | Sí             |
| Gestión de la cadena de suministro              |                                                                                           | Sí       | Sí             |
| Administración de transporte            |                                                                                           | Sí       | Sí             |
| Colaboración de proveedor                 |                                                                                           | Sí       | N.º              |
| Administración de almacenes                 |                                                                                           | Sí       | Sí             |
|                                      | Aplicación móvil del almacén                                                                      | Sí       | Sí             |
|                                      | Informes de almacén de Power BI                                                              | Sí       | Nº              |
| Cliente web                           |                                                                                           | Sí       | Sí             |
|                                      | Grabador de tareas: guarde o cargue grabaciones de tareas desde la biblioteca de BPM                         | Sí       | N.º              |
| Soporte                              |                                                                                           | Sí       | Sí             |
|                                      | Acceso al soporte a través del menú de ayuda y servicio técnico                                             | Sí       | No              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Para ver una lista de capacidades que estén disponibles en implementaciones locales, consulte [Capacidades de Commerce que están disponibles en implementaciones locales](../../../commerce/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Área**         | **Característica**         | **Nube** | **Local** |
|------------------|---------------------|-----------|-----------------|
| Todas las áreas de Recursos humanos | Todas las características de Recursos humanos | Sí       | No              |

## <a name="development-and-administration-features"></a>Características de desarrollo y administración

| **Área**                   | **Característica**                               | **Nube** | **Local** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Creación y prueba             |                                           | Sí       | Sí             |
| Extensibilidad              |                                           | Sí       | Sí             |
| Supervisión y telemetría   |                                           | Sí       | Sí             |
| Compatibilidad de la plataforma     |                                           | Sí       | Sí             |
| Servicio                  |                                           | Sí       | Sí             |
|                            | Entornos de servicio                    | Sí       | N.º              |
| Trace Parser               |                                           | Sí       | Sí             |
| PerfTimer                  |                                           | Sí       | Sí\*           |
| Actualizar                    |                                           | Sí       | Sí             |
|                            | Actualizar                                   | Sí       | N.º              |
|                            | Actualización y soporte para versiones anteriores | Sí       | N.º              |
| Desarrollo de Visual Studio  |                                           | Sí       | Sí             |

\* En entornos locales, PerfTimer solo muestra resultados para el cliente.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
