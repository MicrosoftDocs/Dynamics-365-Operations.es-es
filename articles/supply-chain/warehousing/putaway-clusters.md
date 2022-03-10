---
title: Clústeres de ubicación
description: Los grupos de almacenamiento ofrecen una forma de elegir varias placas al mismo tiempo y luego llevarlas a almacenamiento en diferentes ubicaciones. Pueden ser muy útiles para negocios minoristas, donde las placas de matrícula generalmente no son paletas llenas de inventario.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d5aa579394a0e3bd4c27cd44c9ff98951b3bfe1c
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103672"
---
# <a name="putaway-clusters"></a>Clústeres de ubicación

[!include [banner](../includes/banner.md)]

Los grupos de almacenamiento ofrecen una forma de elegir varias placas al mismo tiempo y luego llevarlas a almacenamiento en diferentes ubicaciones. Este proceso suele denominarse como *recorrido*. Los clústeres de ubicación pueden ser muy útiles para negocios minoristas, donde las placas de matrícula generalmente no son paletas llenas de inventario. 

## <a name="turn-the-cluster-putaway-feature-on-or-off"></a>Activar o desactivar la característica de ubicación de clúster

Para utilizar la funcionalidad descrita en este tema, debe activarse la característica *Función de almacenamiento en grupo* en su sistema. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Función de almacenamiento en grupo* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="setup-for-the-example-scenario"></a>Configuración para el escenario de ejemplo

### <a name="cluster-profiles"></a>Perfiles de clúster

El perfil del grupo de almacenamiento determina dónde irá un artículo, según la ubicación asignada al artículo en el momento de la recepción. Si se requieren diferentes clústeres, se deben crear un clústeres de ubicación diferentes, uno para cada elemento del menú de dispositivo móvil.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Perfiles de clúster**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en la vista **Encabezado**:

    - **ID de perfil de clúster de almacenamiento:** *Almacenamiento en clúster*
    - **Nombre de ID de perfil de clúster de almacenamiento:** *Almacenamiento en clúster*
    - **Tipo de clúster:** *Ubicación*
    - **Número de secuencia:** acepte el valor predeterminado.

1. Seleccione **Guardar** para tener disponibles los campos necesarios en la ficha desplegable **General**.
1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Tiempo de asignación de clústeres:** *Al recibir*

        Este campo define si el grupo de almacenamiento debe asignarse inmediatamente cuando se recibe el inventario, o si debe clasificarse más tarde.

    - **Regla de asignación de clústeres:** *Manual*

        Este campo define si la asignación de clúster se debería determinar automáticamente por el sistema o hacer manualmente por el usuario.

    - **Código de directiva:** deje en blanco este campo.
    - **Ubicación del clúster de almacenamiento:** *Recepción*

        Los siguientes valores están disponibles:

        - **Recepción**: una ubicación se encuentra inmediatamente durante la recepción.
        - **Cierre del clúster**: la ubicación encontrada cuando se cierra el clúster.
        - **Dirigido por el usuario**: se encuentra una ubicación cuando se elige la placa de matrícula del grupo para guardarla. En este caso, no se especifica ninguna ubicación cuando se crea el trabajo de almacenamiento. Durante el almacenamiento en sí, el usuario debe escanear la matrícula o la identificación del trabajo para iniciar el paso de colocación. Luego, el sistema encuentra la ubicación de colocación nuevamente y le dice al usuario dónde colocar la cantidad recolectada.

    - **Clúster de almacenamiento por usuario:** *No*

        Este campo define si cada clúster debe ser único por usuario cuando los clústeres se asignan automáticamente. Está disponible solo cuando el campo **Regla de asignación de clústeres** está configurado en *Automático*.

    - **Restricción de unidad:** deje este campo en blanco.

        Este campo define la unidad que se debe recibir para que el perfil sea válido. Si se deja en blanco, todas las unidades son válidas.

    - **Rotura de la unidad de trabajo:** *Individual*

        Este campo define si todo el inventario debe consolidarse (mediante el uso de la identificación del grupo y la placa) en una placa cuando un grupo está cerrado, y si debe guardarse como una sola placa o por separado en las placas que estaban recibido. Este campo no está disponible cuando el campo **Ubicación del clúster de almacenamiento** el campo está configurado en *Recibo*.

    - **El clúster persiste como matrícula principal:** *No*

        Si esta opción se establece en *Sí*, cuando se completa el paso de colocación, la identificación del grupo se convertirá en una placa de matrícula principal y todos los elementos de la identificación de grupo se vincularán a esa placa de matrícula principal.

1. En la ficha desplegable **Clasificación de grupos**, puede definir criterios de clasificación de almacenamiento. Seleccione **Nuevo** en la barra de herramienats para agregar una línea y después establezca los valores siguientes:

    - **Número de secuencia:** acepte el valor predeterminado.
    - **Nombre de campo:** introduzca *WMSLocationId*.

        Este campo define el campo que esta línea debe usar como criterio de clasificación.

    - **Clasificación:** *Ascendente*

        Este campo define si la ordenación se debe realizar en orden ascendente o descendente.

