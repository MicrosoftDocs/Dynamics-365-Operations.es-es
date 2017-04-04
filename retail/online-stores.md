---
title: "Visión general de la tienda en línea"
description: "Este artículo proporciona información sobre tiendas minoristas en línea y sobre cómo configurarlas en Microsoft Dynamics 365 for Operations."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40fbf8b4fdfed32dd67013b6b21cc2c8ee3d31e6
ms.lasthandoff: 03/31/2017


---

# <a name="online-store-overview"></a>Visión general de la tienda en línea

Este artículo proporciona información sobre tiendas minoristas en línea y sobre cómo configurarlas en Microsoft Dynamics 365 for Operations.

La venta minorista y el comercio en Microsoft Dynamics 365 for Operations admiten varios canales de venta minorista. Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas). Las tiendas en línea proporcionan al distribuidor una presencia en línea, de modo que los clientes puedan comprar productos de su tienda en línea además de en sus tiendas físicas. Si los clientes compran productos en la tienda en línea, esos productos se les pueden enviar o los clientes pueden recogerlos en una tienda local. Puede crear una tienda en línea en el cliente Dynamics 365 for Operations. A continuación esta tienda en línea se publica en un tienda en línea de terceros que se integra con Dynamics 365 for Operations. Su tienda en línea de terceros sirve como escaparate electrónico (interfaz de usuario) para la tienda en línea y le proporciona una serie de capacidades de sistema de gestión del cliente (CMS) y de interfaz de usuario. Varias integraciones de este tipo están disponibles para Dynamics 365 for Operations. Las propiedades que defina para la tienda en línea controlan el comportamiento de la tienda en línea. Por ejemplo, puede definir la jerarquía de categorías de navegación en Dynamics 365 for Operations y asignarla a la tienda en línea. Cuando se publique la tienda en línea en la tienda en línea de terceros, la jerarquía de categorías de navegación aparecen en la versión en línea de la tienda. Después, ,los compradores usan la jerarquía de categorías de navegación para explorar la tienda en línea y para buscar productos. Para crear una tienda en línea, debe configurar los componentes que permiten el procesamiento de transacciones para la tienda. Por ejemplo, debe agregar los surtidos, aplicar atributos y establecer métodos de pago y métodos de envío. También puede definir precios, promociones, descuentos, acuerdos comerciales y condiciones de envío específicos de la tienda en línea. Después publicar la tienda en línea en la tienda en línea de terceros, puede crear catálogos de productos comerciales para la tienda en línea. Los productos del catálogo se convierten en listados de productos en la tienda en línea. Cuando un comprador adquiere productos de la tienda en línea, el inventario disponible se actualiza y se sincroniza en el cliente. Además, se generan pedidos de ventas para las compras y se envían al cliente para el cumplimiento y procesamiento de pedidos.

## <a name="set-up-an-online-store"></a>Configurar una tienda en línea
Para configurar una tienda en línea, debe completar las tareas siguientes.

1.  Crear la tienda en línea.
2.  Agregue la tienda en línea a las jerarquías organizativas adecuadas.
3.  Agregue surtidos que incluyan los productos que están disponibles en la tienda en línea.
4.  Asigne o cree grupos de precios para la tienda en línea.
5.  Configure los modos de entrega disponibles para la tienda en línea.
6.  Asigne los métodos de pago que acepta la tienda en línea.
7.  Si permite a los compradores pedir productos en línea y recogerlos en una tienda local, asigne grupos de localizadores de tiendas a la tienda en línea.
8.  Asigne atributos para canales, productos y pedidos de ventas a la tienda en línea. Los atributos de canal se aplican a toda la tienda en línea, los atributos del producto se aplican a los productos que se ofrecen en la tienda en línea y los atributos de pedido de ventas se aplican a los pedidos de ventas que se generan desde la tienda en línea.
9.  Asigne los atributos para definir las propiedades que determinan el comportamiento de los atributos en la tienda en línea. Por ejemplo, los atributos se pueden definir como obligatorios o disponibles para la búsqueda.
10. Publique su tienda en línea para generar la estructura de tienda en la tienda en línea de terceros que elija. **Importante**: para poder publicar la tienda en línea, debe configurar una ubicación de distribución para ella.

## <a name="retail-channel-navigation-hierarchies"></a>Jerarquías de navegación de canales comerciales
Antes de crear una tienda en línea, debe definir la jerarquía de navegación de canales comerciales que desee usar en ella. La jerarquía de navegación de canales comerciales representa la jerarquía de categoría que se muestra en la tienda en línea después de la publicación del almacén. Cuando se publiquen catálogos de productos comerciales en la tienda en línea, los productos del catálogo se asignan a las categorías de la jerarquía de navegación de canales comerciales. Después los compradores usan la jerarquía para navegar por la tienda en línea.

## <a name="organization-hierarchies"></a>Jerarquías organizativas
Las jerarquías organizativas se usan para estructurar los canales comerciales. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio. Al configurar tiendas en línea, puede agregarlas a una jerarquía organizativa. A continuación, las tiendas comparten los datos que se usan para los surtidos, el reaprovisionamiento y los informes. Al crear una jerarquía organizativa, se le asigna un propósito. El propósito indica cómo se usa la jerarquía en la estructura comercial. Puede crear una jerarquía organizativa para sus operaciones de tienda y usarla para las selecciones, reabastecimientos e informes. También puede crear una jerarquía organizativa independiente para cada propósito. También puede crear varias jerarquías con el mismo propósito y asignar un canal independiente a cada una de ellas. Si tiene previsto publicar catálogos de productos comerciales en la tienda en línea, deberá, como mínimo, agregar la tienda en línea a una jerarquía organizativa para los surtidos. Los productos de un catálogo se seleccionan de los surtidos asignados a la tienda en línea. Cuando se publique el catálogo, el proceso de publicación compara las fechas de vigencia para el surtido asignado a la tienda en línea con los productos que se incluyen en el catálogo para determinar los productos que estarán disponibles en la tienda en línea.


