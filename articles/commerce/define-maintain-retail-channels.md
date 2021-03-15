---
title: Definir y mantener canales comerciales
description: Este tema proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas en Dynamics 365 Commerce. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51524ad6918d962d70a8a700f135f96e236f7d34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000884"
---
# <a name="define-and-maintain-retail-channels"></a>Definir y mantener canales comerciales

[!include [banner](includes/banner.md)]

Este tema proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas en Dynamics 365 Commerce. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda.

Commerce admite varios canales, como tiendas en línea, almacenes físicos y centros de llamadas. Las tiendas físicas también se denominan tiendas. Cada tienda puede tener sus propios métodos de pago, grupos de precios, puntos de venta (PDV), cuentas de ingresos y gastos o personal. Debe configurar todos estos elementos para una tienda antes de crearla. Después de crear la tienda, se asignan los productos que desea que tenga. También asigna empleados, cajas registradoras y clientes a la tienda. Por último, la nueva tienda se agrega a una jerarquía organizativa.

## <a name="setting-up-stores"></a>Configurar tiendas

Antes de poder configurar una tienda en Commerce, debe completar algunas de las tareas de requisitos previos. A continuación, puede crear la tienda y agregar detalles.

### <a name="prerequisites"></a>Requisitos previos

Para poder configurar una tienda, debe completar las siguientes tareas:

1. Configure la estructura de la organización y las jerarquías organizativas para las selecciones comerciales, el reabastecimiento y los informes.
2. Configure un almacén que represente la tienda.
3. Configure las secuencias numéricas para las tiendas, los extractos de tienda y los comprobantes del extracto.
4. Configurar parámetros para Commerce.
5. Configure los métodos de pago que acepta la tienda.
6. Para procesar transacciones de tarjeta de crédito en los registros de PDV, también puede configurar servicios de pago.
7. Configure los grupos de impuestos.
8. Configurar productos. Como parte de esta tarea, también configura jerarquías de productos, variantes del producto y surtidos de producto.
9. Configure los grupos de precios de producto.
10. Configure el precio del producto. Como parte de esta tarea, también configura ajustes de precios, descuentos y períodos de descuento.
11. Configure los empleados.

    > [!NOTE]
    > También debe asignar los permisos adecuados a los trabajadores, de modo que puedan iniciar sesión y realizar tareas con el sistema PDV.

12. Configure los perfiles de PDV que se deben asignar a la tienda. Esta tarea incluye muchas otras tareas, por ejemplo, la configuración de los registros, los perfiles sin conexión y los formatos y perfiles de recepción.

Revise todas las tareas que se incluyen en los requisitos previos y complete solo las tareas que se aplican a su caso.

### <a name="set-up-a-store"></a>Configurar una tienda

Tras completar las tareas de requisito previo, complete estas tareas para configurar los detalles de la tienda:

1. Cree una tienda.
2. Asigne un grupo de impuestos a la tienda.
3. Asigne los métodos de pago aceptados a la tienda.
4. Agregue detalles a las descripciones de producto para los productos que ofrece en las tiendas. Por ejemplo, puede agregar texto enriquecido e imágenes. Estos detalles de producto aparecen en distintos contextos, por ejemplo, en el registro de PDV o en etiquetas impresas.
5. Agregue la tienda a la jerarquía organizativa predeterminada que está asignada a una finalidad de **Selección comercial**, **Reabastecimiento comercial** o **Informes comerciales**.

### <a name="after-you-set-up-a-store"></a>Después de configurar una tienda

Tras especificar los detalles de la tienda, complete estas tareas para enviar los datos de la nueva tienda minorista a PDV.

1. Configure los registros de PDV para la tienda.
2. Asigne los surtidos del producto a la tienda.
3. Procese los surtidos para generar la lista de productos incluidos en el surtido y para hacer que los productos estén disponibles en la tienda.
4. Envíe datos como, por ejemplo, secuencias numéricas, perfiles de hardware y diseños de pantalla de PDV a los registros de PDV.
5. Publique la tienda para enviar datos de tienda a PDV.
6. Ejecute los trabajos para enviar los datos de tienda a PDV.

## <a name="organization-hierarchies"></a>Jerarquías organizativas

Commerce usa jerarquías organizativas para estructurar los canales. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio. Al configurar tiendas, puede agregarlas a una jerarquía organizativa. A continuación, los almacenes comparten los datos que se usan para las selecciones, el reaprovisionamiento y los informes.

> [!NOTE]
> Para usar la funcionalidad de ventas de Commerce, la clave de configuración **Envíos múltiples** debe estar habilitada. Esta clave de configuración se puede encontrar en las claves **Configuración de comercio** en **Administración del sistema**\> **Configuración** \> **Configuración de licencia**. Esto es necesario debido a que realiza diversas validaciones en función de la dirección de entrega configurada en el nivel de línea del pedido de ventas.



[!INCLUDE[footer-include](../includes/footer-banner.md)]