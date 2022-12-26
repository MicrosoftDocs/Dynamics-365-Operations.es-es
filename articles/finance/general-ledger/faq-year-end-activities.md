---
title: Preguntas frecuentes sobre las actividades de fin de ejercicio
description: Este artículo enumera las preguntas que pueden surgir al cerrar un ejercicio y las respuestas que pueden ayudar con las actividades de cierre de fin de ejercicio.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853052"
---
# <a name="year-end-activities-faq"></a>Preguntas frecuentes sobre las actividades de fin de ejercicio 

[!include [banner](../includes/banner.md)]

Este artículo enumera las preguntas que pueden surgir al cerrar un ejercicio y las respuestas que pueden ayudar con las actividades de cierre de fin de ejercicio. La información de este artículo se centra principalmente en dudas sobre actividades de cierre de fin de ejercicio para contabilidad general y Proveedores.

## <a name="general-ledger-year-end-enhancements"></a>Mejoras de fin de año de contabilidad general

Microsoft Dynamics 365 Finance, versión 10.0.20 introdujo una mejora de cierre de fin de año. Esta mejora está habilitada de forma predeterminada a partir de la versión 10.0.25 y es obligatoria a partir de la versión 10.0.29. Si su organización utiliza una versión anterior a la 10.0.25, le recomendamos que habilite esta característica antes de comenzar el proceso de cierre de fin de ejercicio. Para poder usar esta característica, debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo **Administración de características** para comprobar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** Contabilidad general
- **Nombre de la característica:** mejoras de fin de año de contabilidad general

La configuración de las plantillas de cierre de fin de año se ha pasado a una nueva página de configuración, **Configuración de la plantilla de cierre de fin de año**. La página de cierre de fin de ejercicio actual será como la página de **revalorización de divisa extranjera de contabilidad general**, donde se muestra una lista cada vez que se ejecuta o revierte el cierre de fin de ejercicio. La página no mostrará información histórica sobre los cierres de fin de año que se realizaron antes de habilitar la característica. Un gerente de contabilidad puede iniciar el cierre de fin de ejercicio desde la nueva página.

Para revertir el cierre de fin de ejercicio, seleccione el ejercicio más reciente para la entidad jurídica apropiada y, a continuación, seleccione **Revertir cierre de fin de ejercicio**. La reversión eliminará los asientos contables del cierre de fin de ejercicio anterior y no volverá a ejecutar automáticamente el cierre de fin de ejercicio. Si habilita la característica **Mejoras de fin de año de contabilidad general** después de haber completado un cierre de año y desea revertir los resultados históricos de fin de año, ejecute el cierre histórico de fin de año nuevamente después de habilitar el parámetro de contabilidad general **Eliminar entradas existentes de cierre de fin de año al volver a cerrar el año**.

Puede volver a ejecutar el cierre de fin de ejercicio reiniciando el proceso para el ejercicio y la entidad jurídica. El proceso continuará usando la configuración del parámetro Contabilidad laboral para determinar si la repetición del cierre de fin de ejercicio tendrá en cuenta solo las transacciones nuevas o modificadas, o si se repetirá el proceso para todas las transacciones y revertirá completamente el cierre anterior.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Contabilidad general: la característica Mejoras de fin de año de contabilidad general está habilitada. ¿Por qué no puedo ver mis cierres de años anteriores en la sección Historial de la página de cierre de fin de año?

Antes de habilitar la característica **Mejoras de fin de año de contabilidad general**, se realiza un seguimiento de la fecha y la hora en que se ejecutó el último proceso de cierre de año. No realizó un seguimiento del historial de cada vez que se realizó el cierre de fin de año. Como tal, los detalles de cada ejecución de cierre de fin de año no están disponibles para mostrar. Después de habilitar la característica, se mantiene la información del proceso de cierre de fin de año posterior. Los comprobantes de todos los procesos de cierre de fin de año, incluso los ejecutados antes de la activación de la característica, se pueden ver en la página **Transacciones de asiento**. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Contabilidad general: el proceso de cierre de fin de año está fallando debido al siguiente error: "El cierre de fin de año no se puede ejecutar porque una o más transacciones contables registradas en el ejercicio que está cerrando se liquidaron en una transacción contable en un ejercicio diferente". ¿Qué significa este error?

