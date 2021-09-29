---
title: Códigos de motivo para recuento de inventario
description: En este tema se describe cómo configurar y aplicar códigos de motivo para tareas de recuento.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4c178ddf342b13a0ef8fee8b8b958554a9a31069
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500609"
---
# <a name="reason-codes-for-inventory-counting"></a>Códigos de motivo para recuento de inventario

[!include [banner](../includes/banner.md)]

Los códigos de motivo le permiten analizar los resultados de un proceso de recuento y cualquier discrepancia que surja durante dicho proceso. Puede especificar el motivo por el que se realiza el recuento, como un pallet roto o un ajuste de existencias basado en ejemplos de inventario. Al mismo tiempo, puede utilizar la función de ajuste para registrar el valor de los ajustes de inventario disponibles en la cuenta de contrapartida correspondiente, según el motivo de cada ajuste de inventario.

## <a name="recommendation"></a>Recomendación

Antes de configurar el sistema, le recomendamos que defina una estrategia para trabajar con códigos de motivo. Por ejemplo, intente responder a las siguientes preguntas:

- ¿Los códigos de motivo deben ser obligatorios en los almacenes?
- ¿Los códigos de motivo deben ser obligatorios u opcionales en algunos artículos?
- ¿Cuántos códigos de motivo necesita?
- ¿Tiene que preseleccionar una lista limitada de códigos de motivo para realizar ajustes?
- ¿Cómo deben usar los usuarios de escáneres de códigos de barras los códigos de motivo? ¿Los códigos de motivo deben ser preseleccionados, obligatorioo o no editables?
- ¿Los trabajadores de almacén requieren un comportamiento de código de motivo diferente en los escáneres móviles? Si la respuesta es afirmativa, puede crear más elementos de menú y asignarlos a diferentes personas.
- ¿Deberían los códigos de motivo impulsar la contabilización de la cuenta de contrapartida financiera?

## <a name="turn-on-reason-code-features-in-your-system"></a>Active las funciones del código de motivo en su sistema

Si no ve todas las funciones que se describen en este tema en su sistema, probablemente tenga que activar la función *Contabilizar ajustes disponibles utilizando códigos de motivo configurables conectados a cuentas de contrapartida*. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Contabilizar ajustes disponibles utilizando códigos de motivo configurables conectados a cuentas de contrapartida*

## <a name="set-up-reason-codes"></a>Configurar códigos de motivos

### <a name="set-up-reason-code-policies"></a>Configurar directivas de código de motivo

Puede crear varias políticas de códigos de motivo para controlar cuándo y cómo se aplican los códigos de motivo de recuento. Cada política de código de motivo puede tener uno de dos tipos de código de motivo de recuento (*Opcional* u *Obligatorio*). Las políticas de código de motivo de recuento se pueden utilizar en el nivel de almacén o en el nivel de artículo.

Para crear una política de código de motivo, siga estos pasos.

1. Vaya a **Gestión del inventario** \> **Configuración** \> **Inventario** \> **Políticas de código de motivo de recuento**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una política a la cuadrícula.
1. Defina el campo **Nombre** para la nueva política.
1. En el campo **Tipo de código de motivo de recuento**, seleccione *Obligatorio* u *Opcional* para especificar si la selección de un código de motivo debe ser una acción opcional u obligatoria en uno de los siguientes procesos de ajuste de inventario:

    - Recuento cíclico (dispositivo móvil)
    - Recuento puntual (dispositivo móvil)
    - Recuento de umbral (dispositivo móvil)
    - Entrada de ajuste (dispositivo móvil)
    - Salida de ajuste (dispositivo móvil)
    - Diario de recuento (cliente rico)
    - Ajuste de cantidad / recuento en línea (cliente enriquecido)

También puede configurar políticas de códigos de motivo para almacenes individuales y para productos. La configuración del código de motivo de un producto puede anular la configuración del almacén del producto.

