---
title: Preguntas frecuentes sobre las actividades de fin de ejercicio
description: Este artículo enumera las preguntas que pueden surgir al cerrar un ejercicio y las respuestas que pueden ayudar con las actividades de cierre de fin de ejercicio.
author: moaamer
ms.date: 11/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a25f20c320b905a2cdd3091e76e3c5e73f1a845a
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752760"
---
# <a name="year-end-activities-faq"></a>Preguntas frecuentes sobre las actividades de fin de ejercicio 

[!include [banner](../includes/banner.md)]

Este artículo enumera las preguntas que pueden surgir al cerrar un ejercicio y las respuestas que pueden ayudar con las actividades de cierre de fin de ejercicio. La información de este artículo se centra principalmente en dudas sobre actividades de cierre de fin de ejercicio para contabilidad general y Proveedores.

## <a name="general-ledger-year-end-enhancements"></a>Mejoras de fin de año de contabilidad general 
La versión 10.0.20 introdujo una mejora de cierre de fin de ejercicio, que está habilitada de forma predeterminada a partir de la versión 10.0.25. Si su organización utiliza una versión anterior a la 10.0.25, le recomendamos habilitar esta característica antes de comenzar el proceso de cierre de fin de ejercicio. Para poder usar esta característica, debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo Administración de características para comprobar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

 - Módulo: Contabilidad general
 - Nombre de la característica: mejoras de fin de año de contabilidad general

La configuración de las plantillas de cierre de fin de año se ha pasado a una nueva página de configuración, **Configuración de plantilla de cierre de fin de ejercicio**. La página de cierre de fin de ejercicio actual cambiará de manera similar a la revalorización de divisa extranjera de contabilidad general, donde se muestra una lista cada vez que se ejecuta o revierte el cierre de fin de ejercicio. Un gerente de contabilidad puede iniciar el cierre de fin de ejercicio desde la nueva página. 

Para revertir el cierre de fin de ejercicio, seleccione el año fiscal más reciente para la entidad legal apropiada y elija el botón **Revertir cierre de fin de ejercicio**. La reversión eliminará los asientos contables del cierre de fin de ejercicio anterior y no volverá a ejecutar el cierre de fin de ejercicio automáticamente. 

Puede volver a ejecutar el cierre de fin de ejercicio reiniciando el proceso para el ejercicio y la entidad jurídica. El proceso continuará usando la configuración del parámetro Contabilidad laboral para determinar si la repetición del cierre de fin de ejercicio tendrá en cuenta solo las transacciones nuevas o modificadas, o revertirá completamente el cierre anterior, volviendo a ejecutar el proceso para todas las transacciones.  

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Contabilidad general: ¿Cómo puedo saber que estamos llevando a cabo el cierre de fin de ejercicio y no deshaciendo el cierre de fin de ejercicio?
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
La plantilla del cierre de fin de año permite a las organizaciones seleccionar el nivel de la dimensión financiera que deben mantener a la hora de transferir los saldos de pérdidas y ganancias a las ganancias retenidas. La configuración permite que una organización mantenga las dimensiones financieras detalladas (**Cerrar todo**) al mover los saldos a ganancias retenidas o elegir resumir los importes en un valor de dimensión única (**Cerrar uno**). Esto se puede definir para cada dimensión financiera. Para obtener más información sobre estas configuraciones, consulte el artículo [Cierre de fin de año](year-end-close.md).

Le recomendamos que evalúe los requisitos de su organización y, si es posible, cierre tantas dimensiones como sea posible mediante la opción de fin de año **Cerrar uno** para mejorar el rendimiento. Al cerrar a un valor de dimensión única (que también puede ser un valor en blanco), el sistema calcula menos detalles a la hora de determinar los saldos para los asientos contables de ganancias retenidas.

## <a name="degenerate-dimensions"></a>Dimensiones degeneradas

Una dimensión degenerada proporciona poca o ninguna reutilización por sí misma ni en combinación con otras dimensiones. Existen dos tipos de dimensiones degeneradas. El primer tipo es una dimensión que es degenerada de forma individual. Por lo general, este tipo de dimensión degenerada aparecerá únicamente en una sola transacción o en pequeños conjuntos de transacciones. El segundo tipo es una dimensión que se pasa a ser degenerada en combinación con una o más dimensiones adicionales que exhiben el mismo potencial, según las posibles permutaciones que pueden generarse. Una dimensión degenerada puede tener un impacto significativo en el rendimiento del proceso de cierre de fin de año. Para minimizar los problemas de rendimiento, defina todas las dimensiones degeneradas como **Cierre único** en la configuración de cierre de fin de ejercicio, como se describe en la sección anterior.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Contabilidad general: ¿Qué hacen el cierre de período y el cierre de fin de ejercicio?
 
