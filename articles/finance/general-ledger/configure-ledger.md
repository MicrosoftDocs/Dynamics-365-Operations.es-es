---
title: Configurar libros de contabilidad
description: Este tema proporciona información sobre cómo configurar libros contables para cada entidad jurídica. Incluye información sobre cómo seleccionar las divisas, los calendarios fiscales, el plan de cuentas y las estructuras de cuentas que deben usarse con cada entidad jurídica.
author: kweekley
manager: ''
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: roschlom
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 929ab7ae66a217de836ce49373faed76325c4d3a
ms.sourcegitcommit: ac0a676c91e3053ad7f9432d576c9af3ff98a99a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "4447822"
---
# <a name="configure-ledgers"></a>Configurar libros de contabilidad

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre cómo configurar libros contables para cada entidad jurídica. Incluye información sobre cómo seleccionar las divisas, los calendarios fiscales, el plan de cuentas y las estructuras de cuentas que deben usarse con cada entidad jurídica.

## <a name="selecting-the-chart-of-accounts"></a>Selección del plan de cuentas

Para cada entidad legal en Microsoft Dynamics 365 Finance, se deben configurar los detalles sobre el libro mayor. La página **Libro mayor** le permite seleccionar el plan de cuentas y las estructuras de cuentas que se utilizarán para la entidad jurídica seleccionada. Puede compartir su plan de cuentas y las estructuras de cuentas configurando la página **Libro mayor** de cada entidad jurídica para utilizar el mismo plan de cuentas y las mismas estructuras de cuentas. También puede compartir parte de la configuración de cada entidad jurídica y tener configuraciones específicas en cada entidad jurídica.

Si sus entidades jurídicas deben tener diferentes planes de cuentas o diferentes estructuras de cuentas, la función de anulación de entidad jurídica puede ser útil. Al utilizar el mismo plan de cuentas y estructuras de cuentas para varias entidades jurídicas, y luego administrar las excepciones a través de anulaciones de entidades jurídicas, puede simplificar el mantenimiento con el tiempo.

Para configurar el plan de cuentas de una entidad jurídica, vaya a **Libro mayor \> Configuración del libro mayor \> Libro mayor**. En la página **Libro mayor**, seleccione **Plan de cuentas** y, a continuación, en la lista, seleccione el plan de cuentas a utilizar. Tenga en cuenta que el plan de cuentas no se puede cambiar después de seleccionar un valor y registrar transacciones en la entidad jurídica.

Para obtener más información sobre cómo planificar y configurar el plan de cuentas y las cuentas principales, consulte [Planificar el plan de cuentas](plan-chart-of-accounts.md).

## <a name="selecting-account-structures"></a>Selección de estructuras contables

Cada entidad legal en Dynamics 365 Finance se puede configurar para utilizar una o más estructuras de cuentas. Cada estructura de cuenta define las dimensiones financieras y las combinaciones de cuentas principales y dimensiones financieras que se permitirán cuando se registren las transacciones. Puede utilizar las mismas estructuras de cuentas en más de una entidad jurídica.

Tenga en cuenta que, si tiene varias estructuras de cuentas, puede seleccionar solo estructuras de cuentas que no tengan combinaciones superpuestas de cuentas principales y dimensiones financieras. Por ejemplo, una de sus estructuras de cuenta está configurada para agregar una unidad de negocios para las cuentas principales entre 1000 y 1999. En otra estructura de cuenta, ha agregado una dimensión financiera de departamento para las cuentas principales que comienzan con 1. En este caso, solo se puede agregar una de las estructuras de cuenta en la misma entidad jurídica.

Para configurar estructuras de cuentas para su libro mayor, en la página **Libro mayor**, en la ficha desplegable **Estructuras de cuentas**, seleccione **Agregar**, seleccione una estructura de cuenta en la lista y luego seleccione **Seleccionar**. Es posible que las estructura de las cuentas tarden unos minutos en agregarse y guardarse. Tenga en cuenta que las estructuras de cuentas que seleccione deben estar activas. De lo contrario, los detalles de las estructuras de cuentas no serán efectivos en las entidades jurídicas donde están vinculadas.

Para eliminar una estructura de cuenta, en la página **Libro mayor**, en la ficha desplegable **Estructuras de cuentas**, seleccione **Eliminar**. Tenga en cuenta que, si elimina una estructura de cuenta de su libro mayor, no elimina ninguna transacción que se haya registrado mediante la configuración de esa estructura de cuenta.

Para obtener más información sobre cómo configurar las estructuras de cuentas, consulte [Configurar estructuras de cuentas](configure-account-structures.md).

## <a name="configuring-calendars-for-the-ledger"></a>Configurar calendarios para el libro mayor

Otro componente del libro mayor es el calendario fiscal. Es necesario seleccionar un calendario fiscal para cada entidad jurídica. Puede utilizar el mismo calendario fiscal en más de una entidad jurídica. Cuando selecciona un calendario fiscal para el libro mayor, se realiza una copia. Esta copia se conoce como calendario contable. El calendario contable le permite seleccionar el estado de los períodos y los módulos de cada período.