> [!NOTE]
> Para almacenes y artículos donde el campo **Política de códigos de motivo de recuento** está definido como *Obligatorio*, el diario de recuento no se podrá completar y cerrar hasta que se proporcione un código de motivo. Para obtener más información, consulte la sección siguiente.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>Asignar políticas de código de motivo de recuento a almacenes

Para asignar una política de código de motivo de recuento a un almacén, siga estos pasos.

1. Vaya a **Gestión del inventario** \> **Configuración** \> **Desglose del inventario** \> **Almacenes**.
1. En el panel de lista, seleccione un almacén.
1. En el panel Acciones, en la pestaña **Almacén**, en el grupo **Configurar**, seleccione **Política de códigos de motivo de recuento**. En el cuadro de diálogo desplegable **Asignar política de código de motivo de recuento**, siga uno de estos pasos:

    - Para utilizar la configuración de la política para cada artículo a fin de determinar si los diarios de recuento son obligatorios para él, no introduzca ningún valor (o elimine el valor existente).
    - Para solicitar un código de motivo en los diarios de recuento del almacén, seleccione una política de motivo donde el campo **Tipo de código de motivo de recuento** está configurado en *Obligatorio*.
    - Si el código de motivo es opcional en los diarios de recuento del almacén, seleccione una política de motivo donde el campo **Tipo de código de motivo de recuento** está configurado en *Opcional*.

### <a name="assign-counting-reason-code-policies-to-products"></a>Asignar políticas de código de motivo de recuento a productos

Para asignar una política de código de motivo de recuento a un producto, siga estos pasos.

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.
1. Seleccione un producto en la cuadrícula.
1. En el panel Acciones, en la pestaña **Producto**, en el grupo **Configurar**, seleccione **Política de códigos de motivo de recuento**. En el cuadro de diálogo desplegable **Asignar política de código de motivo de recuento**, siga uno de estos pasos:

    - Para utilizar la configuración de la política para el almacén a fin de determinar si los diarios de recuento son obligatorios para el producto, no introduzca ningún valor (o elimine el valor existente).
    - Para solicitar un código de motivo en los diarios de recuento del producto, seleccione una política de motivo donde el campo **Tipo de código de motivo de recuento** está configurado en *Obligatorio*. Esta configuración anula cualquier configuración del código de motivo en el nivel de almacén.
    - Si el código de motivo es opcional en los diarios de recuento del producto, seleccione una política de motivo donde el campo **Tipo de código de motivo de recuento** está configurado en *Opcional*. Esta configuración anula cualquier configuración del código de motivo en el nivel de almacén.

### <a name="set-up-counting-reason-codes"></a>Configurar códigos de motivo de recuento

Siga estos pasos para configurar códigos de motivo de recuento.

1. Vaya a **Gestión del inventario** \> **Configuración** \> **Inventario** \> **Códigos de motivo de recuento**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Defina los campos de **Código de motivo de recuento** y **Descripción** para la nueva fila.
1. Para asignar una cuenta de contrapartida, introduzca o seleccione un valor en el campo **Cuenta de contrapartida**.

    > [!NOTE]
    > Si se asigna una cuenta de contrapartida a un código de motivo de recuento, cuando registra un diario de recuento que utiliza ese código de motivo de recuento, el valor se contabiliza contra la cuenta de contrapartida asignada en lugar de la cuenta de perfil de contabilización de inventario predeterminada.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Configuración de grupos de código de motivo de recuento

