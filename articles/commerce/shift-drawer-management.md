---
title: Gestión de turnos y caja registradora
description: Este tema explica cómo configurar y utilizar los turnos en el punto de venta (PDV) de Commerce.
author: jblucher
manager: AnnBe
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 32b7be42509a2c857f1357eb64a6b488f9cd2269
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023949"
---
# <a name="shift-and-cash-drawer-management"></a>Gestión de turnos y caja registradora

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar y utilizar los turnos en el punto de venta (PDV) de Commerce.

En Dynamics 365 Commerce, el término *turno* describe la recopilación de datos transaccionales de PDV y actividades entre dos puntos en el tiempo. Para cada turno, la suma de dinero prevista se compara con la suma que se cuenta y declara.

Normalmente, los turnos están abiertos al inicio del día laboral. En ese momento, un usuario declara el importe inicial que contiene la caja registradora. Las transacciones de venta se realizan durante todo el día. Finalmente, al final del día, se cuenta la caja y se declaran los importes de cierre. Se cierra el turno y se genera un informe Z. El informe Z indica si existe un superávit o déficit.

## <a name="typical-shift-scenarios"></a>Escenarios de turno típicos

Commerce proporciona varias opciones de configuración y operaciones de PDV para admitir una amplia gama de procesos empresariales al final del día para el PDV. Esta sección describe algunos escenarios de turno típicos.

### <a name="fixed-till"></a>Caja registradora fija

Tradicionalmente, este escenario se utilizado con más frecuencia. Todavía se utiliza ampliamente. En un turno con "caja registradora fija", el turno y la caja registradora se asocian a un registro específico. No se mueven de un registro a otro. Un turno con "caja registradora fija" puede ser utilizado por un usuario único o compartido entre varios usuarios. Los turnos con "caja registradora fija" no requieren ninguna configuración especial.

### <a name="floating-till"></a>Caja registradora flotante

En un turno con "caja registradora flotante", el turno y la caja se pueden mover de un registro a otro. Aunque un registro puede tener solo un turno activo por caja registradora, los turnos pueden suspenderse y luego reanudarse más tarde o en un registro diferente.

Por ejemplo, una tienda tiene dos registros. Cada registro se abre al principio del día cuando el cajero abre un nuevo turno y proporciona el importe inicial. Cuando un cajero está listo para tomarse un descanso, ese cajero suspende su turno y quita la parte superior de la caja registradora. Ese registro quedará entonces disponible para otros cajeros. Otro cajero puede iniciar sesión y abrir su propio turno en el registro. Una vez que ha acabado el primer descanso del cajero, ese cajero puede reanudar su turno cuando uno de los otros registros esté disponible. Los turnos con "caja registradora flotante" no requieren ninguna configuración o permiso especial.

### <a name="single-user"></a>Usuario único

Muchos minoristas prefieren dejar solo un usuario por turno para ayudar a garantizar el nivel superior de contabilidad para el efectivo en la caja registradora. Si solo un usuario puede utilizar la caja registradora asociada a un turno, ese usuario será el único responsable de cualquier discrepancia. Si más de un usuario utiliza un turno, es difícil determinar quién cometió un error o quién podría estar intentando robar de la caja registradora.

### <a name="multiple-users"></a>Varios usuarios

Algunos minoristas están dispuestos a sacrificar el nivel de contabilidad que proporcionan los turnos de usuario único y a permitir más de un usuario por turno. Este planteamiento es habitual cuando hay más usuarios que registros disponibles, y la necesidad de flexibilidad y velocidad supera la posibilidad de pérdidas. También es habitual cuando los administradores de tienda no tienen sus propios turnos pero, si es necesario, pueden usar los turnos de cualquiera de sus cajeros. Para iniciar sesión y usar un turno que abrió otro usuario, un usuario debe tener el permiso de PDV **Permitir varios inicios de sesión de turno**.

### <a name="shared-shift"></a>Turno compartido

Una configuración de "turno compartido" permite a los minoristas tener un turno único en múltiples registros, cajas registradoras y usuarios. Un turno compartido tiene un único importe inicial y un único importe de cierre que se resumen en todos los cajones de efectivo. Los turnos compartidos son los más habituales cuando se utilizan dispositivos móviles. En esta situación, no se reserva una caja registradora independiente para cada registro. En su lugar, todos los registros pueden compartir una caja registradora.