[![Cierre de período, cierre de fin de ejercicio.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Mejoras de rendimiento para volver a crear conjuntos de dimensiones financieras
Una nueva característica agregada en la versión 10.0.16 mejora el rendimiento de los procesos de cierre y consolidación de fin de ejercicio. La característica se llama: Mejoras de rendimiento para volver a crear conjuntos de dimensiones financieras. Esta función cambia la forma en que se reconstruyen los conjuntos de dimensiones para que se vuelvan a crear solo durante un plazo de tiempo relevante. En las versiones anteriores, los conjuntos de dimensiones se volvían a crear para todas las fechas. Por ejemplo, si está cerrando el año 2020, el sistema solo volverá a crear los saldos de las transacciones dentro del ejercicio de 2020. Si está ejecutando la consolidación para un intervalo de fechas del 1 de noviembre de 2020 al 30 de noviembre de 2020, el sistema solo volverá a crear los saldos para dicho intervalo.

Para poder usar esta característica, debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo Administración de características para comprobar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:
 
- Módulo: Contabilidad general
- Nombre de la característica: Mejoras de rendimiento para volver a crear conjuntos de dimensiones financieras

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Proveedores: ¿Qué cambios se han realizado para admitir el informe de fin de ejercicio 1099 para 2022?

#### <a name="update-to-all-1099-forms"></a>Actualizar a todos los formularios 1099
Se han realizado los siguientes cambios en todos los formularios 1099 para el año fiscal 2022:

  - En 2021, el año se fijó en los formularios 1099. A partir de 2022, el año se completa con el informe. 

#### <a name="1099-misc"></a>1099-MISC
Se han realizado las siguientes actualizaciones en el formulario 1099-MISC para el año fiscal 2022:

 - Casilla 13: ahora indica el requisito de presentación de la Ley de Cumplimiento Tributario de Cuentas Extranjeras (Foreign Account Tax Compliance Act, FATCA). 
 - Casilla 14: ahora se usa para declarar los pagos excesivos por desvinculación laboral dorados. 
 - Casilla 15: ahora se usa para declarar el pago bajo planes de compensación diferida no calificada (NQDC). 
 - Casilla 16: ahora se usa para declarar los impuestos retenidos estatales.
 - Casilla 17: ahora se usa para informar del número de estado del pagador.
 - Casilla 18: ahora se usa para declarar los ingresos estatales. 

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Proveedores: ¿Qué cambios se han realizado para admitir los informes de fin de ejercicio 1099 para 2021?

En 2021, los formularios DIV, NEC y MISC se modificaron ligeramente y se agregaron algunas casillas adicionales.

#### <a name="div-new-box2e-2f"></a>DIV: nuevas casillas 2e, 2f
 
- Casilla 2e. Muestra la parte del importe de la casilla 1a que es la ganancia de la sección 897 atribuible a la disposición de intereses de bienes raíces de EE. UU. (USRPI).  
- Casilla 2f. Muestra la parte del importe de la casilla 2a que es la ganancia de la sección 897 atribuible a la disposición de USRPI. Tenga en cuenta que las casillas 2e y 2f se aplican solo a las personas y entidades extranjeras cuyos ingresos mantienen su carácter cuando se transfieren o distribuyen a sus propietarios o beneficiarios extranjeros directos o indirectos. Por lo general, se trata como si estuviera efectivamente conectado a un comercio o negocio de dentro de Estados Unidos. Consulte las instrucciones para su declaración de impuestos. 
 
#### <a name="nec-new-box-2"></a>NEC: nueva casilla 2 
 
Si se marca la casilla 2, informe de los productos de consumo por un total de 5000 $ o más que se le vendieron para reventa, en una compraventa, en depósito o comisión u otra base. En general, declare cualquier ingreso de su venta de estos productos en el Anexo C (Formulario 1040). 
 
Mientras tanto, se cambia el tamaño del formulario de NEC. Durante la impresión, existen tres formularios por página. 
 
#### <a name="misc-new-box-11"></a>MISC: nueva casilla 11 
 
La casilla 11 muestra el importe pagado por la compra de pescado para reventa de cualquier persona dedicada al comercio o negocio de la captura de pescado. Consulte las instrucciones de su declaración de impuestos para declarar este ingreso. 
 
#### <a name="electronic-filing"></a>Tramitación electrónica 
Para obtener información sobre la tramitación electrónica, consulte [Publicación de los requisitos de presentación electrónica](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Actualizar las especificaciones de formato y los diseños de registro para el informe electrónico de 2021 
- Sec. 2 Registro de emisor “A”. 
- Códigos de importe: posición de campo aumentada 28-45, longitud a 18. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>Sec. 2 Registro de emisor “A”, para declarar pagos en el formulario 1099-DIV: 
- Tipo de importe: se agregó la Sección 897 de dividendos ordinarios y se agregó el código de importe H. 
- Tipo de importe: se agregó la Sección 897 de ganancias de capital y se agregó el código de importe J. 
 
#### <a name="sec-3-payee-b-record"></a>Sec. 3 Registro de beneficiario “B” 
- Registros de información general: se actualizó la tercera viñeta de los campos 16 a 18 de importe de pago. 
- Campo de título del pago H: se actualizó la posición del campo 247-258, el título del campo, la longitud y la descripción general del campo. 
- Campo de título del pago J: se actualizó la posición del campo 259-270, el título del campo, la longitud y la descripción general del campo. 
- Campo en blanco actualizado a la posición de campo 271-286. 
- Indicador de país extranjero actualizado a la posición de campo 287. 
- Se actualizó el campo Línea de nombre del primer beneficiario a la posición de campo 288-327. 
- Se actualizó el campo Línea de nombre del segundo beneficiario a la posición de campo 328-367. 
- Posiciones de diseño de registro, formulario 1099-MISC: se eliminó la posición de campo 548 y el indicador de requisito de presentación FATCA del título del campo. 
- Posiciones de diseño de registros, formulario 1099-NEC: 545-546 actualizado a en blanco, campo 547 actualizado a Indicador de ventas directas, Longitud y descripción, y campo Comentarios 548-722 actualizado a en blanco. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>Sec. 4 Fin del registro “C” del Emisor 
- Campo de título del pago H: se actualizó la posición del campo 304-321, el título del campo, la longitud y la descripción general del campo. 
- Campo de título del pago J: se actualizó la posición del campo 322-339, el título del campo, la longitud y la descripción general del campo. 
- Título del campo 340-499: longitud actualizada a 160. 
 
#### <a name="sec-5-state-totals-k-record"></a>Sec. 5 Registro “K” de totales de 5 estados 
- Campo de título del pago H: se actualizó la posición del campo 304-321, el título del campo, la longitud y la descripción general del campo. 
- Campo de título del pago J: se actualizó la posición del campo 322-339, el título del campo, la longitud y la descripción general del campo. 
- Título del campo 340-499: longitud actualizada a 160.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Proveedores: 1099, ¿Cómo cambio la casilla 1099 y los valores de un proveedor que no estaba haciendo un seguimiento de la información relacionada con el 1099 durante todo el año?
Utilice la función de Actualizar 1099 (**Proveedores > Proveedores > Todos los proveedores > Seleccionar un proveedor > pestaña Proveedor en la cinta de opciones > Actualizar 1099**) para pasar por transacciones de facturas pagadas previamente para reasignar los datos relacionados con 1099 de manera adecuada de acuerdo con la configuración en la pestaña **1099** en la página **Proveedor**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>¿Puedo ejecutar Actualizar 1099 para todos mis proveedores a la vez?
No. La rutina de Actualizar 1099 se lleva a cabo en un solo proveedor al mismo tiempo. Si su organización necesita este requisito, vote por la idea llamada [Proceso por lotes para la actualización de los datos del 1099 del proveedor](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Proveedores: 1099, volver a calcular los importes existentes de la declaración de 1099 frente a Actualizar todo en la función Actualizar 1099.
La casilla **Volver a calcular los importes existentes de la declaración 1099** restablecerá el importe de la declaración 1099 a los valores pagados totales cuando se use junto a la casilla **Actualizar todo**. 

[![Transacciones del 1099: antes de ejecutar la rutina de actualización.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

La casilla **Volver a calcular los importes existentes de la declaración de 1099** solo es útil cuando hay valores parciales en la declaración 1099 en la factura o si se ha modificado en el formulario de 1099. Por ejemplo, suponga que tiene una factura con valor de 1000 $, pero el usuario introduce manualmente un importe de declaración de 1099 en la factura de 500 $.

[![Transacciones del 1099: marcar Actualizar todo y Volver a calcular los importes existentes de la declaración de 1099.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Cuando se pague, 500 $ será el importe de 1099 que se pague. Si vuelve a calcular los importes, el sistema cambiará el importe del 1099 a 1000 $, que es el total que se ha pagado.

[![Transacciones del 1099: después de ejecutar la rutina de 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Proveedores: 1099 - Crear manualmente transacciones del 1099
Es posible que una organización deba crear manualmente transacciones del 1099 que no estén asociadas con una factura. Puede agregar transacciones del 1099 manuales si va a **Proveedores > Tareas periódicas > 1099 > Liquidación del proveedor para 1099**. Seleccione el botón **Transacciones manuales de 1099**. 

Las transacciones del 1099 creadas de forma manual no se actualizan con el proceso **Actualizar todo** o el proceso **Volver a calcular los importes de 1099 existentes** en la función **Actualizar 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Proveedores: 1099 - ¿es Dynamics 365 Finance compatible con el formulario 1099? 

Dynamics 365 Finance no imprime el formulario 1096 de resumen anual y transmisión de declaraciones de información de EE. UU.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Proveedores: 1099 - ¿hay alguna nueva función compatible con el informe 1099 para el sector público? 
Se ha agregado una nueva característica para el sector público, **Actualizar información de informe 1099 por cuenta principal**, que puede habilitar en el espacio de trabajo **Administración de características**. Esta función le permite asociar los valores de informe 1099 a un proveedor por la cuenta principal en la distribución contable, en lugar de la cuenta predeterminada en el registro del proveedor.

Para obtener más información, consulte [Configurar proveedores para informes 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
