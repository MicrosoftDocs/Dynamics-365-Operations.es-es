---
title: "Conciliar extractos bancarios mediante la conciliación bancaria avanzada"
description: "La característica Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 for Finance and Operations. En este tema se explica el proceso de conciliación."
author: saraschi2
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationWorksheet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: ed3a1fae6ca30b9411fde47e7ef8a08150d7d748
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Conciliar extractos bancarios mediante la conciliación bancaria avanzada

[!include [banner](../includes/banner.md)]

La característica Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 for Finance and Operations. En este tema se explica el proceso de conciliación.  

<a name="import-an-electronic-bank-statement"></a>Importar un extracto bancario electrónico
-----------------------------------

Importa los extractos bancarios mediante la acción **Importar extracto** en la página **Extractos bancarios**. En el extracto bancario, la cuenta bancaria se identifica mediante una combinación de valores que se establecen en los detalles de la cuenta bancaria. Estos valores incluyen el nombre del banco, el número de cuenta bancaria, el número de ruta, el código SWIFT (Society for Worldwide Interbank Financial Telecommunication, Sociedad para la telecomunicación financiera interbancaria en el mundo) y el número internacional de cuenta bancaria (IBAN). 

Puede cargar un extracto bancario que contiene información tanto para una cuenta individual como para varias cuentas. Si hay varias cuentas, las cuentas pueden estar en entidades jurídicas diferentes.

-   Para importar un único archivo de extracto bancario para una única cuenta, establezca la opción **Importar extracto para varias cuentas bancarias en todas las entidades jurídicas** en **No** y seleccione la cuenta bancaria asociada al extracto. Haga clic en **Examinar** para seleccionar el archivo del extracto bancario asociado y, a continuación, haga clic en **Cargar**.
-   Para importar un único archivo de extracto bancario para varias cuentas, establezca la opción **Importar extracto para varias cuentas bancarias en todas las entidades jurídicas** en **Sí**. Haga clic en **Examinar** para seleccionar el archivo del extracto bancario asociado y, a continuación, haga clic en **Cargar**.

Si no se puede asociar ningún extracto del archivo electrónico con la cuenta bancaria mediante los campos de identificación, no se importarán. No obstante, se pueden importar todavía otros extractos del archivo. El usuario recibe, a continuación, un mensaje que indica que la importación de los extractos bancarios para las cuentas bancarias específicas no ha podido realizarse. Tenga en cuenta que el usuario que está importando el archivo del extracto bancario debe tener acceso a una entidad jurídica para importar los extractos para las cuentas bancarias de dicha entidad jurídica. 

Para cargar varios archivos de extractos a Finance and Operations en un único proceso, puede usar un archivo zip. Para importar varios archivos de extractos bancarios para varias cuentas, combine todos los archivos de extractos bancarios en un archivo zip. En el cuadro de diálogo **Importar extractos bancarios**, establezca la opción **Importar extracto para varias cuentas bancarias en todas las entidades jurídicas** en **Sí**. Haga clic en **Examinar** para seleccionar el archivo zip que contiene los archivos de extractos bancarios y, a continuación, haga clic en **Cargar**. El proceso de importación reconocerá el archivo zip y cargará cada extracto que se incluye en el mismo, independientemente de la entidad jurídica de la cuenta bancaria. 

Hay una opción **Conciliar tras la importación** disponible. Cuando establece esta opción en **Sí**, el sistema valida el extracto bancario automáticamente, crea una conciliación bancaria y una hoja de cálculo nuevas, y ejecuta el Conjunto de reglas de coincidencia predeterminado cuando se carga el extracto bancario. Esta funcionalidad automatiza el proceso hasta el punto donde deben conciliarse manualmente transacciones.

## <a name="validate-the-bank-statement"></a>Validar el extracto bancario
Para validar un extracto, en la página **Extractos bancarios**, haga clic en **Validar**. Los extractos bancarios se deben validar para que se pueden conciliar. Este paso se completa automáticamente si establece la opción **Conciliar tras la importación** en **Sí** en el momento de la importación. 

