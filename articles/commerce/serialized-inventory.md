---
title: Mejoras en el punto de venta (PDV) para productos serializados
description: En este tema se muestran las mejoras que se han realizado en los productos serializados para que pueda ahorrar tiempo y ser más productivo.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bf3a6a2b713e5fe1fe22ae886080945e7a87c9b2
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023960"
---
# <a name="point-of-sale-pos-improvements-for-serialized-products"></a>Mejoras en el punto de venta (PDV) para productos serializados

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Visión general

Según la configuración de Commerce Headquarters, los productos se pueden clasificar como serializados o no serializados. Cuando se serializan los productos, cada artículo se puede asignar un número único que le permite hacer un seguimiento de las garantías, los artículos y confirmar la propiedad. Aunque la capacidad para proporcionar los números de serie de los productos existía en los PDV modernos o en la nube, se han agregado algunas mejoras para que los cajeros puedan ahorrar tiempo y ser más productivos.

## <a name="pos-improvements"></a>Mejoras de PDV

- **Los números de serie no se solicitan hasta el fin de la transacción**: antes un cajero que añadía un producto serializado a la transacción necesitaba escribir el número de serie. Este requisito se convirtió en un problema en las situaciones relacionadas con los clientes, si los cajeros y los ayudantes de ventas tenían la oportunidad de realizar una venta vertical de productos. Hasta el paso en el que se realizaba el pago, los productos se actualizaban a menudo en el carro. Debido a ello, cada vez que el cajero tenía que agregar un nuevo producto, el sistema le pedía que añadiera el número de serie. El cuadro de diálogo del número de serie ahora incluye un botón **Agregar más adelante**. Por lo tanto, los ayudantes de ventas pueden agregar el artículo a la transacción pero pueden escribir el número de serie más adelante. Igualmente, los ayudantes de ventas pueden agregar y reemplazar artículos serializados en el carro y proporcionar el número de serie justo antes de realizar la venta. Si no se proporciona el número de serie de ningún producto serializado, el cajero que intente completar la transacción recibirá un mensaje de error. Este mensajes indica al cajero que debe proporcionar los números de serie que faltan antes de poder continuar.

    Para cada artículo serializado donde el número de serie se ha omitido, aparecerá un comentario en la línea de transacción. Este comentario indica que no se proporcionó el número de serie del artículo. Por lo tanto, el cajero puede buscar rápidamente los artículos a los que les falta el número de serie.

    La nueva operación **Agregar número de serie** también proporciona el número de serie de los artículos a los cuales les falta el mismo. Una vez proporcionado el número de serie, no se puede editar. El cajero debe anular la línea y agregar el producto de nuevo.
    
- **Los números de serie no son necesarios para realizar pedidos de cliente**: los pedidos de cliente se pueden realizar en una tienda y cerrar en otra. Un cajero que realiza un pedido de cliente no tiene por qué proporcionar el número de serie. Este número se proporciona durante el paso de selección o de recogida. Sin embargo, se debe proporcionar el número de serie de todos los artículos de línea en los cuales se seleccionó el tipo de entrega **Ejecutar**. Si no, la transacción no se podrá completar.
- **Los productos serializados no se agregan en la pantalla de la transacción**: la configuración **Productos agregados** del grupo de campo **Terminal** en la página **Perfil de funcionalidad** le permite agregar los mismos productos no serializados en la pantalla de la transacción. Cuando se agregan los mismos productos, estos son fáciles de ver en la cuadrícula de la transacción. Sin embargo, ya que los números de serie suelen ser únicos y como los ayudantes de ventas no tienen que escribir los números de serie hasta que no finaliza la transacción, la configuración **Productos agregados** no se aplica a los productos serializados. Así pues, los productos serializados no se agregarán en la pantalla de la transacción si la opción de configuración **Productos agregados** está seleccionada.
- **Capacidad de buscar los diarios según el número de serie** - Los diarios se pueden buscar ahora por los números de serie. Para ello, abra la operación "Diarios" y presione el botón de "Búsqueda avanzada" en la barra de la aplicación. Mediante el botón "Agregar filtro", se puede aplicar un filtro para buscar números de serie también.
