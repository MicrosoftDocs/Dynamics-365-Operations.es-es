---
title: Automatizar propuestas de pago a proveedores
description: Este tema explica cómo las organizaciones que pagan a los proveedores con programación periódica pueden automatizar el proceso de generación de propuestas de pago a proveedores.
author: kweekley
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 63f2d3dc55799efefaedb10134edb219fa8588e0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003587"
---
# <a name="automate-vendor-payment-proposals"></a>Automatizar propuestas de pago a proveedores

[!include [banner](../includes/banner.md)]

Las organizaciones que pagan a los proveedores con programación periódica pueden automatizar ahora el proceso de generación de propuestas de pago a proveedores. Las automatizaciones de propuestas de pago a proveedores definen los siguientes detalles:

- Cuando se ejecutan las propuestas de pago
- ¿Qué criterios se utilizan para seleccionar las facturas que se deben pagar?
- En qué diario de pago a proveedores se guardan los pagos resultantes

Las automatizaciones de propuestas de pago no contabilizan automáticamente los pagos. Por lo tanto, puede continuar utilizando los procesos de validación y flujo de trabajo que utiliza actualmente para aprobar los pagos que se crean.

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Definir la aparición de propuestas de pago a proveedores

Las automatizaciones de propuestas de pago a proveedores utilizan el marco de automatización de procesos. Diferentes procesos de negocios utilizan este marco para definir la periodicidad de un proceso seleccionado. Para propuestas de pago de proveedores, se puede acceder a la automatización en **Proveedores \> Configuración de pago \> Automatización de procesos**.

Primero, use la opción de automatización **Crear nuevo proceso** y seleccione **Propuesta de pago a proveedor**. Luego, un asistente le guía a través del proceso de configuración de la propuesta de pago a proveedor.

## <a name="general-page"></a>Página general

En la página **General** del asistente, introduzca el nombre de la propuesta de pago del proveedor que está creando. Por ejemplo, si paga a todos los proveedores nacionales con cheque los lunes, introduzca un nombre descriptivo como **Cheque\_nacional**. El nombre que introduzca se muestra en la vista semanal de automatización de procesos en el espacio de trabajo **Pagos a proveedores**.

A continuación, defina el propietario del diario de pagos que se crea. El propietario suele ser el empleado de pago a proveedores (AP), que es responsable del diario de pagos después de su creación.

Las configuraciones restantes de la página son genéricas y se utilizan para definir el patrón de ocurrencia para esta versión de propuesta de pago a proveedor. Por ejemplo, si una ocurrencia es para pagos de cheques en lunes, puede definirla para que se ejecute semanalmente, y puede seleccionar el lunes como el día de la semana en que se ejecuta. También puede introducir una hora de programación temprana, como las 2:00 a.m., para que la automatización del proceso se complete antes del inicio del siguiente día hábil.

Es importante que comprenda que está utilizando el asistente para definir cuándo se procesa la propuesta de pago a proveedor. No está definiendo cuándo se generan, imprimen ni publican los pagos al proveedor. En la vista semanal, la automatización del proceso para las propuestas de pago a proveedor aparecerá en los días seleccionados en el patrón de ocurrencia.

Para obtener más información sobre los otros campos de la página **General**, consulte la documentación de automatización de procesos.

## <a name="vendor-payment-proposal-page"></a>Página de propuesta de pago a proveedor

La siguiente página del asistente es la página **Propuesta de pago a proveedor**. Se utiliza para definir los criterios para seleccionar las facturas de proveedores que se deben pagar. En general, las mismas opciones se encuentran en la propuesta de pago del diario de pagos al proveedor. Sin embargo, hay algunas excepciones. Por ejemplo, todas las fechas de esta página deben definirse como fechas relativas, porque la fecha de la propuesta de pago cambia cada vez que se ejecuta la propuesta.

### <a name="journal-name"></a>Nombre del diario

