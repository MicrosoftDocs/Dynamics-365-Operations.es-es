---
title: "Creación de un catálogo de centro de llamadas"
description: "Este artículo proporciona información general del proceso de crear un catálogo para un centro de llamadas."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 28aaa84c11a897b895b2a106ca5f0cd6168997b2
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

# Creación de un catálogo de centro de llamadas
<a id="create-a-call-center-catalog" class="xliff"></a>

[!include[banner](includes/banner.md)]


Este artículo proporciona información general del proceso de crear un catálogo para un centro de llamadas. 

En un centro de llamadas, puede usar los catálogos de productos comerciales para identificar los productos que desee ofrecer a los clientes. Los centros de llamadas usan normalmente catálogos impresos. El diseño y la producción de un catálogo impreso se gestiona fuera de Microsoft Dynamics 365 for Retail. Sin embargo, puede crear y almacenar un formulario digital de un catálogo con los mismos formularios que usa para configurar catálogos de venta al por mayor en línea. Antes de poder crear un catálogo, debe configurar las selecciones de productos y asignar las selecciones a un centro de llamadas. A continuación agrega productos al catálogo seleccionando los productos de estas selecciones. Después de agregar los productos al catálogo y de haberlo completado, debe validar el catálogo para comprobar los datos. A continuación, debe enviar el catálogo para su revisión y aprobación. Una vez aprobado el catálogo, es se puede publicar. Cuando se crea un catálogo de centro de llamadas, puede tomar una instantánea de los datos del catálogo en el momento en que el catálogo se publica. Esta función de la instantánea permite el acceso a una versión concreta del catálogo incluso si el catálogo se cambia y se actualiza más adelante. Los catálogos del centro de llamadas también se pueden configurar para incluir las características opcionales siguientes.

-   **Códigos de origen**: códigos que se utilizan para realizar un seguimiento de la respuesta del cliente a correos de catálogos particulares.
-   **Productos gratuitos**: productos incluidos en el pedido de un cliente sin ningún cargo adicional. Estos productos se agregan automáticamente al pedido cuando el código de origen del catálogo se especifica en el pedido.
-   **Scripts**: textos que un trabajador del centro de llamadas lee a un cliente cuando se crea un pedido de ventas. Las secuencias de comandos pueden incluir saludos o sugerencias de compras.
-   **Venta vertical o venta cruzada de artículos**: artículos que se muestran como sugerencia cuando se agrega un producto específico al pedido.

Estas opciones deben configurarse antes de aprobar y publicar el catálogo.

## Requisitos previos
<a id="prerequisites" class="xliff"></a>
Las siguientes tareas se deben realizar antes de comenzar:

-   Configure los productos y surtidos de productos.
-   Configure los productos comerciales.
-   Configure un surtido.
-   Cree un centro de llamadas.
-   Configure un centro de llamadas.
-   Agregue el centro de llamadas a una jerarquía organizativa.
-   Cree o modifique una jerarquía organizativa.

## Crear un catálogo
<a id="create-a-catalog" class="xliff"></a>
Primero debe crear un catálogo, agregar los productos al catálogo y luego revisar y actualizar los atributos de los productos.

## Validación del catálogo
<a id="validate-the-catalog" class="xliff"></a>
Una vez haya terminado de configurar el catálogo, debe validarlo. El proceso de validación comprueba que los datos necesarios para los atributos de canal y los atributos de producto son completos y válidos, y que el catálogo puede publicarse.

## Envío del catálogo para su revisión y aprobación
<a id="submit-the-catalog-for-review-and-approval" class="xliff"></a>
Cuando un catálogo se haya validado, puede enviarlo para su revisión y aprobación. Un catálogo debe aprobarse antes de que se pueda publicar. Puede configurar un flujo de trabajo de modo que los catálogos se aprueben automáticamente o requieran la aprobación manual.

## Opcional: agregar los códigos fuente, los productos gratuitos y las secuencias de comandos
<a id="optional-add-source-codes-free-products-and-scripts" class="xliff"></a>
También puede agregar los siguientes artículos a un catálogo del centro de llamadas. Estos artículos son opcionales.

-   Las empresas que ofrecen catálogos impresos pueden usar los **códigos de origen** para realizar un seguimiento de la respuesta del cliente a catálogos particulares. Los códigos de origen se imprimen en la parte de atrás desde un catálogo y se introducen en el pedido de ventas cuando un cliente realiza una compra. Para agregar un código de origen al catálogo, debe crear primero un mercado de destino. El mercado de destino se asigna normalmente a una lista de correo de su propiedad o alquilada.
-   Los **productos gratuitos** son artículos promocionales que se incluyen gratuitamente con el pedido del cliente cuando se hace referencia al catálogo.
-   Los **scripts** puede usarse para dirigir las interacciones del trabajador con los clientes en el contexto de un catálogo o de un producto dentro de un catálogo.

## Publicación del catálogo
<a id="publish-the-catalog" class="xliff"></a>
Al publicar un catálogo para un centro de llamadas, se finaliza la información de productos en el catálogo. La publicación también indica que el catálogo está listo para cualquier acción adicional que desee realizar. Por ejemplo, puede crear un catálogo impreso. Puede publicar los catálogos manualmente o usar un proceso por lotes para realizar publicaciones en función de una programación. Antes de que pueda publicar un catálogo, este se debe validar y aprobar. Para cambiar el catálogo después de su publicación, puede retraer el catálogo y volverlo a publicar.




