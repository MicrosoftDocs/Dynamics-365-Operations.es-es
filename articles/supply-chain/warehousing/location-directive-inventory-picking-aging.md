---
title: Vencimiento de picking de inventario de directiva de ubicación
description: Este tema explica cómo usar las estrategias de directivas de ubicación de primero en entrar, primero en salir (FIFO) y último en entrar, primero en salir (LIFO) durante la selección.
author: mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 937af7e24fc72b5b8bc741857913899a239a64d3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835543"
---
# <a name="location-directive-inventory-picking-aging"></a>Vencimiento de picking de inventario de directiva de ubicación

[!include [banner](../includes/banner.md)]

Este tema explica cómo usar las estrategias de directivas de ubicación de primero en entrar, primero en salir (FIFO) y último en entrar, primero en salir (LIFO) durante la selección. Estas estrategias funcionan en conjunto con las fechas de vencimiento que se registran en las ubicaciones para rastrear cuándo el inventario entró por primera vez al almacén. La característica *Vencimiento de picking de inventario de directiva de ubicación* utiliza la fecha de la ubicación para determinar el vencimiento. La característica *Estado de ubicación del almacén* actualiza la fecha de la ubicación, según la fecha de la matrícula.

Puede usar las estrategias FIFO y LIFO para enviar artículos con seguimiento por lotes y artículos sin seguimiento por lotes, según la fecha en que el inventario entró en el almacén. Esta capacidad puede ser especialmente útil para el inventario sin seguimiento por lotes, en el que una fecha de vencimiento no está disponible para utilizarla en la clasificación.

Cuando el inventario se recibe o crea por primera vez en el almacén, el sistema actualiza la matrícula correspondiente para que la fecha actual se muestre como la fecha de vencimiento. Esta fecha es utilizada por las estrategias de directivas de ubicación para identificar el inventario más antiguo o más nuevo en el almacén. Si el inventario se mueve a una ubicación que no está rastreada por la matrícula, se actualiza la ubicación en sí con información antigua, y esta información será utilizada por las estrategias.

## <a name="turn-on-the-feature"></a>Activar la característica

Para que esta característica esté disponible, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), en este orden:

1. Estado de ubicación de almacén
1. Vencimiento de picking de inventario de directiva de ubicación

## <a name="feature-requirements"></a>Requisitos de características

Para usar esta característica, debe configurar el conjunto de opciones **Habilitar estado de la ubicación** en *Sí* en cada [perfil de ubicación](tasks/create-location-profile.md) que se use para almacenar el inventario. Para configurar esta opción en un perfil de ubicación, vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación** y seleccione el perfil de ubicación. Puedes encontrar la opción en la ficha desplegable **General**.

## <a name="feature-scenarios"></a>Escenarios de características

Esta sección proporciona ejemplos que muestran cómo configurar y usar las estrategias FIFO y LIFO.

> [!TIP]
> Esta sección proporciona dos escenarios, uno para FIFO y otro para LIFO. Los procedimientos que se proporcionan asumen que realizará ambos escenarios, por orden. Recomendamos que realice ambos escenarios, para que pueda experimentar las diferencias entre las dos estrategias.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en estos escenarios mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar estos escenarios como guía para usar la característica en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores para cada configuración aquí descrita.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Configuración de escenarios

Los datos de demostración requieren ajustes de configuración e inventario para admitir los escenarios. Siga estos pasos para crear los datos de inventario necesarios para trabajar en los escenarios FIFO y LIFO.

1. Inicie sesión en un sistema que tenga los datos de demostración instalados y seleccione la entidad jurídica **USMF**.
1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En el panel Acciones, seleccione **Editar**.
1. En la lista de perfiles de ubicación, seleccione **PLANTA-05**.
1. En la ficha desplegable **General**, configure la opción **Habilitar estado de la ubicación** en *Sí*.
1. Seleccione **Guardar**.
1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En la lista de directivas de ubicación, seleccione **63 Creación de contenedores de recogida**.
1. Seleccione **Editar** para poner la página en modo de edición.
1. En la ficha desplegable **Acciones de directivas de localización**, busque la línea donde el campo **Número de secuencia** esté establecido en *1*, y siga uno de estos pasos:

    - Si está configurando un escenario FIFO, cambie el valor del campo **Estrategia** a *Vencimiento de ubicación FIFO*.
    - Si está configurando un escenario LIFO, cambie el valor del campo **Estrategia** a *Vencimiento de ubicación LIFO*.

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.
1. En el cuadro de diálogo de consulta, en la pestaña **Rango**, seleccione **Agregar** para agregar una línea y luego establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Tabla derivada:** *Ubicaciones*
    - **Campo**: *ID de zona*
    - **Criterios:** *Floor*

