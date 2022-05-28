---
title: Cierre de fin de año
description: Este tema describe la configuración y los pasos necesarios para ejecutar el proceso de cierre de fin de año de la contabilidad general.
author: kweekley
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: kfend
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 247c3286124da946937c8afd248a275e5a745044
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725244"
---
# <a name="year-end-close"></a>Cierre de fin de año

[!include [banner](../includes/banner.md)]

Este tema describe la configuración y los pasos necesarios para ejecutar el proceso de cierre de fin de año de la contabilidad general.

Al final de un ejercicio, se debe realizar el proceso de cierre de fin de año para transferir los saldos de apertura al nuevo año. La mayoría de las organizaciones realizará el proceso de cierre de fin de año varias veces. La primera ejecución mueve los saldos al nuevo año fiscal. El proceso puede volver a ejecutarse tantas veces como sea necesario para mover los saldos de las entradas de ajuste al nuevo ejercicio.

Durante el proceso de cierre de fin de año existen dos tipos de transacciones creadas posibles. Se genera siempre una transacción de apertura y se usará para crear los saldos de apertura del nuevo ejercicio. La transacción de apertura muestra los saldos de cuentas contables del balance de situación en el nuevo ejercicio y los saldos de las cuentas contables de pérdidas y ganancias en la cuenta contable de ganancias retenidas del nuevo ejercicio. La transacción de cierre se crea opcionalmente para poner a cero los saldos de las cuentas de pérdidas y ganancias del ejercicio que se está cerrando.

## <a name="prepare-to-run-the-year-end-close"></a>Preparar el cierre de fin de año

Antes de realizar el proceso de cierre de fin de año, valide la configuración de:

En la página de **Cuenta principal**:

- Verifique que el campo **Tipo de cuenta principal** está configurado correctamente para cada cuenta principal. El tipo de cuenta principal determina si el saldo de la cuenta principal se presentará como saldo de apertura o cerrado en las ganancias retenidas de la transacción de apertura.
- El saldo de la cuenta principal se puede transferir a una nueva cuenta principal durante el cierre de fin de año. Introduzca la nueva cuenta principal en el campo **Cuenta de apertura**. Este campo normalmente se usará en las cuentas principales del balance de situación cuando la cuenta principal esté inactiva y se use una nueva cuenta principal para el nuevo ejercicio.

En la página **Parámetros de Contabilidad general** en **Cierre del ejercicio**:

- La opción **Eliminar entradas de cierre de año cuando se vuelve a cerrar el año** se usa para especificar si la transacción de apertura generada por el sistema de un cierre de fin de año anterior se debe eliminar cuando se realice de nuevo el cierre de fin de año. Si esta opción se establece **Sí**, se eliminará la transacción de apertura anterior y las transacciones opcionales de cierre y se creará una nueva transacción de apertura o cierre en los saldos actuales. Si se establece esta opción **No**, la transacción de apertura anterior y las transacciones opcionales de cierre se mantendrán y se creará una transacción de apertura o cierre adicional para mover los saldos de las transacciones de ajuste registrados después del cierre de fin de año anterior.
- La opción **Creación de transacciones de cierre durante una transferencia** se usa para crear transacciones de cierre en el ejercicio que se está cerrando para poner a 0 (cero) los saldos de todas las cuentas principales. Si esta opción se establece **Sí**, se crean la transacción de apertura y la transacción de cierre. Si se establece esta opción en **No**, solo se crea la transacción de apertura en el siguiente ejercicio para transferir los saldos. Los saldos de las cuentas principales se mantienen al final del ejercicio.
- La opción **Establecer el estado del ejercicio en Cerrado de forma permanente** se usa para establecer el ejercicio en un estado cerrado de forma permanente. Utilice esta opción con cuidado, porque los períodos que tienen un estado cerrado permanentemente no se pueden volver a abrir. Por lo tanto, los ajustes no se pueden contabilizar en el año fiscal. Se recomienda establecer esta opción en **No**.
- La opción **Se debe completar el número de cupón** ha sido eliminada. Ahora se requiere un comprobante cuando se ejecuta el proceso de cierre de fin de año. En ese momento, el número de cupón se ingresa manualmente.

