---
title: Mostrar descuentos en PDV
description: Este tema explica cómo Microsoft Dynamics 365 Commerce ayuda a los asociados de ventas a conocer las promociones y cómo se pueden usar para las ventas cruzadas y las ventas adicionales.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 07/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: 3934390b86f821233c2620405e316cf732b3d7bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230625"
---
# <a name="show-discounts-in-pos"></a>Mostrar descuentos en PDV

[!include [banner](includes/banner.md)]

Las promociones juegan un papel importante en motivar a los clientes que toman decisiones de compra. Por ejemplo, las vacaciones pueden producir el mayor número de ventas para los minoristas, porque todo el mercado minorista está inundado de atractivas promociones y descuentos. Si los asociados de la tienda conocen y entienden las promociones disponibles, pueden aprovechar fácilmente esas promociones para realizar ventas cruzadas y ventas adicionales. Este tema explica cómo Microsoft Dynamics 365 Commerce ayuda a los asociados de ventas a conocer las promociones y cómo se pueden usar para las ventas cruzadas y las ventas adicionales.

## <a name="learn-about-store-discounts"></a>Aprenda sobre descuentos en tiendas

Commerce incluye una operación que se denomina "Ver todos los descuentos". Esta operación muestra todos los descuentos que se están ejecutando actualmente en una tienda. La operación "Ver todos los descuentos" se puede asignar a un botón en el punto de venta (PDV), y ese botón se puede agregar a la página **Bienvenido** o **Transacción**. La ilustración siguiente muestra un ejemplo de la página **Todos los descuentos** que está abierta.

![Página todos los descuentos](./media/View_all_discounts.png "Página todos los descuentos")

Para mostrar descuentos, el sistema busca todos los descuentos que coincidan con una o más de las siguientes condiciones:

- El grupo de precios del descuento coincide con el grupo de precios de la tienda.
- El grupo de precios del descuento se asigna a un programa de fidelización o afiliación.
- El grupo de precios del descuento se asigna a un catálogo asociado con la tienda.

La página **Todos los descuentos** muestra solo algunos descuentos basados en cupones, ya que los minoristas suelen crear miles de cupones y descuentos correspondientes para clientes únicos, y esta página no pretende mostrar descuentos específicos para clientes. Los descuentos basados en cupones se muestran solo si la opción **Aplicar sin un código de cupón** está activada en cada encabezado de cupón. En ese caso, los cajeros pueden aplicar el cupón sin tener que introducir o escanear ningún código de cupón o código de barras.

Cuando la opción **Aplicar sin un código de cupón** está activada, hay varios escenarios disponibles. Por ejemplo, los cajeros pueden ofrecer descuentos adicionales a los clientes para fines de apaciguamiento del cliente o por defectos del producto. Los códigos de cupones o códigos de barras impresos no tienen que distribuirse a los cajeros. En cambio, los cajeros pueden seleccionar el botón **Aplicar cupón**. El cupón se aplica automáticamente a la transacción. Si existen varios cupones para un encabezado de cupón, el sistema selecciona automáticamente el primer cupón activo en la transacción.

En la página **Todos los descuentos**, los asociados de ventas también pueden buscar descuentos por palabras clave. La búsqueda de palabras clave se ve en los campos que contienen el nombre y la descripción del descuento. Los asociados de ventas también pueden filtrar descuentos en función de si un descuento requiere un código de cupón.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Venta cruzada y ventas adicionales mediante el uso de descuentos

Los descuentos multilínea, como los descuentos por cantidad, los descuentos mixtos y los descuentos por umbral, son una excelente manera de motivar a los clientes a comprar más productos para obtener mayores descuentos. Por lo tanto, también ayudan a aumentar el tamaño del carrito de un cliente y los ingresos del minorista. Estos descuentos pueden publicarse en sitios web de comercio electrónico, en redes sociales y en pancartas en la tienda.

Sin embargo, incluso cuando se utilizan todos estos métodos de publicidad, los clientes pueden perder la oportunidad de aprovechar las promociones. Para facilitar que los asociados de ventas sepan qué promociones son aplicables a una línea seleccionada, o incluso a todo el carrito, los minoristas pueden agregar el botón para la operación **"Ver descuentos disponibles"** a la cuadrícula de botones de la página **Transacción**. De esta manera, un asociado de ventas puede seleccionar una línea de transacciones y luego seleccionar el botón para mostrar todos los descuentos disponibles para la línea seleccionada. El asociado de ventas también puede seleccionar otra pestaña para mostrar los descuentos que se aplican a toda la transacción. Es importante observar que **Ver descuentos disponibles** no muestra los descuentos que ya se aplican en la línea de ventas porque la información de descuento ya se muestra en la línea de ventas. El propósito de este escenario es mostrar solo los descuentos que aún no se aplican. La excepción a esto son los descuentos que se aplican en función de un cupón marcado como "Aplicar sin un código de cupón". Esto facilita que el asociado de ventas elimine fácilmente el cupón que ha aplicado.

La página **Todos los descuentos** muestra solo descuentos que no compiten con ninguno de los descuentos aplicados. Este comportamiento ayuda a garantizar que, si un asociado de ventas informa a un cliente sobre un descuento, y el cliente toma la acción requerida (por ejemplo, el cliente compra un artículo más para obtener un 10 por ciento de descuento), el descuento se aplica a la transacción. Los descuentos basados en cupones se muestran solo si la opción **Aplicar sin un código de cupón** está activada.

En un escenario simple donde todos los descuentos tienen la misma prioridad, el modo de concurrencia de descuento es **Compuesto**, y el control de concurrencia de descuento se establece en **El mejor precio y compuesto dentro de la prioridad, nunca compuesto a través de prioridades**, la página **Todos los descuentos** muestra todos los descuentos disponibles para un producto, porque todos los descuentos son compuestos y no compiten entre sí.

Las siguientes ilustraciones muestran la lógica que determina qué descuentos se muestran en escenarios avanzados, como un escenario donde el modo de concurrencia de descuento es **Mejor precio** o **Exclusivo**, y se utilizan dos o más prioridades. En estos escenarios, los descuentos que se muestran se ven afectados aún más en función de si el control de concurrencia de descuentos está establecido en **El mejor precio y compuesto dentro de la prioridad, nunca compuesto a través de prioridades** o **El mejor precio solo dentro de la prioridad, siempre compuesto por prioridad**.

La siguiente ilustración muestra la lógica que se utiliza cuando el control de simultaneidad de descuento se establece en **El mejor precio y compuesto dentro de la prioridad, nunca compuesto a través de prioridades**.

![Lógica para el mejor precio y compuesto dentro de la prioridad, nunca compuesto entre prioridades](./media/Model_1.png "Lógica para el mejor precio y compuesto dentro de la prioridad, nunca compuesto entre prioridades").

La siguiente ilustración muestra la lógica que se utiliza cuando el control de simultaneidad de descuento se establece en **El mejor precio solo dentro de la prioridad, siempre compuesto a través de la prioridad**.

![Lógica para el mejor precio solo dentro de la prioridad, siempre compuesto entre prioridad](./media/Model_2.png "Lógica para el mejor precio solo dentro de la prioridad, siempre compuesto entre prioridad").


[!INCLUDE[footer-include](../includes/footer-banner.md)]