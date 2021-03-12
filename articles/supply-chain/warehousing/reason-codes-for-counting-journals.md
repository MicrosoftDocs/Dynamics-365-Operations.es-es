---
title: Códigos de motivo para recuento de inventario
description: En este tema se describe cómo configurar y aplicar códigos de motivo para tareas de recuento.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 66e1fb9f32aa31221f85180339b8b6ee55836be1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996157"
---
# <a name="reason-codes-for-inventory-counting"></a>Códigos de motivo para recuento de inventario

[!include [banner](../includes/banner.md)]

Los códigos de motivo le permiten analizar los resultados de un proceso de recuento y cualquier discrepancia que surja durante dicho proceso. Puede especificar el motivo por el que se realiza el recuento, como un pallet roto o un ajuste de existencias basado en ejemplos de inventario.

## <a name="recommendation"></a>Recomendación

Antes de configurar el sistema, le recomendamos que defina una estrategia para trabajar con códigos de motivo. Por ejemplo, intente responder a las siguientes preguntas:

- ¿Los códigos de motivo deben ser obligatorios en los almacenes?
- ¿Los códigos de motivo deben ser obligatorios u opcionales en algunos artículos?
- ¿Cuántos códigos de motivo necesita?
- ¿Cómo deben usar los usuarios de escáneres de códigos de barras los códigos de motivo? ¿Los códigos de motivo deben ser preseleccionados, obligatorioo o no editables?
- ¿Los trabajadores de almacén requieren un comportamiento de código de motivo diferente en los escáneres móviles? Si la respuesta es afirmativa, puede crear más elementos de menú y asignarlos a diferentes personas.

## <a name="where-reason-codes-apply"></a>Donde se aplican los códigos de motivo

Puede crear varias directivas de código de motivo, y cada una puede tener dos directivas de código de motivo de recuento. Las directivas de código de motivo de recuento se pueden utilizar en el nivel de almacén o en el nivel de artículo.

## <a name="set-up-reason-code-policies"></a>Configurar directivas de código de motivo

1. Seleccione **Gestión del inventario** \> **Configuración** \> **Inventario** \> **Directivas de código de motivo de recuento** y cree una nueva directiva de código de motivo.
2. En el campo **Tipo de código de motivo de recuento**, seleccione **Obligatorio** u **Opcional** para especificar si la selección de un código de motivo debe ser una acción opcional u obligatoria en uno de los siguientes diarios de recuento:

    - Recuento cíclico (dispositivo móvil)
    - Recuento puntual (dispositivo móvil)
    - Recuento de umbral (dispositivo móvil)
    - Entrada de ajuste (dispositivo móvil)
    - Salida de ajuste (dispositivo móvil)
    - Diario de recuento (cliente rico)

También puede configurar códigos de motivo para almacenes individuales y para productos. La configuración del código de motivo para productos puede omitir la configuración para almacenes.

## <a name="mandatory-reason-codes"></a>Códigos de motivo obligatorios

Si el parámetro **Obligatorio** se establece en la configuración de códigos de motivo para almacenes o artículos, el diario de recuento no se podrá completar y cerrar hasta que se proporcione un código de motivo.

### <a name="set-up-reason-codes-for-warehouses"></a>Configurar códigos de motivo para almacenes

1. Seleccione **Gestión del inventario** \> **Configurar** \> **Desglose del inventario** \> **Almacenes**.
2. En la pestaña **Almacén**, en el campo **Directiva de código de motivo de recuento**, seleccione una de las siguientes opciones:

    - **En blanco**: el parámetro configurado para el artículo se utiliza para determinar si los diarios de recuento son obligatorios para el producto.
    - **Obligatorio**: siempre es neceario un código de motivo en los diarios de recuento para el almacén.
    - **Opcional**: no es necesario un código de motivo en los diarios de recuento para el almacén.

### <a name="set-up-reason-codes-for-products"></a>Configurar códigos de motivo para productos

1. Seleccione **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.
2. En la pestaña **Producto**, seleccione **Directiva de código de motivo de recuento** y, a continuación, seleccione una de las siguientes opciones:

    - **En blanco**: el parámetro configurado para el almacén se utiliza para determinar si los diarios de recuento son obligatorios para el producto.
    - **Obligatorio**: siempre es neceario un código de motivo en los diarios de recuento para el producto. Esta configuración anula cualquier configuración del código de motivo en el nivel de almacén.
    - **Opcional**: no es necesario un código de motivo en los diarios de recuento para el producto. Esta configuración anula cualquier configuración del código de motivo en el nivel de almacén.