En la página **Calendario fiscal**:

- El siguiente ejercicio debe existir antes de realizar el cierre de fin de año. De lo contrario, los saldos iniciales no se pueden crear en el período de apertura.

En la página **Calendario contable**:

- Opcional: cada período fiscal del ejercicio que se cerrará se puede establecer en **En suspensión** para evitar que se introduzcan nuevas transacciones. Si se detectan entradas de ajuste, los períodos en suspensión se pueden volver a abrir para registrar entradas de ajuste, incluso si el proceso de cierre de fin de año ya se ha realizado.

En la página **Configuración de la plantilla de cierre de fin de año**:

- Cuando la característica **Mejoras de fin de año en el libro mayor** está activada, el proceso de configuración de la plantilla de cierre de fin de año se separa del proceso de ejecución del cierre de fin de año. La plantilla se puede definir en la página **Configuración de la plantilla de cierre de fin de año** (**Libro mayor \> Configuración del libro mayor \> Configuración de la plantilla de cierre de fin de año**), o se puede acceder desde el proceso de cierre de fin de año.

## <a name="define-year-end-close-templates"></a>Definir plantillas de cierre de fin de año

Después de configurar el sistema, se puede realizar el proceso de cierre de fin de año. En la página **Configuración de plantilla de cierre de fin de año**, se puede definir una plantilla para el grupo de entidades jurídicas para las que se realizará el proceso de cierre de fin de año. La plantilla se volverá a utilizar en cada cierre de fin de año, pero se puede modificar si la organización cambia.

Primero establezca el campo **Nombre del grupo** para la plantilla y seleccione el calendario fiscal. El nombre de grupo debe identificar el grupo de entidades jurídicas incluido. Cuando esté determinando los grupos de entidades legales, recuerde que las entidades legales pueden incluirse en el mismo grupo solo si se selecciona el mismo calendario fiscal para ellas. Por ejemplo, las plantillas se pueden configurar según la geografía, pudiendo crear grupos independientes para las entidades jurídicas de América del Norte, Europa, Oriente Medio y África (EMEA) y Asia-Pacífico (APAC).

A continuación, se pueden agregar las entidades jurídicas a la plantilla. Las entidades jurídicas se pueden agregar seleccionado una jerarquía organizativa o seleccionado las entidades jurídicas. Si se selecciona una jerarquía organizativa, solo se agregarán a la plantilla las entidades jurídicas de la jerarquía que utilizan el calendario fiscal seleccionado. Si usa las entidades jurídicas para agregar a la plantilla, solo se podrán agregar las entidades jurídicas con el mismo calendario fiscal. Se requiere el mismo calendario fiscal porque el cierre de fin de año se realiza seleccionando un ejercicio, que puede variar en función del calendario.

Después de agregar las entidades jurídicas, defina las cuentas principales de ganancias retenidas de cada entidad jurídica.

La ficha **Dimensión financiera** se emplea para definir las dimensiones financieras que se utilizarán en la transacción de apertura. Tenga en cuenta que los valores que está configurando solo son relevantes para la entidad jurídica seleccionada en la cuadrícula **Entidades jurídicas**. Debe repetir la configuración para cada entidad jurídica de la cuadrícula.

