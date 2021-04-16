---
title: Especificar saldos iniciales de nómina
description: El tema se describen los pasos para especificar los saldos iniciales para los códigos de ganancias, las deducciones, las prestaciones y los impuestos.
author: andreabichsel
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9272828fe5d6e0bf131ea66353a0d5c3c7b1c4bd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752159"
---
# <a name="enter-payroll-beginning-balances"></a>Especificar saldos iniciales de nómina

[!include [banner](../../includes/banner.md)]

El tema se describen los pasos para especificar los saldos iniciales para los códigos de ganancias, las deducciones, las prestaciones y los impuestos. Esta información tiene valor para que los socios que transfieran los datos para una nueva implementación de nóminas desde otro sistema. Para prepararse para especificar los saldos iniciales de nóminas, comprobamos la siguiente información:

- Los registros de empleados se especificaron y están disponibles en el sistema
- Los siguientes datos se configuraron y asignaron a los empleados:

    - Ciclos y períodos de pago
    - Códigos de ganancia
    - Impuestos
    - Beneficios y deducciones

- La empresa debe haber elegido una fecha en la que saldos iniciales de nóminas se pueden configurar.
- La información fue recopilada en todas las ganancias, las prestaciones/deducciones, las contribuciones de prestación, los impuestos del empleado y los impuestos del empresario y los importes del año hasta la fecha del sistema heredado.

Cuando vaya a especificar saldos iniciales, considere cómo lo detallados que deben estar los datos. La mayoría de las empresas especifican un importe único, consolidado del año hasta la fecha. Sin embargo, si se necesita más información detallada, los saldos se pueden especificar en incrementos trimestrales. Decidir el nivel de detalle que sea necesario determina cuántos extractos de pago manuales se deben crear para cada trabajador. Para un solo importe del año hasta la fecha, solo una instrucción manual es necesaria para cada empleado. Para hacer esto utilice importes de año hasta la fecha desde el extracto de pago final del sistema anterior como el importe especificado en el nuevo sistema de nóminas.

El siguiente ejemplo muestra cómo puede especificar saldos iniciales de nómina de empleados, incluidos los códigos de ganancias, las prestaciones/deducciones y los impuestos. En un ejemplo del mundo real sólo recibiría un artículo de línea para cada código de ganancias, deducción de prestaciones, contribución de prestaciones impuesto de empleado e impuesto de empresario con el importe especificado siendo el importe del año hasta la fecha. Mediante esta lista de códigos e importes, siga los pasos para crear una ganancia manual y extracto de pago con la contabilidad deshabilitada para traer saldos iniciales para fines de nómina. Se deshabilita la contabilidad ya que no se recomienda registrar este extracto de pago de saldo inicial en la contabilidad general. Esto se ha realizado en el sistema heredado y pasará al nuevo sistema cuando configure los saldos iniciales en la contabilidad general.

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Cómo configurar los códigos de ganancias que se utilizarán en los saldos iniciales de nóminas

Al especificar los saldos iniciales de nómina, asegúrese de que los códigos de ganancias que usará están configurados con la opción “Permitir edición de tasas de extracto de ganancias” habilitada. Esto le permitirá especificar manualmente el importe del sistema heredado. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Crear el extracto de ganancias para que un empleado con saldo inicial

Este paso crea manualmente una instrucción de ganancias para cada trabajador para el último período salarial del sistema heredado, lo que crea las líneas de extracto de ganancias en el nuevo sistema de nóminas. Especifique una línea por código de ganancias y el importe y las horas de del año hasta la fecha. Los pasos de ejemplo son los siguientes:

1. Abra la página **Todos los extractos de ganancias** y haga clic en **Nuevo**.

    Especifique la información siguiente: 

    | Campo      | Valor                 |
    |------------|-----------------------|
    | Trabajador     | Michael Redmond       |
    | Ciclo de pago  | Se                    |
    | Período de pago | 16/6/2017 - 30/6/2017 |

2. En la pestaña **Línea de extracto de ganancias**, especifique lo siguiente:

    Línea 1: Pestaña **Línea de extracto de ganancias**

    | Campo            | Valor       |
    |------------------|-------------|
    | Código de ganancias    | Pago regular |
    | Cantidad         | 1.00        |
    | Índice             | 30,000      |
    | Pestaña Detalles de línea |             |
    | Manual           | (marcado)    |

    Línea 2: Pestaña **Línea de extracto de ganancias**

    | Campo            | Valor    |
    |------------------|----------|
    | Código de ganancias    | Bonificación    |
    | Cantidad         | 1.0000   |
    | Índice             | 4250.00  |
    | Pestaña Detalles de línea |          |
    | Manual           | (marcado) |

    Línea 3: Pestaña **Línea de extracto de ganancias**

    | Campo           | Valor      |
    |-----------------|------------|
    | Código de ganancias   | Comisión |
    | Cantidad        | 1.0000     |
    | Índice            | 1299,00   |
    | Índice            | 1,299.00   |
    | Pestaña Detalles de línea |            |
    | Manual          | (Marcado)   |

    > [!NOTE]
    > Establecer el control deslizante **Manual** en **Sí** en la pestaña **Detalles de línea** para cada línea de extracto de ganancias es fundamental para tener saldos iniciales de nómina especificados para cada trabajador.

