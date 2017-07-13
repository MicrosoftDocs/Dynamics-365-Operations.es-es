---
title: Definir y mantener canales comerciales
description: "Este artículo proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas minoristas en Microsoft Dynamics 365 for Retail. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda minorista."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 3f0b566963574569cb40b72550e2337c9ba8a2ce
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017


---

# Definir y mantener canales comerciales
<a id="define-and-maintain-retail-channels" class="xliff"></a>

[!include[banner](includes/banner.md)]


Este artículo proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas minoristas en Microsoft Dynamics 365 for Retail. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda minorista.

Dynamics 365 for Retail admite varios canales de venta, como tiendas en línea, centros de llamadas y almacenes físicos. Las tiendas físicas también se denominan tiendas minoristas. Cada tienda minorista puede tener sus propios métodos de pago, grupos de precios, puntos de venta (PDV), cuentas de ingresos y gastos o personal. Debe configurar todos estos elementos para una tienda antes de crearla. Después de crear la tienda, se asignan los productos que desea que tenga. También asigna empleados, cajas registradoras y clientes a la tienda. Por último, la nueva tienda se agrega a una jerarquía organizativa.

## Configurar tiendas
<a id="setting-up-retail-stores" class="xliff"></a>
Antes de poder configurar una tienda minorista en Dynamics 365 for Retail, debe completar algunas de las tareas de requisitos previos. A continuación, puede crear la tienda y agregar detalles.

### Requisitos previos
<a id="prerequisites" class="xliff"></a>

Para poder configurar una tienda, debe completar las siguientes tareas:

1.  Configure la estructura de la organización y las jerarquías organizativas para las selecciones comerciales, el reabastecimiento y los informes.
2.  Configure un almacén que represente la tienda.
3.  Configure las secuencias numéricas para las tiendas minoristas, los extractos de tienda y los comprobantes del extracto.
4.  Configure parámetros para Venta minorista.
5.  Configure los métodos de pago que acepta la tienda.
6.  Para procesar transacciones de tarjeta de crédito en los registros de PDV, también puede configurar servicios de pago.
7.  Configure los grupos de impuestos.
8.  Configure los productos comerciales. Como parte de esta tarea, también configura jerarquías de productos comerciales, variantes del producto y surtidos de producto.
9.  Configure los grupos de precios de producto.
10. Configure los precios de producto comercial. Como parte de esta tarea, también configura ajustes de precios, descuentos y períodos de descuento.
11. Configure los empleados. **Nota:** También debe asignar los permisos adecuados a los trabajadores, de modo que puedan iniciar sesión y realizar tareas con el sistema de Dynamics 365 for Retail POS.
12. Configure los perfiles de Retail POS que se deben asignar a la tienda. Esta tarea incluye muchas otras tareas, por ejemplo, la configuración de los registros, los perfiles sin conexión y los formatos y perfiles de recepción.

Revise todas las tareas que se incluyen en el requisito previo y complete solo las tareas que se aplican a su caso.

### Configurar una tienda comercial
<a id="set-up-a-retail-store" class="xliff"></a>

Tras completar las tareas de requisito previo, complete estas tareas para configurar los detalles de la tienda minorista:

1.  Cree una nueva tienda.
2.  Asigne un grupo de impuestos a la tienda.
3.  Asigne los métodos de pago aceptados a la tienda.
4.  Agregue detalles a las descripciones de producto para los productos que ofrece en las tiendas comerciales. Por ejemplo, puede agregar texto enriquecido e imágenes. Estos detalles de producto aparecen en distintos contextos, por ejemplo, en el registro de PDV o en etiquetas impresas.
5.  Agregue la tienda a una jerarquía organizativa predeterminada que está asignada a una finalidad de **Selección comercial**, **Reabastecimiento comercial** o **Informes comerciales**.

### Después de configurar una tienda minorista
<a id="after-you-set-up-a-retail-store" class="xliff"></a>

Tras especificar los detalles de la tienda minorista, complete estas tareas para enviar los datos de la nueva tienda minorista a Retail POS:

1.  Configure los registros de PDV para la tienda.
2.  Asigne los surtidos del producto a la tienda.
3.  Procese los surtidos para generar la lista de productos incluidos en el surtido y para hacer que los productos estén disponibles en la tienda minorista.
4.  Envíe datos como, por ejemplo, secuencias numéricas, perfiles de hardware y diseños de pantalla de PDV a los registros de Retail POS.
5.  Publique la tienda comercial para enviar datos de tienda a Retail POS.
6.  Ejecute los trabajos para enviar los datos de tienda a Retail POS.

## Jerarquías organizativas
<a id="organization-hierarchies" class="xliff"></a>
Retail usa jerarquías organizativas para estructurar los canales comerciales. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio. Al configurar tiendas, puede agregarlas a una jerarquía organizativa. A continuación, los almacenes comparten los datos que se usan para las selecciones, el reaprovisionamiento y los informes.