Debido a que la característica **Las transacciones entre la liquidación de contabilidad y el cierre de fin de año** está habilitada, solo las transacciones contables liquidadas del ejercicio que se está cerrando se excluyen del saldo de apertura. Este comportamiento hace que los débitos y créditos no cuadren. Para obtener información adicional, consulte [Las transacciones entre la liquidación de contabilidad y el cierre de fin de año](awareness-between-ledger-settlement-year-end-close.md).

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Contabilidad general: la inversión del proceso de cierre de fin de año está fallando debido al siguiente error: "El cierre de fin de año para el 1/1/2022 no se puede invertir porque la transacción contable inicial se liquidó en el libro mayor en el ejercicio 1/1 /2023". ¿Qué significa este error?

Debido a que la característica **Las transacciones entre la liquidación de contabilidad y el cierre de fin de año** está habilitada, no se permiten inversiones del procesamiento de fin de año si las transacciones de apertura se han liquidado en el nuevo ejercicio. Invierta la liquidación de contabilidad en el nuevo ejercicio 2023 antes de invertir el cierre de fin de año para el 1 de enero de 2022. O bien, vuelva a cerrar el año para el 1 de enero de 2022, pero solo para nuevas entradas de ajuste. Para volver a cerrar el año solo para ajustes, deshabilite el parámetro de contabilidad general **Eliminar las entradas existentes de fin de año al volver a cerrar el año**.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Contabilidad general: ¿Por qué la automatización de la liquidación de contabilidad no procesa las transacciones de liquidación de contabilidad de diciembre?

La característica **Automatización liquidaciones de contabilidad** ejecutará la automatización para las transacciones con fecha desde el primer día del ejercicio hasta la fecha actual en que se ejecuta la ocurrencia. Para los ejercicios que terminan el 31 de diciembre, es posible que deba ajustar la fecha de ejecución de su ocurrencia para asegurarse de que se ejecute en diciembre. Por ejemplo, la automatización está configurada para ejecutarse el primer día de cada mes. Esta automatización se ejecutará el 1 de diciembre de 2022 y está programada para ejecutarse el 1 de enero de 2023. Le recomendamos que cambie la ocurrencia del 1 de enero de 2023 para que se ejecute el 31 de diciembre de 2022. Este cambio asegurará que las transacciones con fecha del 2 al 31 de diciembre se consideren para su liquidación automática.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Contabilidad general: ¿Cuál es la diferencia entre la acción de cierre de fin de año inverso y el parámetro Eliminar las entradas existentes de fin de año al volver a cerrar el año para el cierre de fin de año?

Puede haber confusión acerca de la diferencia entre la acción **Invertir cierre de fin de año** y el parámetro **Eliminar las entradas existentes de fin de año al volver a cerrar** en Contabilidad general (**Contabilidad general \> Configuración de contabilidad \> Parámetros de contabilidad general**).

Seleccione la acción **Invertir cierre de fin de año** al ejecutar el proceso de cierre de fin de año para eliminar todos los movimientos de saldo de cierre y de apertura, como si el cierre de fin de año nunca se hubiera ejecutado. En este caso, los asientos se eliminarán. El cierre de fin de año no se volverá a ejecutar de forma automática. Para ejecutar el cierre de fin de año, seleccione la acción **Ejecutar cierre de fin de año**.

El parámetro **Eliminar las entradas existentes de fin de año al volver a cerrar el año** en la contabilidad general se usa solo cuando está ejecutando (no invirtiendo) el cierre de fin de año. Si el parámetro se establece en **Sí**, todas las entradas de saldo de cierre y de apertura se eliminarán y el cierre de fin de año se ejecutará de nuevo. Esta opción se utiliza cuando una organización desea que todas las transacciones, incluidos los ajustes desde el último cierre de año, se registren en una sola entrada contable para las entradas de saldo de cierre y de apertura. Si el parámetro se establece en **No**, se mantienen todas las entradas de saldo de cierre y de apertura. No se eliminan. En su lugar, se creará una nueva entrada de saldo de cierre y apertura solo para las transacciones delta o nuevas que se hayan registrado desde el último cierre de fin de año para ese ejercicio.

