---
title: Catálogos de centros de llamadas
description: Este tema describe la funcionalidad específica del centro de llamadas para catálogos en Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2ad50be1394daf5bffa6391d2f56340aad14120b
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023668"
---
# <a name="call-center-catalogs"></a>Catálogos de centros de llamadas

[!include [banner](includes/banner.md)]

Este tema describe la funcionalidad específica del centro de llamadas vinculada a las capacidades del catálogo en Dynamics 365 Retail.

Las características del catálogo que se encuentran en Retail se pueden utilizar para varios propósitos. Las características del catálogo se crearon inicialmente para admitir las integraciones de comercio electrónico de terceros. La configuración del catálogo permitieron a las empresas crear una agrupación de productos y atributos que se podrían publicar externamente para su consumo por una solución de comercio electrónico de terceros.

Cuando el soporte del canal de centro de llamadas se agregó en Retail, el concepto del catálogo se amplió para agregar capacidades adicionales para admitir y gestionar características relacionadas con catálogos tradicionales de marketing de directo a consumidor. Una empresa de directo a consumidor mostrará a menudo catálogos impresos, que se registran en uno o más segmentos de clientes. Normalmente, estos catálogos tendrán promociones u ofertas específicas que solo se aplicarán si el cliente proporciona un código de identificación del catálogo en el momento de la creación de pedidos.

La empresas de marketing de directo a consumidor se centran mucho en realizar un seguimiento de la respuesta a estos catálogos para garantizar que se justifican los costes de producción y envío por correo electrónico. Para realizar un seguimiento de la respuesta, se imprime tradicionalmente un código en la parte trasera del catálogo y luego este código se solicita y se aplica cuando el destinatario del catálogo llama para realizar un pedido por teléfono (o ahora, más tradicionalmente, el código se puede introducir cuando el cliente realiza un pedido en línea). Si bien existen diferentes términos del sector que se han utilizado para identificar este código de seguimiento del catálogo (incluido el código de clave, el código de promoción, el código del catálogo, el código de origen), nos referimos al código en Retail como el **Identificador del código de origen**.

## <a name="basic-catalog-setup"></a>Configuración de catálogo básico

Vaya **Retail** \> **Catálogos y surtidos** \> **Todos los catálogos** para configurar el catálogo.

Cuando cree un nuevo catálogo, primero debe vincular el catálogo a uno o varios canales comerciales. Esto se hace en la ficha desplegable **Canales comerciales** en el formulario **Configuración del catálogo**. Haga clic en **Agregar** y seleccione uno o varios canales comerciales. Solo pueden utilizarse elementos vinculados a sus [surtidos](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) de canal seleccionados al crear el catálogo.

Para agregar productos a un catálogo, debe elegirse una jerarquía de navegación. La jerarquía de navegación admitirá la estructura de categoría para el catálogo. Debe elegir desde una de las jerarquías de navegación vinculadas a los canales comerciales seleccionados en la ficha desplegable **Canales comerciales** de la página **Catálogo**. Si un canal de navegación no se vinculó previamente a un canal, vaya a **Retail** \> **Configuración de canal** \> **Categorías de canal y atributos de producto** para vincular una jerarquía de navegación predeterminada para cada uno de sus canales comerciales.

En la ficha de menú **Catálogos**, en la página **Configuración del catálogo**, haga clic en **Agregar productos** para configurar los productos que va a agregar al catálogo, o seleccione un nodo en la jerarquía de navegación (la selección de un nodo cambiará la presentación de la pantalla y le permitirá agregar productos directamente a una categoría del catálogo).

Haga clic en el nodo superior de la jerarquía del catálogo para volver a la vista de encabezado del catálogo principal. Configure las fechas de vigencia y vencimiento según sea necesario en el ficha desplegable **General**.

Antes de que el catálogo esté disponible para su uso, debe publicarse. Haga clic en **Validar catálogo** en el menú **Catálogos** para procesar una validación. Esta es acción requerida y validará que la configuración necesaria es precisa. Haga clic en **Ver resultados** para ver los detalles de la validación. Si se detectan errores, debe corregir los datos y volver a ejecutar la validación hasta que haya pasado la validación.

Una vez confirmada la validación, haga clic en **Flujo de trabajo** en el menú para iniciar el flujo de trabajo de aprobación. Haga clic en **Enviar** en el menú **Flujo de trabajo** para ejecutar el proceso. Configure los pasos y los usuarios autorizados para el flujo trabajo desde **Retail** \> **Configuración de sede central** \> **Flujos de trabajo comerciales**. El flujo de trabajo definirá los pasos necesarios para obtener el catálogo en un estado **Aprobado**. Cuando el catálogo se encuentra en un estado **Aprobado**, puede hacer clic en la opción **Publicar** en el menú **Catálogos** para completar el proceso. Una vez que el catálogo esté en un estado **Publicado**, se puede utilizar en la entrada de pedidos del centro de llamadas y enviar procesos del catálogo.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Utilizar catálogos para generar precios y promociones del pedido de ventas

