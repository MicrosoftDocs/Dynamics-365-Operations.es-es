---
title: "Cierre de fin de año"
description: "Este tema describe la configuración necesaria y los pasos para ejecutar el proceso de cierre de fin de año de contabilidad general."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Cierre de fin de año

Este tema describe la configuración necesaria y los pasos para ejecutar el proceso de cierre de fin de año de contabilidad general. 

Al final de un ejercicio, debe ejecutar el proceso de fin de año de cierre para transferir saldos de apertura al nuevo año. La mayoría de las organizaciones decidir con varias veces de fin de año del proceso de cierre. Estar la primera vez obtener los saldos movidos el nuevo ejercicio. El cierre de fin de año se podrá ejecutar de nuevo, tantas veces es necesario, para mover los saldos de ajustar entradas al nuevo ejercicio. 

Durante el proceso de fin de año de cierre, existen dos tipos de transacciones creadas posibles. Una transacción de apertura se genera y siempre se usará para crear los saldos de apertura en el nuevo ejercicio. La transacción de apertura muestre los saldos de la cuenta contable del balance de situación en el nuevo ejercicio y los saldos de los saldos de pérdidas y ganancias de la cuenta contable en la cuenta contable de ganancias retenidas en el nuevo ejercicio. La transacción de cierre se crea opcionalmente para derribar los saldos de las cuentas de pérdidas y ganancias para cero en el ejercicio que se cerrará.

## <a name="prepare-to-run-the-year-end-close"></a>Preparar para ejecutar el cierre de fin de año
Antes de ejecutar el proceso de fin de año de cierre, validar los valores para: 

En la página de **Cuenta principal**:

-   Validar ** tipo de cuenta principal ** se define correctamente para cada cuenta principal. El tipo de cuenta principal para determinar si el saldo de la cuenta principal se mostrará como saldo de apertura o cerrado en ganancias retenidas en la transacción de apertura.
-   ** Cuenta de apertura ** el campo se puede utilizar para transferir el saldo de la cuenta principal a una nueva cuenta principal durante el cierre de fin de año. La nueva cuenta principal se especifica en ** cuenta de apertura ** el campo. Esto normalmente se usará para las cuentas principales del balance de situación en la que se desactiva la cuenta principal y una nueva cuenta principal se utiliza para el nuevo ejercicio.

En ** parámetros de contabilidad general ** la página en ** cierre del ejercicio **:

-   ** Eliminar cercana de transacciones del año ** se usa la opción para especificar si la transacción de apertura generada por el sistema de un cierre anterior de cierre de ejercicio se eliminará cuando el cierre de fin de año se ejecute de nuevo. Si esta opción se establece ** Sí **, se eliminará la transacción de apertura anterior y una nueva transacción de apertura se crea en función del saldo actual. Si se establece esta opción ** ningún **, la transacción de apertura anterior y una transacción de apertura adicional se crea para mover los saldos delanteros de ajustar las transacciones registradas después del cierre anterior de final de año.
-   ** Cree las transacciones de cierre durante la transferencia ** se usa la opción de crear transacciones de cierre en el ejercicio que se cerrará para reunir los saldos de las cuentas de pérdidas y ganancias a cero. Si esta opción se establece ** Sí **, se crea la transacción de apertura y la transacción de cierre. Si se establece esta opción ** ningún **, sólo la transacción de apertura se crea al ejercicio siguiente para transferir los saldos. Permanece los saldos de cuenta de pérdidas y ganancias al final del ejercicio.
-   ** Determinado Estado del ejercicio a permanentemente cerrado ** se usa la opción de establecer el ejercicio a un estado cerrado permanentemente. Use esta configuración con precaución, ya que todos los períodos con un estado cerrado permanentemente no se puede reabrir, lo que permite evitar que los ajustes pueda realizarse el ejercicio. Es una práctica recomendada establecer esto ** ningún **.
-   ** El número de asiento se debe completar ** se usa la opción de definir si un número de asiento se requiere al ejecutar el proceso de fin de año de cierre. Es una práctica recomendada requerir un número de asiento para identificar fácilmente la transacción de apertura.