1. En la ficha desplegable **Plantilla de trabajo de clúster**, seleccione **Nuevo** en la barra de herramientas para agregar una línea y luego establecer los siguientes valores:

    - **Tipo de orden de trabajo**: *Pedidos de compra*
    - **Plantilla de trabajo:** *PO directa 61*

1. En el panel de acciones, seleccione **Salvar** y luego seleccione **Editar consulta**.
1. En el cuadro de diálogo **Ubicación de clúster**, en la pestaña **Rango**, seleccione **Agregar** para añadir una línea a la cuadrícula. Luego actualice las líneas de consulta como se muestra en la siguiente tabla.

    | Tabla | Tabla derivada | Campo | Criterios |
    |---|---|---|---|
    | Trabajo | Trabajo | Almacén | *61* |
    | Trabajo | Trabajo | Id. de trabajo | Deje este campo en blanco. |

1. Seleccione **Aceptar** para guardar la consulta y cerrar el cuadro de diálogo.
1. En el la panel de acciones, seleccione **Guardar** y después cierre la página.

> [!IMPORTANT]
> Campos en el perfil del clúster que aparecen atenuados cuando **Generar ID de clúster** se establece en *Sí* no están disponibles y no se tendrán en cuenta cuando se utilice esta función.

### <a name="mobile-device-menu-items"></a>Elementos de menú del dispositivo móvil

Hay dos nuevos elementos del menú del dispositivo móvil disponibles para esta función. El elemento de menú **Recibir y ordenar clúster** se utiliza para clasificar el inventario recibido en un grupo de almacenamiento al recibirlo. El elemento de menú **Ubicación de clúster** se utiliza para guardar el clúster después de haber sido asignado.

#### <a name="receive-and-sort-cluster"></a>Recibir y ordenar clúster

Cree un nuevo elemento de menú de dispositivo móvil para recibir inventario y clasificar en un grupo. Este elemento del menú creará trabajo entrante después de que se reciba el inventario, lo que indica que el elemento del menú de recepción se utilizará para los grupos de almacenamiento.

> [!NOTE]
> El elemento del menú **Recibir y ordenar clúster** se puede utilizar con los siguientes elementos del menú de recepción:
>
> - Recepción de línea del pedido de compra
> - Recepción de artículo del pedido de compra
> - Recepción de artículo de carga

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en la vista **Encabezado**:

    - **Nombre del elemento del menú:** *Recibir y ordenar clúster*
    - **Título:** *Recibir y ordenar clúster*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *No*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Proceso de creación de trabajo**: *Recepción de artículos de pedido de compra*
    - **Generar matrícula de entidad de almacén:** *Sí*
    - **Asignar clúster de almacenamiento:** *Sí*

        > [!NOTE]
        > La opción **Asignar clúster de almacenamiento** está disponible solo para la actividad *Proceso de creación de obra* para la recepción.

    Acepte los valores predeterminados del resto de campos.

1. En el panel Acciones, seleccione **Guardar**.

#### <a name="cluster-putaway"></a>Ubicación de clúster

Cree un nuevo elemento de menú de dispositivo móvil para guardar el clúster después de que se haya asignado.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en la vista **Encabezado**:

    - **Nombre del elemento del menú**: *Ubicación de clúster*
    - **Título:** *Almacenamiento de clúster*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*

1. En la ficha desplegable **General**, establezca el campo **Dirigido por** en *Ubicación de clúster*. Acepte los valores predeterminados del resto de campos.
1. En la ficha desplegable **Clases de trabajo**, configure la clase de trabajo válida para este elemento de menú de dispositivo móvil:

    - **Id. de la clase de trabajo**: *Compra*
    - **Tipo de orden de trabajo**: *Pedidos de compra*

1. En el panel Acciones, seleccione **Guardar**.

### <a name="mobile-device-menu"></a>Menú del dispositivo móvil

Agregue los elementos del menú que acaba de crear al menú de entrada de la aplicación móvil.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En el panel Acciones, seleccione **Editar**.
1. En la lista de menús, seleccione **Entrante**.
1. En la lista **Menús disponibles y elementos de menú**, busque y seleccione **Recibir y ordenar clúster**.
1. Seleccione el botón de flecha derecha para mover el elemento de menú seleccionado a la lista **Estructura del menú**.
1. Utilice el botón de flecha hacia arriba o flecha hacia abajo para mover el elemento del menú a la posición deseada en el menú.
1. En el panel Acciones, seleccione **Guardar**.
1. Repita los pasos del 4 al 7 para agregar los elementos de menú restantes:

    - Asignar clúster
    - Ubicación de clúster

## <a name="example-scenario"></a>Supuesto de ejemplo

Este escenario simula el procesamiento del clúster de almacenamiento.

### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:

    - **Cuenta del proveedor:** *1001*
    - **Almacén**: *61*

1. Seleccione **Aceptar**.

    Aparece la página **Todos los pedidos de compra**.