### <a name="use-reason-codes-in-counting-journals"></a>Utilice códigos de motivo en diarios de recuento

En un diario de recuento, puede agregar códigos de motivo para recuentos de los siguientes tipos:

- Recuento cíclico
- Recuento puntual
- Recuento de umbral
- Entrada de ajuste
- Salida de ajuste

Los códigos de motivo se agregan a las líneas del diario en los diarios de recuento del tipo **Diario de recuento**.

1. Seleccione **Gestión del inventario** \> **Movimiento de diario** \> **Recuento de artículos** \> **Recuento**.
2. En los detalles de línea del diario de recuento, en el campo **Código de motivo de recuento**, seleccione una opción.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>Ver el historial de recuento tal como está registrado por códigos de motivo

- Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Historial de recuento** y, a continuación, en el campo **Código de motivo de recuento**, vea el historial de recuento que se ha registrado a través del código de motivo.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Utilice un código de motivo para un ajuste de cantidad

1. En la página **Inventario disponible**, seleccione **Ajustar cantidad**. Puede abrir la página **Inventario disponible** de varias maneras. Por ejemplo, seleccione **Gestión del inventario** \> **Consultas e informes** \> **Inventario disponible**.
2. Seleccione **Ajustar cantidad** y, a continuación, en el campo **Código de motivo de recuento**, seleccione un código de motivo.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Configurar códigos de motivo para elementos de menú del dispositivo móvil

Puede configurar códigos de motivo para cualquier tipo de recuento en un elemento de menú del dispositivo móvil. La configuración del elemento de menú del dispositivo móvil incluye la siguiente información:

- Si el código de motivo se muestra al trabajador del dispositivo móvil durante el recuento.
- El código de motivo predeterminado que se muestra en un elemento de menú del dispositivo móvil.
- Si el usuario puede editar el código de motivo.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Configurar códigos de motivo en un dispositivo móvil

1. Seleccione **Gestión de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil**.
2. En la pestaña **Recuento cíclico**, seleccione **Recuento cíclico**.
3. En el campo **Código de motivo de recuento predeterminado**, establezca el código de motivo predeterminado que debe registrarse cuando el recuento se realiza mediante el elemento de menú del dispositivo móvil.
4. En el campo **Visualizar código de motivo de recuento**, seleccione **Línea** para mostrar el código de motivo después de que se registre cada desviación. De manera alternativa, seleccione **Ocultar** si no debe mostrarse el código de motivo.
5. Establezca la opción **Editar código de motivo de recuento** en **Sí** o **No**. Si establece esta opción en **Sí**, el trabajador puede editar el código de motivo cuando se muestre en el dispositivo móvil durante el recuento.

> [!NOTE]
> El botón **Recuento cíclico** se puede habilitar en cualquier elemento de menú del dispositivo móvil en el que se puedan hacer recuentos. El ejemplo incluye los elementos de menú para recuentos puntuales, trabajo dirigido por el usuario y trabajo dirigido por el sistema.

## <a name="cycle-count-approvals"></a>Aprobaciones de recuento cíclico

Antes de que se apruebe un recuento, el usuario puede cambiar el código de motivo asociado al recuento. Cuando se aprueba el recuento, el código de motivo se introduce en las líneas del diario de recuento.

### <a name="modify-cycle-count-approvals"></a>Modificar aprobaciones de recuento cíclico

1. Seleccione **Gestión de almacenes** \> **Recuento cíclico** \> **Revisión pendiente del trabajo de recuento cíclico**.
2. Seleccione **Recuento cíclico** y, a continuación, en el campo **Código de motivo**, seleccione un nuevo código de motivo.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>Modificar el elemento de menú del dispositivo móvil para la entrada de ajuste y la salida de ajuste

1. Seleccione **Gestión de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil** y, a continuación, seleccione **Entrada de ajuste y salida ajuste**.
2. Establezca la opción **Usar trabajo existente** en **No**.
3. En el campo **Proceso de creación de trabajo**, seleccione **Entrada de ajuste**.

Los siguientes campos se agregarán al elemento de menú del dispositivo móvil cuando se selecciona **Entrada de ajuste** o **Salida de ajuste** durante el proceso de creación de trabajo:

- Código de motivo de recuento predeterminado
- Visualizar código de motivo de recuento
- Editar código de motivo de recuento
