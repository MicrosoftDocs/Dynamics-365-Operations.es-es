---
title: "Cierre de fin de año"
description: "Este tema describe la configuración y los pasos necesarios para ejecutar el proceso de cierre de fin de año de la contabilidad general."
author: kweekley
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1355dbf0adaa8915c1aa3c9460d1cb07ab4c7fba
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="year-end-close"></a>Cierre de fin de año

[!include[banner](../includes/banner.md)]


Este tema describe la configuración y los pasos necesarios para ejecutar el proceso de cierre de fin de año de la contabilidad general. 

Al final de un ejercicio, se debe realizar el proceso de cierre de fin de año para transferir los saldos de apertura al nuevo año. La mayoría de las organizaciones realizará el proceso de cierre de fin de año varias veces. La primera vez se tendrán que obtener los saldos que se pasarán al nuevo ejercicio. El cierre de fin de año se podrá ejecutar de nuevo tantas veces como sea necesario para mover los saldos de las entradas de ajuste al nuevo ejercicio. 

Durante el proceso de cierre de fin de año existen dos tipos de transacciones creadas posibles. Se genera siempre una transacción de apertura y se usará para crear los saldos de apertura del nuevo ejercicio. La transacción de apertura muestra los saldos de cuentas contables del balance de situación en el nuevo ejercicio y los saldos de las cuentas contables de pérdidas y ganancias en la cuenta contable de ganancias retenidas del nuevo ejercicio. La transacción de cierre se crea opcionalmente para poner a cero los saldos de las cuentas de pérdidas y ganancias del ejercicio que se está cerrando.

## <a name="prepare-to-run-the-year-end-close"></a>Preparar el cierre de fin de año
Antes de realizar el proceso de cierre de fin de año, valide la configuración de: 

En la página de **Cuenta principal**:

-   Validar que el **Tipo de cuenta principal** está definido correctamente en cada cuenta principal. El tipo de cuenta principal se emplea para determinar si el saldo de la cuenta principal se presentará como saldo de apertura o cerrado en las ganancias retenidas de la transacción de apertura.
-   El campo **Cuenta de apertura** se puede utilizar para transferir el saldo de la cuenta principal a una nueva cuenta principal durante el cierre de fin de año. La nueva cuenta principal se especifica en el campo **Cuenta de apertura**. Esto normalmente se usará en las cuentas principales del balance de situación cuando la cuenta principal esté inactiva y se use una nueva cuenta principal para el nuevo ejercicio.

En la página **Parámetros de Contabilidad general** en **Cierre del ejercicio**:

-   La opción **Eliminar transacciones de cierre de fin de año** se usa para especificar si la transacción de apertura generada por el sistema de un cierre de fin de año anterior se debe eliminar cuando se realice de nuevo el cierre de fin de año. Si esta opción se establece **Sí**, se eliminará la transacción de apertura anterior y se creará una nueva transacción de apertura en los saldos actuales. Si se establece esta opción **No**, la transacción de apertura anterior se mantendrá y se creará una transacción de apertura adicional para mover los saldos de las transacciones de ajuste registrados después del cierre de fin de año anterior.
-   La opción **Creación de transacciones de cierre durante una transferencia** se usa para crear transacciones de cierre en el ejercicio que se está cerrando para poner a cero los saldos de las cuentas de pérdidas y ganancias. Si esta opción se establece **Sí**, se crean la transacción de apertura y la transacción de cierre. Si se establece esta opción en **No**, solo se crea la transacción de apertura en el siguiente ejercicio para transferir los saldos. Los saldos de las cuentas de pérdidas y ganancias se mantienen al final del ejercicio.
-   La opción **Establecer el estado del ejercicio en Cerrado de forma permanente** se usa para establecer el ejercicio en un estado cerrado de forma permanente. Use esta configuración con precaución, ya que los períodos con un estado cerrado de forma permanente no se pueden reabrir, lo que impide que se registren ajustes en el ejercicio. Es mejor establecerlo en **No**.
-   La opción **Es necesario rellenar el número de asiento** se usa para definir si se necesita un número de asiento al ejecutar el proceso de cierre de fin de año. Es una práctica recomendada requerir un número de asiento para identificar fácilmente la transacción de apertura.

