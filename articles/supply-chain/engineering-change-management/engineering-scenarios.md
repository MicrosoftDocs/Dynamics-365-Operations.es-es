---
title: Tutorial de la característica de gestión de cambios de ingeniería
description: Este artículo proporciona un tutorial de un extremo a otro que muestra cómo trabajar con la administración de cambios de ingeniería.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e66cda6e529a70d40e599718332152bac95b061e
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220039"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Tutorial de la característica de gestión de cambios de ingeniería

[!include [banner](../includes/banner.md)]

Este artículo proporciona un tutorial de un extremo a otro que muestra cómo trabajar con la administración de cambios de ingeniería. Pasa por cada uno de los escenarios más importantes:

- Configuración de funciones básicas
- Cómo una empresa de ingeniería crea un nuevo producto de ingeniería
- Cómo una empresa de ingeniería lanza un producto de ingeniería a una empresa local
- Cómo una empresa local puede revisar y aceptar un producto que le ha entregado una empresa de ingeniería
- Cómo una empresa local puede utilizar un producto de ingeniería en transacciones estándar
- Cómo agregar un producto de ingeniería a una orden de venta
- Cómo solicitar cambios en un producto de ingeniería creando una solicitud de cambio de ingeniería
- Cómo programar e implementar los cambios solicitados mediante la creación de una orden de cambio de ingeniería
- Cómo lanzar un producto que ha sido modificado

Todos los ejercicios de este artículo utilizan los datos de muestra estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Además, cada ejercicio se basa en el ejercicio anterior. Por lo tanto, le recomendamos que realice los ejercicios en orden, de principio a fin, especialmente si nunca antes ha utilizado la función de gestión de cambios de ingeniería. De esta manera, obtendrá una comprensión completa de la función.

## <a name="set-up-for-the-sample-scenario"></a>Configuración para el escenario de ejemplo

Para seguir el escenario de muestra que se proporciona en este artículo, primero debe preparar la función haciendo que los datos de demostración estén disponibles y agregando algunos registros personalizados.

Antes de intentar hacer cualquiera de los ejercicios del resto de este artículo, siga las instrucciones en todas las subsecciones siguientes. Estas subsecciones también presentan varias páginas de configuración importantes que utilizará cuando configure la gestión de cambios de ingeniería para su propia organización.

### <a name="make-standard-demo-data-available"></a>Hacer que los datos de demostración estándar estén disponibles

Trabajar en un sistema donde los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar están instalados. Los datos de demostración estándar agregan datos para varias entidades legales de demostración (empresas y organizaciones). A medida que avance en los ejercicios, utilizará el selector de empresas del lado derecho de la barra de navegación para cambiar entre una empresa (*DEMF*) que está configurado como *organización de ingeniería* y otra empresa (*USMF*) que está configurado como *organización operativa*.

### <a name="set-up-an-engineering-organization"></a>Configurar una organización de ingeniería

Una organización de ingeniería es propietaria de los datos de ingeniería y es responsable del diseño y los cambios de productos. Siga estos pasos para configurar las organizaciones de ingeniería.

1. Vaya a **Gestión de cambios de ingeniería &gt; Preparar &gt; Organizaciones de ingeniería**.
1. Seleccione **Nuevo** para agregar una fila al a cuadrícula y establezca los valores siguientes:

    - **Organización de ingeniería**: *DEMF*
    - **Nombre de la organización:** *Contoso Entertainment System Alemania*

    ![Agregar una organización de ingeniería.](media/engineering-org.png "Agregar una organización de ingeniería")

### <a name="set-up-the-version-product-dimension-group"></a>Configurar el grupo de dimensiones del producto de la versión

1. Vaya a **Gestión de información de producto &gt; Preparar &gt; Dimensiones y grupos de variantes &gt; Grupos de dimensiones de productos**.
1. Seleccione **Nuevo** para crear un grupo de dimensiones de productos.
1. Establezca el campo **Nombre** en *Versión*.
1. Seleccione **Salvar** para guardar la nueva dimensión y cargar valores en la ficha desplegable **Dimensiones del producto**.
1. Sobre la ficha desplegable **Dimensiones del producto**, establezca **Versión** en una dimensión del producto activa.

    ![Agregar un grupo de dimensiones de producto.](media/product-dimension-groups.png "Agregar un grupo de dimensiones de producto")

