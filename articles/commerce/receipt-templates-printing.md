---
title: Configurar y diseñar formatos de recibo
description: Este artículo describe cómo modificar diseños de formulario para modificar la forma de imprimir recibos, facturas y otros documentos. Dynamics 365 Commerce incluye un diseñador de formularios que puede usar para crear y modificar con facilidad diversos tipos de diseños de formulario.
author: rubencdelgado
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFormLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 281a5e2be6f43f5a83ef7435b2041423dd5d4caa
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792132"
---
# <a name="set-up-and-design-receipt-formats"></a>Configurar y diseñar formatos de recibo

[!include [banner](includes/banner.md)]

Este artículo describe cómo modificar diseños de formulario para modificar la forma de imprimir recibos, facturas y otros documentos. Dynamics 365 Commerce incluye un diseñador de formularios que puede usar para crear y modificar con facilidad diversos tipos de diseños de formulario.

> [!IMPORTANT]
> Debe configurar diseños de formulario y perfiles de recibo para imprimir recibos y otros documentos desde Retail Modern POS y Cloud POS. Puede incluir varios diseños de formulario en un perfil de recibo. Puede asignar el perfil de recibo a una impresora modificando un perfil de hardware.

## <a name="set-up-a-receipt-format"></a>Configurar un formato de recibo

1. Haga clic en **Retail y Commerce** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **PDV** &gt; **Formatos de recibos**.
2. En la página **Formato de recibo**, haga clic en **Nuevo** para crear un diseño de formulario nuevo o seleccione un diseño de formulario existente.
3. En el campo **Formato de recibo**, introduzca un identificador para el diseño de formulario y, a continuación, seleccione el tipo de recibo para el que se utiliza este diseño. También puede introducir una descripción y un nombre corto para el recibo en el campo **Título**.
4. En la fecha desplegable **General**, seleccione una opción para definir el comportamiento de impresión:

    - **Imprimir siempre:** el recibo se imprime automáticamente, según corresponda.
    - **No imprimir:** el recibo no se imprime.
    - **Preguntar al usuario:** se debe preguntar al usuario si desea imprimir el recibo.
    - **Según sea necesario:** esta opción solo se usa para los recibos de regalo. Cuando se selecciona esta opción, el usuario puede imprimir un alabrán de regalo desde la página **Cambiar**, si se requiere un recibo de regalo.

## <a name="print-images"></a>Imprimir imágenes

El diseñador de recibos incluye una variable **Logotipo** que se puede utilizar para especificar imágenes que se imprimirán en el recibo. Las imágenes que se incluyan en recibos con la variable **Logotipo** deben ser archivos de tipo mapa de bits monocromo (.bmp). Si se especifica una imagen .bmp en el diseñador de recibos, pero no se imprime cuando se envía a la impresora, puede deberse a que el tamaño del archivo es demasiado grande o a que las dimensiones en píxeles de la imagen no son compatibles con la impresora. En este caso, pruebe a reducir la resolución del archivo de imagen.   

## <a name="design-a-receipt-format"></a>Diseñar un formato de recibo

Utilice el diseñador de formularios para crear gráficamente el diseño del documento de formulario. La página **Diseñador de formato de recibo** tiene tres secciones: **Encabezado**, **Líneas** y **Pie de página**. Algunos tipos de diseño de formulario usan elementos de las tres secciones, mientras que otros usan elementos sólo de una o dos secciones. Para ver los elementos que están disponibles para cada sección, haga clic en el botón apropiado del panel de navegación en el lado izquierdo de la página.

1. Haga clic en **Retail y Commerce** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **PDV** &gt; **Formatos de recibos**.
2. En la página **Formato de formulario** seleccione una configuración de formulario, y haga clic en **Diseñador**.
3. Haga clic en **Ejecutar** para iniciar la instalación del host del diseñador de venta de Commerce.
4. En la barra de notificación que aparece en la parte inferior de la ventana de Internet Explorer, haga clic en **Abrir** para empezar a instalar el diseñador de un solo clic. (La barra de notificación puede aparecer en una ubicación diferente en otros exploradores). El indicador de progreso muestra el progreso del proceso de instalación.
5. Después de que la instalación esté completada, escriba el nombre de usuario y la contraseña de Commerce y haga clic en **Iniciar sesión** para iniciar el diseñador.
6. Después de que se lleva a cabo una validación de sus credenciales y se inicia el diseñador, puede empezar a diseñar el formato de recibo o a modificar un formato existente.
7. Para crear los elementos del formulario, seleccione la sección **Encabezado**, **Líneas** o **Pie de página** y, a continuación, arrastre un elemento de la sección hasta el espacio de trabajo. La mayoría de los elementos contienen variables, que se rellenan automáticamente con datos de la base de datos. Otros elementos, por ejemplo **Texto**, permiten imprimir texto personalizado en el recibo.

    > [!NOTE]
    > Puede especificar el número de líneas que abarcará cada sección si ajusta el número de la esquina inferior derecha de esa sección. Para facilitar la modificación de una sección, aumente su altura. Para ello, arrastre la barra de cambio de tamaño situada en la parte inferior de la sección. La altura de la sección en el espacio de trabajo no afectará al número de líneas en el recibo en sí.

8. Después de arrastrar el elemento al espacio de trabajo, defina las propiedades de la parte en el panel **Información de objeto** en la parte inferior de la página. Especifique uno o más de los parámetros siguientes:

    - **Alinear**: establezca la alineación del campo en **Izquierda** o **Derecha**.
    - **Carácter de relleno**: permite especificar el carácter de espacio en blanco. De manera predeterminada se utiliza un espacio vacío, pero puede introducir cualquier carácter.
    - **Prefijo**: escriba el valor que aparece al principio del campo. Este valor solo se aplica a la sección **Líneas** del diseño.
    - **Caracteres**: permite especificar el número máximo de caracteres que el campo puede contener si el elemento contiene una variable. Si el texto del campo es más largo que el número de caracteres que especifique, quedará truncado para que quepa en el campo.
    - **Variable**: esta casilla se activa automáticamente si el elemento contiene una variable y no se puede personalizar.
    - **Tipo de fuente**: establezca el estilo de fuente en **Normal** o **Negrita**. Las letras en negrita utilizan el doble de espacio que las letras normales. Por lo tanto, es posible que se trunquen algunos caracteres.
    - **Tamaño de fuente**: establezca el tamaño de fuente en **Normal** o **Grande**. Las letras grandes son dos veces superior a letras normales. Por lo tanto, el uso de letras grandes podría conducir a superponer el texto del recibo.
    - **Eliminar**: haga clic en este botón para quitar el elemento seleccionado del diseño de formulario.

## <a name="assign-receipt-profiles"></a>Asignación de perfiles de recibo

Los perfiles de recibo se asignan directamente a impresoras mediante el perfil de hardware.

1. Abra el perfil de hardware haciendo clic en **Retail y Commerce** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Perfiles del PDV** &gt; **Perfiles de hardware**.
2. Seleccione la impresora y, a continuación, en el campo **Perfil de recibo**, asigne el perfil de recibo para usarlo en el registro.

> [!NOTE]
> Si se usan dos impresoras, una impresora se puede usar para imprimir recibos térmicos estándar de 40 columnas. La segunda impresora se usa normalmente para imprimir los tipos de recibo a toda página que requieren más información. Estos tipos de recibo incluyen los recibos y facturas de pedidos del cliente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]