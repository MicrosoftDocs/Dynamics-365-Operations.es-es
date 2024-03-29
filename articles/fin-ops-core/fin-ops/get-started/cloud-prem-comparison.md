---
title: Comparación de características locales y en la nube
description: En este artículo se muestran qué características se admiten en la nube y en local.
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
ms.openlocfilehash: e3b200186096a49f800d5b650ac81a45fe5e9e30
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644151"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Comparación de características locales y en la nube

[!include [banner](../includes/banner.md)]

En este artículo se muestra una comparación de las características disponibles en la nube frente a local para las siguientes aplicaciones:

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
| Ayuda                                 |                                                                                           | Sí       | No              |
| Recursos humanos                      |                                                                                           | Sí       | Sí             |
| Inteligencia                         |                                                                                           | Sí       | Sí             |
|                                      | Informes electrónicos (ER)                                                                 | Sí       | Sí             |
|                                      | ER: integración con LCS                                                                  | Sí       | No              |
|                                      | ER: integración con SharePoint                                                           | Sí       | No              |
|                                      | ER: Integración con Regulatory Configuration Services (RCS)                              | Sí       | No              |
|                                      | ER: permite usar el sistema de archivos local como almacenamiento de las configuraciones de ER accesibles mediante los repositorios de ER | No        | Sí             |
|                                      | Integración con PowerBI.com                                                              | Sí       | No              |
|                                      | Integración con PowerBI Desktop                                                          | No        | Sí             |
|                                      | Espacios de trabajo analíticos                                                                     | Sí       | No              |
|                                      | Proceso empresarial inteligente: recomendaciones                                             | Sí       | No              |
|                                      | Creación de informes de Power BI con OData mediante el escritorio de Power BI o herramientas de Excel PowerQuery    | Sí       | No              |
|                                      | SQL Server Reporting Services (SSRS) admite el escalado                                 | Sí       | Sí             |
|                                      | La telemetría se transfiere a la nube                                                   | Sí       | No              |
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
|                                      | Grabador de tareas: guarde o cargue grabaciones de tareas desde la biblioteca de BPM                         | Sí       | No              |
| Soporte                              |                                                                                           | Sí       | Sí             |
|                                      | Acceso al soporte a través del menú de ayuda y servicio técnico                                             | Sí       | No              |
|                                      | Eventos de negocio                                                                           | Sí       | Sí (se requiere conectividad a Internet o se deben implementar puntos finales personalizados para enviar/recibir eventos de negocios dentro de la intranet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Área**                | **Característica**             | **Nube** | **Local** |
|-------------------------|-------------------|-----------|-----------------|
| Administración de activos                     |                                                                                           | Sí       | Sí             |
| Cumplimiento y certificaciones        |                                                                                           | Sí       | Sí             |
|                                      | Certificación SOC 1 de tipo 1                                                                | Sí       | No              |
| Contabilidad de costes                      |                                                                                           | Sí       | Sí             |
|                                      | Paquete de contenido de contabilidad de costes para Power BI                                                 | Sí       | No              |
|                                      | Área de trabajo de la contabilidad de costes para aplicaciones móviles                                                  | Sí       | No              |
| Gestión de costes                      |                                                                                           | Sí       | Sí             |
|                                      | Paquete de contenido gestión de costes para Power BI                                                 | Sí       | No              |
| Administración de datos e integración      |                                                                                           | Sí       | Sí             |
|                                      | Extensión diseñada según la configuración                                                            | Sí       | No              |
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
|                                      | ER: permite usar el sistema de archivos local como almacenamiento de las configuraciones de ER accesibles mediante los repositorios de ER | No        | Sí             |
|                                      | Integración con PowerBI.com                                                              | Sí       | No              |
|                                      | Integración con PowerBI Desktop                                                          | No        | Sí             |
|                                      | Espacios de trabajo analíticos                                                                     | Sí       | No              |
|                                      | Proceso empresarial inteligente: recomendaciones                                             | Sí       | No              |
|                                      | Creación de informes de Power BI con OData mediante el escritorio de Power BI o herramientas de Excel PowerQuery    | Sí       | No              |
|                                      | SQL Server Reporting Services (SSRS) admite el escalado                                 | Sí       | Sí             |
|                                      | La telemetría se transfiere a la nube                                                   | Sí       | No              |
| Gestión de inventarios                 |                                                                                           | Sí       | Sí             |
| Servicios de Lifecycle                   |                                                                                           | Sí       | Sí             |
|                                      | Procesos empresariales configurables                                                           | Sí       | No              |
| Localizaciones                        |                                                                                           | Sí       | Sí             |
| Fabricación                        |                                                                                           | Sí       | Sí             |
| Previsión y planificación maestra      |                                                                                           | Sí       | Sí             |
|                                      | Optimización de planificación                                                                     | Sí       | N.º              |
|                                      | Previsión de demanda                                                                        | Sí       | N.º              |
| Aplicaciones móviles, espacios de trabajos y plataforma |                                                                                           | Sí       | Sí             |
| Integración con Office                   |                                                                                           | Sí       | Sí             |
| Administración de la organización          |                                                                                           | Sí       | Sí             |
| Adquisición y abastecimiento             |                                                                                           | Sí       | Sí             |
|                                      | Catálogo externo en línea de la solicitud de compra                                   | Sí       | No              |
|                                      | Análisis de compras e informes de gastos Power BI                                                  | Sí       | No              |
| Gestión de información de productos       |                                                                                           | Sí       | Sí             |
| Datos del producto principal                  |                                                                                           | Sí       | Sí             |
| Producción                           |                                                                                           | Sí       | Sí             |
|                                      | Informes de rendimiento de producción de Power BI                                                   | Sí       | No              |
| Gestión de proyectos y contabilidad    |                                                                                           | Sí       | Sí             |
| Ventas                                |                                                                                           | Sí       | Sí             |
|                                      | Informes de rendimiento de ventas y rentabilidad de Power BI                                      | Sí       | No              |
| Seguridad                             |                                                                                           | Sí       | Sí             |
| Gestión de servicio                   |                                                                                           | Sí       | Sí             |
| Gestión de la cadena de suministro              |                                                                                           | Sí       | Sí             |
| Administración de transporte            |                                                                                           | Sí       | Sí             |
| Colaboración de proveedor                 |                                                                                           | Sí       | No              |
| Administración de almacenes                 |                                                                                           | Sí       | Sí             |
|                                      | Aplicación móvil del almacén                                                                      | Sí       | Sí             |
|                                      | Informes de almacén de Power BI                                                              | Sí       | No              |
| Cliente web                           |                                                                                           | Sí       | Sí             |
|                                      | Grabador de tareas: guarde o cargue grabaciones de tareas desde la biblioteca de BPM                         | Sí       | No              |
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
|                            | Entornos de servicio                    | Sí       | No              |
| Trace Parser               |                                           | Sí       | Sí             |
| PerfTimer                  |                                           | Sí       | Sí\*           |
| Actualizar                    |                                           | Sí       | Sí             |
|                            | Actualizar                                   | Sí       | No              |
|                            | Actualización y soporte para versiones anteriores | Sí       | No              |
| Desarrollo de Visual Studio  |                                           | Sí       | Sí             |

\* En entornos locales, PerfTimer solo muestra resultados para el cliente.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
