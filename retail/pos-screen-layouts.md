---
title: "Configurar diseños de pantalla para el PDV"
description: "Este tema proporciona información sobre los diseños de pantalla para Microsoft Dynamics 365 for Operations - Retail point of sale (POS)."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7dee20166ea89b56523e3ef38e66de53d6e4a621
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Configurar diseños de pantalla para el PDV

[!include[banner](includes/banner.md)]


Este tema proporciona información sobre los diseños de pantalla para Microsoft Dynamics 365 for Operations - Retail point of sale (POS).

La interfaz de usuario de Microsoft Dynamics 365 for Operations - Retail point of sale (POS) se puede configurar mediante una combinación de perfiles visuales y diseños de pantalla asignados a tiendas, registros y/o usuarios.

## <a name="visual-profile"></a>Perfil visual
Los perfiles visuales se asignan a los registros y se utilizan para especificar los elementos visuales que son específicos del registro y que se comparten entre los usuarios. Cualquier usuario que se registre tendrá el mismo tema y colores e imágenes iguales. 

**Número de perfil** - El número del perfil es el identificador exclusivo del perfil visual. 

**Descripción** - La descripción permite especificar un nombre descriptivo que ayude a identificar el perfil correcto para su situación.

**Tema** - Los usuarios pueden elegir entre los temas de aplicación claro u oscuro. Estos ajustes afectan a la fuente y a los colores de fondo de toda la aplicación.

**Color de acento** - El color de acento se utiliza en el sistema POS para distinguir o resaltar determinados elementos visuales como mosaicos, botones de comandos o hipervínculos. Estos elementos normalmente se pueden accionar.

**Color de encabezado** - El color de encabezado permite al usuario configurar el color del encabezado de página para satisfacer las necesidades de marca del distribuidor. Esta función solo está disponible en Dynamics 365 for Operations, versión 1611.

**Fondo de inicio de sesión** - Los usuarios pueden especificar una imagen de fondo para la pantalla de inicio de sesión. El tamaño de archivo de las imágenes de fondo se debe mantener lo más pequeño posible, ya que el almacenamiento y la carga de archivos grandes podría tener un impacto en el comportamiento y el rendimiento de la aplicación.

**Fondo de la aplicación** - El PDV puede usar también una imagen como fondo en la aplicación en lugar del color liso del tema. Como sucede con los fondos de inicio de sesión, se aconseja mantener el tamaño de archivo lo más pequeño posible.

## <a name="screen-layouts"></a>Diseños de pantalla
La configuración del diseño de pantalla determina las acciones, el contenido y la posición de los controles de la interfaz de usuario en la pantalla de bienvenida del PDV y en la pantalla de transacciones. 

**Pantalla de bienvenida** - En la mayoría de los casos, la pantalla de bienvenida es la página que verán los usuarios la primera vez que inicien sesión en el PDV. La pantalla de bienvenida puede constar de una imagen de marca y de cuadrículas de botones que proporcionan acceso a las operaciones del PDV. Normalmente, las operaciones que no son específicas de la transacción actual se colocan aquí. 

**Pantalla de transacción** - La pantalla de transacción es la pantalla principal del PDV para procesar transacciones de venta y pedidos. La pantalla de transacción se puede configurar mediante el diseñador de pantalla. 

**Pantalla de inicio predeterminada** - Algunos minoristas prefieren que el cajero vaya directamente a la pantalla de transacción después de iniciar sesión. El valor predeterminado de la pantalla de inicio permite a los usuarios definir esto en cada diseño de pantalla.

### <a name="assignment"></a>Asignación

Los diseños de pantalla se pueden asignar a la tienda, el registro o el nivel de usuario. La asignación del usuario anula la asignación del registro y tienda, y la asignación del registro anula la asignación de la tienda. En una situación sencilla en la que todos los usuarios utilizan el mismo diseño independientemente del registro o el rol, el diseño de pantalla solo puede establecerse en la tienda. En caso de que algunos registros o usuarios necesiten diseños especializados, se pueden asignar de la forma adecuada.

### <a name="layout-sizes"></a>Tamaños de diseño

