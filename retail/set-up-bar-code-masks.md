---
title: "Configuración de máscaras de código de barras"
description: "Este tema describe cómo configurar los caracteres de máscara de código de barras, máscaras de código de barras, y cómo asignar a las máscaras de código de barras a los códigos de barras."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Configuración de máscaras de código de barras

Este tema describe cómo configurar los caracteres de máscara de código de barras, máscaras de código de barras, y cómo asignar a las máscaras de código de barras a los códigos de barras.

<a name="set-up-bar-code-mask-characters"></a>Configuración de los caracteres de máscara de código de barras
-------------------------------

Los máscaras de código de barras para crear códigos de barras e identificar rápidamente los códigos de barras que se procesan en el punto de venta (POS). Las máscaras se componen de caracteres que actuarán como marcadores de posición que indican el formato para los códigos de barras que se crearán. Para configurar una máscara de código de barras, debe configurar los caracteres de máscara de código de barras. ** Va al por menor y comercio ** &gt; ** gestión de inventario ** &gt; ** los códigos de barras y etiquetan ** &gt; ** los caracteres de máscara **. Haga clic en ** nuevo ** para crear los caracteres de máscara de código de barras. Los caracteres de máscara se pueden crear para indicar los siguientes datos del código de barras.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | Marcador para el identificador del producto.                                                                                     |
| **Any number**       | Utilizado para especificar un número que se codificado en Códigos de barras.                                                  |
| **Check digit**      | Indica que el formato de código de barras en una máscara de código de barras utiliza un dígito de control para confirmar la validez de un código de barras. |
| **Size digit**       | Indicar el tamaño en un código de barras creado para una variante del producto que incluya el tamaño.                                 |
| **Color digit**      | Indicar el color en un código de barras creado para una variante del producto que incluya color.                               |
| **Style digit**      | Indica estilo en un código de barras creado para una variante del producto que incluya un estilo.                             |
| **EAN license code** | Marcador para la licencia EAN de emitida para los códigos de licencia EAN de.                                                       |
| **Precio**            | Indica el precio para los códigos de barras insertados precio.                                                                   |
| **Quantity**         | Indica cantidad en la cantidad/actualizar códigos de barras insertados peso aleatoria.                                                |
| **Employee**         | Indica el segmento de código de barras para el número de identificador de empleado utilizado para el inicio de sesión de Retail POS del código de barras.                                  |
| **Customer**         | Indica el segmento el identificador de cliente.                                                                                  |
| ** Entrada de datos **       | *Not con todos implemented.*                                                                                          |
| **Discount code**    | Indica el descuento codificado para un código de barras que se usa para agregar un descuento en una transacción de punto de venta             |
| **Tarjeta regalo**        | Indica un número de tarjeta regalo al emitir o pago con tarjeta regalo.                                               |
| **Loyalty card**     | Agrega un cliente fidelizado a la transacción, y se puede usar para pagar por fidelidad.                             |

## <a name="define-bar-code-masks"></a>Defina las máscaras de código de barras
Una vez que los caracteres de máscara de código de barras se especifiquen por las máscaras de código de barras necesarias **, vaya al por menor y comercio ** &gt; ** gestión de inventario ** &gt; ** los códigos de barras y etiquetan ** &gt; ** máscara de código de barras configurar **. En esta página, puede definir máscaras de código de barras que usan los caracteres especificados anteriormente. Utilizará al generar códigos de barras y también ayudarán a estas máscaras de código de barras a identificar los códigos de barras procesan en el sistema POS.

1.  Haga clic en ** nuevo ** para crear una nueva máscara de código de barras.
2.  Especifique los valores en ** identificador de la máscara ** y ** descripción ** campos, y seleccione una máscara de código de barras escribir ** tipo ** el campo.
3.  En ** general ** la sección, seleccione un valor en ** estándar para el código de barras ** campo y, a continuación especifique el prefijo del código de barras, si se requiere uno.
4.  En ** segmento de la máscara de código de barras ** la sección, agregue los segmentos de código de barras que se usarán en el código de barras que se creará.

Como ejemplo, crear una máscara de código de barras con el identificador “” producto de máscara, puede hacer lo siguiente:

1.  Cree una nueva máscara de código de barras y seleccione el tipo “” producto.
2.  Seleccione un estándar para el código de barras, por ejemplo, “Código 39”.
3.  Proporcione un prefijo que se utilizará identificar fácilmente el código de barras. Por ejemplo, “22 ".
4.  Agregar un segmento de la máscara. El segmento de la máscara de producto “” estará seleccionado.
5.  Proporcione una duración para el segmento de producto, por ejemplo, "10 ". La longitud debe coincidir con la duración de un identificador de producto de uso general en el almacén. La máscara se mostrará como vista previa en ** general ** la sección en ** máscara **.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Máscaras de códigos de barras a los códigos de barras
Las máscaras de códigos de barras se deben asignar a los códigos de barras antes de que se puedan usar. Si se sigue con el ejemplo anterior, asignar a la máscara de código de barras a un código de barras, haga lo siguiente:

1.  Retroceda ** Administración de organización ** &gt; ** la configuración ** &gt; ** los códigos de barras **. Haga clic en ** nuevo ** para crear un nuevo código de barras.
2.  Especifique los valores en ** código de barras ** ** ** configuración y ** configuración ** campos.
3.  ** En general, Idiomas ** en ** tipo de código de barras ** campo, seleccione “Código 39”. En ** máscara ** ** el identificador ** campo, seleccione la máscara de producto “” creada anteriormente.
4.  En ** ** tamaño, especifique "12 ".
5.  Click **Save**.

La máscara de código de barras podrá usar para crear los códigos de barras para los productos. Los pasos anteriores son ejemplos de cómo crear máscaras de código de barras para los productos, pero también muestra cómo crear máscaras de código de barras para cualquiera de los otros tipos de código de barras admitidos. Las máscaras de código de barras, los tipos, y las longitudes se deben ajustar para su uso en el entorno específico.


