---
title: Características quitadas o en desuso en Dynamics 365 Commerce
description: En este artículo se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.
author: josaw1
ms.date: 08/23/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 59ffcc00d67f6538980dec8965f894eb51f7230d
ms.sourcegitcommit: 649f1db26da8f20602f11180fc565b7c59eaf545
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337606"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Características quitadas o en desuso en Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

En este artículo se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones de finanzas y operaciones se puede encontrar en los [Informes de referencia técnica](/dynamics/s-e/). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones de finanzas y operaciones.

## <a name="features-removed-or-deprecated-in-the-commerce-10029-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.29

### <a name="commerce-parameters-setting---allow-price-adjustments-to-increase-product-price"></a>Configuración de parámetros de Commerce: permitir que los ajustes de precios incrementen el precio del producto

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Teníamos esta configuración para controlar si la función de ajuste de precios permite aumentar el precio del producto. Cuando este parámetro está desactivado, al usar la función de ajuste de precios, las organizaciones solo pueden establecer el precio unitario de un producto por debajo del precio base y el precio de venta del acuerdo comercial. Rechazamos esta configuración porque la función de ajuste de precios se actualizó para admitir ajustes bidireccionales (aumento o disminución) listos para usar. |
| **¿Reemplazado por otra característica?**   | N.º |
| **Áreas de producto afectadas**         | Precios y descuentos |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: esta configuración está activada de forma predeterminada desde la versión 10.0.29 de Commerce y se eliminará en octubre de 2023. |

### <a name="commerce-parameters-setting---enable-price-report-for-retail-store"></a>Configuración de parámetros de comercio: habilite el informe de precios para la tienda minorista

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Teníamos esta configuración para controlar si la función de informe de precios está disponible para su uso en el formulario de configuración de la tienda. Rechazamos esta configuración porque el formulario de configuración de la tienda se ha actualizado para proporcionar siempre la función de informe de precios como función estándar. |
| **¿Reemplazado por otra característica?**   | N.º |
| **Áreas de producto afectadas**         | Precios y descuentos |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: esta configuración se eliminará en octubre de 2023. |

### <a name="commerce-parameters-setting---use-todays-date-to-calculate-prices"></a>Configuración de parámetros comerciales: use la fecha de hoy para calcular los precios

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El motor de precios de Supply Chain Management (SCM) admite el cálculo de precios basado en la fecha de envío solicitada y la fecha de recepción solicitada, junto con la fecha actual. El motor de precios de TheCommerce solo admite el cálculo de precios en función de la fecha de hoy. Para los clientes que usan las capacidades de SCM y Commerce, proporcionamos esta configuración y recomendamos que los clientes siempre la establezcan en **Sí** para que los dos motores de precios puedan trabajar juntos. Rechazamos esta configuración porque no cambia el comportamiento del cálculo y es redundante. |
| **¿Reemplazado por otra característica?**   | N.º |
| **Áreas de producto afectadas**         | Precios y descuentos |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: esta configuración está activada de forma predeterminada desde la versión 10.0.29 de Commerce y se eliminará en octubre de 2023. |

## <a name="feature-deprecation-effective-july-2022"></a>Aviso de desactivación de características a partir de julio de 2022

### <a name="commerce-analytics-preview"></a>Commerce analytics (versión preliminar)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El equipo de Dynamics 365 Commerce ha analizado el uso y la adopción de la característica de análisis de Commerce (versión preliminar), y ha tomado la decisión de no seguir adelante con la disponibilidad general de la característica.   |
| **¿Reemplazado por otra característica?**   | En este momento, el análisis de comercio (versión preliminar) no será reemplazado por otra función o solución. La exportación de transacciones sin procesar y datos maestros de aplicaciones de finanzas y operaciones a Azure Data Lake sigue estando disponible, como se explica en [Exportar a Data Lake en aplicaciones de finanzas y operaciones](../../fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake.md). Los socios y clientes pueden aprovechar esa secuencia de datos para crear cualquier informe de análisis previsto para sus necesidades comerciales.
| **Áreas de producto afectadas**         | Commerce analytics (versión preliminar) |
| **Opción de implementación**              | Todo |
| **Status**                         | Tenemos previsto deshabilitar esta función antes del 30 de agosto de 2022.  A partir de esta fecha, no se producirá ninguna actualización en los actuales informes de Power BI proporcionados por análisis de Commerce (versión preliminar).     |

## <a name="features-removed-or-deprecated-in-the-commerce-10021-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.21