La validación del extracto bancario comprueba los siguientes detalles:

-   El extracto bancario coincide con la cuenta bancaria seleccionada.
-   La divisa del extracto bancario coincide con la divisa de la cuenta bancaria.
-   El saldo de apertura del extracto es igual al saldo de cierre del extracto anterior de la cuenta bancaria.
-   La fecha no solapa la fecha de otro extracto bancario para la misma cuenta bancaria.
-   No hay ningún espacio en las fechas para las instrucciones de la cuenta bancaria.
-   Las fechas de las líneas del extracto se encuentra entre la fecha de inicio y la fecha final del extracto bancario.
-   El saldo de apertura y los importes de línea resumidos son iguales que el saldo final.

Una vez finaliza la validación, se actualiza el estado del extracto bancario en **Validado**. Un extracto bancario se deben validar para que se pueda conciliar.

## <a name="reconcile-the-bank-statement"></a>Conciliar el extracto bancario
Una vez hay importado un extracto bancario electrónico y haya validado el extracto en la página **Extractos bancarios**, puede conciliar el extracto bancario con las páginas **Conciliación bancaria** y **Hoja de cálculo de conciliación bancaria**. 

En la página **Conciliación bancaria**, haga clic en **Nueva** para crear una conciliación nueva y, a continuación, seleccione la cuenta bancaria del extracto que se importó. Una cuenta bancaria solo puede tener una conciliación bancaria abierta. La fecha límite determina las transacciones de extracto bancario y las transacciones bancarias de Operaciones que se incluyen en la hoja de cálculo de conciliación. De forma predeterminada, se utiliza la fecha actual del sistema como la fecha límite, pero puede cambiar la fecha de la conciliación. La información restante del encabezado se toma automáticamente del extracto. Este paso se completa automáticamente si establece la opción **Conciliar tras la importación** en **Sí** en el momento de la importación. 

En la página **Conciliación bancaria**, haga clic en **Hoja de cálculo** para abrir la página **Hoja de cálculo de conciliación bancaria**. Si establece la opción **Conciliar tras la importación** en **Sí**, el Conjunto de reglas de coincidencia predeterminado se ejecuta automáticamente para la conciliación. Para ejecutar manualmente las reglas de coincidencia, haga clic en **Ejecutar las reglas de coincidencia** para seleccionar los conjuntos de reglas de coincidencia o las reglas de coincidencia para que se ejecuten con las transacciones bancarias. Si tiene muchas transacciones para procesar, puede completar este paso como un proceso por lotes. 

La página **Hoja de cálculo de conciliación bancaria** tiene cuatro cuadrículas que contienen transacciones. Las dos cuadrículas superiores muestran las transacciones del extracto bancario y las Operaciones que aún no se han conciliado. Las dos cuadrículas inferiores muestran transacciones conciliadas. La pestaña **Detalles de transacción de extracto bancario** muestra detalles para la transacción de extracto bancario no conciliada que está seleccionada en la cuadrícula superior. 

Hay tres formas para hacer coincidir o conciliar las transacciones de extracto bancario:

-   Conciliar las transacciones con transacciones bancarias de Operaciones.
-   Conciliar las transacciones con una transacción de extracto bancario de inversión.
-   Marcar las transacciones como **Nueva**, de manera que puedan registrarse posteriormente como transacción bancaria en Finance and Operations.

Para conciliar transacciones manuales, seleccione las transacciones de la cuadrícula **Transacciones de extracto bancario**, seleccione las transacciones correspondientes en la cuadrícula **Transacciones bancarias de Operaciones** y, a continuación, haga clic en **Conciliar**. Las transacciones seleccionadas se mueven desde las cuadrículas superiores para transacciones no conciliadas hasta las cuadrículas inferiores de transacciones conciliadas. Además, se actualizan los importes totales conciliados y no conciliados. Puede tener coincidencias de transacciones unívocas, de varios a uno y de varios a varios. Las coincidencias deben seguir las reglas para las diferencias de fecha permitidas y la asignación de tipos de transacción. Estas reglas se establecen en la página **Parámetros de gestión de efectivo y bancos**.

