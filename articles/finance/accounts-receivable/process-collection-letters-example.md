---
title: Ejemplo de proceso de cartas de cobro
description: Este tema analiza un ejemplo que muestra el proceso de creación, impresión y publicación de cartas de cobranza.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021425"
---
# <a name="process-collection-letters-example"></a>Ejemplo de proceso de cartas de cobro

[!include [banner](../../includes/banner.md)]

Este tema analiza un ejemplo que muestra el proceso de creación, impresión y publicación de cartas de cobranza. El ejemplo se basa en la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** en Crédito y cobros. Utiliza datos de la empresa de demostración USMF y de un nuevo cliente, US-045.

Para empezar, vaya a **Clientes \> Clientes \> Todos los clientes**, seleccione **Nuevo** y luego introduzca la información requerida para crear el cliente US-045.

Cuando haya terminado, siga estos pasos.

1. Vaya a **Crédito y cobros \> Carta de cobro \> Configurar secuencia de letras de cobro** y configure la secuencia de cartas de cobro como se muestra en la siguiente tabla, que está asignada al perfil de contabilización del cliente.

|     Código de la carta de cobro      |     Descripción                           |     Divisa      |     Cuenta principal        |     Cargo en la divisa     |     Mínimo sobre        |     Bloque de días      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     Carta de cobro 1         |     Segunda notificación con cargo        |     USD           |                           |     0,00                  |     0,00                  |     2                 |
|     Carta de cobro 2         |     Segunda notificación con cargo        |     USC           |     403150                |     20.00                 |     10,00                 |     3                 |
|     Cobro                    |     Notificación final con cargo         |     USD           |     403150                |     50.00                 |     100.00                |     15                |

La siguiente ilustración muestra la información que está en la tabla, tal como aparecería en la página **Cartas de cobro**. 