[!include [banner](../includes/preview-banner.md)]

### <a name="overlapping-discounts-handling-setting-in-commerce-parameters"></a>Configuración de gestión de descuentos superpuestos en parámetros de Commerce

La configuración **Gestión de descuentos superpuestos** en la página **Parámetros de Commerce** queda obsoleta en la versión 10.0.21 de Commerce. En el futuro, el motor de precios de Commerce utilizará un solo algoritmo para determinar la combinación óptima de descuentos superpuestos.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | <p>La configuración **Gestión de descuentos superpuestos** de los parámetros de Commerce controla cómo busca el motor de precios de Commerce y determina la combinación óptima de descuentos superpuestos. Actualmente ofrece tres opciones:<p><ul><li> **Mejor rendimiento**: esta opción utiliza un algoritmo heurístico avanzado y un método de [clasificación de valor marginal](../optimal-combination-overlapping-discounts.md) para priorizar, evaluar y determinar la mejor combinación de descuentos de manera oportuna.</li><li>**Cálculo equilibrado**: en la base de código actual, esta opción funciona igual que la opción **Mejor rendimiento**. Por lo tanto, es esencialmente una opción duplicada.</li><li>**Cálculo exhaustivo**: esta opción utiliza un algoritmo antiguo que pasa por todas las combinaciones de descuentos posibles durante el cálculo del precio. Para pedidos que tienen grandes líneas y cantidades, esta opción puede causar problemas de rendimiento.</li></ul><p>Para ayudar a simplificar la configuración, mejorar el rendimiento y reducir los incidentes causados por el algoritmo anterior, eliminaremos por completo la configuración **Gestión de descuentos superpuestos** y actualizar la lógica interna del motor de precios de Commerce para que ahora use solo el algoritmo avanzado (es decir, el algoritmo detrás de la opción **Mejor rendimiento**).</p> |
| **¿Reemplazado por otra característica?**   | No. Recomendamos que las organizaciones que utilizan las opciones **Cálculo equilibrado** o **Cálculo exhaustivo** cambien a la opción **Mejor rendimiento** antes de que se elimine esta función. |
| **Áreas de producto afectadas**         | Precios y descuentos |
| **Opción de implementación**              | Todo |
| **Estado**                         | A partir de la versión 10.0.21, la configuración **Gestión de descuentos superpuestos** se eliminará de los parámetros de Commerce en octubre de 2022. |

### <a name="retail-sdk-distributed-by-using-lifecycle-services"></a>SDK de Retail distribuido mediante el uso de Lifecycle Services

El SDK de Retail se envía con Lifecycle Services (LCS). Este modo de distribución está obsoleto en la versión 10.0.21. En el futuro, los paquetes de referencia, las bibliotecas y las muestras del SDK de Retail se publicarán en repositorios públicos en GitHub.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El SDK de Retail se envía con LCS. El proceso de LCS tarda unas horas en finalizar y el proceso debe repetirse para cada actualización. En el futuro, los paquetes de referencia, las bibliotecas y las muestras del SDK de Retail se publicarán en repositorios públicos en GitHub. Las muestras de extensión y los paquetes de referencia se pueden consumir fácilmente y las actualizaciones terminan en unos minutos. |
| **¿Reemplazado por otra característica?**   |  [Descargar muestras y paquetes de referencia del SDK de Retail desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md) |
| **Áreas de producto afectadas**         | SDK de Retail |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.21, el SDK enviado a través de las VM de LCS se eliminarán en octubre de 2023. |

### <a name="retail-deployable-package-and-combined-pos-hardware-station-and-cloud-scale-unit-installers"></a>Instaladores de paquetes desplegables de Retail e instaladores combinados de PDV, estación de hardware y unidad de escalado en la nube

