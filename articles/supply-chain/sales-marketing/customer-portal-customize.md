---
title: Personalizar y usar el Portal del cliente
description: Este tema explica cómo personalizar el Portal del cliente después de que se haya agregado a su sistema.
author: dasani-madipalli
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: db087fdfe27a32e3368002e193fdcd4e5d5c253821cd5e00dad8fe59be4461bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776833"
---
# <a name="customize-and-use-the-customer-portal"></a>Personalizar y usar el Portal del cliente

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las diferentes páginas que están disponibles inmediatamente en el Portal del cliente. Explica qué hacen las páginas y cómo puede personalizarlas.

El Portal del cliente ofrece algunas páginas web y acciones listas para usar. El siguiente mapa del sitio proporciona una descripción general de esas páginas web y acciones, y los roles que pueden realizar las acciones.

![Mapa del sitio del Portal del cliente.](media/customer-portal-site-map.png "Mapa del sitio del Portal del cliente")

## <a name="typical-customizations"></a>Personalizaciones típicas

Los siguientes temas le ayudarán a aprender los conceptos básicos sobre portales Power Apps y cómo puede personalizar los portales:

- [Trabajar con plantillas](/powerapps/maker/portals/work-with-templates): este tema proporciona una descripción general de cómo funcionan los portales Power Apps y cómo puede hacer personalizaciones simples de portales.
- [Administrar contenido del portal](/dynamics365/portals/manage-portal-content): este tema explica cómo puede administrar y personalizar el contenido que aparece en su portal.
- [Editar CSS](/powerapps/maker/portals/edit-css): este tema le ayuda a realizar personalizaciones más complejas en la interfaz de usuario (UI) de su portal.
- [Crear un tema para el portal](/dynamics365/portals/create-theme): este tema le ayuda a crear un tema de interfaz de usuario para su portal.
- [Crear y exponer el contenido del portal fácilmente](/dynamics365/portals/create-expose-portal-content): este tema le ayuda a administrar los datos y tablas subyacentes que utiliza para su portal.
- [Configurar un contacto para usar en un portal](/powerapps/maker/portals/configure/configure-contacts): este tema explica cómo crear y personalizar roles de usuario, y cómo funcionan la seguridad y la autenticación en los portales Power Apps.
- [Configurar notas para formularios de tabla y formularios web en portales](/powerapps/maker/portals/configure-notes): este tema explica cómo agregar documentos y almacenamiento adicional a su portal.
- [Manejo de errores para el sitio web del portal](/powerapps/maker/portals/admin/view-portal-error-log): este tema explica cómo ver los registros de errores del portal y almacenarlos en su cuenta de almacenamiento de blobs Microsoft Azure.

## <a name="customize-the-order-creation-process"></a>Personalizar el proceso de creación de pedidos

Cuando un usuario envía un pedido utilizando el Portal del cliente, el pedido se sincroniza automáticamente con el correspondiente entorno Dynamics 365 Supply Chain Management. Debido a que el usuario es un cliente externo, parte de la información requerida se le oculta intencionalmente. Esta información se completará automáticamente cuando se envíe el formulario.

Esta sección muestra cómo debe configurar los contactos para evitar errores. Explica los campos que se configuran automáticamente y cómo puede modificar el valor de esos campos si es necesario.

### <a name="the-out-of-box-order-creation-process"></a>Proceso de creación de pedidos inmediato

Estos son los pasos estándar para enviar un pedido desde el Portal del cliente.

1. En la página de inicio, seleccione la ventana **Crear pedido** para abrir el asistente **Crear pedido**.
1. En la página **Información del pedido**, configure los siguientes campos:

    - **Fecha de recibo solicitada**: especifique la fecha de entrega.
    - **Dirección de entrega**: introduzca la dirección en la que se debe entregar el pedido.
    - **Empresa**: seleccione el nombre de la empresa del cliente. Este campo se configura automáticamente para usuarios que no son administradores.
    - **Numero requerido**: introduzca el número de solicitud del pedido. Este campo no es obligatorio.
    - **Enviar a país/región**: introduzca el país o la región a la que se enviarán los artículos. Este campo se configura automáticamente para usuarios que no son administradores.

    ![Página de información de pedido.](media/customer-portal-order-information.png "Página de información de pedido")

1. Seleccione **Siguiente**.
1. En la página **Artículos**, seleccione **Agregar artículo**.

    ![Página de artículos.](media/customer-portal-items.png "Página de artículos")

1. En el cuadro de diálogo **Información de artículo**, establezca los campos siguientes:

    - **Nombre del producto**: busque y seleccione un producto para agregar al pedido.
    - **Cantidad**: introduzca la cantidad del producto seleccionado.
    - **Unidad**: especifique la unidad de medida (por ejemplo, **ea.**, **kgs** o **caja**).
    - **Importe neto estimado**: el valor se calcula como el precio estimado del artículo × la cantidad para la unidad seleccionada.

    ![Cuadro de diálogo Información de artículo.](media/customer-portal-item-information.png "Cuadro de diálogo Información de artículo")

1. Seleccione **Enviar** para agregar el artículo al pedido.
1. Repita los pasos del 4 al 6 hasta que haya agregado todos los artículos que desea pedir.
1. Cuando haya terminado de agregar elementos, seleccione **Siguiente** en la página **Artículos**.
1. La página **Información del pedido** proporciona un resumen del pedido. Revise el contenido del pedido y los detalles de entrega. Si todo parece correcto, seleccione **Enviar** para enviar el pedido.

    ![Página de información de pedido completada.](media/customer-portal-order-submit.png "Página de información de pedido completada")

### <a name="standard-data-setup"></a>Configuración de datos estándar