[![Configuración de una secuencia de cartas de cobro](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 Ahora debe establecer los dos parámetros necesarios para este ejemplo.

2. Vaya a **Crédito y cobros \> Configuración \> Parámetros de clientes** y siga estos pasos:

    1. En la pestaña **Cobros**, establezca la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** en **Sí**.
    2. Asegúrese de que el campo **Crear carta de cobro por** está configurado en **Cliente**.

    [![Configuración de parámetros de clientes para cobros de créditos](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Vaya a **Clientes \> Facturas \> Todas las facturas de servicios**, seleccione **Nuevo** y luego siga estos pasos:

    1. En el campo **Cuenta de cliente**, seleccione **US-045**.
    2. En el campo **Fecha de factura**, especifique **1/15/2021**.
    3. En el campo **Fecha de vencimiento**, escriba **16/1/2021**.
    4. En la ficha desplegable **Líneas de factura**, en el campo **Cuenta principal**, introduzca **401100**.
    5. En el campo **Precio unitario**, escriba **500.00**.
    6. Seleccione **Registrar**.

    Ahora debe introducir dos notas de crédito para el cliente.

4. Seleccione **Nueva** y, a continuación, siga estos pasos:

    1. En el campo **Cuenta de cliente**, seleccione **US-045**.
    2. En el campo **Fecha de factura**, especifique **1/15/2021**.
    3. En el campo **Fecha de vencimiento**, escriba **16/1/2021**.
    4. En la ficha desplegable **Líneas de factura**, en el campo **Cuenta principal**, introduzca **401100**.
    5. En el campo **Precio unitario**, escriba **-100,00**.
    6. Seleccione **Registrar**.

5. Repita el paso 4, pero introduzca **-200,00** en el campo **Precio unitario**.
6. Vaya a **Clientes \> Clientes \> Todos los clientes** y seleccione el cliente **US-045**. Luego, en el Panel de acciones, seleccione **Transacciones \> Transacciones** para revisar las transacciones del cliente que registró anteriormente.

    [![Revisión de las transacciones de clientes registrados](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    Ahora debe crear cartas de cobro para el cliente US-045.

7. Vaya a **Crédito y cobros \> Carta de cobro \> Crear cartas de cobro**, y siga estos pasos:

    1. Seleccione las opciones **Factura** y **Nota de crédito** en **Sí**.

        Por defecto, el campo **Carta de cobro** debe establecerse en **Cobro por cliente**.

    2. En el campo **Fecha de carta de cobro**, especifique **19/1/2021**.
    3. En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego, en el campo **Cuenta de cliente**, agregue al cliente **US-045**.
    4. Seleccione **Aceptar**.
    5. Seleccione **Aceptar** para crear cartas de cobro.

8. Vaya a **Crédito y cobros \> Carta de cobro \> Revisar y procesar cartas de cobro**, y siga estos pasos:

    1. Tenga en cuenta que el código de la carta de cobro tanto en el encabezado como en las líneas de transacción es **Carta de cobro 1**, porque esta carta de cobro es la primera carta de cobro de la secuencia. (Para ver las líneas de transacción, es posible que deba seleccionar la ficha desplegable **Transacciones**).

   [![Verificar que aparezca el mismo código de letra de cobro en el encabezado y las líneas](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. En el panel de acciones, seleccione **Registrar**.
    3. En el campo **Fecha de registro**, especifique **19/1/2021**.

    Ahora debe crear cartas de cobro de nuevo para el cliente US-045.

9. Vaya a **Crédito y cobros \> Carta de cobro \> Crear cartas de cobro**, y siga estos pasos:

    1. Seleccione las opciones **Factura** y **Nota de crédito** en **Sí**.

        Por defecto, el campo **Carta de cobro** debe establecerse en **Cobro por cliente**.

    2. En el campo **Fecha de carta de cobro**, especifique **23/1/2021**.
    3. En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego, en el campo **Cuenta de cliente**, agregue al cliente **US-045**.
    4. Seleccione **Aceptar**.
    5. Seleccione **Aceptar** para crear cartas de cobro.

10. Vaya a **Crédito y cobros \> Carta de cobro \> Revisar y procesar cartas de cobro**, y siga estos pasos:

    1. Observe que el código de la carta de cobro en el encabezado es **Carta de cobro 1**. Sin embargo, el código en las líneas de transacción es **Carta de cobro 2**.

   [![Compruebe que aparezcan códigos de letra de cobro diferentes en el encabezado y las líneas](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  Los códigos difieren porque la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** está en **Sí**.

  2. No registre esta carta de cobro.

11. Vaya a **Crédito y cobros \> Configuración \> Parámetros de clientes** y luego, en la pestaña **Cobros**, establezca la opción **Ignorar pagos y notas de crédito al calcular el código de la carta de cobro** en **No**.

    [![Establecimiento de la opción Ignorar pagos y notas de crédito al calcular el código de carta de cobro en No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    Ahora debe crear cartas de cobro de nuevo para el cliente US-045.

12. Vaya a **Crédito y cobros \> Carta de cobro \> Crear cartas de cobro**, y siga estos pasos:

    1. Seleccione las opciones **Factura** y **Nota de crédito** en **Sí**.

        Por defecto, el campo **Carta de cobro** debe establecerse en **Cobro por cliente**.

    2. En el campo **Fecha de carta de cobro**, especifique **23/1/2021**.
    3. En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego, en el campo **Cuenta de cliente**, agregue al cliente **US-045**.
    4. Seleccione **Aceptar**.
    5. Seleccione **Aceptar** para crear cartas de cobro.

13. Vaya a **Créditos y cobros \> Carta de cobro \> Revisar y procesar cartas de cobro** y observe que el código de la carta de cobro tanto en el encabezado como en las líneas de transacción es **Carta de cobro 2**.

    [![Volver a mostrar que aparece el mismo código de letra de cobro en el encabezado y las líneas](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    Los mismos códigos aparecen en ambos lugares porque la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** está en **No**.