### <a name="set-up-product-lifecycle-states"></a>Configurar estados de ciclo de vida de producto

A medida que un producto de ingeniería pasa por su ciclo de vida, es importante que pueda controlar qué transacciones están permitidas para cada estado del ciclo de vida. Para configurar los estados de ciclo de vida del producto, siga estos pasos.

1. Vaya a **Gestión de cambios de ingeniería &gt; Preparar &gt; Estado de ciclo de vida del producto**.
1. Seleccione **Nuevo** para agregar un estado de ciclo de vida y establezca los valores siguientes para el mismo:

    - **Estado:** *Operacional*
    - **Descripción:** *Operacional*

1. Seleccione **Salvar** para guardar el nuevo estado de ciclo de vida y cargar valores en la ficha desplegable **Procesos de negocio habilitados**.
1. Sobre la ficha desplegable **Procesos comerciales habilitados**, seleccione los procesos de negocio que deberían estar disponibles. Para este ejemplo, deje el campo **Política** establecido en *Habilitado* para todos los procesos comerciales.

    ![Habilitación de procesos comerciales para un estado de ciclo de vida.](media/product-lifecycle-states-1.png "Habilitación de procesos comerciales para un estado de ciclo de vida")

1. Seleccione **Nuevo** para agregar otro estado de ciclo de vida y establezca los valores siguientes para el mismo:

    - **Estado:** *Prototipo*
    - **Descripción:** *Prototipo*

1. Seleccione **Salvar** para guardar el nuevo estado de ciclo de vida y cargar valores en la ficha desplegable **Procesos de negocio habilitados**.
1. Sobre la ficha desplegable **Procesos comerciales habilitados**, seleccione los procesos de negocio que deberían estar disponibles. Para este ejemplo, establezca el campo **Política** en *Habilitado con advertencia* para todos los procesos comerciales.

    ![Habilitación (con advertencias) de procesos comerciales para un estado de ciclo de vida.](media/product-lifecycle-states-2.png "Habilitación (con advertencias) de procesos comerciales para un estado de ciclo de vida")

### <a name="set-up-a-version-number-rule"></a>Configurar una regla de número de versión

1. Vaya a **Gestión de cambios de ingeniería &gt; Preparar &gt; Regla de número de versión de producto**.
1. Seleccione **Nuevo** para agregar una regla y establezca los valores siguientes para la misma:

    - **Nombre:** *Auto*
    - **Regla numérica:** *Auto*
    - **Formato:** *V-\#\#*

    ![Agregar una regla de número de versión de producto.](media/version-number-rule.png "Agregar una regla de número de versión de producto")

### <a name="set-up-a-product-release-policy"></a>Configurar una política de lanzamiento de productos

1. Vaya a **Gestión de cambios de ingeniería &gt; Preparar &gt; Políticas de lanzamiento de productos**.
1. Seleccione **Nuevo** para agregar una política de lanzamiento y establezca los valores siguientes para el mismo:

    - **Nombre:** *Componentes*
    - **Descripción:** *Componentes*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Tipo de producto:** *Artículo*
    - **Aplicar plantillas:** *Siempre*
    - **Activo:** *Sí*

1. En la ficha desplegable **Todos los productos**, seleccione **Agregar** para agregar una línea y luego establecer los siguientes valores en ella:

    - **Empresa:** *DEMF*
    - **Plantilla de producto liberada**: *D0006*

1. Seleccione **Agregar** para agregar otra línea y establezca los siguientes valores para ella:

    - **Id. de cuenta de empresa**: *USMF*
    - **Plantilla de producto liberada**: *D0006*
    - **Recibir L.MAT:** seleccione esta casilla.
    - **Copiar la aprobación de la lista de materiales:** seleccione esta casilla.
    - **Copiar la activación de la lista de materiales:** seleccione esta casilla.
    - **Recibir ruta:** seleccione esta casilla.
    - **Copiar la aprobación de la ruta:** seleccione esta casilla.
    - **Copiar la activación de la ruta:** seleccione esta casilla.

    ![Agregar una política de lanzamiento de productos.](media/product-release-policy.png "Agregar una política de lanzamiento de productos")

### <a name="set-up-an-engineering-product-category"></a>Configurar una categoría de productos de ingeniería 

