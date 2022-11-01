---
title: Automatizar liquidaciones de contabilidad
description: En este artículo se proporciona información general sobre el proceso de automatización de liquidaciones de contabilidad.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708337"
---
# <a name="automate-ledger-settlements"></a>Automatizar liquidaciones de contabilidad

[!include [banner](../includes/banner.md)]

En Microsoft Dynamics 365 Finance versión 10.0.31, la función **Automatizar el proceso de liquidación de contabilidad** está disponible en el espacio de trabajo **Gestión de características** . Puede habilitar la función **Automatizar el proceso de liquidación de contabilidad** solo si se ha habilitado **Las transacciones entre la liquidación de contabilidad y el cierre de fin de año**.

La liquidación de contabilidad es el proceso de coincidir las transacciones de débito y crédito en la contabilidad general. Las organizaciones que realizan actividades de liquidación de libros mayores en un horario recurrente ahora pueden automatizar el proceso. Durante el proceso de liquidación automática del libro mayor, una transacción de débito y una transacción de crédito pueden coincidir automáticamente solo si sus montos en la moneda de contabilidad son iguales. Por ejemplo, un monto de débito de $ 1,00 puede coincidir automáticamente con un monto de crédito de $ 1,00. Sin embargo, un valor de débito de $ 1,00 no puede coincidir automáticamente con dos créditos, cada uno de los cuales tiene un valor de $ 0,50. No se admite la conciliación parcial de importes de transacciones contables.

La automatización de la liquidación del libro mayor define los siguientes detalles:

- Cuando se ejecutan las liquidaciones contables
- Qué criterios se utilizan para conciliar los débitos y créditos que se pueden liquidar automáticamente
- En qué orden se procesa la información de liquidación del libro mayor

## <a name="define-the-occurrence-of-ledger-settlements"></a>Definir la ocurrencia de liquidaciones contables

La automatización de la liquidación del libro mayor utiliza el marco de automatización de procesos. Diferentes procesos de negocios utilizan este marco para definir la periodicidad de un proceso seleccionado. Para liquidaciones contables, vaya a  **Administracion del sistema \> Configuración \> Automatizaciones de procesos** o **Libro mayor \> Configuración del libro mayor \> Automatizaciones de procesos**.

Primero, seleccione la opción **Crear nuevo proceso de automatización** y seleccione **Liquidaciones de contabilidad**. Luego, un asistente le guía a través del proceso de configuración de la automatización.

## <a name="general-page"></a>Página general

En la página **General** del asistente, introduzca el nombre de la instancia de liquidación de contabilidad que está creando. Por ejemplo, si sus débitos y créditos coincidentes se liquidan en el libro mayor el lunes, ingrese un nombre descriptivo como **LedgerSettle\_Mon**. El nombre que ingresa se muestra en la columna **Regla de automatización** en la página **Liquidaciones del libro mayor**.

Las configuraciones restantes de la página son genéricas y definen el patrón de ocurrencia para esta versión de liquidaciones de contabilidad. Por ejemplo, si una ocurrencia es para el lunes, puede definirla para que se ejecute semanalmente, y puede seleccionar el lunes como el día de la semana en que se ejecuta. También puede introducir una hora de programación temprana, como las 2:00 a.m., para que la automatización del proceso se complete antes del inicio del siguiente día hábil. Le recomendamos que programe la automatización del proceso para que se realice fuera de su horario laboral habitual. De esta forma, ayudas a reducir el impacto en tu personal contable durante la jornada laboral.

Para obtener más información sobre los otros campos de la página **General**, consulte la documentación de automatización de procesos.

## <a name="ledger-settlements-match-criteria-page"></a>Página Criterios de coincidencia de liquidaciones de contabilidad

La siguiente página del asistente es la página **Criterios de coincidencia de liquidaciones de contabilidad**. Se utiliza para definir las cuentas principales que se incluyen en la ocurrencia de automatización de procesos y los criterios que se utilizan para determinar los débitos y créditos coincidentes.

### <a name="account-selection"></a>Selección de cuenta

Se muestran las cuentas principales que definió previamente como cuentas de liquidación contable para la entidad jurídica. (Se definen las cuentas principales como cuentas de liquidación del libro mayor en **Libro mayor \> Configuración del libro mayor \> Parámetros del libro mayor \> Liquidaciones del libro mayor**).

### <a name="main-account-and-posting-layer"></a>Cuenta principal y capa de contabilización

Los valores  **Cuenta principal** y **Capa de publicación** son criterios de coincidencia obligatorios. Los valores **Cuenta principal** y **Capa de publicación** de la transacción de débito y la transacción de crédito del libro mayor deben ser iguales para que coincidan durante el proceso automático de liquidación del libro mayor.

### <a name="posting-type"></a>Tipo de registro

Seleccione la opción **Tipo de registro** si las transacciones de débito y crédito contable deben tener el mismo tipo de registro para que coincidan durante el proceso de liquidación de contabilidad automática.

### <a name="financial-dimensions"></a>Dimensiones financieras

Seleccione la opción **Dimensiones financieras** si las transacciones de débito y crédito contable deben tener las mismas dimensiones financieras para que coincidan durante el proceso de liquidación de contabilidad automática. Cuando se selecciona esta opción, los criterios para los valores de la dimensión financiera deben seleccionarse en la lista **Dimensiones financieras disponibles**. La lista **Dimensiones financieras disponibles** no contiene la dimensión de la cuenta principal, porque se requiere automáticamente como parte de los criterios de coincidencia.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Ver los resultados de una automatización de liquidación de contabilidad

