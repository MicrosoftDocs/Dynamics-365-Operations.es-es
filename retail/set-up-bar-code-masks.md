---
title: "Configuración de máscaras de código de barras"
description: "Este tema describe cómo configurar los caracteres de máscara de código de barras, máscaras de código de barras, y cómo asignar máscaras de código de barras a códigos de barras."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 958cac2e85ae7fa514f6f26cbb6178d8fdec9783
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017



---

# Configuración de máscaras de código de barras
<a id="set-up-bar-code-masks" class="xliff"></a>

[!include[banner](includes/banner.md)]


Este tema describe cómo configurar los caracteres de máscara de código de barras, máscaras de código de barras, y cómo asignar máscaras de código de barras a códigos de barras.

Configuración de los caracteres de máscara de código de barras
<a id="set-up-bar-code-mask-characters" class="xliff"></a>
-------------------------------

Los máscaras de código de barras se usan para crear códigos de barras e identificar rápidamente los códigos de barras que se procesan en el punto de venta (PDV). Las máscaras se componen de caracteres que actuarán como marcadores de posición que indican el formato para los códigos de barras que se crearán. Para configurar una máscara de código de barras, debe configurar los caracteres de máscara de código de barras. Vaya a **Venta minorista** &gt; **Gestión de inventarios** &gt; **Códigos de barras y etiquetas** &gt; **Caracteres de máscara**. Haga clic en **Nuevo** para crear caracteres de máscara de código de barras. Los caracteres de máscara se pueden crear para indicar los siguientes datos del código de barras.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Campo**            | **Descripción**                                                                                                 |
| **Producto**          | Marcador de posición para el identificador del producto.                                                                                     |
| **Un número cualquiera**       | Utilizado para especificar un número que se codificará en los códigos de barras.                                                  |
| **Dígito control**      | Indica que el formato de código de barras en una máscara de código de barras utiliza un dígito de control para confirmar la validez de un código de barras. |
| **Dígito tamaño**       | Indica el tamaño en un código de barras creado para una variante del producto que incluya el tamaño.                                 |
| **Dígito color**      | Indica el color en un código de barras creado para una variante del producto que incluya el color.                               |
| **Dígito estilo**      | Indica el estilo en un código de barras creado para una variante del producto que incluya el estilo.                             |
| **Código licencia EAN** | Marcador de posición para la licencia de EAN emitido para los códigos de licencia de EAN.                                                       |
| **Precio**            | Indica el precio para los códigos de barras insertados en el precio.                                                                   |
| **Cantidad**         | Indica cantidad en los códigos de barras insertados en el peso aleatoriamente o la cantidad.                                                |
| **Empleado**         | Indica el segmento de código de barras para el número de identificador de empleado utilizado para el inicio de sesión de PDV del código de barras.                                  |
| **Cliente**         | Indica el segmento del identificador de cliente.                                                                                  |
| **Entrada de datos**       | *No implementado todavía.*                                                                                          |
| **Código de descuento**    | *Despreciado*: a partir de la versión de primavera 2017 de Dynamics 365 for Retail. Anteriormente: indica el código de descuento para un código de barras que se usa para agregar un descuento a una transacción de punto de venta.                                                                   |
| **Código del vale**      | Indica el código de vale para un código de barras utilizado para agregar un descuento a un pedido de ventas al por menor. Este código sustituyó al código de descuento.     |
| **Tarjeta regalo**        | Indica un número de tarjeta regalo al emitir o pago con tarjeta regalo.                                               |
| **Tarjeta de fidelización**     | Agrega un cliente fidelizado a la transacción, y se puede usar para pagar por fidelidad.                             |

## Definición de máscaras de código de barras
<a id="define-bar-code-masks" class="xliff"></a>
Una vez que los caracteres de máscara de código de barras se especifiquen para las máscaras de código de barras necesarias, vaya a **Retail** &gt; **Gestión del inventario** &gt; **Códigos de barras y etiquetas** &gt; **Configuración de máscara de código de barras**. En esta página, puede definir máscaras de código de barras que usan los caracteres especificados anteriormente. Estas máscaras de códigos de barras se usarán al generar códigos de barras y nos ayudarán a identificar los códigos de barras examinados en el PDV.

1.  Haga clic en **Nuevo** para crear una máscara de código de barras nueva.
2.  Especifique los valores en el campo **Id. de máscara** y **Descripción** y seleccione un tipo de máscara de código de barras en el campo **Tipo**.
3.  En la sección **General**, seleccione un valor en el campo **Estándar de código de barras** y especifique el prefijo del código de barras, si se requiere uno.
4.  En la sección **Segmento de máscara de código de barras**, agregue los segmentos de código de barras que se usarán en el código de barras que se creará.

Como ejemplo, crear una máscara de código de barras con el identificador de máscara “Producto” puede hacer lo siguiente:

1.  Cree una nueva máscara de código de barras y seleccione el tipo “Producto”.
2.  Seleccione un estándar de código de barras; por ejemplo, "Código 39".
3.  Proporcione un prefijo que se utilizará para identificar fácilmente el código de barras. Por ejemplo, "22".
4.  Agregue un segmento de la máscara. El segmento de la máscara "Producto” se seleccionará.
5.  Proporcione una duración para el segmento de producto, por ejemplo, "10 ". La longitud debe coincidir con la duración de un identificador de producto de uso general en el almacén. La máscara se mostrará como vista previa en la sección **General** en **Máscara**.

## Asignar máscaras de códigos de barras a códigos de barras
<a id="assign-bar-code-masks-to-bar-codes" class="xliff"></a>
Las máscaras de códigos de barras se deben asignar a los códigos de barras antes de que se puedan usar. Si se sigue con el ejemplo anterior, para asignar la máscara de código de barras a un código de barras, haga lo siguiente:

1.  Vaya a **Administración de la organización** &gt; **Configurar** &gt; **Códigos de barras**. Haga clic en **Nuevo** para crear un código de barras nuevo.
2.  Especifique los valores en los campos **Código de barras** **Configuración** y **Configuración**.
3.  En la sección **General**, en el campo **Tipo de código de barras**, seleccione “Código 39”. En el campo **Id. de** **máscara**, seleccione la máscara "Producto" creada anteriormente.
4.  En **Tamaño** especifique "12 ".
5.  Haga clic en **Guardar**.

Ahora, la máscara de código de barras se podrá usar para crear códigos de barras para productos. Los pasos anteriores son ejemplos de cómo crear máscaras de código de barras para los productos, pero también muestra cómo crear máscaras de código de barras para cualquiera de los otros tipos de código de barras admitidos. Las máscaras de código de barras, los tipos, y las longitudes se deben ajustar para su uso en el entorno específico.