Las categorías de productos de ingeniería proporcionan la base para crear productos de ingeniería (es decir, productos que se versionan y controlan a través de la gestión de cambios de ingeniería). Siga estos pasos para configurar las categorías de productos de ingeniería.

1. Vaya a **Gestión de cambios de ingeniería &gt; Detalles de la categoría de productos de ingeniería**.
1. Seleccione **Nuevo** para crear una categoría.
1. En la ficha desplegable **Detalles**, establezca los valores siguientes:

    - **Nombre:** *Componentes*
    - **Organización de ingeniería**: *DEMF*
    - **Tipo de producto:** *Artículo*
    - **Seguimiento de la versión en transacciones:** *Sí*
    - **Grupo de dimensiones de producto:** *Versión*
    - **Estado del ciclo de vida del producto en el momento de la creación:** *Operacional*
    - **Regla de número de versión:** *Auto*
    - **Hacer cumplir la efectividad:** *No*
    - **Utilice la nomenclatura de la regla numérica:** *No*
    - **Utilice la nomenclatura de la regla de nombres:** *No*
    - **Utilice la nomenclatura de la regla de descripción:** *No*

1. En la ficha desplegable **Política de publicación**, establezca el campo **Política de lanzamiento de productos** en *Componentes*.
1. Seleccione **Guardar**.

    ![Agregar una categoría de productos de ingeniería.](media/product-category-details.png "Agregar una categoría de productos de ingeniería")

### <a name="set-up-product-acceptance-conditions"></a>Configurar las condiciones de aceptación del producto

1. Utilice el selector de empresa en el lado derecho de la barra de navegación para cambiar a la entidad legal (empresa) *USMF*.
1. Vaya a **Gestión de cambios de ingeniería &gt; Preparar &gt; Parámetros de gestión de cambios de ingeniería**.
1. En la pestaña **Control de versiones**, en la sección **Aceptación del producto**, configure el campo **Aceptación del producto** como *Manual*.

    ![Configurar las condiciones de aceptación del producto.](media/engineering-change-management-parameters.png "Configurar las condiciones de aceptación del producto")

## <a name="create-a-new-engineering-product"></a>Crear un nuevo producto de ingeniería

Un producto de ingeniería es un producto que se versiona y controla mediante la gestión de cambios de ingeniería. En otras palabras, puede controlar los cambios durante su vida útil y la información de cambio se guardará mediante órdenes de cambio de ingeniería. Para crear productos de ingeniería, siga estos pasos.

1. Asegúrese de pertenecer a la entidad legal de su organización de ingeniería (*DEMF* para este ejemplo). Utilice el selector de empresas en el lado derecho de la barra de navegación según sea necesario.
1. Abra la página **Productos emitidos** mediante uno de estos pasos:

    - Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.
    - Vaya a **Gestión de cambios de ingeniería &gt; Común &gt; Productos lanzados**.

1. En el panel de acciones, en la pestaña **Producto** del grupo **Nuevo**, seleccione **Producto de ingeniería**.
1. En el cuadro de diálogo **Nuevo producto**, establezca los valores siguientes:

    - **Categoría de productos de ingeniería:** *Componentes*
    - **Número de producto:** *Z0001*
    - **Nombre del producto:** *Juego de altavoces*

    ![Agregar un producto de ingeniería.](media/new-product-dialog.png "Agregar un producto de ingeniería")

    Tenga en cuenta que el campo **Versión** se establece automáticamente mediante la regla del número de versión del producto que configuró anteriormente.

1. Seleccione **Aceptar** para crear el producto y cerrar el cuadro de diálogo.
1. Se abre la página de detalles del nuevo producto. Observe que los valores ya están completados para algunos campos, como **Grupo de dimensiones de almacenamiento**, **Grupo de dimensiones de seguimiento** o **Grupo de modelo de artículo**. Estos campos se establecieron automáticamente porque el producto se lanza en la entidad jurídica *DEMF* y utiliza la política de lanzamiento de productos de *Componentes*, que está asociada con la categoría de producto de ingeniería *Componentes*. Porque usó anteriormente el artículo *D0006* como plantilla para configurar una línea para la entidad jurídica *DEMF*, los valores que se completaron se tomaron del elemento *D0006*.

    ![Detalles de producto emitido.](media/product-details.png "Detalles de producto emitido")

