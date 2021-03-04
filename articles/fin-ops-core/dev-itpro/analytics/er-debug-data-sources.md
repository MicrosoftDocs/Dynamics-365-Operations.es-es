---
title: Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación
description: Este tema explica cómo puede depurar las fuentes de datos de un formato ER ejecutado para comprender mejor el flujo y la transformación de datos configurados.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 3a486800f37dda7829aeeaa56a30285a92a61b9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680791"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Cuando [configure](tasks/er-format-configuration-2016-11.md) una solución de informes electrónicos (ER) para generar documentos electrónicos resultantes, se definen los métodos que se usan para sacar datos de la aplicción e introducirlos en la salida que se genera. Para que el soporte del ciclo de vida de la solución ER sea más eficiente, su solución debe consistir en un [modelo de datos](general-electronic-reporting.md#DataModelComponent) ER y sus componentes [correspondientes](general-electronic-reporting.md#ModelMappingComponent), y también un [formato](general-electronic-reporting.md#FormatComponentOutbound) ER y sus componentes correspondientes, de modo que la asignación del modelo sea específica de la aplicación, mientras que otros componentes permanecen independientes de la aplicación. Por lo tanto, varios componentes de ER podrían [afectar](general-electronic-reporting.md#FormatComponentOutbound) al proceso de introducir datos en la salida generada.

A veces, los datos de la salida generada parecen diferentes de los mismos datos en la base de datos de la aplicación. En estos casos, querrá determinar qué componente de ER es responsable de la transformación de datos. La función del depurador de la fuente de datos ER reduce significativamente el tiempo y el coste involucrados en esta investigación. Puede interrumpir la ejecución de un formato ER y abrir la interfaz del depurador de origen de datos. Allí, puede examinar las fuentes de datos disponibles y seleccionar una fuente de datos individual para la ejecución. Esta ejecución manual simula la ejecución de la fuente de datos durante la ejecución real de un formato ER. El resultado se presenta en una página donde puede analizar los datos que se reciben.