Para ayudar a garantizar una experiencia de usuario fluida, el Portal del cliente completa automáticamente los valores de varios campos obligatorios. Estos valores se basan en la información del registro de contacto del cliente que envía el pedido.

Para cada [fila de contacto](/powerapps/maker/portals/configure/configure-contacts) que pertenece a un cliente que utilizará el Portal del cliente para enviar pedidos, los valores deben especificarse para los siguientes campos obligatorios. De lo contrario, se producirán errores.

- **Empresa**: entidad jurídica a la que pertenece el pedido
- **Cliente potencial**: cuenta de cliente asociada al pedido
- **Lista de precios**: lista de precios personalizada para el cliente
- **Divisa**: divisa del precio
- **Enviar a país/región**: país o la región a donde se enviarán los artículos

Los siguientes campos se configuran automáticamente para la tabla de pedido de ventas:

- **Idioma**: idioma del pedido (de forma predeterminada, el valor se toma del registro de contacto).
- **Enviar a país/región**: país o región a la que se enviarán los artículos (de forma predeterminada, el valor se toma del registro de contacto).
- **Persona de contacto**: el usuario con el que se puede contactar para obtener información sobre el pedido (de forma predeterminada, el valor se toma del registro de contacto).
- **Empresa**: la entidad jurídica a la que pertenece el pedido (de forma predeterminada, el valor se toma del registro de contacto).
- **Cliente potencial**: la cuenta del cliente asociada con el pedido (de forma predeterminada, el valor se toma del registro de contacto).
- **Facturar al cliente**: la cuenta de facturación del cliente asociada con el pedido (de forma predeterminada, el valor es el cliente potencial del registro de contacto).
- **Nombre del pedido de ventas**: nombre del pedido de ventas (el valor predeterminado es **pedido de venta** .)
- **Divisa**: divisa del precio (de forma predeterminada, el valor se toma del registro de contacto).
- **Lista de precios**: la lista de precios personalizada para el cliente (de forma predeterminada, el valor se toma del registro de contacto).
- **Descripción de la dirección de entrega**: la dirección de entrega del pedido de ventas (el valor predeterminado es **descripción de la dirección de entrega**).

### <a name="modify-the-order-creation-process"></a>Modificar el proceso de creación de pedidos

Puede modificar libremente la apariencia y la interfaz de usuario del Portal del cliente si no cambia el proceso básico de creación de pedidos. Si desea cambiar el proceso de creación de pedidos, hay algunos puntos que debe tener en cuenta.

No elimine las siguientes columnas de la tabla de pedido de ventas en Microsoft Dataverse, porque deben crear un pedido de cliente en doble escritura:

- **Empresa**: entidad jurídica a la que pertenece el pedido
- **Nombre**: nombre del pedido de ventas
- **Divisa**: divisa del precio
- **Lista de precios**: lista de precios personalizada para el cliente
- **Enviar a país/región**: país o la región a donde se enviarán los artículos
- **Cliente potencial**: cuenta de cliente asociada al pedido
- **Idioma**: el idioma del pedido (por lo general, este idioma es el idioma del cliente potencial).
- **Descripción de la dirección de entrega**: la dirección de entrega del pedido de ventas

Las columnas siguientes son obligatorios para los artículos:

- **Producto**: el producto a pedir
- **Cantidad**: la cantidad del producto seleccionado
- **Unidad**: la unidad de medida (por ejemplo, **ea.**, **kgs** o **caja**)
- **Enviar a país/región**: el país o región de entrega
- **Descripción de la dirección de entrega**: la dirección de entrega del pedido

Debe asegurarse de que su Portal de clientes de alguna manera envíe valores para todas estas columnas.

Si desea agregar columnas a la página o eliminar columnas, consulte [Crear o editar formularios de creación rápida para una experiencia de entrada de datos optimizada](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Si desea cambiar cómo se configuran las columnas y cómo se configuran los valores cuando se guarda la página, consulte la siguiente información en la documentación de portales Power Apps:

- [Campo prerellenado](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Establecer valor al guardar](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>Personaliza la página de inicio

Todos los controles del Portal del cliente son controles de portales Power Apps integrados. Puede personalizarlos siguiendo los pasos de [Componer una página](/powerapps/maker/portals/compose-page) en la documentación de portales Power Apps.

El único control personalizado que se incluye en la plantilla del Portal del cliente se usa para crear las ventanas de la página de inicio.

![Ventanas en la página de inicio.](media/customer-portal-home-page-tiles.png "Ventanas en la página de inicio")

Para modificar las ventanas, siga estos pasos.

1. Abra la [aplicación Gestión de portales](/powerapps/maker/portals/configure/configure-portal).
1. En el panel de navegación de la izquierda, seleccione **Plantillas de página**.

    ![Panel de navegación de gestión de portales.](media/customer-portal-nav.png "Panel de navegación de gestión de portales")

1. Seleccione la plantilla de página que se llama **Inicio**.
1. En el campo **Plantilla web**, seleccione el vínculo **Inicio** para abrir el código fuente de esa página.

    ![Campo de plantilla web.](media/customer-portal-web-template.png "Campo de plantilla web")

1. Ahora debería ver todo el código fuente de la página de inicio y puede modificarlo según lo requiera.

## <a name="resources"></a>Recursos

Para obtener más información sobre cómo puede configurar y personalizar el Portal del cliente, consulte los siguientes recursos:

- [Documentación de portales Power Apps](/powerapps/maker/portals/overview)
- [Documentación de doble escritura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [Sobre el ciclo de vida del portal](/powerapps/maker/portals/admin/portal-lifecycle)
- [Actualizar un portal](/powerapps/maker/portals/admin/upgrade-portal)
- [Migrar la configuración del portal](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Administración de ciclo de vida de solución: Dynamics 365 para aplicaciones de Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]