Después de crear la serie de automatización de liquidaciones de contabilida, las ocurrencias de cada liquidación de contabilidad se muestran en la vista semanal de automatización de procesos. Además, se muestra el estado de cada ocurrencia. Se usan los siguientes estados:

- **Programada**: la automatización se ha programado, pero aún no se ha ejecutado.
- **En ejecución** – La automatización se está ejecutando actualmente.
- **Error**: la automatización se ejecutó, pero ocurrió un error. Puede ver los errores seleccionando el botón **Ver resultados**.
- **Terminado**: la automatización se ha ejecutado correctamente. Puede consultar los resultados de la liquidación en la página **Liquidaciones del libro mayor**.

Para ver los resultados coincidentes, vaya a **Libro mayor \> Tareas periódicas \> Liquidaciones del libro mayor**. El campo **Regla de automatización** en la página **Liquidaciones del libro mayor** muestra el nombre de la tarea programada de liquidación automática del libro mayor que se utilizó para liquidar la transacción. Los intentos fallidos de liquidación no actualizarán el valor **Regla de automatización**. Si anula manualmente una transacción que el proceso de automatización liquidó previamente con éxito, el valor **Regla de automatización** será eliminado.

El campo **Fecha liquidada** para los registros coincidentes muestra la fecha en que se realizó el proceso de automatización.

## <a name="editing-a-ledger-settlement-automation"></a>Editar la automatización de una liquidación de contabilidad

El marco de automatización de procesos le permite editar la serie y las ocurrencias que se crean para la liquidación de contabilidad. La serie se puede editar desde la página **Automatización de procesos** o la vista semanal de automatización de procesos. Por ejemplo, si el gerente decide realizar la liquidación de contabilidad el miércoles en lugar del lunes, puede encontrar una ocurrencia en la vista semanal y seleccionar **Ver/Editar: serie**.

Si edita una serie, se le solicita que especifique si el cambio debe realizarse en todas las ocurrencias existentes o solo en las nuevas. Las ocurrencias históricas que ya tienen un estado de **Completado** o que terminaron con estado de **Error** no se cambiarán.

También puede agregar una nueva ocurrencia o cambiar una existente. Por ejemplo, la próxima ocurrencia de liquidación de contabilidad está programada para ejecutarse el miércoles 1 de enero, pero esta fecha es festiva. Puede cambiar la ocurrencia desde la página **Automatización de procesos** o la vista semanal de automatización de procesos. Se abre una página que muestra los detalles de la programación y los criterios de coincidencia. Aquí puede editar la hora y fecha programadas. También puede editar los criterios de coincidencia si se requieren cambios. 

También puede deshabilitar una ocurrencia o una serie. Para deshabilitar una ocurrencia y suspender el procesamiento, selecciónela en la vista semanal de automatización de procesos y luego seleccione **Deshabilitar**. Puede deshabilitar una serie en la página **Automatización de procesos**.

## <a name="security-for-ledger-settlement-automation"></a>Seguridad para la automatización de liquidaciones de contabilidad

El derecho **Mantener la configuración de la serie de automatización de liquidaciones del libro mayor** se ha agregado a los roles de Gerente de contabilidad y Supervisor de contabilidad y el derecho **Ver la configuración de la serie de automatización de liquidaciones del libro mayor** se ha agregado a los roles de Contador, Gerente de contabilidad y Supervisor de contabilidad para las automatizaciones de liquidación de libros mayores. Estos derechos y privilegios son las configuraciones de seguridad predeterminadas, pero se pueden cambiar según los requisitos de su organización.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Parámetros del libro mayor para la automatización de la liquidación del libro mayor

El campo **Saldo típico de liquidación** indica el orden en que se procesará la liquidación automática del libro mayor. Para configurar o ver el valor **Saldo típico de liquidación**, vaya a **Libro mayor \> Configuración \> Parámetros del libro mayor** y seleccione la pestaña **Liquidaciones del libro mayor**.

Si **Débito** está seleccionado, el proceso de liquidación del libro mayor automatizado comienza en el lado del débito y busca los créditos correspondientes. Si **Crédito** está seleccionado, el proceso de liquidación del libro mayor automatizado comienza en el lado del crédito y busca los débitos correspondientes. Esta opción debe reflejar el saldo típico de la cuenta principal.

## <a name="processing-a-ledger-settlement-automation"></a>Procesar la automatización de una liquidación de contabilidad

Cuando se ejecuta la automatización, el sistema selecciona las transacciones del libro mayor para las cuentas principales que se definen para la serie de automatización de procesos. Ordena las transacciones por fecha, utilizando un rango de fechas desde el inicio del año fiscal hasta la fecha en que se ejecuta la automatización del proceso. Coincide en función de los criterios de coincidencia especificados. Los valores absolutos de los importes en moneda contable del débito y el crédito deben coincidir para liquidarse.

Mientras una cuenta principal está siendo procesada por una ocurrencia de una automatización de liquidación de libro mayor, no puede mostrarla en la página **Liquidaciones del libro mayor**. Debe esperar hasta que se complete el proceso de automatización. Le recomendamos que programe la automatización del proceso para que se ejecute fuera del horario laboral, para ayudar a evitar conflictos.

El proceso de automatización incluirá todas las transacciones que cumplan con los criterios, excepto las transacciones que se hayan marcado manualmente para su liquidación en la página **Liquidaciones del libro mayor**.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Reversión de transacciones que son liquidadas por el proceso de automatización

Puede invertir una liquidación que se ha realizado mediante el proceso de liquidación de contabilidad automatizado. Cuando se invierte una transacción que el proceso de automatización liquidó previamente, el valor **Regla de automatización** se elimina.
