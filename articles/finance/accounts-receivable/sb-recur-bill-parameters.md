---
title: Parámetros de facturación periódica del contrato
description: Este artículo explica cómo configurar los valores predeterminados para programaciones de facturación que se crean en Facturación periódica del contrato. También explica cómo crear grupos de programación de facturación.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: cb60253f3cbb8c991ef2e106abdb1c685bf22171
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903345"
---
# <a name="recurring-contract-billing-parameters"></a>Parámetros de facturación periódica del contrato

Utilice la página **Parámetros de facturación periódica del contrato** para configurar los valores predeterminados para programaciones de facturación que se crean en Facturación periódica del contrato. Todas las programaciones de facturación que cree utilizarán inicialmente estos valores predeterminados. Sin embargo, puede cambiar los valores para cada programación de facturación según lo requiera.

## <a name="general-tab"></a>Pestaña General

1. En la página **Parámetros de facturación periódica del contrato**, en la pestaña **General**, en el campo **Grupo de programación de facturación**, seleccione un grupo de programación de facturación. Para obtener información sobre cómo configurar grupos de programación de facturación, consulte la sección [Configurar grupos de de programación de facturación](#set-up-billing-schedule-groups) más adelante en este artículo.
2. En el campo **Tipo de terminación**, seleccione cómo se calcula la factura final cuando finaliza una programación de facturación:

    - **Ajustar programación** – Corte la programación de facturación en la fecha de finalización, cambie el estado de la programación a **Última facturación** y ajuste la programación de aplazamiento asociada revirtiendo el importe que ya no debe ser reconocido. Si la fecha de inicio de facturación es posterior a la fecha de baja, se eliminan los períodos de facturación restantes.
    - **Factura restante** – Agregue cualquier importe restante en la programación de facturación al período de baja y cambie el estado de la programación a **Última facturación** y actualice la programación de aplazamiento. Si la fecha de inicio de facturación es posterior a la fecha de baja, el monto total de todos los períodos de facturación restantes se agrega al período de facturación y los períodos de facturación restantes se eliminan.
    - **Sin ajuste** – Finalice la programación de facturación en la fecha de finalización. No se realizan ajustes en la programación de facturación.

3. En el campo **Tipo de programación único**, seleccione **Ninguno** para especificar que los clientes están limitados a una única programación de facturación. Seleccione **Por cliente** o **Por usuario final** para especificar que los clientes están limitados a una programación única.
4. Establezca la opción **Alinear con mes** como **Sí** para alinear la programación de facturación con el final de un mes cuando se cree o actualice una programación de facturación. Establézcalo como **No** para usar fechas incrementales.
5. Seleccione la opción **Prorratear períodos parciales** como **Sí** para asignar importes de facturación en función del número de días del período. Configúrelo como **No** para tener una cantidad igual en cada período de facturación, independientemente del número de días.
6. Si configura la opción **Prorratear períodos parciales** como **Sí**, seleccione el campo **Método de prorrateo** como **Diario** para distribuir los importes en función del número de días del período. Configúrelo como **Mensual** para tener una cantidad igual todos los meses.
7. Especifique si las programaciones de facturación recién creadas están en espera de forma predeterminada.

    > [!NOTE]
    > Para eliminar la espera en un programa de facturación, el usuario debe ser parte de un grupo de usuarios. Seleccione **Eliminar anulación de grupo de usuarios de retención** para configurar un grupo de usuarios donde esté habilitada la opción **Permitir quitar retención**.

8. En el campo **Tipo de transacción de factura**, seleccione el tipo de transacción de factura predeterminado para las nuevas programaciones de facturación.
9. Seleccione la opción **Alinear aplazamiento con facturación** como **Sí** para alinear la programación de aplazamiento correspondiente para que use las mismas fechas que la programación de facturación. Establézcalo como **No** para usar fechas diferentes.
10. Si está utilizando la característica de división de ingresos, configure la opción **Crear automáticamente división de ingresos** como **Sí** cuando se agregan artículos a una programación de facturación. La casilla **División de ingresos** se seleccionará automáticamente en la línea de programación de facturación si el artículo está configurado como artículo de división de ingresos. Establezca la opción como **No** si desea seleccionar manualmente la casilla **División de ingresos**.
11. Configure los campos para la creación de pedidos de ventas:

    - Las facturas se pueden consolidar por período, cliente o artículo. Puede establecer cualquier combinación de los valores **Sí** y **No**. Las facturas también se pueden dividir por grupo de artículos.
    - Las siguientes opciones de registro están disponibles para facturas:

        - **Crear pedido de ventas** - Cree solo el pedido de ventas.
        - **Mostrar Registrar factura** – Facture el pedido de ventas y abra una página donde puede registrar manualmente la factura.
        - **Crear factura de texto libre** – Seleccione esta opción si está utilizando facturas de texto libre.
        - **Registrar factura automáticamente** – Facture el pedido de ventas y regístrelo automáticamente.

    - Seleccione la opción **Agregar fechas de facturación a la descripción de artículos** como **Sí** para agregar una descripción que incluya la fecha de inicio y la fecha de finalización de la facturación.
    - Seleccione la opción **Excluir consumo cero** como **Sí** para excluir líneas de programación de facturación que no tienen consumo. Configúrela como **No** para incluir esas líneas en el pedido de ventas.
    - Seleccione la opción **No imprimir artículos secundarios** como **Sí** si no desea imprimir los artículos secundarios de una división de ingresos en el pedido de ventas. En la factura solo se mostrará el artículo principal. Si el importe neto de los artículos secundarios (ocultos) es una suma distinta de cero, el importe neto de la línea principal muestra un resumen de las líneas secundarias. Establezca la opción como **No** para imprimir todos los artículos secundarios debajo del artículo principal en la factura de venta.

12. Configure los campos para soporte técnico y renovaciones:

    - Seleccione la opción **Habilitar automáticamente soporte y renovación** como **Sí** para usar automáticamente la característica de soporte técnico y renovación en un pedido de ventas.
    - En el campo **Nivel de soporte y renovación** seleccione el nivel de soporte y renovación predeterminado.
    - En el campo **Cantidad de soporte y renovación** especifique la cantidad de soporte y renovación.
    - En el campo **Fecha de inicio de renovación y soporte predeterminado**, especifique la fecha que desea usar como fecha de inicio predeterminada para soporte y renovaciones:

        - **Fecha de transacción**: use la fecha de transacción como fecha de inicio.
        - **Comienzo del mes actual**: use el primer día del mes actual como fecha de inicio.
        - **Comienzo del próximo mes**: use el primer día del próximo mes como fecha de inicio. Si la fecha de la transacción es el primer día, se utilizará el primer día del mes en curso.
        - **Regla de 15** – Utilice el primer día del mes actual como fecha de inicio si la fecha de la transacción está entre el primero y el quince del mes. Si la fecha de la transacción es el decimosexto día o posterior del próximo mes, use el primer día del próximo mes como fecha de inicio.

    - Seleccione la opción **Incluir descuento en el cálculo** como **Sí** para incluir el importe del descuento en el importe de soporte o renovación. Configúrelo como **No** para excluir el importe del descuento.
    - En los campos **Frecuencia de soporte** y **Frecuencia de renovación**, seleccione la frecuencia que se usará cuando se agreguen artículos de soporte y renovación a una programación de facturación: **Diaria**, **Mensual**, **Trimestral**, **Semestral** o **Anual**.
    - Seleccione la opción **Alinear por grupo de artículos** como **Sí** para alinear las fechas de inicio y finalización de los artículos nuevos con los artículos existentes, según el grupo de artículos.
    - Seleccione la opción **Alinear con el siguiente periodo no facturado** como **Sí** para determinar la fecha de alineación para un artículo de renovación en función de la fecha del siguiente período no facturado después de que comience la renovación.
    - Seleccione la opción **Copiar número de serie** como **Sí** para copiar el número de serie del artículo desde la línea de pedido de ventas inicial hasta la línea de programación de facturación correspondiente.

13. Si está utilizando remisión a una instancia superior en la programación de facturación, seleccione el método que se utiliza para el cálculo del índice de precios al consumidor.
14. Seleccione la opción **Hacer seguimiento de cambio de precio** como **Sí** si desea un registro de los cambios de precios en las líneas de programación de facturación. Si una línea de programación de facturación se cambia manualmente de estándar a plana y se ingresa un nuevo precio, la información de auditoría se rastrea en la línea de programación de facturación. Establezca la opción en **No** si no desea realizar un seguimiento de estos cambios.
15. Especifique si los registros se filtran por fecha de inicio o fecha de finalización de forma predeterminada en la página **Generar factura**.
16. Si utiliza la característica **Ingresos sin facturar**, especifique las opciones que se utilizan:

    - Seleccione la opción **Registrar los diarios generales automáticamente** como **Sí** si desea que el diario general se cree y se registre al mismo tiempo. Establézcalo como **No** si desea crear el diario general y luego registrarlo manualmente.
    - En el campo **Nombre predeterminado de diario**, seleccione el nombre predeterminado del diario que se usará cuando se cree el diario general.
    - En el campo **Método de no facturado a corto plazo**, seleccione el método no facturado a corto plazo, si está utilizando uno. Si selecciona **Ninguno**, la funcionalidad a corto plazo no se utilizará con ingresos no facturados. Seleccione **Períodos de propagación** para utilizar siempre 12 meses o **Año fijo** para utilizar el año fiscal restante.

17. Especifique las opciones que se utilizan cuando finaliza una programación de facturación y sus líneas:

    - **Emitir crédito** – Cree una nota de crédito al dar de baja un programa de facturación o una línea de programa de facturación.
    - **Ajuste de crédito** – Cree un ajuste de crédito para un programa de facturación al dar de baja una línea. El ajuste de crédito aparece en un período de facturación futuro para el programa de facturación. El ajuste de crédito ajustará el importe de la factura para el próximo período de facturación hasta que el crédito haya terminado de aplicarse al programa de facturación.
    - **Sin crédito** – No cree un ajuste de crédito o una nota de crédito al dar de baja un programa de facturación o una línea de programa de facturación. Esta opción está disponible solo cuando utiliza la opción **Sin ajuste** para dar de baja una programación de facturación.

## <a name="sequence-number-tab"></a>Pestaña Número de secuencia

Utilice la pestaña **Número de secuencia** de la página **Parámetros de facturación periódica del contrato** para establecer el valor predeterminado para números de programación de facturación. Los valores predeterminados se configuran en la página **Secuencias numéricas** (**Administración de la organización \> Secuencias numéricas \> Secuencias numéricas**).

## <a name="set-up-billing-schedule-groups"></a>Configurar grupos de programación de facturación

Utilice la página **Grupo de programación de facturación** para crear un grupo de programación de facturación para Facturación periódica del contrato. Cuando se crea una nueva programación de facturación y se le aplica un grupo de programación de facturación, los valores que se definen en la página **Grupo de programación de facturación** se ingresan como valores predeterminados para la programación de facturación. Puede cambiar cualquiera de los valores predeterminados para la programación de facturación específica que cree. Puede configurar varios grupos de programación de facturación y luego asignar uno de ellos como grupo de programación de facturación predeterminado en la página **Parámetros de facturación periódica del contrato**.

Para crear un grupo de programación de facturación para Facturación periódica del contrato, siga estos pasos.

1. En la página **Grupo de programación de facturación**, seleccione **Nuevo** para crear un grupo de programación de facturación.
2. En el campo **Grupo de programación de facturación**, escriba un identificador único.
3. En el campo **Descripción**, escriba una descripción.
4. En el campo **Frecuencia de facturación**, especifique con qué frecuencia se factura la programación de facturación a un cliente: **Una vez**, **Diario**, **Mensual**, **Trimestral**, **Semestral** o **Anual**.
5. En el campo **Intervalo de facturación**, escriba un intervalo de facturación. Por ejemplo, establezca el campo **Frecuencia de facturación** como **Mensual** y el campo **Intervalo de facturación** como **2** para facturar cada dos meses.
6. En el campo **Método de cálculo de precios**, seleccione el método de cálculo de precios para los artículos de la programación de facturación:

    - **Estándar** – Calcule el precio unitario en función de la cantidad total ingresada y use el precio estándar de la página **Productos emitidos** en Gestión de información de productos.
    - **Plano** – Aplique un precio fijo que se ingresa en la línea de programación de facturación.
    - **Nivel** – Calcule el precio unitario utilizando una cantidad fija en diferentes tramos de precios. Cada nivel debe completarse antes de pasar al siguiente tramo de precios.
    - **Nivel plano** – Calcule el precio unitario utilizando una cantidad fija e importes de precio total para diferentes tramos de precios. El precio que se cobra en un período de facturación utiliza el precio total que corresponde al nivel donde existe la cantidad de facturación.

7. En el campo **Tipo de artículo**, seleccione el tipo de artículo para el grupo de facturación:

    - **Estándar** – Seleccione este valor si la cantidad es estática.
    - **Uso** – Seleccione este valor para artículos medidos o de consumo. Si selecciona este valor, configure el campo **Opción de lectura de uso** como **Lectura** para ingresar el valor (lectura) para un período de facturación en un medidor o dispositivo. El valor consumido se calculará en función del período de facturación anterior y la lectura actual que ingrese.
    - **Hito** – Seleccione este valor para utilizar la funcionalidad de facturación por hitos. Si selecciona este valor, en el campo **Plantilla de hitos**, seleccione la plantilla de hitos si está usando una.
    - **Consumo** – Seleccione este valor para ingresar el valor que se consume durante un período de facturación.

8. Establezdca la opción **Factura por separado** como **Sí** para crear una combinación de facturas consolidadas y facturas separadas para el mismo cliente. Por ejemplo, un cliente tiene cinco programaciones de facturación. Tres de ellos se consolidarán en una sola factura, pero cada una de las otras dos requiere una factura por separado. Establezca la opción como **No** para crear solo una factura consolidada para el cliente.
9. Establezca la opción **Renovar automáticamente** como **Sí** para renovar automáticamente la programación de facturación periódica para el siguiente período de facturación cuando se cree la factura. Establézcalo como **No** para renovar manualmente la programación de facturación. En el campo **Líneas a agregar por renovación**, especifique cuántas líneas se agregarán para cada renovación.
10. Seleccione la opción **Remisión a una instancia superior** como **Sí** para aplicar *escaladas* (aumentos de precio) a las programaciones de facturación asociadas con este grupo de programación de facturación.