1. En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **Gestión de cambios de ingeniería**, seleccione **Versiones de ingeniería** para ver las versiones del producto.

    ![Versiones de ingeniería.](media/engineering-versions-list.png "Versiones de ingeniería")

1. En la página **Versiones de ingeniería**, observe que solo hay una versión para el producto, y está activa.
1. Seleccione la versión para ver los detalles.

    ![Detalles de la versión de ingeniería.](media/engineering-version-details.png "Detalles de la versión de ingeniería")

1. En la página **Versión de ingeniería**, en la pestaña desplegable **Lista de materiales**, seleccione **Crear lista de materiales**.
1. En el cuadro de diálogo **Crear L.MAT.**, establezca los valores siguientes:

    - **Número de L.MAT.:** Z0001
    - **Nombre**: Juego de altavoces
    - **Sitio**: 1

    ![Creación de una BOM.](media/create-bom.png "Creación de una BOM")

1. Seleccione **Aceptar** para agregar la lista de materiales y cerrar el cuadro de diálogo.
1. En la ficha desplegable **Lista de materiales**, seleccione **Lista de materiales**.
1. En la página **Lista de materiales**, en la ficha despelgable **Líneas de lista de materiales**, agregue tres líneas, una para cada número de artículo *D0001*, *D0003* y *D0006*.

    ![Agregar líneas de lista de materiales.](media/bom.png "Agregar líneas de lista de materiales")

1. Seleccione **Guardar**.
1. Cierre la página.
1. En la página **Versión de ingeniería**, en la pestaña desplegable **Lista de materiales**, seleccione **Aprobar**.
1. En el cuadro de diálogo que aparece, seleccione **Aceptar**.

    ![Aprobación de la lista de materiales.](media/approve-dialog.png "Aprobación de la lista de materiales")

1. En la página **Versión de ingeniería**, en la pestaña desplegable **Lista de materiales**, seleccione **Activar**.
1. Note que las casillas **Activo** y **Aprobado** están seleccionadas para la lista de materiales.

    ![L.MAT activa y aprobada.](media/approved-bom.png "L.MAT activa y aprobada")

1. Cierre la página.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Liberar un producto de ingeniería a una empresa local

El producto ahora ha sido diseñado por el departamento de Ingeniería. Para este ejemplo, el producto es un prototipo que la ingeniería ha diseñado para un cliente. Porque el cliente es un cliente de la entidad legal *USMF*, el producto debe entregarse a esa entidad legal.

1. Mantener la entidad legal configurada en *DEMF*. (Utilice el selector de empresas en el lado derecho de la barra de navegación según sea necesario).
1. Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.
1. Seleccione el producto *Z0001*.
1. En el panel de acciones, en la pestaña **Producto**, en el grupo **Mantener**, seleccione **Estructura del producto de liberación** para abrir el asistente **Productos de lanzamiento**.
1. En la página **Seleccionar productos de ingeniería para lanzar**, seleccione la casilla **Seleccionar** para el producto *Z0001*.

    ![Seleccionar los productos de ingeniería para lanzar.](media/select-eng-product-to-release.png "Seleccionar los productos de ingeniería para lanzar")

1. Seleccione **Detalles de lanzamiento**.
1. Aparece la página **Detalles del lanzamiento del producto**, donde puede revisar los detalles del producto que se lanzará y su estructura de producto. Observe que la opción **Enviar L.MAT.** está establecida en *Sí*. Por tanto, se liberarán tanto el producto *Z0001* como todos sus elementos secundarios de la lista de materiales.

    Puede seleccionar cualquier elemento secundario en el panel izquierdo para revisar sus detalles. Si algún artículo secundario tiene una lista de materiales, también puede seleccionar liberar la lista de materiales de ese artículo secundario.

    ![Revisión de los detalles del lanzamiento del producto.](media/product-release-details.png "Revisión de los detalles del lanzamiento del producto")

1. Cierre la página para para volver al asistente **Productos liberados**.
1. Seleccione **Siguiente** para abrir la página **Seleccionar productos para lanzar**. Si ha seleccionado algún producto estándar (que no sea de ingeniería), aparecería en esta página. Tenga en cuenta que cuando lanza un producto estándar seleccionando **Estructura del producto de liberación**, también se publican su lista de materiales y su ruta.

    ![Seleccionar los productos estándar para lanzar.](media/select-std-product-to-release.png "Seleccionar los productos estándar para lanzar")