Para turnos compartidos que se utilizarán en una tienda, la caja registradora debe configurarse como una "caja registradora de turno compartido" en **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware \> Caja**. Asimismo, los usuarios deben tener uno o los dos permisos de turnos compartidos (Permitir administración de turnos compartidos y Permitir uso de turnos compartidos).

> [!NOTE]
> Solo puede estar abierto un turno compartido cada vez en cada tienda. Los tunos compartidos e independientes se puede utilizar en el mismo almacén.

## <a name="shift-and-drawer-operations"></a>Operaciones de turnos y caja registradora

Se pueden realizar distintas operaciones para cambiar el estado de un turno, o para aumentar o reducir el importe de dinero en la caja registradora. Esta sección describe estas operaciones de cambio para Modern POS y Cloud POS.

### <a name="open-shift"></a>Turno abierto

El PDV requiere que los usuarios tengan un turno activo y abierto para realizar operaciones que producirán una transacción financiera como una venta, una devolución o un pedido de cliente.

Cuando un usuario inicia sesión en el PDV, en primer lugar el sistema verifica que haya un turno activo disponible para ese usuario en el registro actual. Si un turno activo no está disponible, el usuario puede abrir un nuevo turno, reanudar un turno existente o iniciar sesión en modo de "sin caja", en función de la configuración del sistema y los permisos de los usuarios.

### <a name="declare-start-amount"></a>Declarar importe inicial

Esta operación es a menudo la primera operación que se realiza para un turno recién abierto. Para esta operación, los usuarios especifican el importe de efectivo de inicio en la caja del turno. Esta operación es importante porque el cálculo de superávit/déficit que se produce cuando se cierra un turno tiene en cuenta el importe inicial.

### <a name="float-entry"></a>Entrada flotante

Las *entradas flotantes* son transacciones no comerciales que se realizan en un turno activo para aumentar el importe de efectivo de la caja. Un ejemplo típico de una entrada flotante es una transacción para agregar el cambio adicional a la caja cuando se está acabando.

### <a name="tender-removal"></a>Supresión de forma de pago

Las *supresiones de forma de pago* son transacciones no comerciales que se realizan en un turno activo para reducir el importe de efectivo de la caja. Esta operación es la que se usa con mayor frecuencia junto con una operación de entrada flotante en otro turno. Por ejemplo, puesto que el registro 1 se está quedando sin cambio, el usuario en el registro 2 realiza un supresión de forma de pago para reducir el importe de su caja. El usuario en el registro 1 realiza una entrada flotante para aumentar el importe de su caja.

### <a name="suspend-shift"></a>Suspender turno

Los usuarios pueden suspender el turno activo para liberar el registro actual de otro usuario, o para mover el turno a otro registro (en este caso, el turno suele denominarse "caja registradora flotante").

La suspensión de un turno evita la ejecución de nuevas transacciones o cambios en el turno hasta que este se reanuda.

### <a name="resume-shift"></a>Reanudar turno

Esta operación permite a los usuarios reanudar un cambio suspendido anteriormente en cualquier registro que todavía no tiene ningún cambio activo.

### <a name="tender-declaration"></a>Declaración por forma de pago

Esta operación se realiza para especificar el importe monetario total que hay actualmente en la caja. Los usuarios suelen realizar con mucha frecuencia esta operación antes de cerrar un turno. El valor especificado se compara con la cantidad de turnos esperada para calcular el importe de superávit/déficit.

### <a name="safe-drop"></a>Ingreso en caja fuerte

Los ingresos en caja fuerte se pueden realizar en cualquier momento de un turno activo. Esta operación quita dinero de la caja para que se pueda transferir a una ubicación más segura como una caja fuerte en una sala aparte. El importe total registrado para los ingresos en caja fuerte aún está incluido en los totales de cambio, aunque no es necesario contarlo como parte de la declaración por forma de pago.

### <a name="bank-drop"></a>Ingreso bancario

Al igual que los ingresos en caja fuerte, los ingresos bancarios se realizan en turnos activos. Esta operación quita dinero del turno para prepararse para el depósito bancario.