El campo **Nombre de diario** define el nombre del diario en el que se crean los pagos al proveedor. Los resultados de la automatización de la propuesta de pago al proveedor crearán pagos en el diario definido, pero el diario no se contabiliza.

### <a name="from-date-and-to-date"></a>Fecha "Desde" y fecha "Hasta"

En lugar de definir una fecha "Desde" y una fecha "Hasta" para seleccionar facturas basadas en la fecha de vencimiento o la fecha de descuento en efectivo, debe utilizar la opción **Definir criterios de la fecha Desde** y el campo **Ajuste de número de días para la fecha Hasta** para definir la fecha "Hasta". No existe un concepto de fecha "Desde" en las automatizaciones de propuestas de pago.

Por defecto, la opción **Definir los criterios de la fecha Hasta** está establecida en **No**. Si utiliza este valor predeterminado, el proceso seleccionará todas las facturas para el pago cuando se ejecute el proceso, porque no se ha definido una fecha "Hasta".

Si configura la opción **Definir criterios de fecha Hasta** en **Sí**, utilice el campo **Ajuste de número de días para fecha Hasta** para definir la fecha en que se seleccionan las facturas como el número especificado de días antes o después de la fecha en que se ejecuta el proceso. El número puede ser positivo, negativo o 0 (cero). Luego, el sistema pagará facturas en las que las fechas de vencimiento, o las fechas de descuento en efectivo, son el número especificado de días antes o después de la fecha en que se ejecuta el proceso. Por ejemplo, para todas las facturas que vencen el viernes o antes, la serie de pagos crea pagos a todos los proveedores mediante cheque el miércoles. En este caso, establezca el campo **Ajuste de número de días para la fecha Hasta** en **2**. Cuando se produce la propuesta de pago el miércoles 25 de marzo, todas las facturas que tengan una fecha de vencimiento o una fecha de descuento en efectivo del 27 de marzo o anterior se seleccionarán para el pago.

### <a name="minimum-payment-date"></a>Fecha de pago mínimo

La fecha de pago mínima define la fecha más temprana que se usa al crear pagos. Primero debe configurar la opción **Definir criterios mínimos de fecha de pago** como **Sí**. Esta configuración le permite utilizar la funcionalidad de fecha de pago mínima. Si se configura esta opción en **Sí**, utilice el campo **Ajuste de número de días para fecha mínima** para definir la fecha de pago mínima como el número especificado de días antes o después de la fecha en que se ejecuta el proceso. El número puede ser positivo, negativo o 0 (cero). Por ejemplo, la serie de pagos genera pagos el miércoles para incluir todos los pagos que tengan una fecha de pago mínima del lunes anterior. En este caso, establezca el campo **Ajuste de número de días para fecha de pago mínima** en **-2**.

Aquí hay un ejemplo que muestra cómo funcionan juntos los campos para la fecha "Hasta" y la fecha mínima de pago . La automatización de la propuesta de pago está configurada para ejecutarse el miércoles. El campo **Ajuste de número de días para la fecha Hasta** se establece en **1** para definir la fecha "Hasta" en función de la fecha de vencimiento. El campo **Ajuste de número de días para fecha de pago mínima** se establece en **-2**. Si la automatización del proceso de pago comienza el miércoles 25 de marzo, todas las facturas que vencen el 26 de marzo o antes se incluirán en la propuesta de pago. Las propuestas de pago se generarán de la siguiente manera:

- Todas las facturas que vencen el 23 de marzo o antes tendrán una fecha de pago del 23 de marzo.
- Las facturas que vencen el 24 de marzo tendrán una fecha de pago del 24 de marzo.
- Las facturas que vencen el 25 de marzo tendrán una fecha de pago del 25 de marzo.
- Las facturas que vencen el 26 de marzo tendrán una fecha de pago del 26 de marzo.

### <a name="summarized-payment-date"></a>Fecha de pago resumida