Las diferencias de decimales se pueden producir en la conciliación. Puede conciliar una transacción de extracto bancario única y una única transacción bancaria de Operaciones que tienen diferencias de decimales, si las diferencias de decimales se encuentran dentro del importe de tolerancia definido por el campo **Diferencia de decimales permitida** en la cuenta bancaria. El importe se muestra en el campo de **Importe de corrección** en la transacción bancaria vinculada de Operaciones. Cuando la conciliación bancaria se marca como conciliada, las correcciones se registran automáticamente mediante la cuenta principal definida en el tipo de transacción bancaria asociada. Las correcciones no se admiten para los tipos de documento **Cheque** y **Depósito**. 

Las inversiones de transacciones de extracto bancario se concilian mediante la hoja de cálculo de conciliación. Dos líneas de extracto se pueden conciliar si los importes son opuestos y si una de las transacciones se marca como inversión. También puede configurar una regla coincidente para la acción **Borrar líneas de extracto de inversión**.

Las transacciones bancarias de Operaciones inversas se deben conciliar mediante la página **Transacciones bancarias de Operaciones**. Puede conciliar dos transacciones bancarias de Operaciones juntas si los documentos tienen la misma cuenta bancaria, tipo de documento y referencia de pago, y si tienen importes opuestos. También puede conciliar un único cheque cancelado para evitar que dichas transacciones aparezcan en la hoja de cálculo de conciliación. 

Si hay nuevas transacciones iniciadas por el banco, como intereses, comisiones y gastos, que no están todavía en Finance and Operations, puede agregarlos a un diario asociado a la conciliación de extracto bancario seleccionada. Seleccione una transacción de extracto bancario en la cuadrícula **Transacciones de extracto bancario** para transacciones no conciliadas y, a continuación, haga clic en **Marcar como nuevo**. El estado de la transacción se establece en **Nuevo** y la transacción se mueve a la cuadrícula **Transacciones de extracto bancario** para las transacciones conciliadas. Registrará transacciones que estén marcadas como **Nueva** posteriormente, desde la página **Extracto bancario**. 

Puede quitar la conciliación de las transacciones que estuvieran incorrectamente conciliadas. Seleccione la transacción de extracto bancario conciliada y, a continuación, haga clic en **Quitar conciliación**. Todas las transacciones asociadas se devuelven a las cuadrículas superiores de transacciones no conciliadas y se actualizan los importes totales conciliados y no conciliados. 

Una completado el proceso de conciliación, debe marcar la hoja de trabajo de conciliación bancaria como conciliada.  Este proceso enviará automáticamente los importes de corrección mediante las cuentas establecidas en la página **Tipo de transacción bancaria**.  La conciliación bancaria de un extracto se puede marcar como conciliada en cualquier momento, incluso si hay líneas de extractos bancarios que aún no se hayan conciliado.  Las transacciones no coincidentes se desplazarán automáticamente a la siguiente hoja de cálculo de conciliación como transacciones no coincidentes del extracto bancario que se conciliará.  Tenga en cuenta que una vez que una conciliación del extracto bancario se haya marcado como conciliada, no se puede deshacer.  La conciliación ya no se podrá editar y no tendrá la posibilidad de crear actualizaciones de dicha conciliación.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Registrar nuevas transacciones asociadas con la conciliación
Las transacciones de extracto bancario que marcó como **Nueva** en la hoja de cálculo de conciliación se registran en la página **Extracto bancario**. En el **Extracto bancario** , seleccione el id. de extracto para ver los detalles del extracto. En el menú **Contabilidad**, puede utilizar las opciones **Ver distribuciones** y **Ver contabilidad** para ver detalles de las nuevas transacciones y los movimientos contables asociados. Seleccione la opción **Registrar** para registrar las líneas de extracto bancario marcadas como **Nueva** en la contabilidad general. Tenga en cuenta que el registro solo se puede completar una vez por extracto bancario.