Un motivo fundamental para definir un catálogo para su uso con un centro de llamadas es poder configurar precios y promociones específicos para ese catálogo. Los clientes que piden desde este catálogo recibirán estos precios y promociones en la entrada de pedidos del centro de llamadas si el **Identificador del código de origen** del catálogo se aplica a la cabecera o las líneas del pedido.

Para configurar precios específicos del catálogo, seleccione la opción **Grupos de precio** de la pestaña **Catálogos** para vincular uno o varios grupos de precios al catálogo. Todos los acuerdos comerciales, diarios de ajuste de precios y descuentos comerciales avanzados (umbral, cantidad, combinado) que se han vinculado al mismo grupo de precios se aplicarán cuando los clientes pidan de este catálogo.

En el ficha desplegable **Códigos de origen**, haga clic en **Agregar** para agregar uno o más identificadores **Identificador del código de origen** a este catálogo. Este es el código que se aplicará durante la entrada de pedidos del centro de llamadas a la cabecera del pedido de ventas (y las líneas). Este código se utiliza para vincular el pedido de ventas al catálogo y, finalmente, a los grupos de precios y cualquier precio y promoción especial que se han configurado.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>Utilizar el identificador de origen para realizar un seguimiento de los costes y las tasas de respuesta

Al definir el **Identificador del código de origen**, de forma opcional puede vincular este identificador a un **Id. de mercado de destino**. El **Id. de mercado de destino** se puede definir en **Retail** \> **Clientes** \> **Mercado de destino**. El mercado de destino es una lista de clientes y/o clientes potenciales que pertenecen a un segmento definido por el usuario. Vincular los datos del cliente o del cliente potencial al identificador del código de origen permite una mejor visibilidad en los destinatarios del catálogo. Si un cliente se vincula a un mercado de destino y ese mercado de destino se vincula a un identificador de código de origen/catálogo activo, los usuarios del centro de llamadas podrán ver qué catálogos ha recibido un cliente seleccionando la opción de menú **Códigos de origen** en la ficha de menú **Clientes** en la página **Servicio al cliente**. Durante la entrada de pedidos, los usuarios del centro de llamadas también pueden ver los catálogos específicos que envió un cliente en lista desplegable **Origen** en la cabecera del pedido de ventas. Cambiar el filtro de **Todos** a **Objetivo** permitirá al usuario ver los catálogos activos específicos que se enviaron al cliente. Esto resulta útil en situaciones en las que el cliente puede haber olvidado su catálogo o no puede ubicar o leer el código de catálogo cuando está llamando para crear un pedido de ventas.

Es posible vincular varios identificadores de código de origen a un catálogo. Esto suele ser necesario cuando una empresa desea realizar un seguimiento de la tasa de respuesta por distintos segmentos. La empresa dará un código de catálogo único a los distintos segmentos de cliente, lo que permite realizar el seguimiento de la tasa de respuesta, hasta el nivel de segmento, dentro de un determinado evento del catálogo.

Seleccionar un determinado registro **Identificador del código de origen** y hacer clic en la opción **Detalles** en la ficha desplegable **Códigos de origen** proporcionarán campos adicionales donde se pueden capturar proyecciones de ventas, gastos de envío y costes de impresión. Estos datos son útiles para realizar análisis detallados sobre la eficacia del catálogo. Los usuarios pueden volver a esta página a lo largo del tiempo y usar los botones **Análisis de código de origen** y **Comparar promociones** para activar informes analíticos en función de los datos de ventas actuales y comparar los costes y el presupuesto con los reales.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Configurar secuencias de comandos de pedidos y artículos específicos del catálogo.

Cuando un usuario del centro de llamadas está creando un pedido de ventas, pueden utilizar secuencias de comandos en pantalla. Estas secuencias de comandos basados en texto pueden proporcionar información adicional que el usuario debe decir al cliente, o pueden ser notas internas/recordatorios que el usuario del centro de llamadas debe revisar y reaccionar a medida que están creando el pedido de ventas.

Suele ser útil tener distintos conjuntos de secuencias de comandos para diferentes catálogos. En la ficha desplegable **Secuencias de comandos**, las secuencias de comandos predefinidos se pueden vincular a un catálogo. Utilice el campo **Tiempo** para determinar si la secuencia de comando aparece al principio del pedido (tan pronto como el identificador del código de origen se introduce en la cabecera del pedido) o al final del pedido (en el formulario de resumen del pedido de ventas).

Al seleccionar un nodo en la jerarquía del catálogo y trabajar con los datos en la ficha desplegable **Productos**, los usuarios también pueden vincular secuencias de comandos que sean específicas de catálogos o artículos mediante la acción **Secuencias de comandos** .

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Configurar artículos de ventas cruzadas y ventas verticales específicas del catálogo