1. Seleccione **Siguiente** para abrir la página **Seleccionar variantes de productos**. Para este ejemplo, no hay variantes.
1. Seleccione **Siguiente** para abrir la página **Seleccionar empresas**.
1. Seleccione las empresas a las que se debe entregar el producto. Para este ejemplo, seleccione la casilla para **USMF**.

    ![Seleccionar las empresas a las que lanzar.](media/select-release-companies.png "Seleccionar las empresas a las que lanzar")

1. Seleccione **Siguiente** para abrir la página **Confirmar selección**.
1. Seleccione **Fin**.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>Revise y acepte el producto antes de lanzarlo en la empresa local.

El departamento de Ingeniería ahora ha entregado la información a las empresas locales donde se utilizará el producto. Para este ejemplo, la empresa local es *USMF*.

Porque establece el campo **Aceptación del producto** en *Manual* en la página **Parámetros de gestión de cambios de ingeniería** para la empresa *USMF*, los productos deben aceptarse manualmente antes de que se entreguen a esa empresa. En otras palabras, deben revisarse y aceptarse antes de que se conviertan en productos comercializados.

Para revisar el producto y publicarlo en la empresa *USMF*, siga estos pasos.

1. Establezca la entidad legal configurada en *USMF*. (Utilice el selector de empresas en el lado derecho de la barra de navegación).
1. Vaya a **Gestión de cambios de ingeniería &gt; Común &gt; Lanzamientos de productos &gt; Lanzamientos de productos abiertos**.

    La página **Lanzamientos de productos abiertos** muestra el producto *Z0001*, que tiene un estado de *A la espera de aceptación*.

    ![Emisiones abiertas de productos.](media/open-product-releases.png "Emisiones abiertas de productos")

1. Seleccione el valor en la columna **Número de producto** para abrir la página **Detalles del lanzamiento del producto**. Tenga en cuenta los siguientes detalles:

    - La ficha desplegable **General** muestra información sobre el lanzamiento del producto, como la empresa de lanzamiento (*DEMF* para este ejemplo), el sitio de publicación (*1*) y el sitio de recepción (*1*). Debido a que no especificó un sitio receptor en el asistente **Productos de lanzamiento**, el valor del sitio de liberación se copia en el sitio de recepción.
    - La ficha desplegable **Detalles de lanzamiento** muestra información sobre el producto y la versión que se lanzó. Aquí, puede modificar configuraciones como las fechas de vigencia.
    - La ficha desplegable **Ruta** muestra la ruta del producto. Sin embargo, para este ejemplo, no liberó ninguna ruta.

    ![Detalles de liberación de producto.](media/product-release-details-2.png "Detalles de liberación de producto")

1. Cuando haya terminado de revisar la información, está listo para aceptar el producto y, de esta forma, liberarlo en la empresa *USMF*. En el panel de acciones, seleccione **Acciones &gt; Aceptar**.
1. Ahora el producto se ha lanzado en la compañía *USMF*. Vaya a **Gestión de información de productos &gt; Productos &gt; Productos despachados**. Debería ver el artículo *Z0001*.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>Utilice el producto en transacciones en la empresa local.

El administrador de datos maestros para la empresa *USMF* quiere asegurarse de que el producto esté en un estado *Prototipo*, para garantizar que los usuarios sean advertidos si lo agregan accidentalmente a los procesos en los que están trabajando.

1. Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.
1. Seleccione el producto *Z0001* para abrir su página de detalles. (Puede usar el filtro para encontrar el producto).
1. En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **Gestión de cambios de ingeniería**, seleccione **Versiones de ingeniería**.
1. Sobre la página **Versiones de ingeniería**, seleccione el número de versión *V-01* para abrir su página de detalles.
1. En el panel de acciones, en la pestaña **Producto** del grupo **Estado de ciclo de vida**, seleccione **Cambiar estado de ciclo de vida**.
1. En el cuadro de diálogo desplegable **Cambiar el estado del ciclo de vida**, configure el campo **Estado** en *Prototipo* y luego seleccione **Aceptar**.

    ![Cambiar el estado del ciclo de vida.](media/change-lifecycle-state.png "Cambiar el estado del ciclo de vida")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Agregar un producto de ingeniería a una orden de venta

