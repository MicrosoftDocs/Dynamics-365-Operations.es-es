---
title: Regla de liberación al almacén
description: En este tema se ofrece información sobre la característica Regla de liberación al almacén, que proporciona flexibilidad durante la liberación al almacén. Agrega una opción de configuración que controla si el sistema permite liberar líneas de pedido parcialmente reservadas.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8c4775ca3f44486fd3cd557df49acd229048d186
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996182"
---
# <a name="release-to-warehouse-rule"></a>Regla de liberación al almacén

[!include [banner](../includes/banner.md)]

La característica *Regla de liberación al almacén* proporciona flexibilidad durante la liberación al almacén. Agrega una opción de configuración para cada almacén. Puede usar esta opción para especificar si se pueden liberar líneas de pedido parcialmente reservadas para ese almacén. La característica funciona junto con la funcionalidad de tránsito directo avanzado en situaciones en las que parte de una cantidad de la línea de pedido se marca en una fuente de suministro, pero la parte restante se puede procesar en el almacén. Por lo tanto, la línea se puede liberar para que el procesamiento del almacén de la cantidad de inventario disponible pueda continuar.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>Activar e inicializar la característica Regla de liberación al almacén

### <a name="turn-on-the-feature"></a>Activar la característica

Antes de poder usar la característica *Regla de liberación al almacén*, esta debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Regla de liberación al almacén*

### <a name="initialize-the-feature"></a>Inicializar la característica

Después de activar la característica en su sistema, debe inicializarla para establecer la regla en el estado inicial correcto para todos los almacenes.

- Para los almacenes que no están habilitados para la gestión de almacenes, la regla se establece inicialmente en **No aplicable**.
- Para los almacenes que están habilitados para la gestión de almacenes, la regla se establece inicialmente en **Permitir reserva parcial**.

Siga estos pasos para inicializar la característica y establecer la regla de liberación al almacén para todos los almacenes.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la página **Parámetros de gestión de almacenes**, en la pestaña **General**, en la sección **Información de la empresa**, seleccione el vínculo para la regla **Inicializar liberación al almacén**. (Si no se muestra este vínculo, la característica no está activada o ya se ha inicializado.)
1. Cuando se le pida que confirme la acción, seleccione **Sí** para inicializar la característica.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Establecer la regla de liberación al almacén para cada almacén

Después de que la característica se active e inicialice, todos sus almacenes tendrán una configuración inicial, como se describe en la sección anterior. Puede cambiar esta configuración para almacenes individuales siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. Seleccione el almacén que desea configurar.
1. Seleccione **Editar** para poner la página en modo de edición.
1. En la ficha desplegable **Almacén**, en la sección **Reservas**, el campo **Requisito de reserva de inventario** controla si se permite la liberación parcial de pedidos. Seleccione uno de los siguientes valores:

    - **No aplicable**: cuando la característica se activa e inicializa por primera vez, este valor se asigna automáticamente a todos los almacenes que no están habilitados para la gestión de almacenes. Este valor se puede cambiar. Este valor no está disponible para los almacenes que están habilitados para la gestión de almacenes.
    - **Permitir reserva parcial**: los pedidos se pueden liberar cuando se reserve cualquier cantidad. El sistema evaluará si la cantidad sin reservar debe marcarse para el tránsito directo avanzado y marcará esa cantidad según sea necesario. Si no existe ninguna marca, el sistema creará el trabajo solo para la cantidad reservada. Cuando la característica se activa e inicializa por primera vez, este valor se asigna automáticamente a todos los almacenes que están habilitados para la gestión de almacenes. Este valor no está disponible para los almacenes que no están habilitados para la gestión de almacenes.
    - **Requerir reserva completa**: los pedidos solo se pueden liberar si está reservada la cantidad total. No se pueden liberar si la cantidad total no está reservada físicamente o planificada para el tránsito directo. Este valor no está disponible para los almacenes que no están habilitados para la gestión de almacenes.

1. Seleccione **Guardar**.

## <a name="scenarios"></a>Situaciones

En esta sección se ofrecen dos escenarios en los que puede trabajar para aprender qué hace la característica y cómo usarla.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en estos escenarios mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar estos escenarios como guía para la característica cuando trabaje en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>Escenario 1: requerir liberación completa (sin tránsito directo planificado)

En este escenario se muestra cómo funciona la característica para los almacenes definidos en **Requerir reserva completa**.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. Para el almacén _62_, establezca el campo **Requisito de reserva de inventario** en **Requerir reserva completa**, como se describe en la sección [Establecer la regla de liberación al almacén para cada almacén](#set-option-warehouse) anterior en este tema.
1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en _US-004_.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en _62_.

1. Seleccione **Aceptar** para crear el nuevo pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre su nuevo pedido de ventas. Incluye una línea vacía en la cuadrícula en la sección **Líneas de pedido de venta**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *2*

1. Seleccione **Agregar línea** para agregar una nueva línea y establecer los siguientes valores:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *2*

1. Seleccione la primera línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. No reserve la segunda línea de pedido.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.
1. Observe que recibe el siguiente mensaje de error: "La cantidad total debe reservarse físicamente". Por lo tanto, el sistema no crea ningún trabajo, envío o carga para el pedido.

    > [!NOTE]
    > Recibirá el mismo mensaje de error si reserva parcialmente la segunda línea.

### <a name="scenario-2-allow-partial-release"></a>Escenario 2: permitir liberación parcial

En este escenario se muestra cómo funciona la característica para los almacenes definidos en **Permitir liberación parcial**.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. Para el almacén _62_, establezca el campo **Requisito de reserva de inventario** en **Permitir reserva parcial**, como se describe en la sección [Establecer la regla de liberación al almacén para cada almacén](#set-option-warehouse) anterior en este tema.
1. Como hizo en el [escenario anterior](#scenario1), vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas** y cree un pedido de ventas para la cuenta del cliente _US-004_ del almacén _62_. Agregue las siguientes dos líneas de pedido:

    - **Línea 1**: establezca el campo **Número de artículo** a _A0001_, el campo **Cantidad** a _2_ y el campo **Unidad** a _UDS_.
    - **Línea 2**: establezca el campo **Número de artículo** a _A0002_, el campo **Cantidad** a _2_ y el campo **Unidad** a _UDS_.

1. Como hizo en el [escenario anterior](#scenario1), reserve la cantidad completa para la línea de pedido 1, pero no reserve la línea de pedido 2.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.
1. Tenga en cuenta que esta vez no recibe ningún mensaje de error. En cambio, el sistema crea trabajo, envíos y cargas según sea necesario, y muestra los resultados.
1. Para ver la información de envío, carga y trabajo, use las opciones del menú **Almacén** encima de la cuadrícula:

    - **Línea 1:** hay tres opciones disponibles: **Detalles de envío**, **Detalles de carga** y **Detalles de trabajo**. Seleccione cada opción para ver los detalles de envío, carga y trabajo que se crearon cuando el pedido se entregó al almacén.
    - **Línea 2:** solo está disponible la opción **Detalles de trabajo**. Selecciónela y observe que no se ha creado ningún trabajo porque no se ha reservado inventario. Por lo tanto, tampoco se creó ningún envío o carga.

> [!NOTE]
> Se espera el mismo resultado cuando la segunda línea está parcialmente reservada. En este caso, se creará un trabajo para la cantidad de línea reservada pero no para la cantidad no reservada.