> [!NOTE]
> La entrada de saldo de cierre se crea en el año que se está cerrando. Esto solo sucede si el parámetro de Contabilidad general **Crear el asiento de cierre al lanzar el proceso de transacciones de cierre / apertura** es **Sí**. Siempre se crea la entrada de saldo de apertura porque es el saldo inicial del siguiente año.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Contabilidad general: ¿Cuál es la diferencia entre las opciones "Cerrar todo" y "Cerrar uno" en la sección Transferir dimensiones de pérdidas y ganancias del proceso de cierre de fin de año?

**Cerrar todo** mantiene los valores de la dimensión financiera original de las transacciones registradas y los utiliza para crear los saldos de apertura de la cuenta de ganancias retenidas. Se crearán saldos iniciales de ganancias retenidas separados para cada combinación exclusiva de valores de la dimensión financiera. Si se selecciona **Cerrar uno**, todas las transacciones registradas que tengan esa dimensión financiera se resumirán en un saldo inicial de ganancias retenidas para el valor de dimensión especificado en el campo que aparece después de **Cerrar uno**. 

Por ejemplo, todas las transacciones del ejercicio se registraron con la estructura contable de Cuenta principal - Departamento. Para la dimensión financiera Departamento de la plantilla se selecciona **Cerrar uno** y se especifica el valor de dimensión 100. Si el ingreso total de todas las transacciones registradas en los departamentos 200, 300 y 400 es 100 000 $, se creará un saldo de apertura para las Ganancias retenidas - 100. Si selecciona **Cerrar uno** pero deja el campo de valores de la dimensión financiera en blanco, todas las transacciones se registrarán en las ganancias retenidas con ese valor de dimensión en blanco.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Contabilidad general: cuando selecciono la opción "Cerrar uno" en la sección Transferir dimensiones de pérdidas y ganancias del proceso de cierre de fin de año, ¿se perderá mi información transaccional detallada?

Las opciones **Cerrar todo** y **Cerrar uno** se utilizan para especificar las dimensiones financieras de las transacciones que se registran en ganancias y las cuentas de pérdidas se transferirán a la cuenta principal de utilidades retenidas. Los registros históricos detallados en las cuentas de pérdidas y ganancias no se ve afectada y seguirá detallándose. La opción afecta el nivel de detalle que se transfiere a las cuentas de ganancias retenidas como saldo de apertura en el nuevo año. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Contabilidad general: el proceso de cierre de fin de año está fallando porque la divisa de notificación del año no cuadra. ¿Qué significa esto?

Este error se puede experimentar después de habilitar la característica **Las transacciones entre la liquidación de contabilidad y el cierre** (la función Reconocimiento). Cuando la característica está habilitada, las transacciones del libro mayor que se han liquidado ya no se incluirán en el saldo de apertura del próximo ejercicio cuando se ejecuta el cierre de fin de año de la contabilidad general. Excluir las transacciones del libro mayor que se liquidan puede presentar un desafío para los clientes al cierre del año si el libro mayor se define con una divisa de notificación.   
La liquidación de contabilidad se realiza solo para la divisa de contabilidad.  Cuando se liquidan las transacciones del libro mayor, la validación solo garantiza que los débitos en divisa de contabilidad sean iguales a los créditos en divisa de contabilidad. Los importes en divisa de notificación para esas transacciones del libro mayor no están validados y es posible que no tengan débitos = créditos.  Además, la liquidación de contabilidad no calcula ni registra automáticamente una ganancia/pérdida en la divisa de notificación.  Debido a estas limitaciones, debe existir una transacción de ganancias/pérdidas en la divisa de notificación al realizar la liquidación de contabilidad.  Si la ganancia/pérdida no se incluye en la liquidación de contabilidad, el cierre de fin de año dará como resultado un mensaje de descuadre.  Para obtener información adicional, consulte [Característica de transacciones entre la liquidación de contabilidad y la divisa de notificación descuadrada](reporting-currency-yec.md).

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Contabilidad general: ¿qué se puede cambiar para ayudar a mejorar el rendimiento del procesamiento del fin de año?