En ** calendario fiscal ** la página:

-   El siguiente ejercicio debe existir antes de ejecutar el cierre de fin de año. Los el ejercicio siguiente para crear los saldos iniciales del período de apertura.

En ** calendario de contabilidad ** la página:

-   Opcional: Cada período fiscal para el ejercicio que se cerrará se puede liquidar ** ** en espera para evitar que las nuevas transacciones que se van a especificadas. Al ajustar entradas se identifican, los períodos en espera se puede volver a abrir para ajustar registrar entradas, incluso si el proceso de fin de año de cierre se ha ejecutado ya.

## <a name="define-year-end-close-templates"></a>Permite definir las plantillas del cierre de fin de año
Tras configurar el sistema, el proceso de fin de año de cierre se puede ejecutar. En ** final de año próximo ** la página, una plantilla se puede definir para el grupo de entidades jurídicas para las el proceso de fin de año de cierre sea ejecutado. La plantilla se volverá a utilizar en cada cierre de fin de año, pero se puede modificar si los cambios de la organización. 

Primero, defina ** nombre de grupo ** para la plantilla, y seleccione el calendario fiscal. El nombre de grupo debe identificar el grupo de entidades jurídicas incluidas.  Por ejemplo, las plantillas se pueden configurar según la geografía, con grupos independientes creados para las entidades jurídicas norteamericanas, las personas jurídicas de EMEA, y las entidades jurídicas de APAC. 

A continuación, las entidades jurídicas se puede agregar a la plantilla. Las entidades jurídicas pueden agregar seleccionando una jerarquía organizativa o seleccionando las entidades jurídicas. Si se selecciona una jerarquía organizativa, sólo agregar en las entidades jurídicas dentro de la jerarquía que utilizan el calendario fiscal seleccionado a la plantilla. Si usa las entidades jurídicas para agregar a la plantilla, sólo las entidades jurídicas con el mismo calendario fiscal se pueden agregar. Se requiere el mismo calendario fiscal porque el cierre de fin de año es ejecutado seleccionando un ejercicio, que puede variar calendario del calendario. 

Después de agregar a las entidades jurídicas, defina las ganancias retenidas que la cuenta principal para cada entidad jurídica. ** Fecha de cierre de final del año pasado ** el campo se actualizará cada vez que el cierre de fin de año se ejecuta para la entidad jurídica. 

** Dimensión financiera ** la ficha para definir las dimensiones financieras se utilizarán en la transacción de apertura. Tenga en cuenta que los valores que está definiendo sólo son relevantes a la entidad jurídica seleccionada en ** las entidades jurídicas ** la cuadrícula. Se repetirá la configuración para cada entidad jurídica en la cuadrícula. 

** Dimensiones del balance de situación de la transferencia ** se utiliza para definir si las dimensiones financieras de las transacciones registradas en las cuentas de balance de situación se deben actualizar en la transacción de apertura. Es una práctica recomendada establecer esta opción ** Sí **. ** Dimensiones de pérdidas y ganancias de la transferencia ** se usa para definir qué dimensiones financieras de transacciones registradas en la cuenta de pérdidas y ganancias se transferirá a la cuenta principal de ganancias retenidas. Primero, identifique las dimensiones financieras relevantes en la entidad jurídica seleccionada. Incluyen dimensiones financieras enviada con durante el año, incluso si la dimensión financiera no es parte de una estructura contable activa. A continuación, para definir cada dimensión como ** o cierre escoja ** o ** cierre todos **.  El valor predeterminado es ** cierre todos ** mantenimiento, los valores de la dimensión financiera original de transacciones registradas y las utiliza para crear los saldos de apertura para la cuenta de ganancias retenidas. Los saldos iniciales separados de ganancias retenidas se crearán para cada combinación única de valores de la dimensión financiera. Si solo ** cierre ** está seleccionada, todas las transacciones registradas con esa dimensión financiera se resumen en saldos iniciales de ganancias retenidas por el valor de dimensión especificado en el campo después de haber ** cierre escoja **. Por ejemplo, supongamos que todas las transacciones por el año fiscal se han registrado con la estructura contable de la cuenta principal - Departamento. En la dimensión financiera departamento en la plantilla, ** solo cierre ** se selecciona y 100 es el valor especificado. Si el ingreso total de todas las transacciones registradas en los Departamento 200, 300 y 400, es $100,000, un saldo de apertura son creados para las ganancias retenidas - 100. Si selecciona ** cierre escoja ** y deje el campo vacío de valores de la dimensión financiera, todas las transacciones enviarán a las ganancias retenidas con ese valor de dimensión que está en blanco. 

