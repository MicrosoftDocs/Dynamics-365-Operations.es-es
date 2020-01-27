---
title: Características de accesibilidad
description: Este tema describe la funcionalidad diseñada para ayudar a los usuarios que tienen diferentes discapacidades.
author: TLeforMicrosoft
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 8ec4ee4654bdf306e179dcac5bf246df7f2b8cf7
ms.sourcegitcommit: c3bc5dd007d9f063631232497bd4cda9214e2e5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "2872451"
---
# <a name="accessibility-features"></a>Características de accesibilidad

[!include [banner](../includes/banner.md)]

Este tema describe la funcionalidad diseñada para ayudar a los usuarios que tienen diferentes discapacidades a usar esta aplicación. Por ejemplo, hay características para las personas que usan tecnologías de ayuda a la visión como Microsoft Windows Narrator.

## <a name="windows-narrator-and-keyboard-only-access"></a>Windows Narrator y acceso solo de teclado

Cada campo y control tienen una etiqueta y una descripción de accesos directos aplicables. Un lector de pantalla puede leer la etiqueta y la descripción.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Accesos directos para las acciones realizadas con más frecuencia

Para la mayoría de usuarios, el uso diario del sistema implica un gran volumen de entradas de datos e interacción de teclado. Para mejorar la experiencia del usuario, hemos creado métodos abreviados para ayudarle a "saltar" por la pantalla y accesos directos para acciones especializadas. Para obtener más información, consulte [Métodos abreviados de teclado](shortcut-keys.md).

## <a name="navigation-search"></a>Búsqueda de navegación

Cualquier página a la que se accede mediante el menú del panel de navegación, el panel del extremo izquierdo, también está disponible desde la casilla **Buscar**. Presione Alt+G para mover el foco a la casilla **Buscar** y, a continuación, escriba el nombre o la descripción de la página.

!["Cuentas bancarias” especificadas en el cuadro de búsqueda](media/6d08b0be32808221023e2aa92d69fd70.png ""cuentas bancarias” especificadas en el cuadro de búsqueda")

Para obtener más información, consulte [Búsqueda de navegación](navigation-search.md).

> [!NOTE]
> Puede navegar directamente únicamente a las páginas de nivel superior. Las páginas secundarias se basan en la información o el contexto de su página principal.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Búsqueda de acción para usuarios solo de teclado o para la entrada de datos descendente

Puede accederse a cada acción que se ofrece en una página desde un teclado, mediante la secuencia de tabulaciones. La información acerca de la secuencia de tabulaciones se proporciona más adelante en este tema. Para ejecutar acciones más directamente, puede usar la función de búsqueda de la acción.

### <a name="example"></a>Ejemplo

Desea ejecutar la acción **Registro de notificación por correo electrónico** que aparece en el grupo **Notificación por correo electrónico** en la pestaña **Pedido de ventas** del panel de acciones.

![Acción de registro de la notificación por correo electrónico en el panel de acciones](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "Acción de "Registro de la notificación por correo electrónico" en el panel de acciones")

Una opción es para usar el teclado. Presione Ctrl+F6 para mover el enfoque al panel de acciones, y presione la ficha repetidamente para pasar por todas las fichas y acciones, hasta que la acción **Registro de notificación por correo electrónico** tenga el foco.

Sin embargo, también puede ejecutar la acción más directamente. En cualquier lugar de la página, presione Ctrl+Apóstrofo (') para mostrar el cuadro de búsqueda para las acciones.

![Cuadro de búsqueda de acciones](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "Cuadro de búsqueda de acciones")

En el cuadro de búsqueda, escriba palabras que describen la acción. La acción se a pone a su disposición, y puede ejecutarla directamente. Por ejemplo, si especifica **correo electrónico**, **notific** (una palabra parcial), o **registro**, puede "saltar" a la funcionalidad de registro de la notificación por correo electrónico.

!["Correo electrónico” especificado en el cuadro de búsqueda](media/image4.png ""Correo electrónico” especificado en el cuadro de búsqueda")

!["Notific” especificado en el cuadro de búsqueda](media/image5.png ""notific” especificado en el cuadro de búsqueda")

!["Registro” especificado en el cuadro de búsqueda](media/image6.png ""registro” especificado en el cuadro de búsqueda")

Cuando haya terminado, puede pulsar Ctrl+Apóstrofo otra vez para devolver el enfoque al campo en el que trabajaba antes de ejecutar la búsqueda de acción.

Para obtener más información, consulte [Búsqueda de acciones](action-search.md).

## <a name="tab-sequence"></a>Secuencia de tabulaciones

En el uso diario del sistema, no todos los campos son necesarios para realizar tareas habituales. Por lo tanto, de forma predeterminada, se "optimiza" la secuencia de tabulaciones. Se establecen tabulaciones únicamente en los campos que son esenciales para las situaciones habituales.

Sin embargo, puede detectar que algunos campos que utiliza a menudo para realizar tareas no se incluyen en la secuencia predeterminada de tabulaciones. En este caso, si usa Windows Narrator, puede usar acciones de teclado de Windows Narrator para tener acceso a dichos campos e inspeccionar su contenido. Como alternativa, puede activar la opción **Secuencia de fichas mejorada** en la página **Opciones**. Esta opción crea toda la parte de campos que pueden editarse y de solo lectura de la secuencia de tabulaciones. Puede utilizar la personalización de la página para crear una secuencia de tabulaciones personalizada y omitir campos que no es necesario que formen parte de la secuencia tabulaciones. Para obtener más información acerca de la personalización, consulte [Personalizar la experiencia del usuario](personalize-user-experience.md).

![Opción de "Secuencia de pestañas mejorada"](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "Opción de "Secuencia de pestañas mejorada"")

## <a name="form-patterns"></a>Patrones de formulario

Casi el 90 por ciento de las páginas de la aplicación se basa en un pequeño conjunto de patrones. A estos patrones se les denomina *patrones del formulario*. Cada patrón de formulario se usa para proporcionar las acciones que se realizan con mayor frecuencia en la página. Un patrón de formulario ayuda a garantizar la familiaridad y facilidad de comprensión, ya que las acciones y los datos que se usan con frecuencia se muestran siempre en la misma ubicación en distintas páginas. Debido al pequeño número de patrones del formulario, los usuarios pueden familiarizarse fácilmente con el sistema, con independencia del número de páginas de este y pueden usarlo con confianza después de reconocer los patrones del formulario.

Para obtener más información acerca de los patrones del formulario, consulte [Estilos y patrones del formulario](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Diseño con capacidad de respuesta.

El producto está diseñado para que funcione en distintos dispositivos y factores de forma, desde las pantallas más pequeñas a las pantallas grandes con la más alta resolución. Nuestro motor de diseño con capacidad de respuesta permite a los usuarios hacer el zoom a un nivel de ampliación del 200 por ciento (o, en algunos casos, más del 200 por ciento).

En los teléfonos inteligentes y otras pantallas pequeñas, los controles y el diseño del formulario se adaptarán de manera receptiva para garantizar que los datos principales se vean favorecidos. Estos comportamientos receptivos también pueden incluir reducir el número de columnas en grupos y pestañas a una sola columna, ocultar elementos de shell y colapsar el Panel de acciones.

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Orientación para ayudar a los desarrolladores y los clientes a incorporar un pensamiento accesible a sus personalizaciones

Para obtener más información acerca de las prácticas recomendadas de Microsoft para habilitar la accesibilidad, consulte [Accesibilidad en formularios, productos y controles](../../dev-itpro/user-interface/enable-accessibility.md).