El producto ahora se puede vender a un cliente. Para agregar el producto a un pedido de ventas, siga estos pasos.

1. Vaya a **Ventas y marketing &gt; Pedidos de ventas &gt; Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca el campo **Cuenta de cliente** en *US-0002* y luego seleccione **Aceptar**.
1. Se abre el nuevo pedido de ventas. Sobre la ficha desplegable **Líneas de orden de venta**, agregue una fila y establezca el campo **Número de artículo** en *Z000* para ello.
1. En el panel Acciones, seleccione **Guardar**.

    Recibe un mensaje de advertencia que le informa que el artículo tiene un estado de *Prototipo*. Sin embargo, debido a que el mensaje es solo una advertencia, la orden de venta aún se creó.

    ![Pedido de ventas para un producto de ingeniería.](media/sales-order-eng-product.png "Pedido de ventas para un producto de ingeniería")

## <a name="request-changes-in-the-engineering-product"></a>Solicitar cambios en el producto de ingeniería

El producto se envió a un cliente, pero el cliente no estaba completamente satisfecho y proporciona comentarios que incluyen sugerencias de mejora. Mientras el cliente habla con un empleado de ventas por teléfono, el empleado de ventas puede solicitar los cambios que describe el cliente.

1. Vaya a **Ventas y marketing &gt; Pedidos de ventas &gt; Todos los pedidos de ventas**.
1. Busque y abra el pedido de cliente que creó en el ejercicio anterior.
1. Sobre la ficha desplegable **Líneas de orden de venta**, seleccione **Gestión de cambios de ingeniería &gt; Nueva solicitud de cambio de ingeniería**.

    ![Crear una solicitud de cambio de ingeniería a partir de un pedido de cliente.](media/sales-order-eng-change-request.png "Crear una solicitud de cambio de ingeniería a partir de un pedido de cliente")

1. Complete la solicitud de cambio de ingeniería, según los comentarios del cliente. Para este ejemplo, establezca los siguientes valores:

    - **Cambiar solicitud** *555*
    - **Título:** *Cambio de cliente Z0001*
    - **Prioridad:** *bajo*
    - **Categoría:** establecer cambio
    - **Gravedad:** *Media*

1. En la ficha desplegable **Información**, seleccione **Nueva &gt; Nota** para agregar una nota a la cuadrícula.
1. En el campo **Descripción** para la nueva nota, indique que el elemento *D0003* debe eliminarse de la lista de materiales. Si debe agregar más información para la nota, puede ingresar texto en el campo **Notas**.

    ![Solicitud de cambio de ingeniería.](media/eng-change-request.png "Solicitud de cambio de ingeniería")

1. En el panel Acciones, seleccione **Guardar**.
1. Observe que el elemento se ha agregado automáticamente en la ficha desplegable **Productos** y que el origen de la solicitud de cambio de ingeniería (el pedido de ventas) se ha agregado en la ficha desplegable **Fuente**.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>Realice cambios en el producto mediante una orden de cambio de ingeniería

El vendedor sabe que el producto es importante y fue diseñado especialmente para el cliente. Por lo tanto, el empleado de ventas llama a un ingeniero en la empresa *DEMF* para notificarles sobre la solicitud de cambio. De esta forma, el ingeniero puede acelerar el proceso.

El ingeniero ahora revisa la solicitud del cliente y crea una orden de cambio para el producto.

1. Porque el ingeniero trabaja en la empresa *DEMF*, establezca la entidad legal en *DEMF*. (Utilice el selector de empresas en el lado derecho de la barra de navegación).
1. Vaya a **Gestión de cambios de ingeniería &gt; Común &gt; Solicitudes de cambios de ingeniería**.
1. Abra la solicitud de cambio *555*.
1. Revise la información y luego apruebe el cambio. En el panel de acciones, en la ficha **Solicitud de cambio**, en el grupo **Cambiar estado**, seleccione **Aprobar**.
1. Vaya a **Gestión de cambios de ingeniería &gt; Común &gt; Órdenes de cambios de ingeniería**.
1. En el panel de acciones, seleccione **Nuevo** para crear una orden de cambio y establezca los siguientes valores:

    - **Orden de cambio:** *555*
    - **Título:** *Cambio de cliente Z0001*
    - **Categoría:** *Cambio de cliente*
    - **Prioridad:** *Baja*
    - **Gravedad:** *Media*