En la página **Calendario fiscal**:

-   El siguiente ejercicio debe existir antes de realizar el cierre de fin de año. El siguiente ejercicio es necesario para crear los saldos iniciales del período de apertura.

En la página **Calendario contable**:

-   Opcional: cada período fiscal del ejercicio que se cerrará se puede establecer en **En suspensión** para evitar que se introduzcan nuevas transacciones. Si se detectan entradas de ajuste, los períodos en suspensión se pueden volver a abrir para registrar entradas de ajuste, incluso si el proceso de cierre de fin de año ya se ha realizado.

## <a name="define-year-end-close-templates"></a>Definir plantillas de cierre de fin de año
Después de configurar el sistema, se puede realizar el proceso de cierre de fin de año. En la página **Cierre de fin de año**, se puede definir una plantilla para el grupo de entidades jurídicas para las que se realizará el proceso de cierre de fin de año. La plantilla se volverá a utilizar en cada cierre de fin de año, pero se puede modificar si la organización cambia. 

Primero defina el **Nombre del grupo** para la plantilla y seleccione el calendario fiscal. El nombre de grupo debe identificar el grupo de entidades jurídicas incluido.  Por ejemplo, las plantillas se pueden configurar según la geografía, creando grupos independientes para las entidades jurídicas de América del Norte, de EMEA y de APAC. 

A continuación, se pueden agregar las entidades jurídicas a la plantilla. Las entidades jurídicas se pueden agregar seleccionado una jerarquía organizativa o seleccionado las entidades jurídicas. Si se selecciona una jerarquía organizativa, solo se agregarán a la plantilla las entidades jurídicas de la jerarquía que utilizan el calendario fiscal seleccionado. Si usa las entidades jurídicas para agregar a la plantilla, solo se podrán agregar las entidades jurídicas con el mismo calendario fiscal. Se requiere el mismo calendario fiscal porque el cierre de fin de año se realiza seleccionando un ejercicio, que puede variar en función del calendario. 

Después de agregar las entidades jurídicas, defina las cuentas principales de ganancias retenidas de cada entidad jurídica. El campo **Fecha de último cierre de fin de año** se actualizará cada vez que el cierre de fin de año se realiza para la entidad jurídica. 

La ficha **Dimensión financiera** se emplea para definir las dimensiones financieras que se utilizarán en la transacción de apertura. Tenga en cuenta que los valores que está definiendo solo son relevantes para la entidad jurídica seleccionada en la cuadrícula **Entidades jurídicas**. Deberá repetir la configuración para cada entidad jurídica de la cuadrícula. 

**Transferir dimensiones de balance de situación** se utiliza para definir si las dimensiones financieras de las transacciones registradas en las cuentas de balance de situación se deben mantener en la transacción de apertura. Se recomienda establecer esta opción en **Sí**. **Transferir dimensiones de pérdidas y ganancias** se usa para definir las dimensiones financieras de las transacciones registradas en la cuenta de pérdidas y ganancias se transferirán a la cuenta principal de ganancias retenidas. Primero, identifique las dimensiones financieras relevantes para la entidad jurídica seleccionada. Estas incluirán las dimensiones financieras registradas durante el año, incluso si la dimensión financiera no es parte de una estructura contable activa. A continuación, defina cada dimensión como **Cerrar uno** o **Cerrar todo**.  El valor predeterminado es **Cerrar todos**, que mantiene los valores de la dimensión financiera original de las transacciones registradas y los utiliza para crear los saldos de apertura de la cuenta de ganancias retenidas. Se crearán saldos iniciales de ganancias retenidas separados para cada combinación exclusiva de valores de la dimensión financiera. Si se selecciona **Cerrar uno**, todas las transacciones registradas con esa dimensión financiera se resumirán en un saldo inicial de ganancias retenidas para el valor de dimensión especificado en el campo después de **Cerrar uno**. Por ejemplo, supongamos que todas las transacciones del ejercicio se registraron con la estructura contable de Cuenta principal - Departamento. En la dimensión financiera Departamento de la plantilla se selecciona **Cerrar uno** y se especifica el valor 100. Si el ingreso total de todas las transacciones registradas en los departamentos 200, 300 y 400 es 100 000 $, se creará un saldo de apertura para las ganancias retenidas - 100. Si selecciona **Cerrar uno** y deja el campo de valores de la dimensión financiera en blanco, todas las transacciones se registrarán en las ganancias retenidas con ese valor de dimensión en blanco. 