La opción **Transferir dimensiones de balance de situación** se utiliza para especificar si las dimensiones financieras de las transacciones registradas en las cuentas de balance de situación se deben mantener en la transacción de apertura. Se recomienda establecer esta opción en **Sí**. La configuración de las dimensiones del balance general no afecta los saldos existentes en las cuentas del libro mayor de ganancias retenidas. Estos saldos están determinados por las dimensiones de pérdidas y ganancias que se definen en la siguiente sección. Por ejemplo, el año fiscal 2019 fue el primer año que se cerró, y la opción **Cerrar todo** se usó para seleccionar las dimensiones de cierre de **Departamento** y **Centro de costes**. En este caso, se creó una cuenta de ganancias retenidas separada para cada combinación de un departamento y un centro de costos. Cuando se ejecuta el cierre de fin de año para el año fiscal 2020, las ganancias retenidas del año anterior permanecen exactamente como se contabilizaron, incluso si **Transferir las dimensiones del balance** se establece en **No**. Los saldos que se contabilizan en utilidades retenidas de cierres de fin de año anteriores nunca se modifican.

La sección **Transferir dimensiones de pérdidas y ganancias** se usa para especificar las dimensiones financieras de las transacciones registradas en las cuentas de pérdidas y ganancias se transferirán a la cuenta principal de ganancias retenidas. Primero, identifique las dimensiones financieras relevantes para la entidad jurídica seleccionada. Estas dimensiones financieras incluirán cualquier dimensión financiera registrada durante el año, incluso si la dimensión financiera no es parte de una estructura contable activa. A continuación, defina cada dimensión como **Cerrar uno** o **Cerrar todo**. La opción predeterminada es **Cerrar todo**. Esta opción mantiene los valores de la dimensión financiera original de las transacciones registradas y los utiliza para crear los saldos de apertura de la cuenta de ganancias retenidas. Se crearán saldos iniciales de ganancias retenidas separados para cada combinación exclusiva de valores de la dimensión financiera. Si se selecciona **Cerrar uno**, todas las transacciones registradas que tengan esa dimensión financiera se resumirán en un saldo inicial de ganancias retenidas para el valor de dimensión especificado en el campo que aparece después de **Cerrar uno**. Por ejemplo, todas las transacciones del ejercicio se registraron con la estructura contable de **Cuenta principal - Departamento**. Para la dimensión financiera **Departamento** de la plantilla se selecciona **Cerrar uno** y se especifica el valor de dimensión **100**. Si el ingreso total de todas las transacciones registradas en los departamentos 200, 300 y 400 es 100 000 $, se creará un saldo de apertura para las **Ganancias retenidas - 100**. Si selecciona **Cerrar uno** pero deja el campo de valores de la dimensión financiera en blanco, todas las transacciones se registrarán en las ganancias retenidas con ese valor de dimensión en blanco.

## <a name="run-the-year-end-close-process"></a>Realizar el proceso de cierre de fin de año

Una vez creadas las plantillas de cierre de fin de año, puede iniciar el proceso de cierre de fin de año en la página **Cierre de fin de año** (**Contabilidad general \> Cierre del período \> Cierre de fin de año**). Antes de ejecutar el cierre de fin de año, puede agregar nuevas plantillas de cierre de fin de año o modificar las plantillas existentes seleccionando **Configuración de la plantilla de cierre de fin de año** para abrir la página de configuración de las plantillas.

Seleccione la plantilla de cierre de fin de año y luego, en el Panel de acciones, seleccione **Ejecutar cierre de fin de año**. Seleccione todas las entidades jurídicas o un subconjunto de entidades jurídicas de la plantilla para las que se va a realizar el cierre de fin de año. Si realiza el cierre de fin de año por primera vez en un ejercicio, probablemente elegirá todas las entidades jurídicas para crear los saldos iniciales de todas las entidades jurídicas. Si ya ha realizado el cierre de fin de año de nuevo, puede elegir ejecutar el proceso de nuevo solo para las entidades jurídicas que han registrado entradas de ajuste.

A continuación, seleccione el ejercicio con el que desee realizar el proceso de cierre de fin de año. Si existe más de un período de cierre para el último período del año fiscal, el campo **Nombre del período** se vuelve disponible. A continuación, puede seleccionar el período de cierre que se utilizará para contabilizar la transacción de cierre, si la configuración está definida para crear la transacción de cierre.

