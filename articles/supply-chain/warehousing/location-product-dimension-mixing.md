---
title: Combinación de dimensiones de producto de ubicación
description: Este tema proporciona información acerca de la combinación de dimensiones de producto de ubicación. Esta funcionalidad de perfil de ubicación ayuda a mejorar la administración de ubicación cuando se utilizan variantes de productos o productos que tienen dimensiones, como en la industria de la moda. Le permite decidir si las configuraciones, colores, estilos y tallas se pueden mezclar para un perfil de ubicación específico, o si solo una de estas dimensiones o una combinación de ellas se puede colocar en la misma ubicación.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 031b92f827979c01dbf0208ba21ae827fb13920b
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103497"
---
# <a name="location-product-dimension-mixing"></a>Combinación de dimensiones de producto de ubicación

[!include [banner](../includes/banner.md)]

La combinación de dimensiones de producto de ubicación es una funcionalidad de perfil de ubicación que le ayuda a mejorar la administración de ubicación cuando se utilizan variantes de productos o productos que tienen dimensiones, como en la industria de la moda. Le permite decidir si las configuraciones, colores, estilos y tallas se pueden mezclar para un perfil de ubicación específico, o si solo una de estas dimensiones o una combinación de ellas se puede colocar en la misma ubicación.

## <a name="turn-the-location-product-dimension-mixing-feature-on-or-off"></a>Activar o desactivar la característica de combinación de dimensiones de producto de ubicación

Para utilizar la funcionalidad descrita en este tema, debe activarse la característica *Combinación de dimensiones de producto de ubicación* en su sistema. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Combinación de dimensiones de producto de ubicación* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="setup"></a>Configurar

Cada ubicación en el almacén requiere un perfil de ubicación asociado que describa las propiedades de la ubicación. Por lo tanto, todas las ubicaciones que usan el mismo perfil de ubicación podrán permitir la mezcla de dimensiones del producto después de que se haya configurado.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>Configurar perfiles de ubicación para permitir la mezcla de dimensiones del producto

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En la lista de perfiles de ubicación, seleccione **GRANEL**.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, configure la opción **Habilitar la combinación específica de dimensiones de producto de ubicación** en *Sí*.

    > [!NOTE]
    > Puede establecer esta opción en *Sí* solo si la opción **Permitir elementos mixtos** está establecida en *No*.

1. En la ficha desplegable **Combinación de dimensión de producto permitida**, establezca la opción **Talla** en *Sí*. En el escenario que se describe en este tema, la combinación solo se puede hacer para productos que tienen diferentes dimensiones de **Talla**. Sin embargo, hay otras opciones disponibles.
1. Seleccione **Guardar**.

### <a name="create-a-new-product-master-and-product-variants"></a>Crear un producto maestro nuevo y variantes de producto

1. Vaya a **Gestión de información de productos \> Productos \> Productos maestros**.
1. En el Panel de acciones, seleccione **Nuevo** para crear un producto maestro.
1. En el cuadro de diálogo **Nuevo producto**, establezca los valores siguientes:

    - **Tipo de producto:** *Artículo*
    - **Subtipo de producto:** *Producto maestro*
    - **Número de producto:** *B0001*
    - **Nombre de producto:** *B0001 Talla*
    - **Grupo de dimensiones de producto:** *Talla*
    - **Tecnología de configuración:** *Variante predefinida*

1. Seleccione **Aceptar**.
1. En la página **Detalles de producto**, en la ficha desplegable **General**, establezca los siguientes valores:

    - **Generar variantes automáticamente:** *Sí*
    - **Grupo de talla:** *CASUALDHIR*

1. Para ver las variantes predefinidas, en el Panel de acciones, seleccione **Variantes del producto**.

    Aparecerá la página **Variantes del producto** la página con una lista de variantes de la configuración del grupo de tallas.

### <a name="release-products-to-the-usmf-company"></a>Lanzar productos a la empresa USMF

1. En el panel de acciones, seleccione **Lanzar productos**.
1. En la página **Seleccione productos para lanzar**, confirme que el número de producto *B0001* está en la lista y luego seleccione **Siguiente**.
1. Seleccione **Siguiente** para confirmar las variantes del producto a lanzar.
1. En la página **Seleccione empresas para lanzar a**, seleccione *USMF* y luego seleccione **Siguiente** para confirmar la selección.
1. En la página **Confirmar selección**, seleccione **Terminar** para completar el lanzamiento.

    Recibe un mensaje "Operación completada".

### <a name="update-a-released-product-in-the-usmf-company"></a>Actualizar un producto lanzado en la compañía USMF

