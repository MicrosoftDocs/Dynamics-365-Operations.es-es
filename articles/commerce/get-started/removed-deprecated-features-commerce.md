---
title: Características quitadas u obsoletas de Dynamics 365 Commerce
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: dd982ae60da1c2958d6d759bb5dd256a71fabf6c
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154210"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Características quitadas u obsoletas de Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://docs.microsoft.com/dynamics/s-e/). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.17

> [!Important]
> La versión 10.0.17 está disponible como parte de una versión preliminar. El contenido y la funcionalidad están sujetos a cambios. Para obtener más información acerca las versiones preliminares, consulte [Preguntas frecuentes sobre actualizaciones del servicio de una versión](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

### <a name="full-dataset-generation-interval-is-deprecated"></a>El intervalo de generación del conjunto de datos completo está en desuso

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de esta versión, en el formulario **Parámetros del programador de comercio** de la sede central de Dynamics 365, el campo **Intervalo completo de generación de conjunto de datos en días** quedará en desuso. Además, el campo se eliminará visualmente para que su valor no se pueda editar. Su valor será **0**. |
| **¿Reemplazado por otra característica?**   | N.º |
| **Áreas de producto afectadas**         | Dynamics 365 Commerce |
| **Opción de implementación**              | Todos|
| **Estado**                         | En desuso. No utilice este campo ni cambie su valor.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La compatibilidad de Internet Explorer 11 con Dynamics 365 está en desuso

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de diciembre de 2020, queda en desuso la compatibilidad de Microsoft Internet Explorer 11 con todos los productos de Dynamics 365 e Internet Explorer 11 no se admitirá después de agosto de 2021.<br><br>Esto afectará a los clientes que usan productos Dynamics 365 que están diseñados para usarse a través de una interfaz de Internet Explorer 11. Después de agosto de 2021, Internet Explorer 11 no será compatible con dichos productos de Dynamics 365. |
| **¿Reemplazado por otra característica?**   | Recomendamos que los clientes hagan la transición a Microsoft Edge.|
| **Áreas de producto afectadas**         | Todos los productos Dynamics 365 |
| **Opción de implementación**              | Todos|
| **Estado**                         | En desuso. Internet Explorer 11 no se admitirá después de agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.11
### <a name="data-action-hooks"></a>Enlaces de acción de datos
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La función de enlaces de acción de datos ha quedado en desuso debido a problemas de rendimiento. |
| **¿Reemplazado por otra característica?**   | Le recomendamos utilizar las [anulaciones de acción de datos](../e-commerce-extensibility/data-action-overrides.md) para modificar la lógica de negocios en la capa de acción de datos.|
| **Áreas de producto afectadas**         | Acciones de datos de la extensibilidad de comercio electrónico |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Soporte de SDK de Retail para Visual Studio 2015, msbuild 14.0 y SDK de Retail\bibliotecas y herramientas de referencia
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El soporte de SDK de Retail para Visual Studio 2015 ha quedado desuso y se ha actualizado para admitir VS 2017, msbuild 15.0 y todas las bibliotecas de referencia y herramientas generadoras de proxy de comercio en la carpeta RetailSDK\References movida a paquetes de NuGet para simplificar el modelo de extensión y el proceso de actualización del SDK.|
| **¿Reemplazado por otra característica?**   | Le recomendamos que siga la información en [Migrar el SDK de Retail desde Visual Studio 2015 a Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) para actualizar su sistema. |
| **Áreas de producto afectadas**         | Extensiones de SDK de Retail |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Extensión de Retail Server con IEdmModelExtender y CommerceController
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La extensión de Retail Server que utiliza IEdmModelExtender y CommerceController ha quedado en desuso para proporcionar un modelo de extensión simplificado. La nueva implementación solo tendrá la clase de controlador sin ninguna implementación de clase IEdmModelExtender adicional. Esto también evita la dependencia con una versión particular de OData (si la versión de OData se actualiza, se pueden romper las extensiones.) |
| **¿Reemplazado por otra característica?**   |  Le recomendamos que utilice el modelo de extensión de clase IController importando el paquete de NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas de producto afectadas**         | Extensiones de Retail Server |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Extensión de estación de hardware mediante IHardwareStationController
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La extensión de la estación de hardware mediante IHardwareStationController ha quedado en desuso para proporcionar un modelo de extensión simplificado. La nueva implementación solo tendrá la clase IController sin ninguna implementación de clase adicional y, para evitar la dependencia con las principales bibliotecas de estaciones de hardware, previamente la extensión debe hacer referencia a varias bibliotecas.) |
| **¿Reemplazado por otra característica?**   | Se recomienda usar el modelo de extensión de clase IController importando el paquete de NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas de producto afectadas**         | Extensiones de la estación de hardware |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operación POS 803: recogida y recepción
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las operaciones de recogida y recepción están en desuso debido al nuevo diseño de la operación. |
| **¿Reemplazado por otra característica?**   | Sí. Se reemplazan por dos nuevas operaciones POS: operación entrante (804) y operación saliente (805).|
| **Áreas de producto afectadas**         | Aplicación de punto de venta (POS) |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.10, la operación de selección y recepción ya no recibirá actualizaciones de nuevas funciones. Solo se realizarán correcciones de errores críticos para esta operación en futuras versiones. Se anima a todos los clientes a cambiar a las nuevas [Operaciones de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) y [Operaciones de salida](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), que seguirán formando parte de nuestra hoja de ruta de productos a largo plazo. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API de GetProductAvailabilities y GetAvailableInventoryNearby
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se han creado API nuevas y optimizadas para reemplazar las API de GetProductAvailabilities y GetAvailableInventoryNearby. |
| **¿Reemplazado por otra característica?**   | Sí: se reemplaza por las API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability. |
| **Áreas de producto afectadas**         | SDK de aplicación de comercio electrónico |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.7, ya no se realizarán inversiones de ingeniería para GetProductAvailabilities y GetAvailableInventoryNearby. Las organizaciones que usan estas API en sus implementaciones de comercio electrónico deben convertirse a las nuevas API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability y habilitar la [Función optimizada de cálculo de disponibilidad del producto](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas
Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]