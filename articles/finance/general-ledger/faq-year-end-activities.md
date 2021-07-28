---
title: Preguntas frecuentes sobre las actividades de fin de año
description: Este tema se ha resumido para ayudar con las actividades de cierre de fin de año.
author: kweekley
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9ceacdbe36cc946b64d13b3faff2b3b1ca59afbb
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345485"
---
# <a name="year-end-activities-faq"></a>Preguntas frecuentes sobre las actividades de fin de año 

[!include [banner](../includes/banner.md)]

Este tema se ha resumido para ayudar con las actividades de cierre de fin de año. La información de este tema se centra principalmente en dudas sobre actividades de cierre de fin de año para Contabilidad general y Proveedores.

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Contabilidad general: ¿cómo puedo saber que estamos llevando a cabo el cierre de fin de año y no deshaciendo el cierre de fin de año?
Hemos visto organizaciones que intentas llevar a cabo el cierre de fin de año, pero, en su lugar, estaban deshaciéndolo. Si el cierre de fin de año está acabando muy rápido o no produce saldos de apertura, valide el ajuste **Deshacer cierre anterior** en **Cierre de fin de año** (**Contabilidad general > Cierre de período > Cierre de fin de año > Ejecutar cierre fiscal**). 

[![Ejecutar el cierre de fin de año frente a deshacer el cierre de fin de año.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Si la selección **Deshacer cierre anterior** se ha establecido en **Sí**, se estará deshaciendo el cierre de año anterior. Al deshacer, se eliminarán todos los saldos de cierre y apertura, como si nunca se hubiera ejecutado el cierre de fin de año. Los asientos se eliminan. El cierre de fin de año no se volverá a ejecutar de forma automática. Debe iniciar el proceso de nuevo, pero esta vez cambie **Deshacer cierre anterior** a **No**. 

> [!NOTE]
> La entrada de saldo de cierre se crea de forma opcional en el año que se está cerrando. Esto solo sucede si el parámetro de Contabilidad general **Crear el asiento de cierre al lanzar el proceso de transacciones de cierre / apertura** es **Sí**. Siempre se crea la entrada de saldo de apertura porque es el saldo inicial del siguiente año.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Contabilidad general: ¿cuál es la diferencia entre los parámetros de Contabilidad general Deshacer y Eliminar con respecto al cierre de fin de año?
Puede haber confusión sobre la diferencia entre el parámetro **Deshacer cierre anterior**, que se encuentra en el cuadro de diálogo **Cierre de fin de año**, y el parámetro **Eliminar el asiento de cierre y apertura y generar uno nuevo** en Contabilidad general (**Contabilidad general > Cierre de período > Cierre de fin de año > Ejecutar cierre fiscal**).  

[![Diferencia entre los parámetros de Contabilidad general Deshacer y Eliminar con respecto al cierre de fin de año.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Seleccione **Deshacer cierre anterior** en el menú de diálogo desplegable al ejecutar el proceso de cierre de fin de año para eliminar todos los movimientos de saldo de cierre y de apertura, como si el cierre de fin de año nunca se hubiera ejecutado. Los asientos se eliminarán. El cierre de fin de año no se volverá a ejecutar de forma automática. Para ejecutar el cierre de fin de año, debe iniciar este proceso nuevamente, pero esta vez cambie **Deshacer cierre anterior** a **No** (**Contabilidad general > Configuración de contabilidad general > Parámetros de contabilidad general**). 

[![Configuración de los parámetros de contabilidad general.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

El parámetro **Eliminar el asiento de cierre y apertura y generar uno nuevo** en Contabilidad general se usa solo cuando se ejecuta (no al deshacer) el cierre de fin de año (la selección **Deshacer cierre anterior** está establecida en **No**). Si ese parámetro se establece en **Sí**, todas las entradas de saldo de cierre y de apertura se eliminarán y el cierre de fin de año se ejecutará de nuevo. Este proceso se utiliza cuando la organización desea que todas las transacciones, incluidos los ajustes desde el último cierre de año, se registren en una sola entrada contable para las entradas de saldo de cierre y de apertura. 

Si esta opción se establece en **No**, se mantienen todas las entradas de saldo de cierre y de apertura. No se eliminan. En su lugar, se creará una nueva entrada de saldo de cierre y apertura solo para las transacciones delta o nuevas registradas desde el último cierre de fin de año para ese ejercicio.  

> [!NOTE]
> La entrada de saldo de cierre se crea en el año que se está cerrando. Esto solo sucede si el parámetro de Contabilidad general **Crear el asiento de cierre al lanzar el proceso de transacciones de cierre / apertura** es **Sí**. Siempre se crea la entrada de saldo de apertura porque es el saldo inicial del siguiente año. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Contabilidad general: ¿qué se puede cambiar para mejorar el rendimiento del procesamiento del fin de año? 
Puede llevar a cabo diferentes cambios para mejorar el rendimiento del cierre de fin de año. Le recomendamos que analice estos cambios sugeridos para considerar si el cambio es apropiado para su organización.  

### <a name="dimension-sets"></a>Conjuntos de dimensiones
Al ejecutar el cierre de fin de año, se vuelve a crear el saldo de cada conjunto de dimensiones, lo que tiene un impacto directo en el rendimiento. Algunas organizaciones crean conjuntos de dimensiones de forma innecesaria porque se usaron en un momento concreto o podrían usarse en algún momento.  Estos conjuntos de dimensiones innecesarios aún se recrean durante el cierre de fin de año, lo que ralentiza el proceso. Invierta tiempo en evaluar sus conjuntos de dimensiones y eliminar los que no necesite.

Los conjuntos de dimensiones innecesarios también afectan al trabajo por lotes **BudgetDimensionFocusInitializeBalance** (**Contabilidad general > Plan de cuentas > Dimensiones > Conjuntos de dimensiones financieras**).

[![Conjuntos de dimensiones financieras.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuración de la plantilla del cierre de fin de año
La plantilla del cierre de fin de año permite a las organizaciones seleccionar el nivel de la dimensión financiera que deben mantener a la hora de transferir los saldos de pérdidas y ganancias a las ganancias retenidas. La configuración permite que una organización mantenga las dimensiones financieras detalladas (**Cerrar todo**) al mover los saldos a ganancias retenidas o elegir resumir los importes en un valor de dimensión única (**Cerrar uno**). Esto se puede definir para cada dimensión financiera. Para obtener más información sobre estas configuraciones, consulte el tema [Cierre de fin de año](year-end-close.md).

Le recomendamos que evalúe los requisitos de su organización y, si es posible, cierre tantas dimensiones como sea posible mediante la opción de fin de año **Cerrar uno** para mejorar el rendimiento. Al cerrar a un valor de dimensión única (que también puede ser un valor en blanco), el sistema calcula menos detalles a la hora de determinar los saldos para los asientos contables de ganancias retenidas.

### <a name="10013-update-or-later"></a>Actualización 10.0.13 o posterior
Si ha actualizado a la versión 10.0.13 o posterior desde la última vez que su organización ejecutó un cierre de fin de año, este proceso podría tardar más debido a la [implementación de la función HashV2](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2). (El término *hash* se refiere a un campo que se calcula a partir de otros campos de cadena. La API para calcular el valor hash GUID se actualizó para mejorar la seguridad). Para acelerar el proceso de cierre de fin de año, recomendamos volver a crear los saldos de los conjuntos de dimensiones antes de ejecutar el cierre de fin de año. Si ya ha vuelto a crear los saldos del conjunto de dimensiones después de actualizar a la versión 10.0.13, no es necesario volver a crearlos.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Contabilidad general: ¿qué hace el Cierre de período: cierre de fin de año?
 
[![Cierre de período, cierre de fin de año.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Mejoras de rendimiento para volver a crear conjuntos de dimensiones financieras (nueva característica)
Una nueva característica agregada en la versión 10.0.16 mejora el rendimiento de los procesos de cierre y consolidación de fin de año. La característica se llama: Mejoras de rendimiento para volver a crear conjuntos de dimensiones financieras. Esta función cambia la forma en que se reconstruyen los conjuntos de dimensiones para que se vuelvan a crear solo durante un plazo de tiempo relevante. En las versiones anteriores, los conjuntos de dimensiones se volvían a crear para todas las fechas. Por ejemplo, si está cerrando el año 2020, el sistema solo volverá a crear los saldos de las transacciones dentro del ejercicio de 2020. Si está ejecutando la consolidación para un rango de fechas del 1 de noviembre de 2020 al 30 de noviembre de 2020, el sistema solo volverá a crear los saldos para ese tramo.

Esta función se considera un cambio importante y deberá habilitarla mediante el espacio de trabajo **Administración de características**.
 
[![Cierre de fin de año.](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Proveedores: ¿qué cambios se han realizado para respaldar la declaración de informe 1099 de fin de año para 2020?

Se han agregado dos nuevas características regulatorias para los cambios de fin de año de informe 1099 en 2020. La primera característica, **Aplicar cambios a los formularios 1099-NEC y 1099-MISC para 2020**, se lanzó a mediados de año como característica obligatoria. Su objetivo es garantizar que se pueda hacer un seguimiento de los datos transaccionales de informe 1099 para el año 2020 para el nuevo formulario 1099-NEC. Esta característica agregó los campos de IRPF que se necesitan para que el nuevo 1099-NEC sea compatible y actualizó los campos de 1099-MISC. Esta actualización también mejoró los datos del registro del proveedor para la información de la casilla 1099. 

La segunda característica regulatoria, **Impuesto 1099 actualizado para la ley tributaria de 2020**, contiene los siguientes cambios.

- 1099-OID: la Agencia tributaria ha transformado el formulario para su uso continuo.
   - El tercer y cuarto dígito del año de notificación se deben completar cuando se imprime. Use el tercer y cuarto dígito del campo **Año de notificación** de **Opciones de impresión de IRPF**. 

- 1099-NEC: un nuevo formulario para 2020. Esto registra la compensación de los no empleados. 

-   1099-MISC: debido a la creación del formulario 1099-NEC, la Agencia tributaria ha revisado el formulario 1099-MISC y ha reorganizado los números de casilla para notificar ciertos ingresos.
Los cambios en la declaración de ingresos y los números de casilla del formulario se enumeran a continuación.
   - El contribuyente realizó ventas directas de 5000 $ o más (marque la casilla) en la casilla 7.
   - En la casilla 9 se notifican los ingresos obtenidos por los seguros agrícolas.
   - Los ingresos brutos a un abogado se notifican en la casilla 10.
   - Los aplazamientos de la sección 409A se notifican en la casilla 12.
   - Los ingresos por compensación diferida no habilitada se notifican en la casilla 14.
   - Las casillas 15, 16 y 17 sirven para notificar sobre los impuestos estatales retenidos, el número de identificación estatal y el importe de ingresos obtenidos en el estado, respectivamente.

- 1099-DIV o 1099-INT no han sufrido cambios en 2020.

- Tramitación electrónica: el formato ha cambiado para adaptarse al nuevo formulario NEC y los cambios a la casilla MISC descritos anteriormente. Para obtener información específica sobre los requisitos de tramitación electrónica, consulte [Publicación de la agencia tributaria 1220](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Proveedores: IRPF - ¿cómo cambio la casilla 1099 y los valores de un proveedor que no estaba haciendo un seguimiento de la información relacionada con el IRPF durante todo el año?
Utilice la función de Actualizar IRPF (**Proveedores > Proveedores > Todos los proveedores > Seleccionar un proveedor > pestaña Proveedor en la cinta de opciones > Actualizar IRPF**) para pasar por transacciones de facturas pagadas previamente para reasignar los datos relacionados con IRPF de manera adecuada de acuerdo con la configuración en la pestaña **IRPF** en la página **Proveedor**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>¿Puedo ejecutar Actualizar IRPF para todos mis proveedores a la vez?
No. La rutina de Actualizar IRPF se lleva a cabo en un solo proveedor al mismo tiempo. Si su organización necesita este requisito, vote por la idea llamada [Proceso por lotes para la actualización de los datos de IRPF del proveedor](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Proveedores: IRPF - "Volver a calcular los importes existentes de la declaración de IRPF" frente a "Actualizar todo" en la función Actualizar IRPF.
La casilla **Volver a calcular los importes existentes de la declaración de IRPF** restablecerá el importe de la declaración de IRPF a los valores pagados totales cuando se use junto a la casilla **Actualizar todo**. 

[![Transacciones de IRPF: antes de ejecutar la rutina de actualización.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

La casilla **Volver a calcular los importes existentes de la declaración de IRPF** solo es útil cuando hay valores parciales en la declaración de IRPF en la factura o si se ha modificado en el formulario de IRPF. Por ejemplo, suponga que tiene una factura con valor de 1000 $, pero el usuario introduce manualmente un importe de declaración de IRPF en la factura de 500 $.

[![Transacciones de IRPF: marcar Actualizar todo y Volver a calcular los importes existentes de la declaración de IRPF.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Cuando se pague, 500 $ será el importe de IRPF que se pague. Si vuelve a calcular los importes, el sistema cambiará el importe de IRPF a 1000 $, que es el total que se ha pagado.

[![Transacciones de IRPF: después de ejecutar la rutina de IRPF.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Proveedores: IRPF - Crear manualmente transacciones de IRPF
Es posible que una organización deba crear manualmente transacciones de IRPF que no estén asociadas con una factura. Puede agregar transacciones de IRPF manuales si va a **Proveedores > Tareas periódicas > IRPF > Liquidación del proveedor para IRPF**. Seleccione el botón **Transacciones manuales de IRPF**. 

Las transacciones de IRPF creadas de forma manual no se actualizan con el proceso **Actualizar todo** or el proceso **Volver a calcular los importes de 1099 existentes** en la función **Actualizar IRPF**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Proveedores: IRPF - ¿Dynamics 365 Finance es compatible con el formulario 1099? 

Dynamics 365 Finance no imprime el formulario 1096 de resumen anual y transmisión de declaraciones de información de EE. UU.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Proveedores: IRPF - ¿hay alguna nueva función compatible con el informe 1099 para el sector público? 
Se ha agregado una nueva característica para el sector público, **Actualizar información de informe 1099 por cuenta principal**, que puede habilitar en el espacio de trabajo **Administración de características**. Esta función le permite asociar los valores de informe 1099 a un proveedor por la cuenta principal en la distribución contable, en lugar de la cuenta predeterminada en el registro del proveedor.

Para obtener más información, consulte [Configurar proveedores para informes 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