1. Asegúrese de haber iniciado sesión en la empresa **USMF**.
1. Vaya a **Gestión de información de productos \> Productos \> Productos lanzados** para terminar de crear el producto lanzado.
1. Encuentre y seleccione el número de artículo *B0001* para abrir la página **Detalles del producto lanzado**.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, asegúrese de que el campo **Grupo de modelo de artículo** se establece en *FIFO*.
1. En el panel Acciones, en la pestaña **Producto** del grupo **Configurar**, seleccione **Grupos de dimensión**.
1. Establezca los valores siguientes:

    - **Grupo de dimensiones de almacenamiento:** *Almacén*
    - **Grupo de dimensiones de seguimiento:** *Ninguno*

1. Seleccione **Aceptar**.
1. En el panel Acciones, en la pestaña **Producto** del grupo **Configurar**, seleccione **Jerarquía de reservas**.
1. Establezca el campo **Jerarquía de reservas** a *Predeterminado* y luego seleccione **Aceptar**.
1. En la ficha desplegable **General**, en la sección **Administración**, observe que sus selecciones se han actualizado.
1. En la ficha desplegable **Compra**, en el campo **Precio**, introduzca *10*.
1. En la ficha desplegable **Gestionar costes**, en el campo **Grupo de artículos**, introduzca *Audio*.
1. En la ficha desplegable **Compra**, en el campo **Precio**, introduzca *10*.
1. En la ficha desplegable **Almacén**, en el campo **Identificador de grupo de secuencia de unidad**, introduzca *ea*.
1. Seleccione **Guardar**.

### <a name="create-a-location-directive"></a>Crear una directiva de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, en el campo **Tipo de orden de trabajo**, seleccione *Pedidos de compra*.
1. En la lista, seleccione la directiva de ubicación que se denomina *24 PO directo*.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Número de secuencia:** *1*

        La nueva línea debe estar frente a la línea existente anteriormente. Para hacer el cambio, use los botones **Mover arriba** y **Mover abajo** en la barra de herramientas, o cambie el valor **Secuencia de números** de las líneas existentes a *2*.

    - **Nombre:** *Poner en perfil de ubicación GRANEL*
    - **Uso de ubicación fija:** *Ubicaciones fijas y no fijas*
    - **Permitir inventario negativo:** *desactive esta casilla de verificación (=No)*
    - **Lote habilitado:** *desactive esta casilla de verificación (=No)*
    - **Estrategia:** *Ninguna*

1. Mientras la nueva línea aún está seleccionada, seleccione **Editar consulta** sobre la cuadrícula.
1. En el cuadro de diálogo de consultas, en la pestaña **Rango**, seleccione **Agregar** para añadir una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Tabla derivada:** *Ubicaciones*
    - **Campo**: *ID de perfil de ubicación*
    - **Criterios**: *BULK*

1. Seleccione **Aceptar**.
1. En la página **Directivas de ubicación**, en el panel de acción seleccione **Guardar**.

> [!NOTE]
> En la ficha desplegable **Acciones de directiva de ubicación** en el campo **Estrategia**, si usa la estrategia de ubicación *Consolidar*, la configuración de la ficha desplegable **Permitir combinación de dimensiones de producto** en los **Perfiles de ubicación** se anulará y los elementos se colocarán en la misma ubicación incluso si la configuración no permite este comportamiento.

### <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el Panel de acciones, seleccione **Nuevo** para crear un elemento de menú para usar para ordenar.
1. Establezca los siguientes valores en el encabezado:

    - **Nombre del elemento del menú:** *Recepción de línea de pedido*
    - **Título:** *Recepción de línea de pedido*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *No*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Proceso de creación de trabajo:** *Recepción de línea de pedido de compra y almacenamiento*
    - **Generar matrícula de entidad de almacén:** *Sí*

1. Seleccione **Guardar**.

### <a name="configure-the-mobile-device-menu"></a>Configurar el menú de dispositivos móviles

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En la lista de menús, seleccione **Entrante**.
1. En el panel Acciones, seleccione **Editar**.
1. En la lista **Menús disponibles y elementos de menú**, busque y seleccione el elemento de menú **Recepción de línea de pedido**.
1. Seleccione el botón de flecha derecha para mover el elemento de menú **Recepción de línea de pedido** a la lista **Estructura del menú**. De esta manera, agrega su nuevo elemento de menú al menú seleccionado.
1. Seleccione **Guardar**.

## <a name="scenario"></a>Situación

