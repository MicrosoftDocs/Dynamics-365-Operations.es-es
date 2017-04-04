---
title: "Configurar los diseños de visualización para PDV"
description: "Este tema proporciona información sobre los diseños de visualización para Microsoft Dynamics 365 para las operaciones (experiencias de ventas al por menor (POS) de punto de venta."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Configurar los diseños de visualización para PDV

Este tema proporciona información sobre los diseños de visualización para Microsoft Dynamics 365 para las operaciones (experiencias de ventas al por menor (POS) de punto de venta.

Microsoft Dynamics 365 para las operaciones (la interfaz de usuario de (POS) del punto de venta se puede configurar mediante una combinación de perfiles y de diseños de pantalla visuales, asignada a las tiendas, a los registros, y/o los usuarios.

## <a name="visual-profile"></a>Perfil visual
Los perfiles visuales se asignan a los registros y se utilizan para especificar los artículos visuales que están implementadas concretos y se comparten entre usuarios. Cualquier usuario que registre en el registro tendrá el mismo tema, colores, e imágenes. ** El número del perfil ** número del perfil es el identificador único para el perfil visual. ** ** La descripción del diseño le permite especificar el nombre descriptivo que ayude a identificar el perfil correcto para su situación. ** El tema ** - los usuarios puede elegir entre los temas de la aplicación de la luz o de luces. Estos valores afectan a la fuente y los colores de fondo en la aplicación. ** El acento color - ** el acento color se utiliza en el sistema POS para distinguir o para resaltar visuales determinados elementos como, mosaicos botones de comando, o hipervínculos. Estos artículos son normalmente procesables. ** El encabezado color - ** el encabezado color permite al usuario configurar el color del encabezado de página para satisfacer las necesidades de personalización de marca del distribuidor. Esta función sólo está disponible en Dynamics 365 para la versión 1611 de las operaciones. ** Los fondos de inicio de sesión ** - los usuarios pueden especificar una imagen de fondo para la visualización de inicio. El tamaño de archivo de imagen de fondo se deben actualizar tan pequeño posible, como almacenar y cargar archivos grandes podría tener un impacto en el comportamiento y el rendimiento de aplicación. ** El fondo de aplicación ** - POS puede usar una imagen como fondo en la aplicación en lugar de tema sólido color. Como con los fondos de inicio de sesión, se aconseja mantener el tamaño de archivo tan mínimo como sea posible.

## <a name="screen-layouts"></a>Diseños de pantalla
La configuración del diseño de pantalla determina las acciones, el contenido, y la posición de los controles de la interfaz de usuario en la pantalla de visualización de bienvenida y de la transacción de Retail POS. ** La pantalla de bienvenida ** )en la mayoría de los casos, la pantalla de bienvenida es la página que verán los usuarios cuando primero registrar en el sistema POS. La pantalla de bienvenida puede constar de una imagen y las cuadrículas de botones de personalización de marca que proporcionen el acceso a las operaciones de Retail POS. Normalmente, las operaciones que no son específicas de la transacción actual se colocan aquí. ** La transacción proteger ** - visualización de la transacción es la pantalla principal en el sistema POS para procesar transacciones de ventas y pedidos. La pantalla de la transacción puede ser configuradas mediante el diseñador de Pantalla. ** El inicio predeterminado proteger ** - algunos minoristas prefiere que el cajero navegue directamente a proteger la transacción después de iniciar sesión. El valor predeterminado de la pantalla de inicio permite a los usuarios establezcan esto para cada diseño de pantalla.

### <a name="assignment"></a>Asignación

Los diseños de pantalla se pueden asignar a la tienda, el registro, o el nivel de usuario. La asignación del usuario anula la asignación de registro y almacenes, y la asignación de registro anula la asignación de tienda. En una situación de ejemplo sencillo donde todos los usuarios utilizan el mismo diseño independientemente del registro o el rol, el diseño de pantalla sólo puede establecerse al almacén. En caso de que algunos registros o usuarios necesitan diseños especializados, se pueden asignar correctamente.

### <a name="layout-sizes"></a>Tamaños de diseño

Esta función sólo se aplica a Dynamics 365 la versión 1611 de las operaciones. Dado que muchos casos en los diseños de pantalla se pueden usar en todo de tamaños de pantalla y resoluciones de varios, los usuarios pueden configurar el diseño y contenido para cada uno. La aplicación de PDV automáticamente elegirá el tamaño más cercano de diseño del dispositivo a la hora de inicio. Un diseño de pantalla también puede contener las configuraciones de los dispositivos completa y compactos. Esta configuración permite asignado un usuario a un diseño monopantella que se produce a través de distintos tamaños y factores de forma del almacén. ** PDV moderno - completo ** - los diseños completos suele ser mejor usar para pantallas grandes como monitores del equipo o tabletas. Los usuarios pueden decidir qué artículos de la interfaz de usuario para incluir, determinan el tamaño y puesto, y configure sus propiedades detalladas. Los diseños completos admiten las configuraciones vertical y el paisaje. ** PDV moderno - Acuerdo ** - los diseños compactos suele ser mejor usar para teléfonos o tabletas pequeñas. Las posibilidades de diseño se limitan de los dispositivos compactos. Los usuarios pueden configurar las columnas y los campos para la recepción y suman los paneles.

### <a name="screen-layout-designer"></a>Diseñador de pantalla

Cada tamaño de diseño dentro de un diseño de pantalla se debe configurar mediante el diseñador de Pantalla. El diseñador permite a los usuarios especifiquen y configuración de artículos de la interfaz de usuario de visualización de la transacción. El diseñador de ClickOnce pantalla utiliza para descargar, para la instalación, y para poner en marcha la última versión de la aplicación cada vez un usuario obtiene acceso a él. Asegúrese de comprobar los requisitos del explorador para el uso de ClickOnce- algunos exploradores, como Cromada, requiere las extensiones. ** El teclado numérico - ** el teclado numérico es la entrada del usuario principal en la pantalla de la transacción POS. Se puede configurar para mostrar la trayectoria en pantalla completa, que es ideal de muestra táctiles, o sólo en el campo de entrada, que se puede utilizar con un teclado físico. Los valores de teclado numérico están disponibles en el diseño sólo completo. En Dynamics 365 para la versión 1611 de las operaciones, los diseños compactos siempre tienen el teclado numérico completo disponible de visualización de la transacción. ** El panel de totales - ** el panel de totales puede estar configurado en cualquier uno o dos columnas mostrar campos como número de líneas, el importe de descuento, gastos, subtotal, y los impuestos. En Dynamics 365 para la versión 1611 de las operaciones, los diseños compactos solo admiten una columna de totales. ** Recibo ** - ** ** el panel de recepción contiene las líneas de ventas, las líneas de pago, y la información de entrega para los productos y servicios procesados en el sistema POS. Los usuarios pueden especificar columnas, anchos, y el puesto. En compactos diseños de Dynamics 365 para la versión 1611 de las operaciones, también puede configurar información adicional que aparecerá en la línea bajo fila principal. ** La tarjeta del cliente - ** la tarjeta del cliente muestra información relativa al cliente actualmente asociado a la transacción. La tarjeta del cliente se puede configurar para ocultar o mostrar información adicional. ** El control de la Ficha - ** el control de la ficha puede colocarse sobre el diseño de pantalla, y otros controles como el teclado numérico, la tarjeta de cliente, o las cuadrículas de botones se pueden colocar dentro de la ficha. El control de la ficha es un contenedor que ayuda al usuario no más contenido en la pantalla. El control de la ficha sólo está disponible para los diseños completos. ** La imagen - ** el control de imagen se puede utilizar para mostrar el logotipo de almacén u otra imagen de personalización de marca en la pantalla de la transacción. El control de imagen solo está disponible para los diseños completos. ** Productos recomendados ** - si está configurado para el entorno, el control de productos recomendado mostrará las sugerencias de producto en función del lugar de equipo. El control de productos recomendado es sólo disponible para los diseños completos de Dynamics 365 para la versión 1611 de las operaciones. ** El control personalizado - ** el control personalizado actúa como un marcador de posición en el diseño de pantalla permite a los usuarios reserven el espacio para el contenido personalizado. El personalizado control solo está disponible para los diseños completos.

<a name="see-also"></a>Consulte también
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)


