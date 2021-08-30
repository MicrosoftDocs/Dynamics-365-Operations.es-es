---
title: Configuración de máscaras de código de barras
description: Este tema describe cómo configurar los caracteres de máscara de código de barras, máscaras de código de barras, y cómo asignar máscaras de código de barras a códigos de barras.
author: rubencdelgado
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7004ed901bd4bcac0dab4fede9cf793fd05c3af7796006fb5b089f257f81208e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731578"
---
# <a name="set-up-bar-code-masks"></a>Configuración de máscaras de código de barras

[!include [banner](includes/banner.md)]

Este tema describe cómo configurar los caracteres de máscara de código de barras, máscaras de código de barras, y cómo asignar máscaras de código de barras a códigos de barras.

## <a name="set-up-bar-code-mask-characters"></a>Configuración de los caracteres de máscara de código de barras

Los máscaras de código de barras se usan para crear códigos de barras e identificar rápidamente los códigos de barras que se procesan en el punto de venta (PDV). Las máscaras se componen de caracteres que actuarán como marcadores de posición que indican el formato para los códigos de barras que se crearán. Para configurar una máscara de código de barras, debe configurar los caracteres de máscara de código de barras. Vaya a **Retail y Commerce** &gt; **Gestión de inventarios** &gt; **Códigos de barras y etiquetas** &gt; **Caracteres de máscara**. Haga clic en **Nuevo** para crear caracteres de máscara de código de barras. Los caracteres de máscara se pueden crear para indicar los siguientes datos del código de barras.

| Campo            | Descripción |
|------------------|-------------|
| Producto          | Marcador de posición para el identificador del producto. |
| Un número cualquiera       | Utilizado para especificar un número que se codificará en los códigos de barras. |
| Dígito control      | Indica que el formato de código de barras en una máscara de código de barras utiliza un dígito de control para confirmar la validez de un código de barras. |
| Dígito tamaño       | Indica el tamaño en un código de barras creado para una variante del producto que incluya el tamaño. |
| Dígito color      | Indica el color en un código de barras creado para una variante del producto que incluya el color. |
| Dígito estilo      | Indica el estilo en un código de barras creado para una variante del producto que incluya el estilo. |
| Código licencia EAN | Marcador de posición para la licencia de EAN emitido para los códigos de licencia de EAN. |
| Precio            | Indica el precio para los códigos de barras insertados en el precio. |
| Cantidad         | Indica cantidad en los códigos de barras insertados en el peso aleatoriamente o la cantidad. |
| Empleado         | Indica el segmento de código de barras para el número de identificador de empleado utilizado para el inicio de sesión de PDV del código de barras. |
| Cliente          | Indica el segmento del identificador de cliente. |
| Entrada de datos       | *No implementado todavía.* |
| Código de descuento    | *Desusado* desde la versión de la primavera de 2017 de Dynamics 365 for Retail. Anteriormente: indica el código de descuento para un código de barras que se usa para agregar un descuento a una transacción de punto de venta. |
| Código del vale      | Indica el código de vale para un código de barras utilizado para agregar un descuento a un pedido. Este código sustituyó al código de descuento. |
| Tarjeta regalo        | Indica un número de tarjeta regalo al emitir o pago con tarjeta regalo. |
| Tarjeta de fidelización     | Agrega un cliente fidelizado a la transacción, y se puede usar para pagar por fidelidad. |

## <a name="define-bar-code-masks"></a>Definición de máscaras de código de barras

Una vez que los caracteres de máscara de código de barras se especifiquen para las máscaras de código de barras necesarias, vaya a **Retail y Commerce** &gt; **Gestión del inventario** &gt; **Códigos de barras y etiquetas** &gt; **Configuración de máscara de código de barras**. En esta página, puede definir máscaras de código de barras que usan los caracteres especificados anteriormente. Estas máscaras de códigos de barras se usarán al generar códigos de barras y nos ayudarán a identificar los códigos de barras examinados en el PDV.

1. Haga clic en **Nuevo** para crear una máscara de código de barras nueva.
2. Especifique los valores en el campo **Id. de máscara** y **Descripción** y seleccione un tipo de máscara de código de barras en el campo **Tipo**.
3. En la sección **General**, seleccione un valor en el campo **Estándar de código de barras** y especifique el prefijo del código de barras, si se requiere uno.
4. En la sección **Segmento de máscara de código de barras**, agregue los segmentos de código de barras que se usarán en el código de barras que se creará.

Como ejemplo, crear una máscara de código de barras con el identificador de máscara “Producto” puede hacer lo siguiente:

1. Cree una nueva máscara de código de barras y seleccione el tipo “Producto”.
2. Seleccione un estándar de código de barras; por ejemplo, "Código 39".
3. Proporcione un prefijo que se utilizará para identificar fácilmente el código de barras. Por ejemplo, "22".
4. Agregue un segmento de la máscara. El segmento de la máscara "Producto” se seleccionará.
5. Proporcione una duración para el segmento de producto, por ejemplo, "10". La longitud debe coincidir con la duración de un identificador de producto de uso general en el almacén. La máscara se mostrará como vista previa en la sección **General** en **Máscara**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Asignar máscaras de códigos de barras a códigos de barras

Las máscaras de códigos de barras se deben asignar a los códigos de barras antes de que se puedan usar. Si se sigue con el ejemplo anterior, para asignar la máscara de código de barras a un código de barras, haga lo siguiente:

1. Vaya a **Administración de la organización** &gt; **Configurar** &gt; **Códigos de barras**. Haga clic en **Nuevo** para crear un código de barras nuevo.
2. Especifique los valores en los campos **Código de barras** **configuración** y **Configuración**.
3. En la sección **General**, en el campo **Tipo de código de barras**, seleccione “Código 39”. En el campo **Id. de** **máscara**, seleccione la máscara "Producto" creada anteriormente.
4. En **Tamaño** especifique "12 ".
5. Haga clic en **Guardar**.

Ahora, la máscara de código de barras se podrá usar para crear códigos de barras para productos. Los pasos anteriores son ejemplos de cómo crear máscaras de código de barras para los productos, pero también muestra cómo crear máscaras de código de barras para cualquiera de los otros tipos de código de barras admitidos. Las máscaras de código de barras, los tipos, y las longitudes se deben ajustar para su uso en el entorno específico.


[!INCLUDE[footer-include](../includes/footer-banner.md)]