Los paquetes desplegables de Retail generados con el SDK de Retail MSBuild están en desuso en 10.0.21. En el futuro, use el paquete de unidad de escalado en la nube (Cloud Scale Unit, CSU) para las extensiones de unidad de escalado en la nube (Commerce Runtime, base de datos de canales, API de comercio sin periféricos, pagos y punto de venta (PDV) en la nube). Utilice instaladores solo de extensión para PDV, estación de hardware y unidad de escalado en la nube autoalojada.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Un paquete desplegable de Retail es un paquete combinado que contiene un conjunto completo de paquetes de extensión e instaladores. Este paquete combinado hace que la implementación sea compleja, ya que las extensiones de CSU van a la unidad de escalado en la nube y los instaladores se implementan en los almacenes. Los instaladores incluyen la extensión y el producto base, lo que dificulta las actualizaciones. Con cada actualización, se requiere una combinación de código y generación de paquetes. Para simplificar este proceso, los paquetes de extensión ahora están separados en componentes para una fácil implementación y administración. Con el nuevo enfoque, las extensiones y los instaladores de productos base se separan y se pueden mantener y actualizar de forma independiente sin una combinación de código o reempaquetado.|
| **¿Reemplazado por otra característica?**   | Extensiones de CSU, instaladores de extensiones de PDV, instaladores de extensiones de estaciones de hardware |
| **Áreas de producto afectadas**         | Extensión y despliegue de Dynamics 365 Commerce |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.21, la compatibilidad con la implementación de RetailDeployablePackage en LCS se eliminará en octubre de 2022. |

Para obtener más información, consulte:

+ [Generar un paquete separado para Commerce Scale Unit (CSU) (nube)](../dev-itpro/retail-sdk/retail-sdk-packaging.md#generate-a-separate-package-for-commerce-cloud-scale-unit-csu)
+ [Crear un paquete de extensión de PDV moderno](../dev-itpro/pos-extension/mpos-extension-packaging.md)
+ [Integrar el PDV con un nuevo dispositivo de hardware](../dev-itpro/hardware-device-extension.md)
+ Muestras de códigos
    + [Unidad de escalado en la nube](https://github.com/microsoft/Dynamics365Commerce.ScaleUnit)
    + [PDV, CSU y estación de hardware](https://github.com/microsoft/Dynamics365Commerce.InStore)

### <a name="modernpossln-and-cloudpossln-in-the-retail-sdk"></a>ModernPos.Sln y CloudPos.sln en el SDK de Retail

El desarrollo de extensiones de PDV mediante ModernPos.sln, CloudPos.sln, POS.Extension.csproj y la carpeta PDV está en desuso en la versión 10.0.21. En el futuro, use el SDK de empaquetado independiente de PDV para extensiones de PDV.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | En versiones anteriores del SDK de Retail, si hay extensiones de PDV, se requiere una combinación de código y un reempaquetado para actualizar a la última versión de PDV. La combinación de código fue un proceso de actualización que requirió mucho tiempo y tuvo que mantener el SDK de Retail completo en el repositorio. También tuvo que compilar el proyecto principal POS.App. Al utilizar el modelo de empaquetado independiente, debe mantener solo su extensión. El proceso de actualización a la última versión de las extensiones de PDV es tan fácil como actualizar la versión del paquete NuGet que consume su proyecto. Las extensiones se pueden implementar de forma independiente y los servicios utilizan los instaladores de extensiones. El PDV base se puede implementar y mantener por separado y no se requiere la combinación o reempaquetado de código con el instalador o código base. |
| **¿Reemplazado por otra característica?**   | [SDK de empaquetado independiente de PDV](../dev-itpro/pos-extension/pos-extension-getting-started.md) |
| **Áreas de producto afectadas**         | Extensión y despliegue de PDV de Dynamics 365 Commerce |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.21, la compatibilidad con los paquetes de PDV combinados y el modelo de extensión que utilizan ModernPos.Sln, CloudPOs.sln y POS.Extensons.csproj en el SDK de Retail se eliminará en octubre de 2023. |

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.17

### <a name="full-dataset-generation-interval-is-deprecated"></a>El intervalo de generación del conjunto de datos completo está en desuso

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de esta versión, en el formulario **Parámetros del programador de comercio** de la sede central de Dynamics 365, el campo **Intervalo completo de generación de conjunto de datos en días** quedará en desuso. Además, el campo se eliminará visualmente para que su valor no se pueda editar. Su valor será **0**. |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Dynamics 365 Commerce |
| **Opción de implementación**              | Todo|
| **Status**                         | En desuso. No utilice este campo ni cambie su valor.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La compatibilidad de Internet Explorer 11 con Dynamics 365 está en desuso

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de diciembre de 2020, queda en desuso la compatibilidad de Microsoft Internet Explorer 11 con todos los productos de Dynamics 365 e Internet Explorer 11 no se admitirá después de agosto de 2021.<br><br>Esto afectará a los clientes que usan productos Dynamics 365 que están diseñados para usarse a través de una interfaz de Internet Explorer 11. Después de agosto de 2021, Internet Explorer 11 no será compatible con dichos productos de Dynamics 365. |
| **¿Reemplazado por otra característica?**   | Recomendamos que los clientes hagan la transición a Microsoft Edge.|
| **Áreas de producto afectadas**         | Todos los productos Dynamics 365 |
| **Opción de implementación**              | Todo|
| **Estado**                         | En desuso. Internet Explorer 11 no se admitirá después de agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.11
### <a name="data-action-hooks"></a>Enlaces de acción de datos
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La función de enlaces de acción de datos ha quedado en desuso debido a problemas de rendimiento. |
| **¿Reemplazado por otra característica?**   | Le recomendamos utilizar las [anulaciones de acción de datos](../e-commerce-extensibility/data-action-overrides.md) para modificar la lógica de negocios en la capa de acción de datos.|
| **Áreas de producto afectadas**         | Acciones de datos de la extensibilidad de comercio electrónico |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Soporte de SDK de Retail para Visual Studio 2015, msbuild 14.0 y SDK de Retail\bibliotecas y herramientas de referencia
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El soporte de SDK de Retail para Visual Studio 2015 ha quedado desuso y se ha actualizado para admitir VS 2017, msbuild 15.0 y todas las bibliotecas de referencia y herramientas generadoras de proxy de comercio en la carpeta RetailSDK\References movida a paquetes de NuGet para simplificar el modelo de extensión y el proceso de actualización del SDK.|
| **¿Reemplazado por otra característica?**   | Le recomendamos que siga la información en [Migrar el SDK de Retail desde Visual Studio 2015 a Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) para actualizar su sistema. |
| **Áreas de producto afectadas**         | Extensiones de SDK de Retail |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Extensión de Retail Server con IEdmModelExtender y CommerceController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La extensión de Retail Server que utiliza IEdmModelExtender y CommerceController ha quedado en desuso para proporcionar un modelo de extensión simplificado. La nueva implementación solo tendrá la clase de controlador sin ninguna implementación de clase IEdmModelExtender adicional. Esto también evita la dependencia con una versión particular de OData (si la versión de OData se actualiza, se pueden romper las extensiones.) |
| **¿Reemplazado por otra característica?**   |  Le recomendamos que utilice el modelo de extensión de clase IController importando el paquete de NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas de producto afectadas**         | Extensiones de Retail Server |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Extensión de estación de hardware mediante IHardwareStationController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La extensión de la estación de hardware mediante IHardwareStationController ha quedado en desuso para proporcionar un modelo de extensión simplificado. La nueva implementación solo tendrá la clase IController sin ninguna implementación de clase adicional y, para evitar la dependencia con las principales bibliotecas de estaciones de hardware, previamente la extensión debe hacer referencia a varias bibliotecas.) |
| **¿Reemplazado por otra característica?**   | Se recomienda usar el modelo de extensión de clase IController importando el paquete de NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Áreas de producto afectadas**         | Extensiones de la estación de hardware |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operación de PDV 803: recogida y recepción
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las operaciones de recogida y recepción están en desuso debido al nuevo diseño de la operación. |
| **¿Reemplazado por otra característica?**   | Sí. Se reemplazan por dos nuevas operaciones de PDV: operación entrante (804) y operación saliente (805).|
| **Áreas de producto afectadas**         | Aplicación de punto de venta (PDV) |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.10, la operación de selección y recepción ya no recibirá actualizaciones de nuevas funciones. Solo se realizarán correcciones de errores críticos para esta operación en futuras versiones. Se anima a todos los clientes a cambiar a las nuevas [Operaciones de entrada](../pos-inbound-inventory-operation.md) y [Operaciones de salida](../pos-outbound-inventory-operation.md), que seguirán formando parte de nuestra hoja de ruta de productos a largo plazo. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API GetProductAvailabilities y GetAvailableInventoryNearby de Commerce
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se han creado API nuevas y optimizadas para reemplazar las API de GetProductAvailabilities y GetAvailableInventoryNearby. |
| **¿Reemplazado por otra característica?**   | Sí: se reemplaza por las API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability. |
| **Áreas de producto afectadas**         | SDK de aplicación de comercio electrónico |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.7, ya no se realizarán inversiones de ingeniería para GetProductAvailabilities y GetAvailableInventoryNearby. Las organizaciones que usan estas API en sus implementaciones de comercio electrónico deben convertirse a las nuevas API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability y habilitar la [Función optimizada de cálculo de disponibilidad del producto](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas
Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