Vincular sugerencias de venta vertical/venta cruzada a un artículo se puede realizar desde la configuración de productos, pero en algunos casos, una empresa puede querer promocionar artículos especiales de venta vertical/venta cruzada para clientes que pidan un producto específico de un catálogo concreto. En el ficha desplegable **Productos**, seleccione un artículo y haga clic en **Artículos de venta vertical/venta cruzada** para configurar productos para que se vendan de forma vertical o cruzada a clientes que compren el artículo seleccionado desde el catálogo. Durante la entrada de pedidos del centro de llamadas, los artículos de venta vertical/venta cruzada específicos del catálogo aparecerán en la pantalla en lugar de los productos estándar de venta vertical/venta cruzada que pueden haberse configurado para dicho artículo a través de la configuración de productos habitual.

Los artículos de venta vertical/venta cruzada también pueden aprovechar las características de secuencia de comandos para mostrar mensajes específicos que un usuario verá cuando el artículo de venta vertical/venta cruzada se muestre durante la entrada de pedidos. Las secuencias de comandos asociados a productos de venta vertical/venta cruzada configurados específicamente para un producto del catálogo aparecerán cuando el código de origen de este catálogo se aplique en una entrada de pedidos del centro de llamadas.

## <a name="catalog-page-analysis"></a>Análisis de página de catálogo

En la pestaña **Catálogos**, las opciones están disponibles para configurar **Páginas de catálogo**. Esta función le permite definir páginas específicas y tipos de página para el catálogo impreso y sus costes asociados.

Al configurar los productos del catálogo, utilice la acción **Diseño de página de productos** para definir las páginas específicas, el porcentaje de la página y la posición de los detalles de la página para el artículo. Configurar estos datos permitirá a los usuarios aprovecharse del **Informe de análisis de área de catálogo**. Este informe se encuentra navegando al informe  **Retail** \> **Informes de centro de llamadas** \> **análisis de área de catálogo**. Este informe analiza las ventas ubicadas en el catálogo (pedidos de ventas donde el identificador de origen del catálogo estaba asociado a la cabecera o línea del pedido) y su porcentaje de página y costes asociados para dar un informe **Análisis de pulgadas cuadradas** de marketing directo tradicional.

## <a name="catalog-requests"></a>Solicitudes de catálogo

A medida que los catálogos se configuran y se publican en Retail, se puede utilizar la función **Enviar catálogo**. Esta función está disponible en las páginas **Búsqueda de clientes** y **Servicio al cliente**. Después de seleccionar un registro de cliente a través de **Búsqueda de clientes** o mientras se visualiza una cuenta de clientes seleccionada desde **Servicio al cliente**, los usuarios pueden seleccionar la opción **Enviar catálogo** que abrirá un cuadro de diálogo, lo que permite al usuario elegir entre una lista de cualquier catálogo publicado y activo. Un usuario puede seleccionar un catálogo y una cantidad, y un identificador del código de origen particular para enviarlo. Cuando hagan clic en el botón **Enviar**, se guarda una solicitud que se puede gestionar imprimiendo el informe **Solicitudes de catálogo**. Este informe se encuentra navegando a **Retail** \> **Informes de centro de llamadas** \> **Informe de solicitudes de catálogo**. Muestra todas las solicitudes del catálogo, incluidos detalles del nombre y la dirección del cliente que solicitó el catálogo. Este informe se puede utilizar internamente o los datos se pueden transmitir a un tercero que admita procesos externos para enviar físicamente el catálogo al cliente.

## <a name="additional-features"></a>Funciones adicionales

En la pestaña **Catálogos**, también están disponibles opciones para configurar **Multivencimientos** y **Productos gratuitos**. Si el identificador del código de origen vinculado al catálogo se aplica durante la entrada de pedidos de centro de llamadas, el cliente será apto para los productos gratuitos o utilizará multivencimientos de catálogos específicos como se definen. Si es necesario limitar al cliente para que solo pueda seleccionar entre multivencimientos vinculados a su catálogo y no todos los multivencimientos activos en el sistema, la casilla **Permitir solo planes del catálogo** se puede seleccionar para uno o más de los identificadores de código de origen definidos para aplicar esa limitación.

## <a name="additional-notes"></a>Notas adicionales

Actualmente, cuando un identificador de código de origen se aplica a un pedido de ventas en el centro de llamadas, se utiliza para generar precios, promociones, secuencias de comandos y ventas verticales/cruzadas que son específicas del catálogo. El sistema no prohibirá ni evitará pedir un producto del pedido de ventas que no se encuentre en el catálogo. Si se pide un artículo que no forme parte del catálogo, el sistema utilizará primero el **Grupo de precios** que se define en el canal del centro de llamadas (**Retail** \> **Canales** \> **Centros de llamadas** \> **Todos los centros de llamadas**) para el precio o las promociones del artículo. Si no se encuentra ningún precio específico del canal, se empleará el precio de venta base del artículo.