Esta función solo está disponible en Dynamics 365 for Operations, versión 1611. Dado que en muchos casos los diseños de pantalla se pueden usar en varios tamaños de pantalla y resoluciones, los usuarios pueden configurar el diseño y contenido de cada uno. La aplicación del PDV elegirá automáticamente el tamaño de diseño más cercano para el dispositivo en el arranque. Un diseño de pantalla también puede contener las configuraciones de dispositivos completos y compactos. Esta configuración permite asignar un usuario a un diseño monopantalla que funcionará con diferentes tamaños y factores de formulario en la tienda. 

**Modern POS - Completo** - Los diseños completos suelen emplearse mejor para pantallas grandes como monitores de PC o tabletas. Los usuarios pueden elegir los elementos de la interfaz que van a incluir, determinar su tamaño y posición y configurar sus propiedades detalladas. Los diseños completos admiten la configuración vertical y horizontal. 

**Modern POS - Compact** - Los diseños compactos suelen emplearse mejor para teléfonos o tabletas pequeñas. Las posibilidades de diseño en los dispositivos compactos son limitadas. Los usuarios pueden configurar las columnas y los campos para los paneles de totales y de recepción.

### <a name="screen-layout-designer"></a>Diseñador de pantalla

Cada tamaño de diseño de un diseño de pantalla se debe configurar mediante el diseñador de pantalla. El diseñador permite a los usuarios especificar y configurar los elementos de la interfaz de usuario de la pantalla de transacción. El diseñador de pantalla emplea ClickOnce pantalla descargar, instalar y arrancar la última versión de la aplicación cada vez un usuario accede a ella. Asegúrese de comprobar los requisitos del explorador para el uso de ClickOnce, ya que algunos exploradores como Chrome requieren extensiones. 

**Teclado numérico** - El teclado numérico es la entrada de usuario principal en la pantalla de transacción del PDV. Se puede configurar para mostrar todo el teclado en pantalla, ideal para pantallas táctiles, o solo el campo de entrada, que se puede utilizar con un teclado físico. Los ajustes del teclado numérico están disponibles solo en el diseño completo. En Dynamics 365 for Operations, versión 1611, los diseños compactos siempre tienen el teclado numérico completo disponible en la pantalla de transacción.

**Panel de totales** - El panel de totales se puede configurar en una o dos columnas para mostrar campos como el recuento de líneas, el importe de descuento, los gastos, el subtotal y los impuestos. En Dynamics 365 for Operations, versión 1611, los diseños compactos solo admiten una columna de totales. 

**Recepción** - El panel de recepción contiene las líneas de ventas, las líneas de pago y la información de entrega para los productos y servicios procesados en el PDV. Los usuarios pueden especificar columnas, anchos y posiciones. En los diseños compactos de Dynamics 365 for Operations, versión 1611, también puede configurar información adicional que aparecerá en la fila debajo de la línea principal. 

**Tarjeta de cliente** - La tarjeta del cliente muestra información relativa al cliente actualmente asociado a la transacción. La tarjeta del cliente se puede configurar para que se oculte o muestre la información adicional. 

**Control de fichas** - El control de fichas puede colocarse en el diseño de pantalla, y otros controles como el teclado numérico, la tarjeta de cliente o las cuadrículas de botones se pueden colocar dentro de la ficha. El control de fichas es un contenedor que ayuda al usuario a introducir más contenido en la pantalla. El control de fichas solo está disponible en los diseños completos. 

**Imagen**- El control de imagen se puede utilizar para mostrar el logotipo de la tienda u otra imagen de marca en la pantalla de la transacción. El control de imagen solo está disponible en los diseños completos. 

**Productos recomendados** - Si está configurado para el entorno, el control de productos recomendados mostrará las sugerencias de productos del aprendizaje automático. El control de productos recomendados solo está disponible en los diseños completos de Dynamics 365 for Operations, versión 1611. **Control personalizado **- El control personalizado actúa como un marcador de posición en el diseño de pantalla para que los usuarios puedan reservar espacio para el contenido personalizado. El control personalizado solo está disponible en los diseños completos.

<a name="see-also"></a>Consulte también
--------

[Instale el diseñador de estructura del PDV (punto de venta) al por menor](install-pos-layout-designer.md)