1. En la página **Todas las órdenes de compra**, en la ficha desplegable **Líneas de orden de compra**, use el botón **Añadir línea** para agregar las siguientes líneas:

    - Línea de pedido de compra 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *10*

    - Línea de pedido de compra 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *20*

    - Línea de pedido de compra 3:

        - **Código de artículo:** *M9215*
        - **Cantidad:** *30*

1. En el panel Acciones, seleccione **Guardar**.
1. Anote el número del pedido de compra.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Reciba inventario y guárdelo fuera del dispositivo móvil

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>Reciba y clasifique el inventario en un grupo

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario configurado para el almacén *61*.
1. En el menú principal, seleccione **Entrada**.
1. En el menú **Entrante**, seleccione **Recibir y ordenar clúster**.
1. En el campo **Ponum**, introduzca el número de orden de compra.
1. Seleccione **Aceptar** (botón de de marca de verificación).
1. Seleccione el campo **Artículo**, introduzca el número de artículo *A0001* y seleccione **Aceptar**.
1. Seleccione el campo **Cant.**, ingrese *10* utilizando el teclado numérico y luego seleccione el botón de marca de verificación.
1. En la página de tareas **Cant.**, seleccione **Aceptar** (botón de marca de verificación) para confirmar la cantidad que ingresó.
1. En la página de tareas **Artículo**, seleccione **Aceptar** para confirmar que se introdujo el artículo *A0001*.
1. Seleccione el campo **ID de clúster** e ingrese un valor para asignar un ID para el clúster que está creando.

    La identificación que ingrese aquí se utilizará cuando se reciban los dos artículos restantes en la orden de compra.

1. Seleccione **Aceptar**.

    La página de tareas **Ponum** aparece y muestra un mensaje de "Trabajo completado".

    Ahora el artículo *A0001* ha sido recibido en la ubicación *RECV* y se asigna al ID de clúster que ingresó en el paso 10.

1. Repita los pasos del 4 al 11 para recibir los dos artículos restantes de la orden de compra y asígnelos al ID del clúster:

    - Una cantidad de *20* para el artículo *A0002*
    - Una cantidad de *30* para el artículo *M9215*

#### <a name="close-the-cluster"></a>Cerrar el clúster

Antes de que los elementos del clúster se puedan guardar, el clúster debe cerrarse.

1. En Supply Chain Management, vaya a **Gestión de almacenes \> Trabajo \> Saliente \> Grupos de trabajo**.
1. En la página **Grupos de trabajo**, en la sección **Grupo de trabajo**, busque el **ID de clúster** para el ID de clúster que ingresó anteriormente.
1. Si no se muestra el clúster, es posible que ya se haya cerrado. Para determinar si el clúster estaba cerrado, seleccione la casilla de verificación **Mostrar trabajo cerrado** y busque el ID de clúster que ingresó anteriormente. Luego siga uno de estos pasos:

    - Si el clúster se ha cerrado, omita los pasos restantes de este procedimiento y continúe con el siguiente procedimiento, [Guardar el clúster](#put-the-cluster-away).
    - Si el clúster no se ha cerrado, siga los pasos restantes de este procedimiento para cerrarlo manualmente. Después vaya al procedimiento siguiente.

1. En la sección **Grupo de trabajo**, seleccione el ID de clúster que ingresó anteriormente.
1. En el panel de acciones, seleccione **Cerrar clúster**.

    Una vez cerrado el clúster, ya no se muestra en la sección **Grupo de trabajo** (a menos que la casilla de verificación **Mostrar trabajo cerrado** esté seleccionada).

#### <a name="put-the-cluster-away"></a>Guardar el clúster

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario configurado para el almacén *61*.
1. En el menú principal, seleccione **Entrada**.
1. En el menú **Entrante**, seleccione **Ubicación de clúster**.
1. Seleccione **ID de clúster** e ingrese el ID de clúster que ingresó anteriormente para el clúster cerrado.
1. Seleccione **Aceptar**.

    Aparece la paǵina **Ubicación de clúster: selección**. Muestra el ID del clúster, la ubicación de recolección, los artículos (el valor *Múltiple* se mostrará) y la cantidad total en el grupo que se debe recolectar.

1. Seleccione **Aceptar**.

    Aparece la paǵina **Ubicación de clúster: ubicación**. Las instrucciones de **Ubicación** identifican el ID del grupo, la ubicación de colocación, los artículos, la cantidad total y las identificaciones de las placas de los artículos que se han recibido en el grupo.

    Tiene las opciones estándar para anular o aprobar este paso.

    ![Página Ubicación de clúster: ubicación.](media/Cluster_putaway-Put.png "Página Ubicación de clúster: ubicación")

1. Seleccione **Aceptar** para confirmar la ubicación del clúster.

    Se muestra un mensaje "Clúster completado".

## <a name="notes-and-tips"></a>Notas y consejos

Para los casos en los que la identificación del grupo se convierte en la placa de matrícula principal de un palé anidado, la posición de colocación se da automáticamente cuando se escanea la identificación del grupo. No se deben escanear más matrículas, incluso si la generación de matrículas está configurada en manual.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]