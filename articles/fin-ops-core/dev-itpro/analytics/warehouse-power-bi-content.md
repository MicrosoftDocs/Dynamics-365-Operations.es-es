---
title: Contenido de Power BI de rendimiento de almacén
description: Este artículo describe lo que se incluye en el contenido de rendimiento del almacén en Power BI.
author: Mirzaab
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom:
- "272953"
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.form: WHSWarehousePerformancePowerBI
ms.openlocfilehash: 667f085aa37be0d3a9ea490cf35ea4f22ef3120e
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206042"
---
# <a name="warehouse-performance-power-bi-content"></a>Contenido de Power BI de rendimiento de almacén

[!include [banner](../includes/banner.md)]

Este artículo describe lo que se incluye en el contenido de **rendimiento del almacén** en Microsoft Power BI. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Microsoft Power BI **Rendimiento de almacén** se creó para que los directores de explotación y almacén puedan supervisar las métricas de entrada, salida y de inventario importantes. Usa la gestión de almacenes, productos, y otros datos transaccionales de su sistema, y proporciona una visión global del rendimiento de almacén y un desglose de proveedores, grupos de productos y productos, y sitio y almacenes.

Los directores de almacén pueden usar el contenido de Power BI **Rendimiento de almacén** para medir las tres áreas siguientes:

- **Rendimiento de entrada**: se mide la calidad del trabajo de un proveedor en relación con los requisitos del cliente (es decir, se mide el rendimiento de entrega), y el rendimiento de la ubicación, de modo que se puedan identificar los problemas en los que estén implicados trabajadores o artículos durante un período. Es importante saber si los proveedores entregan los pedidos a tiempo, con antelación o tarde, de modo que se pueda determinar cómo el rendimiento de los proveedores afecta al rendimiento de la ubicación. Un proveedor que no entrega en las fechas acordadas puede suponer una presión adicional para el almacén, debido al trabajo inesperado, y puede aumentar el tiempo medio de ubicación.
- **Rendimiento de envío**: mide si el almacén envía por completo y a tiempo a los clientes (es decir mide el envío de salida y el rendimiento de entrega), de modo que se puedan identificar los problemas en los que están implicados los productos, sitios o almacenes, o clientes dedicados. Si descubre que sus envíos no llegan puntuales cuando van a áreas o ciudades específicas, puede que tenga que prestar más atención al transporte o la administración de cuentas.
- **Exactitud de inventario de la ubicación**: la precisión del inventario es inteligencia empresarial (BI) interna del almacén. Es muy importante que determine el grado de exactitud de sus recuentos en general. Sin embargo, también es importante que determine su grado de precisión cuando almacena artículos en las ubicaciones correctas, y que resalte los datos de las discrepancias, de modo que pueda encontrar mejores puestos para los artículos o iniciar un recuento total de artículos específicos. (Actualmente, la nueva funcionalidad de recuento basada en artículos se entrega como sustitución). Si utiliza este contenido de Power BI para determinar la corrección de los datos de inventario disponibles por ubicación, también puede identificar los robos en las tiendas. También puede determinar si algunas ubicaciones tienen cantidades disponibles que difieren de los datos de (ERP) de planificación de recursos empresariales. Estas ubicaciones pueden ser demasiado grandes, o puede que no sea posible contarlas. O bien, parte de la colocación física puede ser incorrecta, por lo que puede que sea difícil conservar un único tipo de artículo en sincronización con los datos disponibles.

