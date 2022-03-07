---
title: Bienes de doble uso
description: En este tema se explica cómo realizar un seguimiento de productos identificados como de bienes de doble uso, almacenar números de certificados para cada producto relevante y país de destino, e imprimir números de certificados validos en facturas relevantes, albaranes y/o pedidos de ventas.
author: dasani-madipalli
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COODualUseCerts, COORules, COODualUseCountries
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 15e8696b2bfa9f1df3cecd2d98b9ad2f6c5d6000
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829483"
---
# <a name="dual-use-goods"></a>Bienes de doble uso

[!include [banner](../includes/banner.md)]

Los bienes de doble uso normalmente son artículos que tienen aplicaciones tanto civiles como militares. Por ejemplo, un producto químico puede usarse como fertilizante o como explosivo. Muchos países tienen normativas especiales que se aplican a la exportación, la importación y el transporte de bienes de doble uso. Por lo tanto, es importante que las empresas que participan en el comercio internacional de bienes de doble uso realicen un seguimiento de las distintas directivas y certificados.

La función de doble uso ayuda a las compañías a realizar un seguimiento de los productos identificados como de doble uso, a almacenar números de certificados para cada producto relevante y país de destino, y a imprimir números de certificados validos en facturas, albaranes y/o pedidos de ventas relevantes. Ayuda a garantizar que, cuando se envíen sus productos, siempre incluyan certificados actualizados.

Considere el siguiente escenario:

1. La página **Configuración de país de doble uso** de su sistema indica que los envíos a Francia requieren una certificación.
2. La página **Detalles de producto emitido** para el producto X-100 indica que es un bien de doble uso. Juntos, el código, la categoría, el grupo y el régimen indican la clasificación de control de exportación a la que pertenece el producto.
3. La página **Certificados de doble uso** incluye un certificado para el producto X-100 cuando se envía a Francia. Este certificado vence el 1 de enero de 2020.
4. El 17 de junio de 2020, usted crea un pedido de venta para una empresa cliente con sede en Francia, y el pedido contiene el producto X-100.
5. Cuando guarda el pedido de cliente, el sistema determina la siguiente información:

    1. ¿El pedido incluye algún bien que sea de doble uso?
    2. Si el pedido incluye bienes de doble uso, ¿el país de destino requiere certificados de doble uso?
    3. Si el país requiere certificados de doble uso, ¿existe un certificado válido para cada bien de doble uso para el país de destino?

6. El pedido incluye el producto X-100, que se va a enviar a Francia, y existe un certificado francés para el producto. Sin embargo, el certificado ha caducado. Por lo tanto, recibirá el siguiente mensaje de advertencia: "Los certificados de doble uso para uno o más artículos de doble uso en este pedido de ventas no son válidos. ¿Desea continuar con la confirmación? "

En este tema se explica cómo establecer todos los parámetros necesarios para configurar productos de doble uso y admitir este escenario.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>Definir requisitos de doble uso para cada país relevante

Diferentes países tienen diferentes requisitos para bienes de doble uso. Use la página **Configuración de país de doble uso** para realizar un seguimiento de los países que requieren y los que no requieren un certificado. La información que especifique aquí se verifica cuando crea pedidos de ventas, y se le recordará que introduzca las certificaciones requeridas.

Para configurar la información sobre los requisitos de doble uso para diferentes países, siga estos pasos.

1. Vaya a **Gestión de la información del producto \> Configuración \> Cumplimiento de producto \> Productos de doble uso \> Configuración de país de doble uso**.
2. Seleccione una configuración de país existente para editarla o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de país.
3. Establezca los siguientes valores para la configuración del país seleccionada o una nueva.

    | Campo | Descripción |
    |---|---|
    | País/región | Seleccione el país para el que vaya a realizar un seguimiento de requisitos. |
    | Certificado requerido | Seleccione esta casilla para los países que requieren una certificación para productos de doble uso. Desactívela para los países que no la requieran. |

