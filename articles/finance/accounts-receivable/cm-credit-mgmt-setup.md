---
title: Configuración de parámetros de la administración de crédito
description: En este tema se describen las opciones que puede usar para configurar la Administración de crédito a fin de cumplir los requisitos de su empresa.
author: mikefalkner
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4243b7163d822f8b496fb79f6c72cf8d5502ca7e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835349"
---
# <a name="credit-management-parameters-setup"></a>Configuración de parámetros de la administración de crédito

[!include [banner](../includes/banner.md)]

En este tema se describen las opciones que puede usar para configurar la Administración de crédito a fin de cumplir los requisitos de su empresa. Para comenzar a usar las características de Administración de crédito, configure los parámetros en la página **Parámetros de crédito y cobros** (**Crédito y cobros \> Configurar \> Parámetros de crédito y cobros**).

## <a name="credit-parameters"></a>Parámetros de crédito

Existen cuatro fichas desplegables en la sección **Crédito** en las que puede cambiar los parámetros que controlan la Administración de crédito: **Retenciones de crédito**, **Punto de comprobación de administración de crédito**, **Estadísticas de administración de crédito** y **Límites de crédito**. En las siguientes secciones se describe la configuración que está disponible en cada ficha desplegable.

### <a name="credit-holds"></a>Retenciones de crédito

- Establezca la opción **Permitir la edición del valor de los pedidos de ventas después de que se libere la retención de pedidos** en **No** para exigir que se vuelvan a comprobar las reglas de contabilización si el valor del pedido de ventas (precio extendido) ha aumentado desde que se eliminó el pedido de ventas de la lista de retención. .
- En el campo **Motivos de pedidos cancelados**, seleccione el motivo de liberación que se usará de manera predeterminada cuando se cancele un pedido de ventas que estaba en espera de administración de crédito.
- Establezca la opción **Comprobar el límite de crédito de grupos de crédito de cliente** en **Sí** para comprobar el límite de crédito de un grupo de crédito de cliente cuando el cliente de un pedido de ventas pertenece a un grupo de crédito de cliente. Se comprobará el límite de crédito para el grupo y después, si es suficiente, se comprobará el límite de crédito para el cliente.
- Establezca la opción **Comprobar el límite de crédito cuando aumenta las condiciones de pago** en **Sí** para comprobar las clasificaciones de las condiciones de pago a fin de determinar si las condiciones de pago del pedido de ventas difieren de las condiciones de pago predeterminadas del cliente. Si las nuevas condiciones de pago tienen una clasificación más alta que las condiciones de pago originales, el pedido se pone en espera de administración de crédito.
- Establezca la opción **Comprobar el límite de crédito cuando aumenta un descuento de liquidación** en **Sí** para comprobar las clasificaciones de descuento de liquidación a fin de determinar si el descuento por pronto pago del pedido de ventas difiere del descuento por pronto pago predeterminado para el cliente. Si el nuevo descuento por pronto pago tiene una clasificación más alta que el descuento por pronto pago original, el pedido se pone en espera de administración de crédito.
- En el campo **Motivo para liberar pedidos modificados**, seleccione el motivo de liberación que se usará de manera predeterminada cuando los pedidos modificados se liberen automáticamente de la retención de administración de crédito.
- Establezca la opción **Omitir la regla de bloqueo de límite de crédito vencido cuando la fecha de vencimiento está en blanco** en **Sí** para controlar el comportamiento de la regla **Límite de crédito vencido**. Establezca la opción en **No** para bloquear un pedido cuando la fecha de vencimiento esté en blanco.
- En Gestión de almacenes se pueden crear cargas en el momento de la entrada del pedido de ventas. Establezca la opción **Quitar líneas de carga bloqueadas** en **No** para dejar las líneas de pedido de ventas en la carga cuando un pedido de ventas está en retención crediticia. La carga no se puede procesar mientras el pedido de cliente está en espera. Establezca la opción en **Sí** para quitar las líneas de pedido de ventas de la carga cuando un pedido de ventas está en retención crediticia. Entonces se podrá procesar la carga.
- Los pedidos de ventas pueden liberarse automáticamente de la revisión de administración de crédito. En el campo **Motivo para liberar automáticamente**, seleccione el motivo para liberar que se usará de manera predeterminada cuando los pedidos de ventas se liberen automáticamente.
- Los pedidos de ventas pueden liberarse automáticamente de la revisión de administración de crédito. En el campo **Liberar automáticamente**, seleccione **Sin registro** para liberar la retención de un pedido. Debe ejecutar manualmente el proceso que puso el pedido en espera. Seleccione **Con registro** para registrar el pedido con el mismo proceso de registro que se ejecutó cuando se puso el pedido de ventas en espera.