### <a name="blind-close-shift"></a>Turno cerrado en ciego

*Los turnos cerrados en ciego* ya no están activos, pero no se han cerrado por completo. A diferencia de los turnos supendidos, los turnos cerrados en ciego no se pueden reanudar. Sin embargo, las operaciones como Declarar importe inicial y Declaración por forma de pago se pueden realizar posteriormente o desde un registro diferente.

Los turnos cerrados en ciego se suelen usar para liberar un registro para un nuevo usuario o turno, sin tener que contabilizar completamente, conciliar y cerrar el turno primero.

### <a name="close-shift"></a>Cerrar turno

Esta operación calcula los totales de turno, los importes de superávit/déficit y, a continuación, termina un turno activo o cerrado en ciego. Dependiendo de los permisos del usuario, también se imprie un informe Z para el turno. Los turnos cerrados no se pueden reanudar ni modificar.

### <a name="print-x"></a>Imprimir X

Esta operación genera e imprime un informe X para el turno activo actual.

### <a name="reprint-z"></a>Volver a imprimir Z

Esta operación vuelve a imprimir el último informe Z que el sistema generó cuando se cerró un turno.

### <a name="manage-shifts"></a>Administrar cambios

Esta operación permite a los usuarios ver todos los turnos activos, suspendidos, y cerrados en ciego de la tienda. En función de los permisos, los usuarios pueden realizar los procedimientos de cierre finales como las operaciones de declaración por forma de pago y de cierre de turno para los turnos cerrados en ciego. Esta operación también permite a los usuarios ver y eliminar turnos no válidos en el caso poco probable de que los turnos queden en mal estado después de cambiar entre los modos sin conexión y conectado. Estos turnos no válidos no contienen información financiera ni datos transaccionales necesarios para la conciliación.

## <a name="shift-and-drawer-permissions"></a>Permisos de turnos y caja registradora

Los siguientes permisos de PDV afectan a lo que un usuario puede y no puede hacer en varios escenarios:

- **Permitir cierre en ciego**
- **Permitir impresión de informes X**
- **Permitir impresión de informe Z**
- **Permitir declaración por forma de pago**
- **Permitir declaración del capital flotante**
- **Categoría abierta sin venta**
- **Permitir varios inicios de sesión de turno** – Este permiso permite al usuario iniciar sesión y usar un turno que abrió otro usuario. Los usuarios que no tienen este permiso puede iniciar sesión y usar solo turnos que han abierto.
- **Permitir administración de turnos compartidos** – Los usuarios deben tener este permiso para abrir o cerrar un turno compartido.
- **Permitir uso de turnos compartidos** – Los usuarios deben tener este permiso para iniciar sesión y usar un turno compartido.

## <a name="back-office-end-of-day-considerations"></a>Consideraciones de back-office al final del día

La forma en que los turnos y la conciliación de la caja registradora se utilizan en el PDV difiere de la forma en que las datos de transacción se resumen durante el cálculo del extracto. Es importante que entienda esta diferencia. Dependiendo de su configuración y sus procesos empresariales, los datos del turno en el PDV (el informe Z) y un extracto calculado en la back-office puede proporcionarle resultados diferentes. Esta diferencia no implica necesariamente que los datos del turno o el extracto calculado sean incorrectos, o que exista un problema con los datos. Simplemente significa que los parámetros que se proporcionan pueden incluir transacciones adicionales o menos transacciones, o que las transacciones se han resumido de manera distinta.

Aunque cada minorista tiene distintos requisitos empresariales, le recomendamos que configure su sistema de la siguiente forma para evitar situaciones en las que se produzcan diferencias de este tipo:

Vaya a **Retail y Commerce \> Canales \> Tiendas \> Todas las tiendas \> Extracto/cierre**, y para cada tienda, establezca el campo **Método de extracto** y el campo **Método de cierre** en **Turno**.

Esta configuración ayuda a garantizar que los extractos de back-office incluyan las mismas transacciones que los turnos en el PDV, y que los datos se resumen en ese turno.

Para obtener más información sobre los métodos de extracto y de cierre, consulte [Almacenar configuraciones para los extractos de Retail](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).