Este escenario de demostración muestra cómo se pueden colocar dos variantes de producto diferentes en la misma ubicación cuando el perfil de ubicación no permite elementos mixtos, pero la función *Combinación de dimensiones de producto de ubicación* está habilitada. En este caso, utilizará la variante **Talla** como criterio.

Antes de comenzar, asegúrese de que haya ubicaciones vacías en el almacén *24* que usan el perfil de ubicación *GRANEL*.

### <a name="create-a-purchase-order"></a>Crear un pedido de compra

Creará un pedido de compra que tiene tres líneas: dos líneas para el mismo número de producto pero variantes de **Talla** distintas y una tercera línea para un producto diferente que no tiene variantes.

1. Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:

    - **Cuenta del proveedor:** *1001*
    - **Almacén**: *24*

1. Seleccione **Aceptar**.
1. Se crea el pedido de compra y se agrega una nueva línea en la ficha desplegable **Líneas de pedido de compra**. Anote el número del pedido de compra.
1. En la nueva línea, establezca los siguientes valores:

    - **Código de artículo:** *B0001*
    - **Talla** *L*
    - **Cantidad:** *2*

1. Seleccione **Agregar línea** encima de la cuadrícula para agregar una segunda línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *B0001*
    - **Talla** *XL*
    - **Cantidad:** *2*

1. Seleccione **Agregar línea** para agregar una tercera línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *1*

1.Seleccione **Guardar**.

### <a name="receive-purchase-order-lines-in-the-warehouse-management-mobile-app"></a>Reciba líneas de pedido de compra en la aplicación móvil Warehouse Management

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario habilitado para el almacén *24*.
1. Seleccione el menú **Entrante**.
1. Seleccione **Recepción de línea de pedido**.
1. Seleccione el campo **PONUM** e introduzca el número de pedido de compra.
1. Confirme su entrada seleccionando el botón de confirmación (✔) en la parte inferior de la página.
1. Introduzca el número de línea del pedido de compra que se está recibiendo. Selecciona el campo **LINENUM** y luego use el teclado numérico para introducir *1*.
1. Confirme su entrada.
1. Especifique la cantidad a recibir. Seleccione el signo más (**+**) dos veces para aumentar el valor en el campo **Cantidad** a *2*.
1. Registre su entrada seleccionando el botón (✔) en la parte inferior de la página, y luego confirme su entrada seleccionando el botón (✔) nuevamente.
1. Ver la información en la página **Órdenes de compra: Colocar**. Esta página muestra el trabajo que se ha creado para el almacenamiento (Trabajo 1).

    La ubicación donde se guardará el artículo recibido, la matrícula de entidad, el artículo, el tamaño y la cantidad de la tarea **Recibiendo pedido** muestran las tareas que acaba de completar.

1. Confirme el trabajo de ubicación.
1. Repita los pasos del 4 al 11 para la línea del pedido de compra 2. Sin embargo, en el paso 8, especifique una cantidad de *1*.

    Se crea un nuevo trabajo de guardado (Trabajo 2) para la misma ubicación que el Trabajo 1.

1. Repita los pasos del 4 al 11 de nuevo para la línea del pedido de compra 2. Sin embargo, en el paso 8, especifique una cantidad restante de *1*.

    Se crea un nuevo trabajo de guardado (Trabajo 3) para la misma ubicación que el Trabajo 1 y el Trabajo 2. Este comportamiento se produce porque se usa la estrategia directiva de ubicación de *Consolidar* y la ficha desplegable **Permitir combinación de dimensiones de producto** en la configuración *Granel* de **Perfiles de ubicación** permite a la variante **Talla** combinarse en una ubicación.

1. Repita los pasos del 4 al 11 para la línea del pedido de compra 3. En el paso 8, especifique una cantidad de *1* para el número de artículo *A0001*.

    Se crea un nuevo trabajo de almacenamiento (Trabajo 4) para una ubicación diferente a la ubicación que se utiliza para las líneas de pedido de compra 1 y 2. Este comportamiento se produce porque el perfil de ubicación no permite productos mixtos, pero sí permite dimensiones mixtas del mismo producto maestro.

1. Seleccione el botón Menú en la parte superior de la página (a veces denominado hamburguesa o botón de hamburguesa) y luego seleccione **Cancelar** para salir **Recibiendo línea de pedido de compras**.

> [!TIP]
> Puede repetir este escenario, pero esta vez, establezca **Talla** - *No* en la ficha desplegable **Permitir la combinación de dimensiones del producto** en *GRANEL* de **Perfiles de ubicación**, de modo que ninguna de las dimensiones del producto se pueda combinar. En este caso, cuando reciba el pedido de compra, cada variante de producto se colocará en una nueva ubicación.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]