La fecha de pago resumido se utiliza únicamente cuando el campo **Periodo** se establece en **Total** para el método de pago de las facturas. Si el campo **Período** se establece en **Total** para sus métodos de pago, debe establecer la opción **Definir criterios resumidos de fecha de pago** en **Sí**. Si se configura esta opción en **Sí**, utilice el campo **Ajuste de número de días para fecha de pago resumido** para definir la fecha de pago resumido como el número especificado de días antes o después de la fecha en que se ejecuta el proceso. El número puede ser positivo, negativo o 0 (cero). Por ejemplo, la serie genera pagos el miércoles, y la empresa quiere crear un pago resumido el miércoles. En este caso, establezca el campo **Ajuste de número de días para fecha de pago resumido** en **0**.

### <a name="records-to-include"></a>Registros que incluir

Las opciones de filtro aún se pueden definir para la propuesta de pago. Si se define un filtro, los criterios de filtro no se muestran en la página del asistente. Sin embargo, se pueden ver reabriendo el filtro.

Los campos restantes para la propuesta funcionan igual que para la propuesta de pago en el diario de pagos a proveedores. Para obtener información sobre los otros campos, consulte [Crear pagos de proveedores utilizando una propuesta de pago](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Algunos campos específicos de país/región y algunos campos del sector público, aún no están disponibles en las automatizaciones de propuestas de pago a proveedores.

Le recomendamos que evalúe si la automatización será beneficiosa para su organización, en función de sus requisitos.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>Ver los resultados de una automatización de propuesta de pago a proveedor

Después de crear la serie de automatización de propuestas de pago de proveedor, las ocurrencias de cada pago se muestran en la vista semanal de automatización de procesos. Para pagos de proveedores, la vista semanal de automatización de procesos se ha agregado al espacio de trabajo **Pagos a proveedores** y a la página **Automatización de procesos**.

[![Vista semanal de automatización de procesos en el espacio de trabajo de pagos a proveedores](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

La vista semanal de automatización de procesos en el espacio de trabajo **Pagos a proveedores** muestra solo las automatizaciones de propuestas de pago a proveedores. Muestra todas las ocurrencias de pagos de la semana actual, para todas las entidades jurídicas para las que el usuario que inició sesión tiene permisos de seguridad. Por ejemplo, si el empleado de pagos de AP es responsable de los pagos en las empresas USMF y USSI, verá las ocurrencias de la automatización de la propuesta de pago a proveedor para esas dos empresas, pero no para otras empresas.

[![Vista semanal de automatización de procesos para las empresas USMF y USSI](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Cada ocurrencia muestra la empresa en la que se creó o se creará el diario de pagos. Si los pagos se crean mediante pagos centralizados, la empresa que se muestra es la empresa en la que se crearán los pagos. La ocurrencia no necesariamente muestra qué facturas de las empresas se pagarán.

El nombre de cada ocurrencia también se muestra para ayudar a identificar la propuesta de pago.

Además, se muestra el estado de cada ocurrencia. Se usan los siguientes estados:

- **Programada**: la propuesta de pago está programada, pero aún no se ha ejecutado.
- **Error**: la propuesta de pago se ejecutó, pero ocurrió un error. Puede ver los errores seleccionando el botón **Ver resultados**.
- **Terminado**: la propuesta de pago se ha ejecutado correctamente. Puede ver los pagos seleccionando el vínculo **Ver pagos**. Este vínculo abre el diario de pagos creado por la ocurrencia.

Después de crear los pagos, puede ver los importes de los pagos en el diario. Los importes se muestran en las divisas de las transacciones. Por ejemplo, si el diario de pagos contiene pagos tanto en dólares estadounidenses como en dólares canadienses, se muestran los pagos totales para cada moneda. 

El diario de pagos se puede eliminar después de crearlo mediante la automatización del proceso. Si un pago se elimina por completo, se producen los siguientes eventos:

- El estado de la automatización de procesos para la semana sigue siendo **Completado**.
- El proceso elimina los totales de pago y el vínculo **Ver pagos** se reemplaza con un botón **Ver resultados**.
- Cuando ve los resultados, recibe un mensaje que indica que se eliminó el diario original.

Después de eliminar un pago, las facturas se abrirán nuevamente para el pago. Se puede crear una nueva ocurrencia para pagar nuevamente las facturas.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Editar una automatización de propuesta de pago a proveedor

El marco de automatización de procesos le permite editar el pago, la serie y las ocurrencias que se crean para la propuesta de pago. La serie se puede editar desde la página **Automatización de procesos** o la vista semanal de automatización de procesos. Por ejemplo, si el gerente de AP decide generar todos los cheques para proveedores nacionales el miércoles en lugar del lunes, puede encontrar una ocurrencia en la vista semanal y seleccionar **Ver/Editar: serie**. Si edita una serie, el sistema le solicita que especifique si el cambio debe realizarse en todas las ocurrencias existentes o solo en las nuevas. Las ocurrencias históricas que ya tienen un estado de **Completado** o que terminaron con estado de **Error** no se cambiarán.

También puede agregar una nueva ocurrencia o cambiar una existente. Por ejemplo, la próxima ocurrencia de la propuesta de pago está programada para ejecutarse el miércoles 1 de enero, pero esta fecha es festiva. Puede cambiar la ocurrencia desde la vista semanal de automatización de procesos o la página **Automatización de procesos**. Se abre una página que muestra los detalles de la programación y los criterios de propuesta de pago. Aquí puede editar la hora y fecha programadas. También puede editar los criterios de propuesta de pago, si se requieren cambios. Por ejemplo, si cambia la fecha programada de la ocurrencia del pago del 1 de enero al 2 de enero, es posible que también desee cambiar las fechas relativas para la fecha "Hasta".

También puede deshabilitar una ocurrencia o una serie. Para deshabilitar una ocurrencia y suspender el procesamiento, selecciónela en la vista semanal de automatización de procesos y luego seleccione **Deshabilitar**. Puede deshabilitar una serie en la página **Automatización de procesos**.

## <a name="security-for-payment-proposal-automations"></a>Seguridad de automatizaciones de propuestas de pago

Se han agregado los siguientes deberes y privilegios para las automatizaciones de propuestas de pago a proveedor. Estos deberes y privilegios son las configuraciones de seguridad predeterminadas, pero se pueden cambiar según los requisitos de su organización. Por ejemplo, si no solo el administrador de AP sino también el empleado de pagos de AP pueden editar y crear periodicidad de programación, asigne el derecho **Mantener horarios programados** a la persona con el rol de empleado de pagos de AP.

| Deber                              | Función                                                                       | Privilegios |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Mantener series de programación          | Administrador de proveedores                                                   | Este derecho otorga derechos para crear y mantener las series de automatización de propuestas de pago y las ocurrencias a través de los siguientes privilegios:<ul><li>Mantener ocurrencias de programación</li><li>Mantener series de programación</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Ver la vista semanal de ocurrencias</li></ul> |
| Consultar ocurrencias de programación | Empleado de pagos a proveedores, empleado de pago centralizado a proveedores | Este derecho otorga derechos para ver las ocurrencias de automatización de propuestas de pago a través de los siguientes privilegios:<ul><li>Ver ocurrencias de programación</li><li>Ver la vista semanal de ocurrencias</li></ul> |
| Consultar serie de horarios      | None                                                                       | Este derecho otorga derechos para ver las opciones de las series y ocurrencias a través de los siguientes privilegios:<ul><li>Ver ocurrencias de programación</li><li>Ver la página de lista de ocurrencias</li><li>Ver la vista semanal de ocurrencias</li></ul>|
| Mantener ocurrencias de programación     | None                                                                       | Este derecho otorga los derechos para crear y mantener una ocurrencia a través de los siguientes privilegios:<ul><li>Mantener ocurrencias de programación</li><li>Ver la vista semanal de ocurrencias</li></ul> |