Para activar la función de depuración del origen de datos, configure **Habilitar la depuración de datos al ejecutar formato** en **Sí** en los parámetros de usuario ER. Luego puede iniciar la depuración del origen de datos mientras ejecuta un formato ER para generar documentos salientes. También puede usar la opción **Comenzar depuración** para iniciar la depuración del origen de datos para un formato ER que está configurado en el [Diseñador de operaciones ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

Este tema proporciona pautas para iniciar la depuración del origen de datos para los formatos ER ejecutados. Explica cómo la información puede ayudarle a comprender el flujo de datos y las transformaciones de datos. Los ejemplos de este tema utilizan el proceso comercial para el procesamiento de los pagos de proveedores.

## <a name="limitations"></a>Limitaciones

El depurador de fuente de datos se puede utilizar para acceder a los datos de las fuentes de datos que se utilizan en formatos ER que se ejecutan para generar documentos salientes. No se puede utilizar para depurar fuentes de datos de formatos ER diseñados para analizar documentos entrantes.

Actualmente no se puede acceder a las siguientes configuraciones de formatos ER para la depuración de fuentes de datos:

- Transformaciones de formato
- Reglas de validación de formato y mapeo
- Habilitar expresiones
- Detalles de la recopilación de datos en memoria

## <a name="prerequisites"></a>Requisitos previos

- Para completar los ejemplos de este tema, debe tener acceso a uno de los siguientes [roles](../sysadmin/tasks/assign-users-security-roles.md):

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- La empresa debe establecerse en **DEMF**.

- Siga los pasos del [Apéndice 1](#appendix1) de este tema para descargar los componentes de la solución ER de Microsoft que se requieren para procesar los pagos del proveedor.
- Siga los pasos del [Apéndice 2](#appendix2) de este tema para preparar los proveedores para el procesamiento de pagos de proveedores utilizando la solución ER que descargará.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Procesar un pago de proveedor para obtener un archivo de pago

1. Siga los pasos del [Apéndice 3](#appendix3) de este tema para procesar pagos de proveedores.

    ![Procesamiento de pagos de proveedores en curso](./media/er-data-debugger-process-payment.png)

2. Descargue y guarde el archivo zip en el equipo local.
3. Extraiga el archivo de pago **Transferencia de crédito ISO20022.xml** del archivo zip.
4. Abra el archivo de pago extraído utilizando el visor de archivos XML.

    En el archivo de pagos, el número de cuenta bancaria internacional (IBAN) del proveedor no contiene espacios. Por lo tanto, difiere del valor que se [introdujo](#enteredIBANcode) en la página **Cuentas bancarias**.

    ![Código IBAN sin espacios](./media/er-data-debugger-payment-file.png)

    Puede usar el depurador de origen de datos ER para saber qué componente de la solución ER se usa para truncar espacios en el código IBAN.

## <a name="turn-on-data-source-debugging"></a>Activar la depuración del origen de datos

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. Establece la opción **Habilitar depuración de datos al ejecutar formato** en **Sí**.

    > [!NOTE]
    > Este parámetro es específico del usuario y específico de la compañía.

    ![Cuadro de diálogo parámetros de usuario](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Procesar un pago a proveedor para la depuración

1. Siga los pasos del [Apéndice 3](#appendix3) de este tema para procesar pagos de proveedores.
2. En el cuadro de mensaje, seleccione **Sí** para confirmar que desea interrumpir el procesamiento de pagos del proveedor y, en su lugar, iniciar la depuración del origen de datos en la página **Orígenes de datos de depuración**.

    ![Cuadro de mensaje de confirmación](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>Fuentes de datos de depuración que se utilizan en el procesamiento de pagos

### <a name="debug-the-model-mapping"></a>Depurar la asignación del modelo

1. En la página **Fuentes de datos de depuración**, en el Panel Acciones, seleccione **Asignación de modelos** para comenzar a depurar desde este componente ER.
2. En el panel de origen de datos de la izquierda, seleccione la fuente de datos **\$notSentTransactions** y luego seleccione **Leer todos los registros**.

    Puede elegir **Leer 1 registro**, **Leer 10 registros**, **Leer 100 registros** o **Leer todos los registros** para forzar que se lea el número apropiado de registros desde la fuente de datos seleccionada. De esta manera, puede simular el acceso al origen de datos desde el formato ER en ejecución.

3. En el panel de datos de la derecha, seleccione **Expandir todo**.

    Puede ver que la fuente de datos seleccionada del tipo **Lista de registros** contiene un único registro.

4. Amplíe el origen de datos **\$TnotSentTransactions** y seleccione el método anidado **vendBankAccountInTransactionCompany ()**.
5. Amplíe el método **vendBankAccountInTransactionCompany()** y seleccione el campo anidado **IBAN**.
6. Seleccione **Obtener valor**.

    Puede elegir **Obtener valor** para forzar la lectura del valor de un campo seleccionado del origen de datos seleccionado. De esta manera, puede simular el acceso a este campo desde el formato ER en ejecución.

7. Seleccione **Expandir todo**.

    ![Valor del campo IBAN en la asignación del modelo](./media/er-data-debugger-debugging-model-mapping.png)

    Como puede ver, la asignación del modelo no es responsable de los espacios truncados, porque el código IBAN que devuelve para la cuenta bancaria del proveedor incluye espacios. Por lo tanto, debe continuar con la depuración del origen de datos.

### <a name="debug-the-format-mapping"></a>Depurar la asignación de formato

1. En la página **Fuentes de datos de depuración**, en el Panel Acciones, seleccione **Asignación de formato** para continuar depurando desde este componente ER.
2. Seleccione el origen de datos **\$PaymentByDebtor** y luego seleccione **Leer todos los registros**.
3. Expandir **\$PaymentByDebtor**.
4. Expandir **\$PaymentByDebtor.Lines** y luego seleccione **Leer todos los registros**.
5. Expanda **\$PaymentByDebtor.Lines.CreditorAccount**.
6. Expanda **\$PaymentByDebtor.Lines.CreditorAccount.Identification** y luego seleccione **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.
7. Seleccione **Obtener valor**.
8. Seleccione **Expandir todo**.

    ![Valor del campo IBAN en la asignación de formato](./media/er-data-debugger-debugging-format-mapping.png)

    Como puede ver, los orígenes de datos de la asignación de formato no son responsables de los espacios truncados, porque el código IBAN que devuelven para la cuenta bancaria del proveedor incluye espacios. Por lo tanto, debe continuar con la depuración del origen de datos.

### <a name="debug-the-format"></a>Depurar el formato

1. En la página **Orígenes de datos de depuración**, en el Panel Acciones, seleccione **Formato** para continuar depurando desde este componente ER.
2. Expanda los elementos de formato para seleccionar **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** y luego seleccione **Leer todos los registros**.
3. Expanda los elementos de formato para seleccionar **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** y luego seleccione **Leer todos los registros**.
4. Expanda los elementos de formato para seleccionar **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** y luego seleccione **Obtener valor**.
5. Seleccione **Expandir todo**.

    ![Valor del campo IBAN en el formato](./media/er-data-debugger-debugging-format.png)

   Como puede ver, el enlace de formato no es responsable de los espacios truncados, porque el código IBAN que devuelve para la cuenta bancaria del proveedor incluye espacios. Por lo tanto, el elemento **BankIBAN** está configurado para utilizar una transformación de formato que trunca espacios.

6. Cierre el depurador de origen de datos.

### <a name="review-the-format-transformations"></a>Revisar las transformaciones de formato

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, seleccione **Modelo de pago** \> **Transferencia de crédito ISO20022**.
3. Seleccione **Diseñador** y luego expanda los elementos de formato para seleccionar **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.

    ![Elemento BankIBAN de registro en la página Diseñador de formato](./media/er-data-debugger-referred-transformation.png)

    Como puede ver, el elemento **BankIBAN** está configurado para utilizar la transformación **eliminar no alfanumérico**.

4. Seleccione la pestaña **Transformaciones**.

    ![Pestaña Transformaciones para el elemento BankIBAN](./media/er-data-debugger-transformation.png)

    Como puede ver, la transformación **eliminar no alfanumérico** se configura para utilizar una expresión que trunca espacios de la cadena de texto que se proporciona.

## <a name="start-to-debug-in-the-operation-designer"></a>Comenzar a depurar en el Diseñador de operaciones

Cuando configura una versión de borrador del formato ER que se puede ejecutar directamente desde el Diseñador de operaciones, puede acceder al depurador de origen de datos seleccionando **Comenzar depuración** en el panel Acciones.

![Botón Iniciar depuración en la página Diseñador de formato](./media/er-data-debugger-run-from-designer.png)

La asignación de formato y los componentes de formato del formato ER que se está editando están disponibles para la depuración.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Comenzar a depurar en el Diseñador de asignación de modelo

Cuando configura una asignación del modelo ER que se puede ejecutar desde la página **Asignación de modelo**, puede acceder al depurador de origen de datos seleccionando **Comenzar depuración** en el panel Acciones.

![Botón Iniciar depuración en la página Diseñador de asignación de modelo](./media/er-data-debugger-run-from-designer-mapping.png)

El componente de asignación de modelo de la asignación ER que se está editando está disponible para la depuración.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>Apéndice 1: obtener una solución ER

### <a name="download-an-er-solution"></a>Descargar una solución ER

Si desea utilizar una solución de ER para generar un archivo de pago electrónico para un pago de proveedor que se procesa, puede [descargar](download-electronic-reporting-configuration-lcs.md) el formato de pago de ER **Transferencia de crédito ISO20022** disponible en la biblioteca Activos compartidos de Lifecycle Services (LCS) en Microsoft Dynamics o del repositorio global.

![Importación del formato de pago de ER en la página Repositorio de configuración](./media/er-data-debugger-import-from-repo.png)

Además del formato ER seleccionado, las siguientes [configuraciones](general-electronic-reporting.md#Configuration) deben importarse automáticamente a suinstancia de Microsoft Dynamics 365 Finance como parte de la solución ER **Transferencia de crédito ISO20022**:

- **Modelo de pago** [Configuración del modelo de datos de ER](general-electronic-reporting.md#DataModelComponent)
- [Configuración de formato ER](general-electronic-reporting.md#FormatComponentOutbound) de **Transferencia de crédito ISO20022**
- [Configuración de la asignación del modelo de ER](general-electronic-reporting.md#ModelMappingComponent) de la **Asignación de modelo de pago 1611**
- Configuración de la asignación del modelo de ER de la **Asignación de modelo de pago a destino ISO20022**

Puede encontrar estas configuraciones en la página **Configuraciones** del marco ER (**Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**).

![Configuraciones importadas en la página Configuraciones](./media/er-data-debugger-configurations.png)

Si falta alguna de las configuraciones enumeradas anteriormente en el árbol de configuración, debe descargarlas manualmente de la biblioteca Activos compartidos de LCS de la misma manera que descargó el formato de pago de ER **Transferencia de crédito ISO20022**.

### <a name="analyze-the-downloaded-er-solution"></a>Analizar la solución ER descargada

#### <a name="review-the-model-mapping"></a>Revisar la asignación de modelo

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Modelo de pago** \> **Asignación del modelo de pago 1611**.
3. Seleccione **Diseñador**.
4. Selecciona el registro de asignación **Asignación del modelo de pago ISO20022 CT**.
5. Seleccione **Diseñador** y luego revise la asignación de modelo que se abre.

    Tenga en cuenta que el campo **Pagos** del modelo de datos está vinculado al origen de datos **\$notSentTransactions** que devuelve la lista de líneas de pago de proveedores que se están procesando.

    ![Campo de pagos en la página Diseñador de asignación de modelo](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>Revisar la asignación de formato

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Modelo de pago** \> **Transferencia de crédito ISO20022**.
3. Seleccione **Diseñador**.
4. En la pestaña **Asignación**, revise la asignación de formato que se abre.

    Tenga en cuenta que el elemento **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** del archivo **ISO20022CTReports** \> **XMLHeader** está vinculado al origen de datos **\$PaymentByDebtor** que está configurado para agrupar registros de campo **Pagos** del modelo de datos.

    ![Elemento PmtInf de la página Diseñador de formato](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>Revisar el formato

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Modelo de pago** \> **Transferencia de crédito ISO20022**.
3. Seleccione **Diseñador** y luego revise el formato que se abre.

    Observe que el elemento de formato en **Documento** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** está configurado para introducir el código IBAN de la cuenta del proveedor en el archivo de pago.

    ![Elemento BankIBAN de registro en la página Diseñador de formato](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>Apéndice 2: configuración de proveedores

### <a name="modify-a-vendor-property"></a>Modificar una propiedad de proveedor

1. Vaya a **Proveedores** \> **Proveedores** \> **Todos los proveedores**.
2. Seleccione el proveedor **DE-01002** y, a continuación, en el panel Acciones, en la ficha **Proveedor**, en el grupo **Configurar**, seleccione **Cuentas bancarias**.
3. En la ficha desplegable **Identificación**, en el campo **IBAN**, <a name="enteredIBANcode"></a>introduzca **GB33 BUKB 2020 1555 5555 55**.
4. Seleccione **Guardar**.

![Campo IBAN establecido en la página Cuentas bancarias de proveedor](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Configurar un método de pago

1. Vaya a **Proveedores** \> **Configuración de pagos** \> **Formas de pago**.
2. Seleccione el método de pago **SEPA CT**.
3. En la ficha desplegable **Formatos de archivo**, en al sección **Formatos de archivo**, establezca la opción **Formato de exportación electrónica genérica** en **Sí**.
4. En el campo **Configuración de formato de exportación**, seleccione el formato ER **Transferencia de crédito ISO20022**.
5. Seleccione **Guardar**.

![Configuración de formatos de archivo en la página Métodos de pago](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Agregar un pago de proveedor

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.
2. Agregar un diario de pagos nuevo.
3. Seleccione **Líneas** y agregue una nueva línea de pago.
4. En el campo **Cuenta**, seleccione el proveedor **DE-01002**.
5. En el campo **Débito**, introduzca un valor.
6. En el campo **Método de pago**, seleccione **SEPA CT**.
7. Seleccione **Guardar**.

![Pago de proveedor agregado en la página Pagos a proveedores](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>Apéndice 3: procesar un pago a proveedor

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.
2. En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que creó anteriormente y luego seleccione **Líneas**.
3. Seleccione la línea de pago y, a continuación, seleccione **Estado de pago** \> **Ninguno**.
4. Seleccione **Generar pagos**.
5. En el campo **Método de pago**, seleccione **SEPA CT**.
6. En el campo **Cuenta bancaria**, seleccione **DEMF OPER**.
7. En el cuadro de diálogo **Generar pagos**, seleccione **Aceptar**.
8. En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]