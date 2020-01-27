---
title: Picking de agrupación de líneas
description: Este tema proporciona una descripción general de la agrupación de líneas de selección.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1b1d0135d450bc9be7b1303240a9ca70f95ae38e
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906277"
---
# <a name="pick-line-grouping"></a>Picking de agrupación de líneas

[!include [banner](../includes/banner.md)]

En la agrupación de líneas de selección, varias líneas de trabajo que tienen el mismo artículo y ubicación se pueden combinar en una sola selección que se presenta al usuario en un dispositivo móvil. Esto permite que los trabajadores del almacén puedan recibir las instrucciones más eficaces posibles, pero también se mantiene la separación requerida de líneas de trabajo en el sistema (por ejemplo, para diferentes contenedores y pedidos).

## <a name="set-up-pick-line-grouping"></a>Configurar la agrupación de líneas de selección

### <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Elementos del menú del dispositivo móvil** y cree un elemento de menú nuevo denominado **Selección de línea de grupo de ventas: dirigida por el usuario**.
2. En **Elementos de menú del dispositivo móvil**, establezca los siguientes valores:

    - En el campo **Nombre del elemento del menú**, especifique **Selección de ventas: línea de grupo**.
    - En el campo **Título**, especifique **Selección de ventas: línea de grupo**.
    - En el campo **Modo**, seleccione **Trabajo**.
    - Establezca la opción **Usar trabajo existente** en **Sí**.

3. En la ficha rápida **General** puede establecer los siguientes valores:

    - En el campo **Dirigido por**, seleccione **Dirigido por el usuario**.
    - Seleccione la opción **Generar matrícula de entidad de almacén** en **Sí**.
    - Establezca la opción **Selección de grupo** en **Sí**.

4. En la ficha rápida **Clases de trabajo**, siga estos pasos para configurar las clases de trabajo válidas para el elemento de menú del dispositivo móvil:

    1. Seleccione **Nuevo**.
    2. En el campo **Identificador de la clase de trabajo**, seleccione **Ventas** o **Selección de pedidos de ventas** en función del almacén que vaya a utilizar.
    3. En el campo **Tipo de orden de trabajo**, seleccione **Pedidos de ventas**.

### <a name="set-up-a-mobile-device-menu"></a>Configurar un menú de dispositivo móvil

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**. 
1. Agregue el elemento de menú que acaba de crear al menú deseado.

### <a name="set-up-a-work-template"></a>Configurar una plantilla de trabajo

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Encuentre la plantilla de trabajo que se debe usar con esta función. Para este ejemplo, seleccione la plantilla de trabajo estándar de Contoso, **51 Pick to stage**.
1. En el menú, seleccione **Editar consulta**.
1. En la pestaña **Ordenación**, seleccione **Agregar** y, a continuación, establezca los siguientes valores:

    - En el campo **Tabla**, seleccione **Transacciones de trabajo temporal**.
    - En el campo **Tabla derivada**, seleccione **Transacciones de trabajo temporal**.
    - En el campo **Campo**, seleccione **Número de artículo**.
    - En el campo **Dirección de búsqueda**, seleccione **Ascendente**.

> [!NOTE]
> Para que la funcionalidad de agrupación de líneas de selección funcione, las líneas de trabajo deben ordenarse por id. de artículo. Si las líneas que tienen los mismos artículos no se secuencian una tras otra, no se agruparán.

## <a name="example"></a>Ejemplo

### <a name="create-picking-work"></a>Crear trabajo de selección

Antes de poder configurar la agrupación de líneas de clúster debe crear un trabajo de salida válido.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
2. Seleccione **Nuevo** para crear un pedido de ventas. 
3. En el campo **Cuenta de cliente**, seleccione cualquier cliente. 
4. En la ficha desplegable **General**, en el campo **Almacén**, seleccione el almacén **51**. A continuación seleccione **Aceptar**.
5. En **Líneas de pedido de ventas**, agregue las seis líneas siguientes:

    - **Línea 1:** en el campo **Número de artículo**, seleccione **M9200**. En el campo **Cantidad**, especifique **3**.
    - **Línea 2:** en el campo **Número de artículo**, seleccione **M9201**. En el campo **Cantidad**, especifique **3**. 
    - **Línea 3:** en el campo **Número de artículo**, seleccione **M9202**. En el campo **Cantidad**, especifique **2**. 
    - **Línea 4:** en el campo **Número de artículo**, seleccione **M9200**. En el campo **Cantidad**, especifique **1**. 
    - **Línea 5:** en el campo **Número de artículo**, seleccione **M9200**. En el campo **Cantidad**, especifique **3**.
    - **Línea 6:** en el campo **Número de artículo**, seleccione **M9202**. En el campo **Cantidad**, especifique **7**. 

    A continuación se muestra un resumen de las cantidades totales para cada artículo:

    - **Artículo M9200:** 7 cada uno
    - **Artículo M9201:** 3 cada uno
    - **Artículo M9202:** 9 cada uno

6. Antes de liberar los pedidos al almacén, debe asegurarse de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en todos los pedidos. Revisa la configuración de **Directiva de ubicación** para determinar qué ubicaciones de selección se utilizan para la selección de pedidos de ventas.
7. Reserve el inventario y libérelo en el almacén. Se crea un id. de trabajo de seis líneas. Las líneas se ordenan por número de artículo.

### <a name="run-the-mobile-device-flow"></a>Ejecutar el flujo del dispositivo móvil

1. En el dispositivo móvil, seleccione el menú que incluye el nuevo elemento de menú del dispositivo móvil.
1. Seleccione el elemento de menú **Selección de ventas: línea de grupo** e inicie la selección.

    Después de seleccionar el menú e introducir el id. de trabajo, verá el paso de selección en el que se agrupan todas las líneas de selección para el artículo M9200. Recibe una instrucción para elegir 7 cada uno del artículo M9200.

1. Confirme el paso de selección. 
1. Vaya a la pantalla de cliente del trabajo en curso y observe que las tres líneas de selección para el artículo M9200 se cerraron simultáneamente.

    Se presenta la línea de trabajo 4.

1. Confirme el paso de selección.

    El último paso de selección en el dispositivo móvil agrega las dos últimas líneas de selección de la orden de trabajo.

1. Complete el paso de selección para 9 cada uno del artículo M9202.
1. Confirme el paso de colocación y cualquier par adicional de selección/colocación para completar el trabajo.

> [!NOTE]
> - Las líneas de trabajo solo se pueden agrupar si están en secuencia.
> - No se admite la siguiente funcionalidad:
>
>    - Artículos con peso capturado. Si hay artículos con peso capturado en el trabajo, recibirá un mensaje de error antes de iniciar la selección.
>    - Selección de piezas.
>    - Líneas de trabajo que tienen trabajo de reabastecimiento sin terminar.
>    - Selección en exceso.