Para acceder y actualizar el calendario de la entidad jurídica seleccionada, en la página **Libro mayor**, en el panel de acciones, seleccione **Calendario contable**.

Para seleccionar el calendario, seleccione **Calendarios fiscales** y luego seleccione el calendario en la lista. Si cambia el calendario fiscal después de que las transacciones se hayan contabilizado en la entidad jurídica, debe seleccionar **Volver a calcular los períodos contables**. Luego, en el cuadro de diálogo que aparece, puede actualizar los saldos del libro mayor para los períodos de su calendario. Le recomendamos que ejecute el proceso **Volver a calcular los períodos del libro mayor** en modo **Lote** y que lo ejecuta cuando ocurren procesos no críticos en su sistema. Según el número de transacciones y las combinaciones de dimensiones financieras, este proceso puede llevar algún tiempo.

Si no se selecciona un calendario fiscal para una entidad jurídica, recibirá un mensaje de error cuando intente registrar una transacción en esa entidad jurídica.

Para obtener más información, consulte [Calendarios fiscales, ejercicios y períodos.](../budgeting/fiscal-calendars-fiscal-years-periods.md).

## <a name="using-a-balancing-financial-dimension"></a>Uso de una dimensión financiera de equilibrio

Una vez que haya seleccionado el plan de cuentas y haya agregado una o más estructuras de cuentas, puede seleccionar opcionalmente una única dimensión financiera para utilizarla como dimensión financiera de equilibrio. La dimensión que seleccione debe existir en todas las estructuras de cuentas. También debe estar equilibrada en todos los asientos contables. En otras palabras, los débitos y créditos deben ser iguales para la cuenta principal y la dimensión financiera de equilibrio. El sistema crea automáticamente transacciones para equilibrar las entradas, basándose en las cuentas principales que se especifican en los campos **Interunidad: crédito** e **Interunidad: débito** de la página **Cuentas para transacciones automáticas**.

Para obtener más información sobre asientos de saldo, consulte[ Diarios equilibrados para contabilidad interunidad](example-balanced-journals-interunit-accounting.md).

## <a name="configuring-currencies-for-the-ledger"></a>Configurar divisas para el libro mayor

La página **Libro mayor** también se utiliza para controlar y definir las divisas que se utilizarán cuando las transacciones se registren en el libro mayor. Debe especificar la divisa contable, que es la divisa que se utiliza en la columna **Divisa contable** del libro mayor en todos los asientos. Además, en la columna **Divisa de notificación**, opcionalmente puede seleccionar una segunda divisa. Si selecciona una divisa de notificación, todas las transacciones se registrarán en esa divisa en la columna **Divisa de notificación** del libro mayor en todos los asientos.

Si las transacciones se contabilizan en una divisa diferente, el sistema convierte automáticamente el importe de la transacción desde la divisa de las transacciones a la divisa de contabilidad y divisa de notificación en el asiento. En la página **Libro mayor**, en el campo **Tipo de tipo de cambio de divisa contable**, seleccione el tipo de tipo de cambio que está configurado para los tipos de cambio que se deben usar para convertir los valores de la divisa de transacción a la divisa contable del asiento. Si seleccionó una divisa de notificación, también debe establecer el campo **Tipo de cambio de divisa de notificación** para indicar el tipo de cambio que se debe utilizar para convertir los valores de la divisa de la transacción a la divisa de notificación en el asiento.

Si está utilizando la función de presupuestación, también puede establecer el campo **Tipo de cambio presupuestario** para indicar el tipo de cambio que se debe utilizar para convertir las transacciones presupuestarias de una divisa a otra.

Si usa dos divisas, o si usa una sola divisa pero las transacciones se registran en una divisa diferente, debe configurar la ficha desplegable **Cuentas de revalorización de divisa** en la página **Libro mayor**. En esta ficha desplegable, defina las cuentas de pérdidas y ganancias realizadas y no realizadas predeterminadas que se utilizarán de forma predeterminada cuando se registren transacciones, si no se especifica ninguna cuenta en la página **Cuentas de revalorización de divisa**. (La página **Cuentas de revalorización de divisa** se utiliza para configurar diferentes cuentas para las ganancias y pérdidas realizadas y no realizadas para cada divisa).

Las ganancias y pérdidas realizadas son ganancias y pérdidas que se obtienen a partir de transacciones completadas. Se registran en el balance de pérdidas y ganancias. Las ganancias y pérdidas no realizadas son ganancias y pérdidas que se han materializado, pero la transacción no está completa. En otras palabras, ha registrado una factura, por ejemplo, pero la factura aún no se ha liquidado ni pagado. Las ganancias y pérdidas no realizadas se registran en el balance de situación.

Para obtener más información sobre cómo usar dos divisas, consulte [Divisa doble](dual-currency.md).