El proceso de cierre de fin de año no sigue las estructuras contables. Esto se debe a que las estructuras contables pueden cambiar en un ejercicio y no siempre es posible identificar la estructura contable relevante debido a dichos cambios.  Si se crean las transacciones de apertura, los saldos se presentarán con las dimensiones financieras definidas en la plantilla cierre de fin de año. Las entradas de saldo inicial podrían incluir dimensiones financieras que ya no están en la estructura contable actual y combinaciones de segmentos que ya no son válidas en la estructura contable actual. Si su organización desea excluir una dimensión financiera del saldo inicial de ganancias retenidas, establezca la dimensión financiera en **Cerrar uno** y deje el valor de dimensión vacío.

## <a name="run-the-year-end-close-process"></a>Realizar el proceso de cierre de fin de año
Una vez creadas las plantillas de cierre de fin de año, el proceso de cierre de fin de año se inicia eligiendo **Ejecutar ejercicio** en el panel de acciones. Seleccione todas o un subconjunto de entidades jurídicas de la plantilla para las que se va a realizar el cierre de fin de año. Al realizar el cierre de fin de año por primera vez en un ejercicio, probablemente elegirá todas las entidades jurídicas para crear los saldos iniciales de todas las entidades jurídicas. Si realiza el cierre de fin de año de nuevo, puede elegir ejecutar el proceso solo para las entidades jurídicas que han registrado entradas de ajuste. 

Seleccione el ejercicio con el que desee realizar el proceso de cierre de fin de año. Si existe más de un período de cierre para el último período del ejercicio, el campo **Nombre del período** estará disponible para que pueda seleccionar el período de cierre para registrar la transacción de cierre, si la configuración está definida para crear la transacción de cierre. 

Escriba un número de asiento, que puede ser necesario o no en función de la configuración de parámetros de contabilidad general. El mismo número de asiento se usará para todas las entidades jurídicas seleccionadas para el proceso de cierre de fin de año. El número de asiento no se genera con una secuencia numérica. Lo mejor es introducir un número de asiento, incluso si no se requiere. La introducción de un número de asiento hace que sea más fácil encontrar la transacción de apertura en el nuevo ejercicio. Si no se especifica un número de asiento, el asiento estará en blanco en la transacción de apertura. 

Si desea revertir un cierre de fin de año anterior del ejercicio seleccionado, establezca **Deshacer cierre anterior** en **Sí**. El cierre de fin de año se revertirá, pero el proceso se puede volver a realizar en cualquier momento. Si se revierte un cierre de fin de año, la **Fecha de último cierre de fin de año** no estará disponible. 

El proceso de cierre de fin de año se realiza de forma predeterminada en el modo de lotes. Lo mejor es realizar el proceso en el modo de lotes para permitir volver a otras actividades. Una vez finalizado el proceso de cierre, la **Fecha de último cierre de fin de año** se actualizará a la fecha de la sesión.

Para obtener más información, consulte [Cerrar la contabilidad general al final del período](close-general-ledger-at-period-end.md) y [Cerrar el año fiscal](tasks/close-fiscal-year.md).