1. Seleccione **Aceptar** para aplicar su configuración y cerrar el cuadro de diálogo de consulta.
1. Seleccione **Guardar** para guardar los cambios de la directiva de ubicación.
1. En un dispositivo móvil o en la aplicación *Dynamics 365 for Finance and Operations - Warehousing* en su PC, siga estos pasos para eliminar el inventario existente de la ubicación del almacén de cara a admitir los escenarios:

    1. Inicie sesión en el almacén *63* con el Id. de usuario y la contraseña adecuados.
    1. En el menú principal, seleccione **Calidad**.
    1. En el menú **Administración de la calidad**, seleccione **Residuo**.
    1. En la página **Residuo**, seleccione el campo **Ubicación/Matrícula** y luego introduzca *63\_1*.
    1. Seleccione **Entrar** o **Aceptar**.
    1. Confirme los detalles de **Residuo** para **Salida de ajuste** seleccionando **Entrar** o **Aceptar**.

    Cuando se ajuste la salida del inventario de matrículas, recibirá un mensaje de "Trabajo completado".

    Estos pasos dejan el inventario en dos ubicaciones en los datos de demostración. Cada ubicación tiene una fecha de vencimiento diferente. La ubicación *FL-001* tiene una fecha de vencimiento del 15 de abril de 2017 y la ubicación *FL-002* tiene una fecha de vencimiento del 29 de enero de 2017. Ambas ubicaciones contienen artículos *A0001*.

    Para ver estos datos, vaya a **Gestión de inventarios \> Consultas e informes \> Disponible** y luego filtre en el almacén *63* y el artículo *A0001*. En las filas donde el campo **Ubicación** se establece en *FL-001* o *FL-002*, seleccione una línea que tenga un valor de **Inventario físico** positivo y luego, en el Panel de acciones, seleccione **Transacciones**. El campo **Fecha física** mostrará una fecha que se corresponde con una de las fechas de vencimiento mencionadas anteriormente.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>Escenario 1: configurar y usar el vencimiento de la ubicación FIFO

La estrategia FIFO busca la ubicación que contiene la fecha de vencimiento más antigua y asigna el picking en función de esa fecha de vencimiento.

1. Si aún no lo ha hecho, [prepare los datos de muestra](#demo-set-up) necesarios para este escenario.
1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la ficha desplegable **Cliente**, configure el campo **Cuenta de cliente** a *US-001*.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en *63*.

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Incluye una nueva fila vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**. En esta línea de pedido, establezca el campo **Número de artículo** en *A0001* y el campo **Cantidad** en *1*.
1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad pedida de este artículo del inventario en el almacén seleccionado.
1. Cierre la página **Reserva**.
1. En la página **Pedido de ventas** del panel de acciones, en la pestaña **Almacén**, seleccione el grupo **Acciones** y **Despachar al almacén**. Recibirá mensajes informativos. El sistema crea un envío, lo agrega a una nueva carga y crea el trabajo requerido.
1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, seleccione **Detalles del trabajo** para abrir el trabajo creado para este pedido de ventas. Observe que la línea donde el valor **Tipo de trabajo** es *Seleccionar* muestra un valor **Ubicación** de *FL-002*. Esta ubicación contiene la matrícula que tiene la fecha de vencimiento más antigua (FIFO).
1. Seleccione **Almacén \> Detalles del envío**.
1. En la ficha desplegable **General**, tome nota del ID de oleada para que pueda usarlo en el escenario 2.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>Escenario 2: configurar y usar el vencimiento de la ubicación LIFO

La estrategia LIFO busca la ubicación que contiene la fecha de vencimiento más actual y asigna el picking en función de esa fecha de vencimiento. En el escenario 2, editará la configuración del escenario 1 (FIFO) y reutilizará el pedido de ventas y la oleada que se crearon durante ese escenario.

1. Antes de comenzar este escenario, configure y complete el escenario FIFO completo como se describe en [sección previa](#fifo-demo). En este escenario, reutilizará la oleada y la mayor parte de la configuración que se creó para ese escenario.
1. Edite la directiva de ubicación **63 Creación de contenedores de recogida** para que utilice la estrategia *Vencimiento de ubicación LIFO* como se describe en la primera parte del procedimiento [Configuración de escenarios](#demo-set-up).

    A continuación, modificará la oleada que se creó para el pedido de cliente en el escenario 1, de modo que se utiliza la estrategia *Vencimiento de ubicación LIFO*.

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione y abra la oleada que contiene el orden que creó para el escenario FIFO.
1. En el panel de acciones, en la pestaña **Trabajo**, seleccione **Cancelar** para cancelar el trabajo que creó para el escenario FIFO.
1. En el panel de acciones, en la pestaña **Oleada**, en el grupo **Oleada**, seleccione **Proceso**.
1. Cuando finalice el procesamiento, en el panel de acciones, en la pestaña **Oleada**, en el grupo **Información relacionada**, seleccione **Trabajo** para abrir el trabajo creado en esta oleada.
1. Sobre la página **Trabajo**, en la pestaña **Visión general**, debe haber dos líneas. Seleccione la línea donde el campo **Situación del trabajo** se establece en *Abierto*.
1. Observe que la línea donde el valor **Tipo de trabajo** es *Seleccionar* muestra un valor **Ubicación** de *FL-001*. Esta ubicación contiene la matrícula que tiene la fecha de vencimiento más actual (LIFO).

En estos escenarios, puede observar cómo la estrategia de vencimiento de la ubicación dirige el trabajo a la ubicación del inventario que tiene el inventario más antiguo o el más nuevo, según la estrategia seleccionada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]