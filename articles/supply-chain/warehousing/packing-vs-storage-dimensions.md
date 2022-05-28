---
title: Establecer diferentes dimensiones para el embalaje y almacenamiento
description: Este tema muestra cómo especificar para qué proceso (embalaje, almacenamiento o embalaje anidado) se utiliza cada dimensión especificada.
author: Mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 090a6f653b50d8f22a2f34354172f129624813f1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687656"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Establecer diferentes dimensiones para el embalaje y almacenamiento

[!include [banner](../../includes/banner.md)]

Algunos artículos se empaquetan o almacenan de tal manera que es posible que deba realizar un seguimiento de las dimensiones físicas de manera diferente para cada uno de varios procesos diferentes. La característica *Dimensiones del producto de embalaje* le permite configurar uno o varios tipos de dimensiones para cada producto. Cada tipo de dimensión proporciona un conjunto de medidas físicas (peso, ancho, profundidad y altura) y establece el proceso donde se aplican esos valores de medición física. Cuando esta función está habilitada, su sistema admitirá los siguientes tipos de dimensiones:

- *Almacenamiento* - Las dimensiones de almacenamiento se utilizan junto con la volumetría de ubicación para determinar cuántos de cada artículo se pueden almacenar en varias ubicaciones de almacén.
- *Embalaje* - Las dimensiones del embalaje se utilizan durante la colocación en contenedores y el proceso de embalaje manual para determinar cuántos de cada artículo caben en varios tipos de contenedores.
- *Embalaje anidado* - Las dimensiones de empaque anidado se utilizan cuando el proceso de empaque contiene múltiples niveles.

Las dimensiones de *almacenamiento* son compatibles incluso cuando la función *Dimensiones del producto de embalaje* no está habilitada. Los configura utilizando la página **Dimensión física** en Supply Chain Management. Estas dimensiones se utilizan en todos los procesos en los que no se especifican las dimensiones del embalaje y del embalaje anidado.

Las dimensiones de *embalaje* y *embalaje anidado* se configuran utilizando la página **Dimensiones físicas del producto**, que se agrega cuando habilita la característica *Dimensiones del producto de embalaje*.
Este tema proporciona un escenario que ilustra cómo utilizar esta función.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Active la función de dimensiones del producto de embalaje

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica:** *Dimensiones del producto de embalaje*

## <a name="example-scenario"></a>Supuesto de ejemplo

### <a name="set-up-the-scenario"></a>Configuración el escenario

Antes de que pueda ejecutar el escenario de ejemplo, debe preparar su sistema como se describe en esta sección.

#### <a name="enable-demo-data"></a>Active los datos de demostración

Para trabajar en este escenario mediante el uso de los registros y valores de demostración que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal *USMF* antes de empezar.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Agregar una nueva dimensión física a un producto

Agregue una nueva dimensión física para un producto haciendo lo siguiente:

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el número con el **número de artículo** *A0001*.
1. En el panel Acciones, abra la pestaña **Administrar inventario** y, en el grupo **Almacén**, seleccione **Dimensiones del producto físicas**.
1. Se abrirá la página **Dimensiones del producto físicas**. En el panel de acción, seleccione **Nuevo** para agregar una nueva dimensión a la cuadrícula con los siguientes ajustes:
    - **Tipo de dimensión física** - *Embalaje*
    - **Unidad física** - *uds.*
    - **Peso** - *4*
    - **Unidad de peso** - *kg*
    - **Profundidad** - *3*
    - **Altura** - *4*
    - **Anchura** - *3*
    - **Largura** - *cm*
    - **Unidad de volumen** - *cm3*

El campo **Volumen** se calcula automáticamente en función de sus ajustes de **Profundidad**, **Altura** y **Anchura**.

#### <a name="create-a-new-container-type"></a>Crear un nuevo tipo de contenedor

Vaya a **Gestión de almacenes \> Configuración \> Contenedores \> Tipos de contenedores** y cree un nuevo registro con la siguiente configuración:

- **Código de tipo de contenedor** - *Caja grande*
- **Descripción** - *Caja corta*
- **Peso neto máximo** - *50*
- **Volumen** - *144*
- **Longitud** - *6*
- **Anchura** - *6*
- **Altura** - *4*

#### <a name="create-a-container-group"></a>Crear un grupo de contenedores

Vaya a **Gestión de almacenes \> Configuración \> Contenedores \> Grupos de contenedores** y cree un nuevo registro con la siguiente configuración:

- **ID de grupo de contenedores** - *Caja corta*
- **Descripción** - *Caja corta*

Añada una nueva línea en la sección **Detalles**. Ajuste el **Tipo de contenedor** en *Caja corta*.

#### <a name="set-up-a-container-build-template"></a>Configurar una plantilla de creación de contenedores

Vaya a **Gestión de almacén \> Configuración \> Contenedores \> Plantillas de planificación de contenedores** y seleccione **Cajas**. Cambiar el **ID de grupo de contenedores** a *Caja corta*.

### <a name="run-the-scenario"></a>Ejecute el escenario

Una vez que haya preparado su sistema como se describe en la sección anterior, estará listo para ejecutar el escenario como se describe en la siguiente sección.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Cree una orden de venta y un envío

En este proceso, creará un envío basado en las dimensiones de *embalaje* del artículo, para las cuales la altura es menor que 3.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *63*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *5*

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.
1. Cierre la página.
1. En el panel de acciones, abra la pestaña **Almacén**, seleccione **Liberar al almacén** para crear un trabajo para el almacén.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Almacén \> Detalles de envío**.
1. En el Panel acciones, abra la pestaña **Transporte** y seleccione **Ver contenedores**. Confirme que el artículo se colocó en contenedores en los dos contendores *Caja corta*.

#### <a name="place-an-item-into-storage"></a>Coloque un artículo en almacenamiento

1. Abra el dispositivo móvil, inicie sesión en el almacén 63 y vaya a **Inventario \> Ajustar en**.
1. Introducir **Loc** = *SHORT-01*. Haga una nueva placa con **Artículo** = *A0001* y **Cantidad** = *1 ud.*.
1. Seleccione **Aceptar**. Recibirá el error "La ubicación SHORT-01 falló porque el elemento A0001 no encaja en las dimensiones especificadas de la ubicación". Esto es porque las dimensiones del *almacenamiento* de tipo del producto son mayores que las dimensiones especificadas en el perfil de ubicación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]