Los *Grupos de códigos de motivo de recuento* se pueden utilizar como parte de las opciones de menú *Entrada de ajuste* y *Salida de ajuste* en la aplicación móvil Warehouse Management para limitar la lista de códigos de motivo de recuento. (Para obtener más información sobre los grupos de códigos de motivo de recuento, consulte la sección [Configurar opciones de menú del dispositivo móvil para la entrada y salida de ajuste](#setup-adjustment-in-out) más adelante en este tema.)

1. Vaya a **Gestión del inventario** \> **Configuración** \> **Inventario** \> **Grupos de códigos de motivo de recuento**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un grupo.
1. Defina los campos de **Grupo de motivos de recuento** y **Descripción de grupo** para el nuevo grupo.
1. En el panel Acciones, seleccione **Guardar**.
1. En la sección **Detalles**, seleccione **Nuevo** en la barra de herramientas para agregar una fila a la cuadrícula. Defina el campo de **Código de motivo de recuento** para la nueva fila. 
1. Repita el paso anterior para asignar más códigos según sea necesario. Si debe eliminar un código del grupo, selecciónelo y luego seleccione **Eliminar** en la barra de herramientas.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Configurar códigos de motivo para opciones de menú del dispositivo móvil

Puede configurar códigos de motivo para los siguientes tipos de ajustes disponibles:

- Recuento cíclico
- Recuento puntual
- Recuento de umbral
- Entrada de ajuste
- Salida de ajuste

En la mayoría de los casos, puede definir la siguiente información para cada opción de menú de dispositivo móvil relevante:

- Si el código de motivo se muestra al trabajador del dispositivo móvil durante el recuento.
- El código de motivo predeterminado que se muestra en un elemento de menú del dispositivo móvil.
- Si el usuario puede editar el código de motivo.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Configurar opciones de menú del dispositivo móvil para un proceso de recuento

Para configurar una opción de menú de dispositivo móvil para un proceso de recuento, siga estos pasos.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Opciones de menú del dispositivo móvil**.
1. Seleccione la opción de menú relevante en el panel de lista o cree una nueva.
1. En el panel de acciones, seleccione **Recuento cíclico**.
1. En el campo **Código de motivo de recuento predeterminado**, establezca el código de motivo predeterminado que debe registrarse cuando se utilice la opción de menú del dispositivo móvil para hacer el recuento.
1. En el campo **Mostrar código de motivo de recuento**, seleccione uno de los siguientes valores:

    - *Línea* - Muestra el código de motivo después de que se registre cada variación.
    - *Ocultar* - No se muestra el código de motivo.

1. Defina **Editar código de motivo de recuento** como *Sí* para que el trabajador pueda editar el código de motivo cuando se muestre en el dispositivo móvil durante el recuento. Defínalo como *No* para evitar que el trabajador edite el código.

> [!NOTE]
> El botón **Recuento cíclico** se puede habilitar en cualquier elemento de menú del dispositivo móvil en el que se puedan hacer recuentos. Los ejemplos incluyen las opciones de menú para recuentos puntuales, trabajo dirigido por el usuario y trabajo dirigido por el sistema.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>Configurar opciones de menú del dispositivo móvil para la entrada y salida de ajuste

Para configurar una opción de menú de dispositivo móvil para la entrada o salida de ajuste, siga estos pasos.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Opciones de menú del dispositivo móvil**.
1. En el Panel de acciones, haga clic en **Nuevo** para crear una opción de menú.
1. Defina los campos **Nombre de opción móvil** y **Título** para la nueva opción de menú.
1. Defina el campo **Modo** como *Trabajo*.
1. Establezca la opción **Usar trabajo existente** en *No*.
1. En el campo **Proceso de creación de trabajo**, seleccione *Entrada de ajuste* o *Salida de ajuste*.
1. En la ficha desplegable **General**, establezca los siguientes campos. (Todos estos campos se agregan cuando selecciona *Entrada de ajuste* o *Salida de ajuste* en el campo **Proceso de creación de trabajo**).

    - **Usar guía de proceso** - Si está creando un proceso de *Salida de ajuste*, asegúrese de establecer esta opción en *Sí*. Si está creando un proceso de *Salida de ajuste*, esta opción siempre se establece en *Sí*.
    - **Código de motivo de recuento predeterminado** - Establezca el código de motivo predeterminado que debe registrarse cuando se utilice la opción de menú del dispositivo móvil para hacer el recuento.
    - **Mostrar código de motivo de recuento** - Seleccione uno de los siguientes valores:

        - *Línea* - Muestra el código de motivo después de que se registre cada variación.
        - *Ocultar* - No se muestra el código de motivo.

    - **Editar código de motivo de recuento** - Defina esta opción como *Sí* para que el trabajador pueda editar el código de motivo cuando se muestre en el dispositivo móvil durante el recuento. Defínalo como *No* para evitar que el trabajador edite el código.
    - **Grupo de códigos de motivo de recuento** - Seleccione un grupo de códigos de motivo si desea limitar la lista de opciones que se presenta a los trabajadores. Para obtener información sobre cómo configurar grupos de códigos de motivo, consulte la sección [Configurar grupos de códigos de motivo de recuento](#reason-groups) anterior en este tema. 

> [!NOTE]
> Cuando asigna un grupo de códigos de motivo de recuento a opciones de menú de *Entrada de ajuste* y *Salida de ajuste* donde la opción **Usar guía de proceso** está configurada en *Sí*, puede obtener una lista limitada de los códigos de motivo de recuento como parte del procesamiento en la aplicación móvil Warehouse Management.
>
> La opción **Usar guía de proceso** también puede ayudar a evitar que se produzcan por error grandes cantidades de ajuste. (Por ejemplo, un trabajador podría escanear accidentalmente un código de barras de un número de artículo en lugar de un valor de cantidad). Para configurar esta funcionalidad, configure la opción **Usar guía de proceso** como *Sí* para cada opción de menú relevante. Luego, vaya a **Warehouse Management\> Configuración\> Trabajador** y establezca el campo **Límite de cantidad de ajuste** para cada trabajador del almacén relevante para especificar la cantidad máxima de ajuste que el trabajador puede registrar.

## <a name="processing-that-uses-counting-reason-codes"></a>Procesamiento que utiliza códigos de motivo de recuento

Cuando los trabajadores utilizan la aplicación móvil Warehouse Management, se registran los códigos de motivo. A menos que se haya definido un proceso de aprobación de recuento, los códigos de motivo registrados se utilizan inmediatamente como parte de la contabilización del diario de recuento que sigue.

### <a name="cycle-count-approvals"></a>Aprobaciones de recuento cíclico

Antes de que se apruebe un recuento, el trabajador puede cambiar el código de motivo asociado al recuento. Cuando se aprueba el recuento, el código de motivo se introduce en las líneas del diario de recuento.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Modificar códigos de motivo para aprobaciones de recuento de ciclos

Para modificar una aprobación de recuento de ciclo, siga estos pasos.

1. Vaya a **Warehouse Management** \> **Recuento cíclico** \> **Revisión pendiente del trabajo de recuento cíclico**.
1. En la cuadrícula, seleccione un recuento cíclico.
1. En el panel de acciones, en la pestaña **Trabajo**, seleccione **Recuento cíclico**. En el campo **Código de motivo**, seleccione un nuevo código de motivo.

Los códigos de motivo se agregan a las líneas del diario en los diarios de recuento del tipo *Diario de recuento*.

1. Vaya a **Gestión del inventario** \> **Movimientos de diario** \> **Recuento de artículos** \> **Recuento**.
2. En los detalles de la línea del diario de recuento, en el campo **Código de motivo de recuento**, seleccione el código de motivo que coincida con su situación actual.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>Ver los códigos de motivo registrados en el historial de recuentos

Para ver los códigos de motivo que se han registrado en el historial de recuentos, siga estos pasos.

1. Vaya a **Gestión de inventario**\>  **Consultas e informes** \> **Historial de recuento**.
1. Seleccione un registro de recuento de artículos en el panel de lista.
1. En el campo **Código de motivo de recuento**, vea el historial de recuento que se ha registrado a través de un código de motivo.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Usar códigos de motivo para el ajuste de la cantidad o el recuento en línea

Para usar un código de motivo para un ajuste de cantidad o recuento en línea, siga estos pasos.

1. Vaya a **Gestión de inventario \> Consultas e informes \> Inventario disponible**.
1. En el panel de acciones, seleccione **Ajuste de cantidad**.
1. Seleccione **Ajuste de cantidad** y, a continuación, en el campo **Código de motivo de recuento**, seleccione un código de motivo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
