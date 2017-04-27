---
title: "Configuración de visualización del dispositivo móvil del almacén"
description: "Este artículo describe cómo configurar el aspecto de una visualización del dispositivo móvil y cómo asignar teclas de método abreviado a controles, como botones."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup, WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 721b293d1f8c76458ca510732f9bb94f003ac6e3
ms.lasthandoff: 03/31/2017


---

# <a name="warehouse-mobile-device-display-settings"></a>Configuración de visualización del dispositivo móvil del almacén

[!include[banner](../includes/banner.md)]


Este artículo describe cómo configurar el aspecto de una visualización del dispositivo móvil y cómo asignar teclas de método abreviado a controles, como botones. 

Este artículo se aplica a las características "almacenamiento avanzado" en gestión de almacenes. Los dispositivos móviles se pueden usar para muchas de las tareas que los trabajadores de almacén realizan.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Especificar los estilos y asignar los métodos abreviados de teclado
Como parte de la configuración del dispositivo móvil, puede definir diseños diferentes para los dispositivos móviles. Para ello, debe conocer el nombre del archivo de hojas de estilo CSS y el archivo de extensión de página Active server (ASPX). Los archivos predeterminados se instalan como parte de la instalación del portal de los dispositivos móviles de almacén. Si no conoce los nombres de archivo, pregunte al administrador del sistema. Puede definir un nuevo estilo en la página **Configuración de visualización del dispositivo móvil**:

-    En el campo **archivo CSS**, escriba el nombre del archivo CSS. Incluya la extensión del nombre del archivo .css.
-   En el campo **Vista de los valores de visualización del dispositivo móvil**, especifique el archivo ASPX. **No** incluya la extensión de nombre del archivo .aspx.

Los archivos CSS y ASPX deben estar situados en un directorio específico, de modo que la solicitud de los servicios de información de Internet (IIS) puedan cargarlos. Puede ser útil definir distintos archivos CSS si está ejecutando la función del dispositivo móvil en diferentes exploradores o en diferentes tipos de hardware que requieren varios controles de diseño. Ajustes simples como el color de fondo, la fuente y el tamaño de fuente para el texto, y el ancho y el comportamiento de los botones, se pueden controlar fácilmente usando de manera diferente los archivos CSS. El archivo ASPX se utiliza para mostrar el sitio móvil en la solicitud del servidor ASP.NET. El archivo controla cómo se dispone la estructura general del HTML. Conviene personalizar esta funcionalidad solo si tiene problemas estructurales serios con HTML y Javascript, y debe cambiar este código para los dispositivos específicos. Para asignar los controles de HTML en la página del dispositivo móvil a los métodos abreviados de teclado, en la página **Valores de visualización del dispositivo móvil**, en el campo **Métodos abreviados de teclado**, asigne códigos numéricos para las claves. Puede usar el menú **Ver códigos para los métodos abreviados de teclado** en el dispositivo móvil para encontrar los códigos de carácter numérico. Tenga en cuenta que las asignaciones pueden variar, en función del hardware que se usa. Debe usar la siguiente sintaxis para crear la asignación:

&lt;nombre de control&gt;(&lt;nombre de tecla&gt;)=&lt;código de tecla&gt;;

Aquí hay una explicación de las partes de la sintaxis:

-   **&lt;nombre de control&gt;**: el nombre del control (por ejemplo, un botón) que se representa en HTML.
-   **(&lt;nombre de tecla&gt;)**: el nombre de la tecla de teclado para la que está creando el método abreviado.
-   **&lt;Código de tecla&gt;**: el código de carácter numérico para la clave que desea utilizar como la tecla de método abreviado.

Este es un ejemplo:

Cancelar(Esc)=27; Full(F2)=113

En todas las páginas que incluyan el botón **Cancelar**, el botón tendrá este texto:

**(Esc) Cancelar**

Al presionar la tecla ESC en el teclado, se activará el botón **Cancelar**. Para aplicar los ajustes de estilo y métodos abreviados de teclado a un dispositivo específico, debe crear una asignación en el campo **Criterios**. Debe usar una expresión regular de .NET para crear la asignación, y la expresión debe constar de tres seccionesseparadas por una barra vertical (|), como se muestra aquí:

Request.UserHostAddress=&lt;dirección de host de usuario&gt;|HostName=&lt;nombre de host de usuario&gt;|Request.UserAgent=&lt;agente de usuario&gt;

Aquí hay una explicación de las partes de la expresión:

-   **&lt;dirección de host de usuario&gt;**: una expresión regular de .NET que coincida con la dirección IP del solicitante.
-   **&lt;nombre de host del usuario&gt;**: una expresión regular de .NET que coincida con el nombre de red del solicitante.
-   **&lt;agente de usuario&gt;**: una expresión regular de .NET que coincida con el identificador del explorador usada por el solicitante.

En el siguiente ejemplo permite el uso de Internet Explorer 8:

Request.UserHostAddress=.\*|HostName=.\*|Request.UserAgent=MSIE\\s8\\.0

Puede usar el menú **Configuración del servidor de visualización para los valores de visualización** en el dispositivo móvil para buscar información acerca de la configuración.

## <a name="define-text-colors-for-messages"></a>Definir los colores de texto para los mensajes
Puede usar la página**Colores de texto del dispositivo móvil** para controlar los distintos los colores que se usan en los mensajes generados del sistema, como mensajes de error. Por ejemplo, el color de texto puede indicar el propósito o la gravedad del mensaje. Están disponibles los siguientes tipos de mensajes.

| Tipo de mensaje | Descripción                                                                                                                                                                            |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Predeterminada      | Los mensajes predeterminados usan los ajustes de color predeterminados para todos los mensajes, según lo especificado por el archivo CSS para el portal del dispositivo móvil del almacén.                                                   |
| Error        | Los mensajes de error indican un problema que el usuario debe resolver antes de que pueda continuar.                                                                                             |
| Satisfactorio      | Los mensajes de éxito confirman que una acción es correcta.                                                                                                                                |
| Advertencia      | Los mensajes de advertencia notifican al trabajador que hay un problema, o que podría haber un problema si el trabajador continúa. Sin embargo, el trabajador no tiene que resolver el problema para continuar. |

Para seleccionar el color, en la página **Seleccionar color**, haga clic en la paleta o escriba un código de color hexadecimal.

## <a name="define-the-date-format-to-use-on-mobile-devices"></a>Definir el formato de fecha para usar en los dispositivos móviles
Puede ampliar la lista de formatos de fecha aceptados para cada instalación. Esta capacidad puede resultar útil si, por ejemplo, desea proporcionar un formato que haga más fácil al trabajador la especificación de fechas en un dispositivo móvil. El formato predeterminado viene determinado por el idioma predeterminado del usuario, que se especifica en el campo **Opciones de usuario** de la página **Idioma**. (La misma página también se usa para asociar a un empleado con un usuario específico de trabajo de almacén). **Nota:** El portal de dispositivos móviles de almacén no usa el valor del campo **Formato de fecha y hora de número** en la página **Preferencia de idiomas y región**. Para cambiar un formato de fecha, debe estar familiarizado con expresiones regulares en .NET Framework de Microsoft. Para obtener más información, consulte [Expresiones regulares de .Net Framework](http://go.microsoft.com/fwlink/?LinkId=391260). Para definir formatos de fecha, edite el archivo Dates.ini que se encuentra en Content\\Settings\\Dates.ini en el servidor del portal de dispositivos móviles de almacén. Este archivo usa expresiones regulares de .NET para especificar el formato de fecha. La expresión regular debe contener las subexpresiones que crean grupos denominados por día, mes y año (DDMMYY), tal y como se muestra en el siguiente ejemplo:

^(?&lt;día&gt;\\d{2})(?&lt;mes&gt;\\d{2})(?&lt;año&gt;\\d{2})$

Cada subexpression requiere de uno a dos dígitos para el día y el mes, y de uno a cuatro dígitos para el año. Por ejemplo, la siguiente subexpresión define un grupo denominado para un año, y requiere un mínimo de dos dígitos o un máximo de cuatro dígitos:

(?&lt;año&gt;\\d{2,4})

Puede especificar más de una expresión en el mismo archivo. Cada expresión debe estar en una línea independiente. La primera expresión que coincida se usa para analizar la fecha.

<a name="see-also"></a>Consulte también
--------

[Configuración de dispositivos móviles del trabajo de almacén](configure-mobile-devices-warehouse.md)