3. En el panel **Acción**, haga clic en **Liberar extracto de ganancias** USA-FED-ER-FICA.
4. En el panel **Acción** haga clic en **Extracto de pago** para abrir la página **Generar extractos de pago** y establecer lo siguiente:

    | Campo              | Valor     |
    |--------------------|-----------|
    | Fecha de pago       | 6/30/2017 |
    | Tipo de ejecución de pago   | Manual    |
    | Deshabilitar contabilidad |   Sí     |

    > [!NOTE] 
    > Esto solo está disponible cuando el tipo de procesamiento de pago es manual y si el usuario desea deshabilitar la contabilidad en el procesamiento de pagos.

    Haga clic en **Aceptar** y cierre el **Registro de información**.

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a>¿Por qué el control deslizante Deshabilitar contabilidad tiene que establecerse en Sí cuando se generan extractos de pago?

Establecer el control deslizante en **Sí** impide que las líneas de los extractos de pago se distribuya en la contabilidad general. Los importes de la contabilidad general se actualizaron con anterioridad cuando se introdujeron los saldos de cuenta desde el sistema heredado. Introducir los saldos iniciales para la nómina le permite generar informes que contienen información de años anteriores, así como identificar límites para fines de prestaciones e impuestos.

### <a name="c-create-pay-statements-for-employees"></a>C. Crear extractos de pago para empleados

Tras generar los extractos de pago con saldos iniciales, debe comprobar que los extractos de pago reflejan exactamente los datos de la nómina. También debe actualizar manualmente la información de prestaciones y de impuestos para que coincida con los valores del sistema de nóminas anterior. Después de verificar que los importes del sistema de nóminas anterior se corresponden con los importes de los extractos de pago actuales, debe finalizar los extractos de pago.

1. Abre la página **Todos los extractos de pago**.
2. Resalte el último extracto de pago generado para Michael Redmond
3. Haga clic en **Editar** para abrir la página **Extracto de pago**.
4. Abre la pestaña **Deducciones por prestaciones** y especifique lo siguiente:

    | Campo             | Valor            |
    |-------------------|------------------|
    | Prestación           | Importe de deducción |
    | 401K              | Participar      |
    | Dental            | SubSp            |
    | Gastos de atención del Dep | Participar      |
    | Visión            | SupSp            |

5. En la pestaña **Contribuciones por prestaciones**, especifique lo siguiente:

    | Campo   | Valor               |
    |---------|---------------------|
    | Prestación | Importe de contribución |
    | 401K    | Participar         |
    | Dental  | SubSp               |
    | Visión  | SubSp               |

6. En la pestaña **Deducciones por impuestos**, especifique lo siguiente:

    | Campo           | Valor            |
    |-----------------|------------------|
    | Código de impuesto        | Importe de deducción |
    | USA-FED-ER-FICA | 1600.00          |
    | USA-FED-ER-MEDI | 825.75           |

7. En la pestaña **Contribuciones por impuestos**, especifique lo siguiente:
8. Haga clic en **Calcular**.

    > [!IMPORTANT] 
    > Valide los totales del extracto de pago que coincidan con el año hasta la fecha del sistema heredado para el trabajador. Es posible que desee retener la finalización en el paso siguiente para hacer una validación general de todos los extractos de pago en conjunto. Una vez hecha la validación pase por todos los extractos de pago y complételos.

El mismo proceso se puede realizar en incrementos trimestres si fuera necesario para todos los trimestres anteriores de cada año. Esto solo es necesario si el cliente necesita ver los datos por trimestre sin tener que volver al sistema heredado.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>Si se equivoca especificando los saldos iniciales para un empleado

Es posible invertir y repetir las transacciones. Para invertir la transacción, todo lo que debe hacer es completar los pasos siguientes en la página **Todos los extractos de pago**.

1. Haga clic en **Invertir**.
2. Haga clic en **Sí** cuando aparezca el mensaje “Cuando se invierte este extracto de pago, se crea un extracto de pago de inversión para compensarlo. Ninguno de los extractos de pago se podrá modificar. ¿Quiere invertir este extracto de pago? . 

Una vez que revierta el extracto de pago, puede generar un nuevo extracto de pago para el trabajador desde el extracto de ganancias que creó anteriormente. Asegúrese de corregir las líneas incorrectas del extracto de ganancias antes de generar la nueva instrucción de pago, y luego genere nuevos extractos de sueldo con los importes correctos. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]