## <a name="accessing-the-power-bi-content-pack"></a>Acceso al paquete de contenido de Power BI
El contenido de Power BI **Rendimiento de almacén** se muestra en la página **Rendimiento de almacén** (**Gestión de almacenes** \> **Consultas e informes** \> **Análisis del rendimiento de almacén** \> **Rendimiento de almacén**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido de Power BI **Rendimiento de almacén** incluye un informe. Este informe consta de un conjunto de métricas que se visualizan, como gráficos, mosaicos y tablas. La tabla siguiente proporciona una visión general de las visualizaciones en el contenido de **Rendimiento de almacén** en Power BI.

| Página de informes                 | Gráficos                                   | Descripción |
|-----------------------------|------------------------------------------|-------------|
| Rendimiento de entrada         | Total de ubicaciones                          | El número de líneas de trabajo de ubicación que se procesan durante una hora determinada. |
| Rendimiento de entrada         | Tiempo medio de ubicación                    | El tiempo promedio, en horas, de todas las líneas de ubicación del pedido de compra que se procesan, desde el registro de los artículos hasta que se procesa la última colocación. |
| Rendimiento de entrada         | Recibido con antelación                           | El número de líneas de pedido de compra que se reciben pronto. |
| Rendimiento de entrada         | Recibido a tiempo                         | El número de líneas de pedido de compra que se reciben puntualmente. |
| Rendimiento de entrada         | Recepción atrasada                            | El número de líneas de pedido de compra que se reciben tarde. |
| Rendimiento de entrada         | Puntual según proveedor                        | Vista de porcentaje de las líneas de pedido de compra recibidas de un proveedor o un grupo de proveedores que llegan pronto, con puntualidad o tarde. |
| Rendimiento de entrada         | Tiempo medio en guardar del muelle a existencias (horas) | Tiempo medio que se tarda en guardar del muelle a existencias, indicado en horas. |
| Rendimiento de entrada         | Tiempo medio en guardar indicado por trabajador               | El tiempo medio, en horas, que tarda un trabajador en acabar el procesamiento de las líneas de pedido de compra. |
| Rendimiento de entrada         | Tiempo medio en guardar, indicado por proveedor          | El tiempo medio, en horas, que tarda un proveedor o grupo de proveedores en guardar. |
| Rendimiento de entrada         | Tiempo medio en guardar, indicado por producto         | El tiempo medio, en horas, que tarda un artículo o grupo de artículos en ser guardado. |
| Exactitud del inventario de la ubicación | Recuento total                              | El número de líneas de trabajo de recuento que se procesan para un período determinado. |
| Exactitud del inventario de la ubicación | Índice de discrepancia                         | El índice total discrepancia indicado como un porcentaje de todas las líneas que se cuentan para un período determinado. |
| Exactitud del inventario de la ubicación | Recuento sin discrepancia                | Del número total de líneas de recuento que se procesan, el número de líneas que se procesan sin ninguna discrepancia. |
| Exactitud del inventario de la ubicación | Artículos contados en el tiempo                  | El porcentaje de los artículos que se cuentan con y sin discrepancia en el tiempo. |
| Exactitud del inventario de la ubicación | Discrepancia de la cantidad de artículos mayor que % | Una vista de tabla de las líneas de recuento con discrepancias que superan un porcentaje especificado. La tabla incluye información acerca de las ubicaciones, los artículos, la discrepancia media, el número total de líneas de trabajo de recuento que se cuentan, el número de líneas de recuento con discrepancias para la ubicación, la cantidad media que se cuenta, la cantidad total prevista que se contará y la cantidad de artículos real que se cuenta. |
| Exactitud del inventario de la ubicación | Recuento de artículos por trabajador                     | El rendimiento de recuento de los trabajadores. Se expresa el rendimiento como un porcentaje de líneas de recuento del trabajo con y sin discrepancias. |
| Exactitud del inventario de la ubicación | Recuento de artículos por sitio/almacén           | Rendimiento del recuento según el número de líneas de trabajo de recuento procesadas por sitio o almacén que tengan y no tengan discrepancias. |
| Exactitud del inventario de la ubicación | Índice de discrepancia por producto              | El índice de discrepancia del rendimiento del recuento. El índice es expresado como porcentaje de las líneas de trabajo de recuento procesadas por artículo o grupo de artículos. |
| Rendimiento del envío        | Líneas enviadas                            | El número total de líneas de envío que se envían en un período determinado. |
| Rendimiento del envío        | Con antelación                                    | El porcentaje de las líneas de envío que se envían pronto. |
| Rendimiento del envío        | Puntual                                  | El porcentaje de las líneas de envío que se envían puntualmente. |
| Rendimiento del envío        | Con retraso                                     | El porcentaje de las líneas de envío que se envían tarde. |
| Rendimiento del envío        | Envíos en el tiempo                      | El porcentaje de las líneas de envío que se envían a tiempo, pronto o tarde durante un período determinado. Una línea de tendencia muestra la tendencia de las líneas que se envían a tiempo. |
| Rendimiento del envío        | Enviado tarde por ciudad                     | Una visualización en mapa de las ciudades y las áreas afectadas por los envíos que llegan tarde. |
| Rendimiento del envío        | Enviado por producto                       | El porcentaje que se envía pronto, puntualmente o tarde indicado por artículo o grupo de artículos. |
| Rendimiento del envío        | Enviado por cliente                      | El porcentaje que se envía pronto, puntualmente o tarde indicado por cliente o grupo de clientes. |
| Rendimiento del envío        | Enviado por sitio/almacén              | El porcentaje que se envía pronto, puntualmente o tarde indicado por sitio o almacén. |

## <a name="understanding-the-data-model-and-calculations"></a>Comprensión del modelo de datos y los cálculos
Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI **Rendimiento del almacén**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información, consulte [Integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

Las siguientes medidas agregadas clave se usan como la base del contenido.

| Página de informes                 | Gráficos                                   | Tablas                                | Descripciones de cálculo |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Rendimiento de entrada         | Total de ubicaciones                          | WHSWorkLine                           | El recuento de líneas de trabajo en las que el tipo de trabajo es **colocación**. |
| Rendimiento de entrada         | Tiempo medio de ubicación                    | WHSWorkLine                           | La suma de tiempo máximo de las líneas de trabajo dividida por el recuento de tiempo máximo de líneas de trabajo, donde el tiempo máximo de líneas de trabajo es el intervalo de tiempo máximo entre la fecha de creación del trabajo y la fecha de cierre. |
| Rendimiento de entrada         | Recibido con antelación                           | WHSWorkLine                           | El recuento de líneas de trabajo en el que la fecha de creación del trabajo es anterior a la fecha de entrega que se usa. Si la fecha de entrega confirmada no está definida, utilice la fecha de entrega predeterminada. |
| Rendimiento de entrada         | Recibido a tiempo                         | WHSWorkLine                           | El recuento de líneas de trabajo en el que la fecha de creación del trabajo es igual a la fecha de entrega que se usa. Si la fecha de entrega confirmada no está definida, utilice la fecha de entrega predeterminada. |
| Rendimiento de entrada         | Recepción atrasada                            | WHSWorkLine                           | El recuento de líneas de trabajo en el que la fecha de creación del trabajo es posterior a la fecha de entrega que se usa. Si la fecha de entrega confirmada no está definida, utilice la fecha de entrega predeterminada. |
| Rendimiento de entrada         | Puntual según proveedor                        | WHSWorkLine                           | Recibido pronto, recibido puntualmente y recibido tarde (consulte las descripciones anteriores en esta tabla). |
| Rendimiento de entrada         | Tiempo medio en guardar del muelle a existencias (horas)   | WHSWorkLine                           | Tiempo promedio de ubicación (consulte la descripción anterior de esta tabla). |
| Rendimiento de entrada         | Tiempo medio en guardar indicado por trabajador               | WHSWorkLine                           | Tiempo promedio de ubicación (consulte la descripción anterior de esta tabla). |
| Rendimiento de entrada         | Tiempo medio en guardar, indicado por proveedor          | WHSWorkLine                           | Tiempo promedio de ubicación (consulte la descripción anterior de esta tabla). |
| Rendimiento de entrada         | Tiempo medio en guardar, indicado por producto         | WHSWorkLine                           | Tiempo promedio de ubicación (consulte la descripción anterior de esta tabla). |
| Exactitud del inventario de la ubicación | Recuento total                              | WHSWorkLineCycleCount                 | Recuentos de ciclo en los que la cantidad de discrepancia absoluta es igual o superior a 0 (cero). |
| Exactitud del inventario de la ubicación | Índice de discrepancia                         | WHSWorkLineCycleCount                 | Recuentos de ciclo con discrepancias, divididos por el recuento total. Se considera que un recuento de ciclo tiene discrepancias si la cantidad absoluta de la discrepancia es superior a 0 (cero). |
| Exactitud del inventario de la ubicación | Recuento sin discrepancia                | WHSWorkLineCycleCount                 | Recuentos de ciclo en los que la cantidad de discrepancia absoluta es superior a 0 (cero). |
| Exactitud del inventario de la ubicación | Recuento con discrepancia                   | WHSWorkLineCycleCount                 | Recuentos de ciclo en los que la cantidad de discrepancia absoluta es igual a 0 (cero). |
| Exactitud del inventario de la ubicación | Artículos contados en el tiempo                  | WHSWorkLineCycleCount                 | Recuento sin discrepancia y recuento con discrepancia (consulte las descripciones anteriores en esta tabla.) |
| Exactitud del inventario de la ubicación | Discrepancia de la cantidad de artículos mayor que % | WHSWorkLineCycleCount                 | La discrepancia media es la cantidad absoluta de la discrepancia dividida por la cantidad prevista en la que la cantidad absoluta de discrepancia es superior a 0 (cero). La cantidad de discrepancia media es la cantidad de la discrepancia absoluta media en la que la cantidad absoluta de discrepancia es superior a 0 (cero). El recuento con discrepancia, el recuento total, la cantidad prevista, y la cantidad contada, donde toda la cantidad se agrupa por artículo y ubicación (consulte las descripciones anteriores en esta tabla). |
| Exactitud del inventario de la ubicación | Recuento de artículos por trabajador                     | WHSWorkLineCycleCount                 | Recuento sin discrepancia y recuento con discrepancia (consulte las descripciones anteriores en esta tabla). |
| Exactitud del inventario de la ubicación | Recuento de artículos por sitio/almacén           | WHSWorkLineCycleCount                 | Recuento sin discrepancia y recuento con discrepancia (consulte las descripciones anteriores en esta tabla). |
| Exactitud del inventario de la ubicación | Índice de discrepancia por producto              | WHSWorkLineCycleCount                 | Tasa de la discrepancia (consulte la descripción anterior de esta tabla). |
| Rendimiento del envío        | Líneas enviadas                            | SalesLine               | El recuento de las líneas de ventas donde las líneas de ventas se envían. |
| Rendimiento del envío        | Con antelación                                    | CustPackingSlipOnTimeStatus           | Líneas de ventas donde el estado de la fecha de envío es **1 (temprano)**. Temprano significa que la fecha de envío del albarán es anterior a la fecha de envío confirmada de la línea de ventas. Si la fecha de envío confirmada no está definida, use la fecha de envío solicitada. |
| Rendimiento del envío        | Puntual                                  | CustPackingSlipOnTimeStatus           | Líneas de ventas donde el estado de la fecha de envío es **2 (puntual)**. Puntual significa que la fecha de envío del albarán es igual a la fecha de envío confirmada de la línea de ventas. Si la fecha de envío confirmada no está definida, use la fecha de envío solicitada. |
| Rendimiento del envío        | Con retraso                                     | CustPackingSlipOnTimeStatus           | Líneas de ventas donde el estado de la fecha de envío es **3 (tarde)**. Tarde significa que la fecha de envío del albarán es posterior a la fecha de envío confirmada de la línea de ventas. Si la fecha de envío confirmada no está definida, use la fecha de envío solicitada. |
| Rendimiento del envío        | Envíos en el tiempo                      | SalesLine CustPackingSlipOnTimeStatus | Pedidos que se envían completos, donde la cantidad completa de la línea de ventas se envía, más Temprano, Puntual y Tarde (consulte las descripciones anteriores en esta tabla). |
| Rendimiento del envío        | Enviado tarde por ciudad                     | CustPackingSlipOnTimeStatus           | Tarde (consulte las descripciones anteriores de esta tabla). |
| Rendimiento del envío        | Enviado por producto                       | CustPackingSlipOnTimeStatus           | Temprano, Puntual y Tarde (consulte las descripciones anteriores en esta tabla). |
| Rendimiento del envío        | Enviado por cliente                      | CustPackingSlipOnTimeStatus           | Temprano, Puntual y Tarde (consulte las descripciones anteriores en esta tabla). |
| Rendimiento del envío        | Enviado por sitio/almacén              | CustPackingSlipOnTimeStatus           | Temprano, Puntual y Tarde (consulte las descripciones anteriores en esta tabla). |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