1. En la ficha desplegable **Productos afectados**, seleccione **Nuevo &gt; Agregar producto existente** para agregar una fila a la cuadrícula y luego establecer los siguientes valores para ella:

    - **Producto:** *Z0001*
    - **Impacto:** *Nueva versión*

    ![Crear una orden de cambio de ingeniería.](media/eng-change-order.png "Crear una orden de cambio de ingeniería")

1. Tenga en cuenta que, debido a que establece el campo **Impacto** en *Nueva versión*, el campo **Nueva versión** de la pestaña **Detalles** de la ficha desplegable **Detalles de producto** muestra cuál será el nuevo número de versión (*V-02* para este ejemplo).

    ![Detalles de producto para una orden de cambio de ingeniería.](media/eng-change-order-product-details.png "Detalles de producto para una orden de cambio de ingeniería")

1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Detalles de producto**, en la pestaña **Lista de materiales**, seleccione **Líneas** para abrir la lista de materiales para la versión *V-01* del producto *Z0001*.

    ![Líneas de lista de materiales de productos de ingeniería.](media/eng-product-bom-lines.png "Líneas de lista de materiales de productos de ingeniería")

1. Seleccione la línea para el número de artículo *D0003* y, a continuación, en el panel de acciones, seleccione **Eliminar**. El valor del campo **Tipo de cambio** de esta línea cambia a *Eliminado*.
1. En el panel Acciones, seleccione **Guardar**.

    ![Líneas de lista de materiales de productos de ingeniería modificadas.](media/eng-product-bom-lines-modified.png "Líneas de lista de materiales de productos de ingeniería modificadas")

1. Cierre la página **Línea de lista de materiales** para volver a la página **Orden de cambio de ingeniería**.
1. En la ficha desplegable **Detalles de producto**, en la pestaña **Lista de materiales**, observe que el valor del campo **Tipo de cambio** para la L. MAT. *Z0001* ahora es *Cambiado*.

    ![Orden de cambio de ingeniería que incluye una lista de materiales modificada.](media/eng-change-order-changed-bom.png "Orden de cambio de ingeniería que incluye una lista de materiales modificada")

    Ahora se debe aprobar el pedido para que se puedan procesar los cambios. Cuando se procesan los cambios, los productos se actualizan con los cambios que se incluyen en la orden de cambio de ingeniería. Para este ejemplo, la persona que crea la orden de cambio de ingeniería se ha especificado como aprobador.

1. En el panel de acciones, en la ficha **Orden de cambio**, en el grupo **Cambiar estado**, seleccione **Aprobar**.
1. Seleccione **Proceso** para actualizar la información del producto.

## <a name="release-the-changed-product"></a>Liberar el producto cambiado

El producto ahora se puede lanzar nuevamente a la empresa *USMF* y luego se envía al cliente. Para liberar el producto directamente de la orden de cambio de ingeniería, siga estos pasos.

1. Abra la orden de cambio de ingeniería que creó en el ejercicio anterior, si aún no está abierta.
1. En el panel de acciones, en la ficha **Orden de cambio**, en el grupo **Versiones de producto**, seleccione **Buscar**.
1. Los resultados de la búsqueda muestran a qué empresas se han entregado los productos afectados. Cerrar los resultados de la búsqueda.
1. En el panel de acciones, en la pestaña **Orden de cambio**, en el grupo **Lanzamientos de productos**, seleccione **Ver** para abrir el cuadro de diálogo **Lanzamientos**, donde puede ver los resultados de la búsqueda anterior.
1. Seleccione cada empresa a la que desee lanzar productos.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Versiones** y volver a la orden de cambio.
1. En el panel de acciones, en la pestaña **Orden de cambio**, en el grupo **Lanzamientos de productos**, seleccione **Proceso** para liberar los productos afectados a las empresas seleccionadas. Alternativamente, seleccione **Estructura del producto de liberación** para iniciar el proceso de liberación.

## <a name="complete-the-change-order"></a>Completar la orden de cambio

Para marcar la orden de cambio como completada, lo que indica que no quedan más acciones, seleccione **Completar** en el Panel de acciones.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