## <a name="create-dual-use-categories"></a>Crear categorías de doble uso

A menudo, los bienes de doble uso deben clasificarse según su número de clasificación de control de exportación (ECCN). El ECCN es un código alfanumérico que clasifica los artículos en función de factores como la mercancía y la tecnología. La página **Categorías de doble uso** le ayuda a hacer una lista de las categorías que utiliza, con fines informativos.

Siga estos pasos para configurar categorías de doble uso:

1. Vaya a **Gestión de la información del producto \> Configuración \> Cumplimiento de producto \> Bienes de doble uso \> Categorías de doble uso**.
2. Seleccione una categoría existente para editarla o seleccione **Nuevo** en el Panel de acciones para crear una nueva categoría.
3. Establezca los siguientes valores para la categoría seleccionada o una nueva.

    | Campos | Descripción |
    |---|---|
    | Código de doble uso | Introduzca el código ECCN completo (por ejemplo, *3A001*).|
    | Categoría de doble uso | Introduzca la parte de la categoría del código de comercio (CCL) del código ECCN. Por ejemplo, para el código ECCN *3A001*, el valor es *3*. |
    | Grupo de doble uso | Introduzca la parte del grupo de productos del código ECCN. Por ejemplo, para el código ECCN *3A001*, el valor es *A*. |
    | Régimen de doble uso | Especifique el código del régimen para el artículo. Este código identifica la razón por la cual el artículo se clasifica como un bien de doble uso. Por ejemplo, para el código ECCN *3A001*, el valor es *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Aplicar categorías de doble uso a los productos

Para identificar un producto como un bien de doble uso y aplicarle una categoría de doble uso, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione o cree un producto para abrir su página **Detalles de producto**.
1. En la ficha desplegable **Comercio exterior**, configure la opción **Productos de doble uso** en **Sí** para identificar el producto actual como un bien de doble uso.
1. Establezca el campo **Código de doble uso** en el código que se aplique al producto actual. (Ha definido este código en la página **Categorías de doble uso**.)

Esta configuración se verifica cuando crea un pedido de ventas.

## <a name="set-up-dual-use-certificates"></a>Configurar certificados de doble uso

Use la página **Certificados de doble uso** para configurar y administrar los certificados de doble uso necesarios para cada producto y país. Puede realizar un seguimiento de los detalles de cada certificado, como el país y las fechas de validez. También puede establecer opciones para especificar dónde se debe imprimir esta información. Por ejemplo, la información puede imprimirse en la factura, albarán o pedido de venta. Esta configuración se verifica cuando crea un pedido de ventas.

1. Vaya a **Gestión de la información del producto \> Configuración \> Cumplimiento de producto \> Bienes de doble uso \> Certificados de doble uso**.
2. Seleccione un certificado existente para editarlo o seleccione **Nuevo** en el Panel de acciones para crear un nuevo certificado.
3. Establezca los siguientes valores para el certificado seleccionado o uno nuevo.

    | Campo | Descripción |
    |---|---|
    | código de artículo | Seleccione el número de artículo del bien de doble uso al que se aplica este certificado. |
    | País/región | El país o región de destino donde se debe usar este certificado. |
    | Número de certificado | El número que aparece en el certificado que se emite al proveedor o cliente. |
    | Vigencia | Seleccione la primera fecha en la que el certificado actual es válido.|
    | Caducidad | Seleccione la última fecha en la que el certificado actual es válido. |
    | Imprimir en factura | Seleccione esta casilla para imprimir el número de certificado en las facturas que se dirigen al país especificado durante el intervalo de fechas indicado. |
    | Imprimir en albarán | Seleccione esta casilla para imprimir el número de certificado en los albaranes que se dirigen al país especificado durante el intervalo de fechas indicado. |
    | Imprimir en pedido de ventas | Seleccione esta casilla para imprimir el número de certificado en los pedidos de ventas que se dirigen al país especificado durante el intervalo de fechas indicado. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]