Puede llevar a cabo varios cambios para ayudar a mejorar el rendimiento del cierre de fin de año. Le recomendamos que analice estos cambios sugeridos para determinar si son apropiados para su organización.

### <a name="optimize-year-end-close-service"></a>Servicio Optimizar cierre de fin de año

El servicio **Optimizar cierre de fin de año** faculta a clientes de Microsoft Dynamics 365 Finance a acelerar su cierre de año trasladando el pesado procesamiento de fin de año a un microservicio. El tiempo que se ahorra a través de un cierre de fin de año eficiente permite que cada equipo de Finance reaccione de manera oportuna a los ajustes requeridos, finalizando con la generación de los informes financieros. Al procesar el cierre de fin de año en un microservicio, se liberan recursos valiosos. La elevación del procesamiento minimiza la carga en SQL Server y brinda a los clientes la oportunidad de acelerar el procesamiento de cierre de fin de año.

El servicio **Optimizar cierre de fin de año** está disponible en la versión 10.0.31, para que más clientes puedan usar el nuevo servicio para la temporada de fin de año de 2022. Además, el servicio se ha retrotraído a las versiones 10.0.30 y 10.0.29. Para más información, consulte [Optimizar cierre de fin de año](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Conjuntos de dimensiones

Cuando se ejecuta el cierre de fin de año, se reconstruye el saldo de cada conjunto de dimensiones. Este comportamiento tiene un impacto directo en el rendimiento. Algunas organizaciones crean conjuntos de dimensiones de forma innecesaria, porque se usaron en un momento concreto o podrían usarse en algún momento. Debido a que estos conjuntos de dimensiones innecesarios aún se recrean durante el cierre de fin de año, se ralentiza el proceso. Invierta tiempo en evaluar sus conjuntos de dimensiones y eliminar los que no sean necesarios.

Los conjuntos de dimensiones innecesarios también afectan al trabajo por lotes **BudgetDimensionFocusInitializeBalance** (**Contabilidad general \> Plan de cuentas \> Dimensiones \> Conjuntos de dimensiones financieras**).

[![Conjuntos de dimensiones financieras.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Configuración de la plantilla del cierre de fin de año

La plantilla del cierre de fin de año permite a las organizaciones seleccionar el nivel de la dimensión financiera que deben mantener a la hora de transferir los saldos de pérdidas y ganancias a las ganancias retenidas. La configuración permite que una organización mantenga las dimensiones financieras detalladas (**Cerrar todo**) al mover los saldos a ganancias retenidas o elegir resumir los importes en un valor de dimensión única (**Cerrar uno**). Esto se puede definir para cada dimensión financiera. Para obtener más información sobre estas configuraciones, consulte el artículo [Cierre de fin de año](year-end-close.md).

Le recomendamos que evalúe los requisitos de su organización y, si es posible, cierre tantas dimensiones como sea posible mediante la opción de fin de año **Cerrar uno** para mejorar el rendimiento. Al cerrar a un valor de dimensión única (que también puede ser un valor en blanco), el sistema calcula menos detalles a la hora de determinar los saldos para los asientos contables de ganancias retenidas.

### <a name="degenerate-dimensions"></a>Dimensiones degeneradas

Una dimensión degenerada proporciona poca o ninguna reutilización por sí misma ni en combinación con otras dimensiones. Existen dos tipos de dimensiones degeneradas. El primer tipo es una dimensión que es degenerada de forma individual. Por lo general, este tipo de dimensión degenerada aparecerá únicamente en una sola transacción o en pequeños conjuntos de transacciones. El segundo tipo es una dimensión que se pasa a ser degenerada en combinación con una o más dimensiones adicionales que exhiben el mismo potencial, según las posibles permutaciones que pueden generarse. Una dimensión degenerada puede tener un impacto significativo en el rendimiento del proceso de cierre de fin de año. Para minimizar los problemas de rendimiento, defina todas las dimensiones degeneradas como **Cerrar uno** en la configuración de cierre de fin de ejercicio, como se describe en la sección anterior.

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

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Proveedores: 1099, ¿Cómo cambio la casilla 1099 y los valores de un proveedor que no estaba haciendo un seguimiento de la información relacionada con el 1099 durante todo el año?

Use la funcionalidad **Actualizar 1099** para revisar las transacciones de facturas pagadas anteriormente y reasignar los datos 1099 de manera adecuada, de acuerdo con la configuración en la pestaña **IRPF** de la página **Proveedor** . Para usar la funcionalidad **Actualizar formulario de declaración de IRPF**, vaya a **Proveedores\> Proveedores\> Todos los proveedores**, seleccione un proveedor y luego, en el Panel de acciones, en la pestaña **Proveedor**, seleccione **Actualizar formulario de declaración de IRPF**.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>¿Puedo ejecutar la funcionalidad Actualizar formulario de declaración de IRPF para todos mis proveedores a la vez?

Puede usar la página **Actualizar la información 1099 para varios proveedores** para actualizar el cuadro de IRPF en un registro de proveedor y para actualizar transacciones con la información de la casilla de declaración de IRPF. Para abrir esta página, vaya a **Proveedores \> Tarea periódica \> IRPF**. Para acceder a la página, debe tener asignado el privilegio de seguridad **Actualizar el cuadro 1099 y las transacciones para varios proveedores**.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Proveedores: 1099, volver a calcular los importes existentes de la declaración de 1099 frente a Actualizar todo en la función Actualizar 1099.

La casilla **Volver a calcular los importes existentes de la declaración 1099** restablecerá el importe de la declaración 1099 a los valores pagados totales cuando se use junto a la casilla **Actualizar todo**.

[![Transacciones del IRPF: antes de ejecutar la rutina de actualización.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

La casilla **Volver a calcular los importes de 1099 existentes** es útil solo cuando hay valores parciales en la declaración 1099 en la factura o si se ha modificado la factura en el formulario de 1099. Por ejemplo, tiene una factura valorada en 1000 $, pero el usuario introduce manualmente un importe de 500 $ en la factura.

[![Transacciones del 1099: marcar Actualizar todo y Volver a calcular los importes existentes de la declaración de 1099.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Cuando se pague esta factura, 500 $ será el importe de 1099 que se pague. Si vuelve a calcular los importes, el importe del 1099 cambiará a 1000 $, que es el total que se ha pagado.

[![Transacciones del 1099: después de ejecutar la rutina de 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Proveedores: 1099 - Crear manualmente transacciones del 1099

Es posible que una organización deba crear manualmente transacciones del 1099 que no estén asociadas con una factura. Puede agregar transacciones del 1099 manuales si va a **Proveedores \> Tareas periódicas \> 1099 \> Liquidación del proveedor para 1099**. Seleccione el botón **Transacciones 1099 manuales**.

Las transacciones del 1099 creadas de forma manual no se actualizan con el proceso **Actualizar todo** o el proceso **Volver a calcular los importes de 1099 existentes** en la función **Actualizar 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Proveedores: 1099 - ¿es Dynamics 365 Finance compatible con el formulario 1096?

Dynamics 365 Finance no imprime el formulario 1096 de resumen anual y transmisión de declaraciones de información de EE. UU.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Proveedores: 1099 - ¿hay alguna nueva función compatible con el informe 1099 para el sector público?

Se ha agregado una nueva característica para el sector público, **Actualizar información de informe 1099 por cuenta principal**, que puede habilitar en el espacio de trabajo **Administración de características**. Esta función le permite asociar los valores de informe 1099 a un proveedor por la cuenta principal en la distribución contable, en lugar de la cuenta predeterminada en el registro del proveedor.

Para obtener más información, consulte [Configurar proveedores para informes 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
