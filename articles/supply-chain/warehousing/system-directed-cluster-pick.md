---
title: Selección de clúster dirigida por el sistema
description: Este tema proporciona una descripción general de la selección de clúster dirigida por el sistema en Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 390e0a3379a6482e99a13f4f7835b5264e3747ac
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217250"
---
# <a name="system-directed-cluster-picking"></a>Selección de clúster dirigida por el sistema

[!include [banner](../includes/banner.md)]

La selección de clúster es un proceso de selección de piezas que le permite elegir artículos para múltiples pedidos al mismo tiempo agrupándolos en clústeres de selección. Después tendrá que visitar el lugar de selección una sola vez. Por lo general, esta funcionalidad se usa para seleccionar pedidos pequeños o cantidades que son menores que la de cajas.

Cuando se configura la selección de clúster dirigida por el sistema, puede seleccionar los encabezados de trabajo de selección de clúster en función de un clúster generado por el sistema. El sistema selecciona en clúster los pedidos hasta el número de posiciones especificado en el perfil del clúster. Por lo tanto, puede seleccionar varios pedidos a la vez sin tener que crear manualmente un clúster.

La selección de clúster dirigida por el sistema ofrece una alternativa a la creación manual de clúster, donde se utiliza un perfil de clúster para crear un clúster. Hay que definir varias líneas relacionadas con la configuración en el perfil del clúster antes de usarlo:

- **Numero de posiciones** corresponde al número de pedidos que se colocarán en un clúster. Por lo tanto, corresponde al número de bolsas.
- **Dividir clúster** determina cuándo se debe dividir el clúster.
- **Generar id. de clúster** controla si el sistema generará el id. del clúster o si lo especificará el usuario.
- **Tipo de comprobación del orden** determina si se requiere la comprobación de posición.

Se utiliza un nuevo elemento de menú de dispositivo móvil para la selección de clúster dirigida por el sistema. El id. de perfil del clúster debe especificarse para la opción **Dirigido por**. Además, el orden de consulta dirigido por el sistema puede agrupar pedidos en función de criterios específicos de la empresa. Esto le permite optimizar todavía más la asignación de órdenes de trabajo especificando criterios de ordenación personalizados en el orden de consulta dirigido por el sistema.

Cuando se realiza la selección de clúster dirigida por el sistema, a los trabajadores del almacén se les presenta un clúster donde las órdenes de selección se han asignado previamente a las posiciones de clúster. Por lo tanto, los trabajadores pueden comenzar a seleccionar un artículo para múltiples órdenes de trabajo visitando una sola vez la ubicación de selección. El proceso de selección para la selección de clúster dirigida por el sistema es el mismo que el proceso para la selección de clúster dirigida por el usuario.

## <a name="set-up-system-directed-cluster-picking"></a>Configurar la selección de clúster dirigida por el sistema

### <a name="create-cluster-profiles"></a>Crear perfiles de clúster

Los perfiles de clúster controlan cómo el sistema crea cada clúster. Si se requieren diferentes clústeres, se debe crear un perfil de grupo diferente para cada elemento del menú de dispositivo móvil.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Perfiles de clúster**.
2. Seleccione **Nuevo**.
3. En el campo **Id. de perfil de clúster**, escriba **Posición 2**.
4. En el campo **Nombre**, especifique **Posición 2**.
5. En la ficha rápida **General**, establezca los siguientes campos:

    - **Generar id. de clúster:** establezca esta opción en **Sí**. Esta opción determina si el sistema crea automáticamente el id. del clúster o si el usuario lo creará al comienzo de la selección.
    - **Activar posiciones:** establezca esta opción en **Sí**. Esta opción determina si los nombres de las posiciones se generan automáticamente en función de la configuración del nombre de la posición. Si esta opción está establecida en **No** se usará el id. de matrícula para la posición.
    - **Número de posiciones:** escriba **2**. Este campo determina el número máximo de posiciones que puede tener el clúster (es decir, el número máximo de cajas, bolsas, etc.).
    - **Nombre de la posición:** seleccione **Numérico** para asignar a las posiciones números consecutivos como nombre. Si selecciona **Alfabético**, se asignarán nombres a las posiciones por orden alfabético.
    - **Dividir clúster en:** seleccione **Colocar**. Este campo determina cuándo se divide el clúster.
    - **Tipo de comprobación del orden:** seleccione **Escaneo de posición**. Este campo determina si se comprueba el paso de colocación en posición.

6. En la ficha rápida **Ordenación de clústeres** puede definir criterios de ordenación creando una nueva línea y configurando los siguientes campos:

    - **Número de secuencia:** este campo determina la secuencia con la que el sistema ordena. Se introduce un valor automáticamente, pero puede cambiarlo si es necesario.
    - **Nombre de campo:** seleccione **WMSLocationId**. Este campo determina el campo que la línea usa para los criterios de ordenación.
    - **Ordenación:** seleccione **Ascendente**. Este campo define si la ordenación se realiza en orden ascendente o descendente.

### <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil

Para crear un nuevo elemento del menú de dispositivo móvil para la selección de clúster dirigida por el sistema y vincular el id. de perfil del clúster al elemento del menú de dispositivo móvil, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre del elemento del menú**, escriba **Clúster de SD**.
4. En el campo **Título**, escriba **Clúster SD**.
5. En el campo **Modo**, seleccione **Trabajo**.
6. Establezca la opción **Usar trabajo existente** en **Sí**.
7. En la ficha rápida **General**, establezca los siguientes campos:

    - **Dirigido por:** seleccione **Dirigido por el sistema**.
    - **Generar matrícula de entidad de almacén:** establezca esta opción en **Sí**.
    - **Id. de perfil de clúster:** seleccione **Posición 2**.

8. En la ficha rápida **Clases de trabajo**, configure la clase de trabajo válida para este elemento de menú del dispositivo móvil configurando los siguientes campos:

    - **Identificador de la clase de trabajo:** asegúrese de especificar **Ventas**.
    - **Tipo de orden trabajo:** asegúrese de especificar **Pedidos de ventas**.

9. Siga estos pasos para especificar una nueva consulta de secuencia de trabajo dirigida por el sistema:

    1. Seleccione **Nuevo**.
    2. En el campo **Número de secuencia**, escriba **1**.
    3. En el campo **Descripción**, seleccione **Prioridad de trabajo - Id. de trabajo**.

10. En el menú, seleccione **Editar consulta**.
11. En la pestaña **Ordenación**, defina los siguientes campos:

    - **Tabla:** seleccione **Trabajo**.
    - **Tabla derivada:** seleccione **Trabajo**.
    - **Campo:** seleccione **Prioridad de trabajo**.
    - **Dirección de búsqueda:** seleccione **Ascendente**.
    - **Tabla:** seleccione **Trabajo**.
    - **Tabla derivada:** seleccione **Trabajo**.
    - **Campo:** seleccione **Id. de trabajo**.
    - **Dirección de búsqueda:** seleccione **Ascendente**.

Ahora el sistema ordenará los id. de trabajo en el clúster, primero por prioridad de trabajo y luego por id. de trabajo.

### <a name="set-up-a-mobile-device-menu"></a>Configurar un menú de dispositivo móvil

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
2. Agregue el elemento de menú que acaba de crear al menú deseado.

## <a name="example"></a>Ejemplo

### <a name="create-picking-work"></a>Crear trabajo de selección

Antes de poder configurar la selección de clúster dirigida por el sistema, debe crear un trabajo de salida válido. El perfil de clúster que creó anteriormente especifica dos posiciones de clúster. Por lo tanto, debe crear al menos dos identificadores de trabajo.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
2. Seleccione **Nuevo** para crear un pedido de ventas.
3. En el campo **Cuenta de cliente**, seleccione cualquier cliente.
4. En la ficha desplegable **General**, en el campo **Almacén**, seleccione el almacén **62**.
5. Seleccione **Aceptar**.
6. En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Agregar línea**.
7. En el campo **Código de artículo**, seleccione **A0001**.
8. En el campo **Cantidad**, especifique **1**.
9. Seleccione **Agregar línea** para agregar una segunda línea.
10. En el campo **Código de artículo**, seleccione **A0002**.
11. En el campo **Cantidad**, especifique **3**.
12. Repita los pasos del 2 al 6.
13. En el campo **Código de artículo**, seleccione **A0001**.
14. En el campo **Cantidad**, especifique **4**.
15. Seleccione **Agregar línea** para agregar una segunda línea.
16. En el campo **Código de artículo**, seleccione **A0002**.
17. En el campo **Cantidad**, especifique **2**.

Reserve el inventario y libérelo en el almacén. Se crean dos identificadores de trabajo diferentes. Cada id. de trabajo tiene dos líneas de selección.

### <a name="run-the-mobile-device-flow"></a>Ejecutar el flujo del dispositivo móvil

1. En el dispositivo móvil, seleccione el menú que incluye el nuevo elemento de menú del dispositivo móvil.
2. Seleccione el elemento de menú **Clúster SD** e inicie la selección. Se crea un clúster y se le adjuntan los dos identificadores de trabajo que creó anteriormente. Si creó más de dos identificadores de trabajo, solo se agregarán los dos primeros al clúster. Tenga en cuenta que los identificadores de trabajo se agregan al clúster en orden ascendente, como especificó en la configuración de la consulta.

    > [!NOTE]
    > El nuevo clúster se crea automáticamente solo si se creó previamente una cantidad suficiente de identificadores de trabajo adicionales. De lo contrario, se muestra el siguiente mensaje: "No se encuentra trabajo suficiente para el clúster".

    Después de seleccionar el menú, aparece la primera pantalla de selección. El sistema agrega todas las líneas de selección coincidentes de los dos identificadores de trabajo y le indica que visite la ubicación de selección una vez para poder satisfacer ambos pedidos mediante una sola selección. Este proceso se realiza de la misma manera que el proceso de selección de clúster dirigida por el usuario.

3. Confirme la primera selección. A continuación, debe especificar el nombre de la posición para confirmar que los artículos se colocaron en la posición correcta.
4. Repita este proceso hasta que todos los artículos se hayan seleccionado y colocado en la posición correcta.
5. El último paso en el dispositivo móvil es colocar el clúster en la ubicación final. Cuando se confirma esta operación de colocación, el clúster se cierra y se divide según el valor que establecido en el campo **Dividir clúster en** del perfil del clúster. Los identificadores de trabajo también se cierran.
6. Se muestra un mensaje de "Clúster completo" en el dispositivo móvil.