### <a name="credit-management-checkpoint"></a>Punto de comprobación de gestión de créditos

Puede establecer los tiempos que se usan para comprobar si hay problemas de crédito en los pedidos de ventas. La ficha desplegable **Punto de comprobación de administración de crédito** identifica los procesos de registro de documentos que incluyen el procesamiento de las reglas de administración de crédito. También puede comprobar las reglas de crédito mientras realiza un registro proforma o un registro completo del pedido de ventas. Active las casillas de verificación para definir los procesos de registro que deben poner un pedido en espera si se detecta un problema después de procesar las reglas de bloqueo de la administración de crédito.

También puede definir el número de días de gracia antes de que las reglas de crédito se vuelvan a comprobar. Aunque puede especificar que las reglas de administración de crédito se comprueben al registrar, las reglas no se comprobarán durante el número especificado de días de gracia. Por ejemplo, confirma un pedido de ventas el día 1 y especifica dos días de gracia para el paso de confirmación. En este caso, las reglas de crédito no se comprobarán en el siguiente paso de registro (por ejemplo, la creación de un albarán o la facturación del pedido) hasta el día 4. En el día 4 (o después), las reglas se volverán a comprobar cuando se realice el registro, y el número de días de gracia cambiará al valor especificado para el próximo punto de comprobación de registro.

Si no especifica el número de días de gracia, las reglas de crédito se comprobarán en cada paso del registro que esté configurado para ejecutar reglas de administración de crédito. Si libera el pedido de ventas sin registrarlo y luego vuelve a ejecutar el mismo paso de procesamiento del pedido, las reglas de crédito se comprobarán nuevamente. Por ejemplo, un pedido se pone en espera después de una confirmación, y usted lo libera con o sin registro. En este caso, el pedido se pondrá en espera nuevamente si lo vuelve a confirmar. Use días de gracia si el pedido debe pasar al siguiente paso de procesamiento sin que se vuelva a retener.

No es posible especificar días de gracia para algunos puntos de control de registro y no para otros. Debe configurar todos los puntos de control de registro para que tengan días de gracia o para que no los tengan.

- Seleccione la casilla **Registro** para ejecutar las reglas de administración de crédito cuando se ejecuta el punto de control de registro que se muestra en la línea. Si no activa la casilla, las reglas se comprobarán solo una vez durante todo el proceso de registro.
- Si selecciona la casilla **Registro**, especifique el número de días de gracia que deben pasar antes de que las reglas de bloqueo se comprueben nuevamente. No puede agregar días de gracia si la casilla **Registro** está desactivada.
- Seleccione la casilla **Proforma** para ejecutar las reglas de administración de crédito cuando se ejecuta el punto de control de registro que se muestra en la línea. En la mayoría de los casos, el campo **Registro** se establece en **No** en el cuadro de diálogo que aparece cuando se registra un pedido de ventas.
- Si selecciona la casilla **Registro**, especifique el número de días de gracia que deben pasar antes de que las reglas de bloqueo se comprueben nuevamente. No puede agregar días de gracia si la casilla **Registro** está desactivada.

### <a name="credit-management-statistics"></a>Estadísticas de gestión de créditos

Se incluyen varias estadísticas de administración de crédito en cuadro informativo **Estadísticas de administración de crédito de cliente** de la página **Cliente**. Debe especificar varios valores necesarios para calcular esas estadísticas. Introduzca el número de meses que se usa para calcular los siguientes valores en el cuadro informativo **Estadísticas de administración de crédito de cliente**:

1. Ventas diarias pendientes 1
2. Ventas diarias pendientes 2
3. Saldo promedio 1
4. Saldo promedio 2
5. % de límite de crédito promedio
6. % de exposición promedio

### <a name="credit-limits"></a>Límites de crédito

- En Administración de crédito, el límite de crédito del cliente se muestra en la divisa del cliente. Debe definir el tipo de cambio para el límite de crédito en la divisa del cliente. En el campo **Tipo de cambio de límite de crédito**, seleccione el tipo de tipo de cambio que se debe usar para convertir el límite de crédito principal en el límite de crédito del cliente.
- Seleccione la opción **Permitir la edición manual de los límites de crédito** en **No** para evitar que los usuarios editen los límites de crédito en la página **Cliente**. Si esta opción está establecida en **No**, los cambios en el límite de crédito de un cliente solo pueden realizarse registrando transacciones de ajuste de límite de crédito.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Secuencias numéricas y parámetros de secuencia numérica compartida

Se requiere un id. de diario para procesar los ajustes del límite de crédito. Debe agregar el número de ajuste de límite de crédito que se debe usar para generar el id. del diario.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]