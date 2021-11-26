---
title: País de origen
description: Muchas organizaciones emiten certificados a sus proveedores para garantizar que los productos cumplan con estándares de certificación específicos. Estos certificados dependen a menudo del país de origen. Este tema proporciona información sobre la función del país de origen, lo que le permite vincular un producto a su país de origen y realizar un seguimiento de sus certificaciones de producto.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: a2740f6b1ccb52073b013e613d8ab779cc088180
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777647"
---
# <a name="country-of-origin"></a>País de origen

[!include [banner](../includes/banner.md)]

Muchas organizaciones emiten certificados a sus proveedores para garantizar que los productos cumplan con estándares de certificación específicos. Estos certificados dependen a menudo del país de origen. La característica de país de origen le permite vincular un producto a su país de origen y realizar un seguimiento de sus certificaciones de producto.

## <a name="turn-on-the-country-of-origin-feature"></a>Activar la característica de país de origen

A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla o deshabilitarla si es necesario. Aquí, la característica aparece como:

- **Módulo:** *Gestión de información de productos*
- **Nombre de la característica**: *Característica de administración del país de origen*

## <a name="configure-source-and-destination-countries"></a>Configurar países de origen y destino

Antes de emitir un certificado para un producto, debe vincular el producto a su país de destino y su país de origen.

1. Vaya a **Gestión de la información de productos \> Configuración \> Conformidad de producto \> País de origen \> Reglas del país de origen**.
2. Seleccione una configuración de país existente que quiera editar o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de país.
3. Establezca los siguientes valores para el país seleccionado o uno nuevo.

    | Campo | Descripción |
    |---|---|
    | código de artículo | Seleccione el número de artículo del producto. |
    | País de destino | Seleccione el país al que va a enviar el producto. |
    | País de origen | Seleccione el país desde el que va a enviar el producto. |

El propósito de esta configuración es ayudarle a generar un informe de lista de materiales (L. MAT) en el que puede incluir el país de origen de cada pieza para la que se especifican los países de origen y destino. Este informe le ayudará a obtener una vista integral de dónde provienen sus piezas y hacia dónde van.

## <a name="keep-track-of-vendor-certificates"></a>Mantener un seguimiento de los certificados de proveedor

Puede usar la página **Certificados de proveedores del país de origen** para realizar un seguimiento de los certificados que emite a los proveedores.

Debe decidir qué documentos de certificado está emitiendo y cómo informará de ellos a los clientes. Esta característica le ayuda a realizar un seguimiento de sus certificados. También le permite elegir si los números de certificado pertinentes aparecen en las facturas, albaranes o confirmaciones de pedidos.

Siga estos pasos para configurar su información del certificado.

1. Vaya a **Gestión de la información del producto \> Configuración \> Conformidad del producto \> País de origen \> Certificados de proveedores del país de origen**.
2. Seleccione una configuración de certificado existente para editarla o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de certificado.
3. Establezca la siguiente configuración para el certificado seleccionado o uno nuevo.

    | Campo | Descripción |
    |---|---|
    | Cuenta de proveedor | Seleccione el proveedor al que emitió el certificado. |
    | código de artículo | Seleccione artículo para el cual se emitió el certificado. |
    | País/región | El país o región de destino donde se debe usar este certificado. |
    | Número de certificado | Introduzca el número de identificación del certificado que emitió. |
    | Vigencia | Seleccione la primera fecha en la que el certificado actual es válido.|
    | Caducidad | Seleccione la última fecha en la que el certificado actual es válido. |
    | Imprimir en factura | Seleccione esta casilla para imprimir el número de certificado en las facturas que se dirigen al país especificado durante el intervalo de fechas indicado. |
    | Imprimir en albarán | Seleccione esta casilla para imprimir el número de certificado en los albaranes que se dirigen al país especificado durante el intervalo de fechas indicado. |
    | Imprimir en pedido de ventas | Seleccione esta casilla para imprimir el número de certificado en los pedidos de ventas que se dirigen al país especificado durante el intervalo de fechas indicado. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>Incluir el país de origen en los informes de listas de materiales

Cuando genera un informe de L. MAT, puede incluir el país de origen para cada una de las piezas para las que especificó países de origen y destino en la página **Reglas del país de origen**.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione o cree un producto para abrir su página **Detalles de producto**.
1. En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **L. MAT.**, seleccione **Diseñador**.
1. En la página que aparece, en el panel de acciones, seleccione **L. MAT \> Imprimir**.
1. En el cuadro de diálogo **Líneas de lista de materiales**, establezca el campo **País de destino** al país de destino que desea ver en su informe.
1. Seleccione **Aceptar**.

Se genera y muestra un informe con información sobre el país de origen de cada pieza. A continuación se muestra un ejemplo del informe.

![Informe del país de origen.](media/country-of-origin-report.png "Informe del país de origen")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]