A continuación, ingrese un número de cupón. El mismo número de asiento se usará para todas las entidades jurídicas seleccionadas para el proceso de cierre de fin de año. El número de asiento no se genera con una secuencia numérica.

De forma predeterminada, el proceso de cierre de fin de año se realiza en el modo de lotes. Por lo tanto, después de iniciarlo, puede volver a otras actividades.

Debido a que las estructuras de cuentas pueden cambiar a lo largo de un año fiscal, no siempre se puede identificar la estructura de cuentas relevante. Por lo tanto, el proceso de cierre de fin de año no sigue las estructuras contables. Si se crean las transacciones de apertura, los saldos se presentan con las dimensiones financieras definidas en la plantilla cierre de fin de año. Las entradas de saldo inicial podrían incluir dimensiones financieras que ya no están en la estructura contable actual y combinaciones de segmentos que ya no son válidas en la estructura contable actual. Si su organización desea excluir una dimensión financiera del saldo inicial de ganancias retenidas, defina la dimensión financiera como **Cerrar uno** y deje el valor de dimensión en blanco.

Una vez finalizado el proceso, se crea un registro para cada combinación de entidad jurídica y año fiscal. Verá solo los registros para las entidades jurídicas a las que tiene acceso. Cada registro incluye la fecha y hora del sistema en que se ejecutó el proceso y un enlace directo a los comprobantes que se crearon para el cierre de fin de año.

[![Registros creados en la ficha desplegable Historial de cierre de fin de año de la página de cierre de fin de año](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Si vuelve a ejecutar el cierre de fin de año, verá uno o varios registros para cada combinación de una entidad legal y un año fiscal, según la configuración de la opción **Eliminar las entradas de fin de año existentes al volver a cerrar el año** opción en la página **Parámetros de contabilidad general**:

- Si la opción se establece en **Sí**, el asiento del cierre del año anterior se borra. El registro está marcado como **Invertido** y sellada con la fecha y hora en que se realizó la reversión. Además, se elimina el enlace al número de asiento. Cuando se complete el cierre de fin de año, se creará un nuevo registro para el nuevo comprobante que se crea.
- Si la opción está configurada en **No**, se mantiene el registro del cierre del ejercicio anterior, junto con el enlace al bono. Cada vez que se vuelva a ejecutar el cierre de fin de año, se creará un nuevo registro, junto con un enlace a los nuevos asientos.

## <a name="reverse-the-year-end-close-process"></a>Invertir el proceso de cierre de fin de año

En la página **Cierre de fin de año**, puede revertir un cierre de fin de año. Seleccione el registro para la combinación de una entidad legal y un año fiscal que debe revertirse y luego seleccione **Invertir cierre de fin de año**. El proceso de anulación elimina todos los comprobantes de apertura y cierre que se crearon para el año fiscal. El registro está marcado como **Invertido** y sellada con la fecha y hora en que se realizó la reversión. Además, se elimina el enlace al número de asiento. Como el proceso de cierre de fin de año, la inversión se realiza en el modo de lotes.

La casilla de verificación **Mostrar invertido** que está disponible encima de la cuadrícula le permite ocultar o mostrar los registros de los procesos de cierre de fin de año invertidos. Después de ejecutar el proceso **Inversión de cierre de fin de año**, es posible que deba seleccionar la casilla de verificación **Mostrar invertido** para ver el registro. Puede configurar filtros adicionales para ver otra información.

[![Usar la casilla de verificación Mostrar invertido para ver los registros de los procesos de cierre de fin de año invertidos en la página de cierre de fin de año](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

Para obtener más información, consulte [Cerrar la contabilidad general al final del período](close-general-ledger-at-period-end.md) y [Cerrar el año fiscal](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