El proceso de fin de año de cierre no se adhiera a las estructuras contables. Esto se debe a que las estructuras contables pueden cambiar en un año fiscal y no siempre es posible identificar la estructura contable relevante debido a dichos cambios.  Cuando se crean las transacciones de apertura, los saldos se mostrarán con las dimensiones financieras definidas en la plantilla cierre de fin de año. Las entradas de saldo inicial podrían incluir dimensiones financieras ya no en las combinaciones de la estructura y el segmento de cuenta actual no están válidas en la estructura de cuenta actual. Si su organización desea excluir una dimensión financiera para saldos iniciales de ganancias mantendrán, establecer las dimensiones financieras sean ** cierre escoja ** y deje el valor de dimensión vacío.

## <a name="run-the-year-end-close-process"></a>Permite ejecutar el proceso de fin de año de cierre
Una vez creadas las plantillas cierre de fin de año, el proceso de fin de año de cierre es iniciado eligiendo ** ejercicio de la ejecución ** en el panel de acciones. Seleccionar todas las o un subconjunto entidades jurídicas de la plantilla para que ejecute el cierre de fin de año. Al realizar el cierre de fin de año por primera vez en un ejercicio, se elegirá probablemente todas las entidades jurídicas para crear los saldos iniciales para todas las entidades jurídicas. Si se ejecuta el cierre de fin de año de nuevo, puede elegir para ejecutar el proceso para las entidades jurídicas para las entradas ajustando se enviaron. 

Seleccione el ejercicio con el que desee ejecutar el proceso de fin de año de cierre. Si más de un período de cierre existe para el último período del ejercicio, ** nombre del período ** el campo estará disponible para que pueda seleccionar que período de cierre para registrar la transacción de cierre, si la configuración se define para crear la transacción de cierre. 

Escriba un número de asiento, que o no puede que se requiera, en función de la configuración de parámetros de contabilidad general. El mismo número de asiento se usará para todas las entidades jurídicas seleccionadas para el proceso de fin de año de cierre. El número de asiento no se genera mediante una secuencia numérica. Es una práctica recomendada especificar un número de asiento, incluso si no se requiere. Si se especifica un número de asiento más fácil encontrar la transacción de apertura en el nuevo ejercicio. Si un número de asiento no se especifica el asiento, estará en blanco para la transacción de apertura. 

Si desea invertir un cierre de ejercicio anterior cierre para el ejercicio seleccionado, conjunto ** desmarca el cierre anterior ** ** Sí **. El cierre de fin de año se invertirá, pero el proceso se puede volver a ejecutar en cualquier momento. Si se invierte un cierre de fin de año, ** fecha de cierre de final del año pasado ** no esté disponible. 

Los valores predeterminados de fin de año del proceso de cierre a ejecutarse en modo de lotes. Es una práctica recomendada ejecutar el proceso en modo de lotes, permitir al usuario que vuelva a otras actividades. Una vez finalizado el proceso de fin de año de cierre, ** fecha de cierre de final del año pasado ** se actualizará con la fecha de la sesión.

Para obtener más información, consulte [cierra la contabilidad general en el período terminado close-general-ledger-at-period-end.md] ().


