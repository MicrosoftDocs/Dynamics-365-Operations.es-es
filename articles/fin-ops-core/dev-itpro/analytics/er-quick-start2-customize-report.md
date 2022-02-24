---
title: Ajustar un formato ER para generar un documento electrónico personalizado
description: Este tema explica cómo ajustar un formato de informe electrónico (ER) proporcionado por Microsoft para que genere un documento electrónico personalizado.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20e7a32ac5f6ab21f89ed3c11c64458286864c9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680179"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>Ajustar un formato ER para generar un documento electrónico personalizado

[!include[banner](../includes/banner.md)]

Los procedimientos en este tema explican cómo un usuario con el rol de administrador del sistema o consultor funcional de informes electrónicos puede realizar estas tareas:

- Configurar los parámetros para el [marco de informes electrónicos (ER)](general-electronic-reporting.md).
- Importe configuraciones de ER proporcionadas por Microsoft y utilizadas para generar un archivo de pago mientras se procesa un [pago del vendedor](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md).
- Cree una versión personalizada de una configuración de formato ER estándar proporcionada por Microsoft.
- Modifique la configuración del formato ER personalizado para que genere archivos de pago que cumplan con los requisitos de un banco específico.
- Adopte los cambios realizados en la configuración de formato ER estándar en la configuración de formato ER personalizada.

Todos los siguientes procedimientos se pueden hacer en el **GBSI** de la empresa. No se requiere codificación.

- [Configurar el marco ER](#ConfigureFramework)

    - [Configurar los parámetros de ER](#ConfigureParameters)
    - [Activar un proveedor de configuración de ER](#ActivateProvider)

        - [Revise la lista de proveedores de configuración de ER](#ReviewProvidersList)
        - [Añada una nueva configuración para el proveedor de ER](#ActivateProvider)
        - [Activar un proveedor de configuración de ER](#ActivateAddedProvider)

- [Importar configuraciones del formato estándar de ER](#ImportERSolution1)

    - [Importar configuraciones estándar de ER](#ImportERFormat1)
    - [Revisar las configuraciones importadas de ER](#ReviewImportedERSolution)

- [Preparar un pago a proveedor para el procesado](#PrepareVendorPayment)

    - [Agregar información bancaria a una cuenta de proveedor](#AddBankAccount)
    - [Introducir un pago de proveedor](#EnterVendorPayment)

- [Procesar un pago de proveedor utilizando el formato ER estándar](#ProcessVendorPayment1)

    - [Configurar la forma de pago electrónico](#ConfigureMethodOfPayment1)
    - [Procesar un pago de proveedor](#ProcessPayment1)

- [Personalizar el formato ER estándar](#CustomizeProvidedFormat)

    - [Crear un formato personalizado](#DeriveProvidedFormat)
    - [Editar un formato personalizado](#ConfigureDerivedFormat)
    - [Marcar un formato personalizado como ejecutable](#MarkFormatRunnable)

- [Procesar un pago de proveedor utilizando el formato ER personalizado](#ProcessVendorPayment2)

    - [Configurar la forma de pago electrónico](#ConfigureMethodOfPayment2)
    - [Procesar un pago de proveedor](#ProcessPayment2)

- [Importar nuevas versiones de las configuraciones del formato estándar de ER](#ImportERSolution2)

    - [Importar nuevas versiones de las configuraciones estándar de ER](#ImportERFormat2)
    - [Revisar las configuraciones de formato importadas de ER](#ReviewImportedERFormat)

- [Adoptar los cambios en la nueva versión de un formato importado en un formato personalizado](#AdoptNewBaseVersion)

    - [Completar la versión actual de borrador de un formato personalizado](#CompleteDerivedFormat)
    - [Reorganizar un formato personalizado a una nueva versión base](#RebaseDerivedFormat)
    - [Procesar un pago de proveedor utilizando un formato de ER reorganizado](#ProcessPayment3)

- [Recursos adicionales](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurar el marco ER

Como usuario en el rol de Consultor Funcional de Informes Electrónicos, debe configurar el conjunto mínimo de parámetros de ER antes de comenzar a usar el marco de ER para diseñar una versión personalizada de un formato de ER estándar.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurar los parámetros de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.
3. En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.
4. En la pestaña **Adjuntos**, establezca los parámetros siguientes:

    - En el campo **Configuraciones**, seleccione el tipo **Archivo** para el **USMF** de la empresa.
    - En los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros**, seleccione el tipo **Archivo**.

Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Activar un proveedor de configuración de ER

Cada configuración de ER que se agrega está marcada como propiedad de un proveedor de configuración de ER. El proveedor de configuración de ER que se activa en el espacio de trabajo **Informes electrónicos** se utiliza para este propósito. Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.

> [!NOTE]
> Solo el propietario de una configuración de ER puede editarla. Por lo tanto, antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Revise la lista de proveedores de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Tabla de proveedor de configuración**, cada registro de proveedor tiene un nombre y URL únicos. Revise el contenido de esta página. Si un registro para **Litware, Inc.** (`https://www.litware.com`) ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Añada una nueva configuración para el proveedor de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Proveedores de configuración**, seleccione **Nuevo**.
4. En el campo **Nombre**, introduzca **Litware, Inc.**
5. En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.
6. Seleccione **Guardar**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Activar un proveedor de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Litware, Inc.** y luego seleccione **Establecer activo**.

Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importar configuraciones del formato estándar de ER

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>Importar configuraciones estándar de ER

Para agregar las configuraciones ER estándar a su instancia actual de Microsoft Dynamics 365 Finance, debe importarlos desde el [repositorio](general-electronic-reporting.md#Repository) de ER que se configuró para esa instancia.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de Microsoft.
3. En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**. Si se le solicita autorización para conectarse al Regulatory Configuration Service, siga las instrucciones de autorización.
4. En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **BACS (UK)**.
5. En la ficha desplegable **Versiones**, seleccione la versión **1.1** de la configuración de ER seleccionada.
6. Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a la instancia actual de Finance.

![Página de configuración del repositorio](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> Si tiene problemas para acceder al [Repositorio global](er-download-configurations-global-repo.md), puede [descargar configuraciones](download-electronic-reporting-configuration-lcs.md) de Microsoft Dynamics Lifecycle Services (LCS) en su lugar.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Revisar las configuraciones importadas de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago**.
4. Tenga en cuenta que, además del formato de ER **BACS (Reino Unido)**, se importaron otras configuraciones ER necesarias. Asegúrese de que las siguientes configuraciones de ER estén disponibles en el árbol de configuración:

    - **Modelo de pago** - Esta configuración contiene el [modelo de datos](general-electronic-reporting.md#data-model-and-model-mapping-components) del componente ER que representa la estructura de datos del dominio comercial de pago.
    - **Asignación del modelo de pago 1611** - Esta configuración contiene el [asignado de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) del componente ER que describe cómo se completa el modelo de datos con los datos de la aplicación en tiempo de ejecución.
    - **BACS (Reino Unido)** - Esta configuración contiene el [formato](general-electronic-reporting.md#FormatComponentOutbound) y asignación de formato de componentes ER. El componente de formato especifica el diseño del informe. El componente de asignación de formato contiene la fuente de datos del modelo y especifica cómo se completa el diseño del informe utilizando esta fuente de datos en tiempo de ejecución.

![Página Configuraciones](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Preparar un pago a proveedor para el procesado

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Agregar información bancaria a una cuenta de proveedor

Debe agregar información bancaria para una cuenta de proveedor a la que se hará referencia más adelante en un pago registrado.

1. Vaya a **Proveedores** \> **Proveedores** \> **Todos los proveedores**.
2. En la página **Todos los proveedores**, seleccione la cuenta de proveedor **GB_SI_000001**, y luego, en el panel de acciones, en la pestaña **Proveedor**, en el grupo **Configurar**, seleccione **cuentas bancarias**.
3. En la página **Cuentas bancarias de proveedores**, seleccione **Nueva** y luego introduzca la siguiente información:

    1. En el campo **Cuenta bancaria**, introduzca **GBP OPER**.
    2. En el **Grupos de bancos** campo, introduzca **BankGBP**.
    3. En el campo **Número de cuenta bancaria** introduzca **202015**.
    4. En el campo **Código SWIFT**, introduzca <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.
    5. En el campo **IBAN**, introduzca **GB33BUKB20201555555555**.
    6. En el campo **Número de ruta**, conserve el valor predeterminado <a id="DefineRoutingNumber"></a>**123456**.

    ![Página de cuentas bancarias del proveedor](./media/er-quick-start2-bank-account.png)

4. Seleccione **Guardar**.
5. Cierre la página.
6. En la página **Todos los proveedores**, abra la cuenta de proveedor **GB_SI_000001**.
7. En la página de detalles del proveedor, seleccione **Editar** para hacer que la página sea editable, si es necesario.
8. En la ficha desplegable **Pago**, en el campo **Cuenta bancaria**, seleccione **GBP OPER**.

    ![Página de detalles del proveedor](./media/er-quick-start2-bank-account-reference.png)

9. Seleccione **Guardar**.
10. Cierre la página.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Introducir un pago de proveedor

Debe introducir un pago de proveedor nuevo usando una [propuesta de pago](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.
2. En la página **Diario de pago de proveedor**, seleccione **Nuevo**.
3. En el campo **Nombre**, seleccione **VendPay**.
4. Seleccionar **Líneas**.
5. Seleccione **Propuesta de pago** \> **Crear propuesta de pago**.
6. En el cuadro de diálogo **Propuesta de pago del proveedor**, configure condiciones para filtrar registros para solo la cuenta de proveedor **GB_SI_000001** y después seleccione **Aceptar**.
7. Seleccione la línea para la factura **00000007_Inv** y luego seleccione **Crear pago**.

    ![Ventana de diálogo de propuesta de pago de proveedor](./media/er-quick-start2-payment-proposal.png)

8. Verifique que el pago introducido esté configurado para usar la forma de pago **Electrónico**.

    ![Página Pagos a proveedores](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Procesar un pago de proveedor utilizando el formato ER estándar

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Configurar la forma de pago electrónico

Debe configurar el método de pago electrónico para que use la configuración de formato ER importada.

1. Vaya a **Proveedores** \> **Configuración de pagos** \> **Formas de pago**.
2. En la página **Métodos de pago - proveedores**, seleccione el método de pago **Electrónico** en el panel izquierdo.
3. Seleccione **Editar**.
4. En la ficha desplegable **Formatos de archivo**, establezca la opción **Formato de exportación electrónica general** en **Sí**.
5. En el campo **Configuración de formato de exportación**, seleccione la configuración de formato **BACS (Reino Unido)**.

    ![Métodos de pago - página de proveedores](./media/er-quick-start2-method-of-payment1.png)

6. Seleccione **Guardar**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Procesar un pago de proveedor

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.
2. En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que agregó anteriormente y luego seleccione **Líneas**.
3. En la página **Pagos de proveedores** página, seleccione **Generar pagos**.
4. En el cuadro de diálogo **Generar pagos**, especifique la siguiente información:

    - En el campo **Método de pago**, seleccione **Electrónico**.
    - En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.

5. Seleccione **Aceptar**.
6. En el cuadro de diálogo **Parámetros de informes electrónicos**, establezca la opción **Imprimir informe de control** a **Sí** y luego seleccione **Aceptar**.

    ![Página Parámetros de notificación electrónica](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > Además del archivo de pago, ahora puede generar el informe de control.

7. Descargue el archivo zip y luego extraiga los siguientes archivos:

    - El informe de control en formato Excel
    - El archivo de pago en formato TXT

        Tenga en cuenta que según la [estructura](#PositionRoutingNumber) del formato ER proporcionado, la línea de pago en el archivo generado comienza con el número de ruta que fue [definido](#DefineRoutingNumber) para la cuenta bancaria configurada.

        ![Archivo de pago en formato TXT](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personalizar el formato ER estándar

Para el ejemplo que se muestra en esta sección, desea utilizar las configuraciones de ER que proporciona Microsoft para generar archivos de pago de proveedores en formato BACS, pero debe agregar una personalización para admitir los requisitos de un banco específico. También desea poder actualizar su formato personalizado cuando estén disponibles nuevas versiones de configuraciones de ER. Sin embargo, desea poder realizar la actualización al menor costo.

En este caso, como representante de Litware, Inc., debe crear (derivar) una nueva configuración de formato ER utilizando **BACS (Reino Unido)**, configuración proporcionada por Microsoft como base.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Crear un formato personalizado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido)**. Litware, Inc. utilizará la versión 1.1 de esta configuración de formato ER como base para la versión personalizada.
3. Seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable. Puede usar este cuadro de diálogo para crear una nueva configuración para un formato de pago personalizado.
4. En el grupo de campos **Nuevo**, seleccione la opción **Derivar del nombre: BACS (Reino Unido), Microsoft**.
5. En el campo **Nombre**, introduzca **BACS (Reino Unido personalizado)**.

    ![Cuadro de diálogo desplegable Crear configuración](./media/er-quick-start2-add-derived-format.png)

6. Seleccionar **Crear configuración**.

Se creará la versión 1.1.1 del formato de configuración de ER **BACS (personalizado del Reino Unido)**. Esta versión tiene un [estado](general-electronic-reporting.md#component-versioning) de **Borrador** y puede editarse. El contenido actual de su formato ER personalizado coincide con el contenido del formato proporcionado por Microsoft.

![Página Configuraciones](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Editar un formato personalizado

Debe configurar su formato personalizado para que cumpla con los requisitos específicos del banco. Por ejemplo, un banco puede requerir que los archivos de pago que se generan incluyan el código SWIFT (Society for Worldwide Interbank Financial Telecommunication) de un banco al que se le asigna la función de agente en el pago del proveedor procesado. Los códigos SWIFT son códigos bancarios internacionales que identifican bancos específicos en todo el mundo. También se conocen como códigos de identificación bancaria (BIC). El código SWIFT debe tener 11 caracteres y debe introducirse al comienzo de cada línea de pago en un archivo de pago generado.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido personalizado)**.
3. En la ficha desplegable **Versiones**, seleccione la versión **1.1.1** de la configuración seleccionada.
4. Seleccione **Diseñador**.
5. En la página del **Diseñador de formato**, seleccione **Mostrar detalles** para ver más información sobre los elementos de formato.
6. Expanda y revise los siguientes elementos:

    - El elemento **BACSReportsFolder** del tipo **Carpeta**. Este elemento se utiliza para generar resultados en formato ZIP.
    - El elemento **archivo** del tipo **Archivo**. Este elemento se utiliza para generar un archivo de pago en formato TXT.
    - El elemento **transacciones** del tipo **Secuencia**. Este elemento se utiliza para generar una línea de pago único en archivo de pago.
    - El elemento **transacción** del tipo **Secuencia**. Este elemento se utiliza para generar campos individuales de una línea de pago único.

7. Seleccione el elemento **transacción**.

    ![Elemento de transacción en el diseñador de operaciones de ER](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > El informe proporcionado se configura de modo que <a id="PositionRoutingNumber"></a>cada línea de pago comienza con el número de ruta bancaria. El elemento de formato **vendBankRouteNum** se utiliza para este propósito. 

8. Seleccione **Agregar** y luego seleccione el tipo **Texto\\Cadena** del elemento de formato que está agregando:

    1. En el campo **Nombre**, introduzca **vendBankSWIFT**.
    2. En el campo **Longitud mínima**, introduzca **11**.
    3. En el campo **Longitud máxima**, introduzca **11**.
    4. Seleccione **Aceptar**.

    > [!NOTE]
    > El elemento **vendBankSWIFT** se usará para introducir el código SWIFT de un banco de proveedores en los archivos generados.

9. En el árbol de estructura de formato, seleccione **vendBankSWIFT**.
10. Seleccione **Ascender** para mover el elemento de formato seleccionado un nivel hacia arriba. Repita este paso hasta que el elemento **vendBankSWIFT** es el <a id="PositionSWIFTCode"></a>primer elemento debajo del elemento primario **transacción**.

    ![VendBankSWIFT como el primer elemento bajo transacción en el diseñador de operaciones de ER](./media/er-quick-start2-derived-format1.png)

11. Mientras **vendBankSWIFT** está todavía está seleccionado en el árbol de estructura de formato, seleccione la pestaña **Asignación** y luego expanda la fuente de datos **modelo**.
12. Expanda **model.Payment** \> **model.Payment.CreditorAgent** y seleccione el campo de fuente de datos **model.Payment.CreditorAgent.BICFI**. Este campo de fuente de datos expone el código SWIFT de un banco proveedor al que se le asigna el rol de agente en el pago del proveedor procesado.
13. Seleccione **Enlazar**. El elemento de formato **vendBankSWIFT** ahora está vinculado con el campo de fuente de datos **model.Payment.CreditorAgent.BICFI** para que los códigos SWIFT se introduzcan en los archivos de pago generados.

    ![El elemento de formato vendBankSWIFT vinculado con el campo de origen de datos model.Payment.CreditorAgent.BICFI en el diseñador de operaciones de ER](./media/er-quick-start2-derived-format2.png)

14. Seleccione **Guardar**.
15. Cierre la página del diseñador.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Marcar un formato personalizado como ejecutable

Ahora que se ha creado la primera versión de su formato personalizado y tiene un estado de **Borrador**, puede ejecutarlo con fines de prueba. Para ejecutar el informe, debe procesar un pago de proveedor utilizando el método de pago que se refiere a su formato ER personalizado. De forma predeterminada, cuando llama a un formato de ER desde la aplicación, las únicas versiones que tienen un estado de **Completado** o **Compartido** son las que se [consideran](general-electronic-reporting.md#component-versioning). Este comportamiento ayuda a evitar el uso de formatos ER que tienen diseños inacabados. Sin embargo, para sus ejecuciones de prueba, puede obligar a la aplicación a usar la versión de su formato ER que tenga un estado de **Borrador**. De esta manera, puede ajustar la versión del formato actual si se requieren modificaciones. Para obtener más información, consulte [Aplicabilidad](electronic-reporting-destinations.md#applicability).

Para utilizar la versión borrador de un formato ER, debe marcar de forma explícita el formato ER.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.
4. Seleccione **Editar** para hacer que la página actual sea editable, según sea necesario.
5. En el árbol de configuración en el panel izquierdo, seleccione **BACS (Reino Unido personalizado)**.
6. Establezca la opción **Ejecutar borrador** en **Sí**.

    ![Opción Ejecutar borrador en la página Configuraciones](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Procesar un pago de proveedor utilizando el formato ER personalizado

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Configurar la forma de pago electrónico

Debe configurar el método de pago electrónico para que se utilice su formato ER personalizado para procesar los pagos del proveedor.

1. Vaya a **Proveedores** \> **Configuración de pagos** \> **Formas de pago**.
2. En la página **Métodos de pago - proveedores**, seleccione el método de pago **Electrónico** en el panel izquierdo.
3. Seleccione **Editar**.
4. En la ficha desplegable **Formato de archivo**, establezca la opción **Formato de exportación electrónica general** en **Sí**.
5. En el campo **Configuración de formato de exportación**, seleccione la configuración de formato **BACS (Reino Unido personalizado)**.

    ![Métodos de pago - página de proveedores](./media/er-quick-start2-method-of-payment2.png)

6. Seleccione **Guardar**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Procesar un pago de proveedor

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.
2. En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que creó anteriormente.
3. Seleccionar **Líneas**.
4. En la página **Pagos de proveedores**, sobre la cuadrícula, seleccione **Estado de pago** \> **Ninguno**.
5. Seleccione **Generar pago**.
6. En el cuadro de diálogo **Generar pagos**, especifique la siguiente información:

    - En el campo **Método de pago**, seleccione **Electrónico**.
    - En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.

7. Seleccione **Aceptar**.
8. En el cuadro de diálogo **Parámetros de informes electrónicos**, establezca la opción **Imprimir informe de control** a **Sí** y luego seleccione **Aceptar**.

    > [!NOTE]
    > Además del archivo de pago, solo puede generar el informe de control.

9. Descargue el archivo zip y luego extraiga los siguientes archivos:

    - El informe de control en formato Excel
    - El archivo de pago en formato TXT

        Observe que, de acuerdo con la estructura de su formato ER personalizado, la línea de pago en el archivo generado ahora [empieza](#PositionSWIFTCode) con el código SWIFT que [introdujo](#DefineSWIFTCode) para la cuenta bancaria del proveedor cuyo pago ha sido procesado.

        ![Archivo de pago en formato TXT](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>Importar nuevas versiones de las configuraciones del formato estándar de ER

Para el ejemplo que se muestra en esta sección, recibirá una notificación sobre el artículo de Knowledge Base [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). Esta notificación le informa sobre la nueva versión del formato de ER **BACS (Reino Unido)** que ha sido publicado por Microsoft. Además del informe de control, esta nueva versión permite a los usuarios generar el informe de aviso de pago y el informe de la nota de asistencia mientras se procesa el pago de un proveedor. Desea comenzar a usar esa funcionalidad.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>Importar nuevas versiones de las configuraciones estándar de ER

Para agregar nuevas versiones de las configuraciones ER a su instancia actual de Finance, debe importarlos desde el [repositorio](general-electronic-reporting.md#Repository) de ER que configuró para esa instancia.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de Microsoft.
3. En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**. Si se le solicita autorización para conectarse al Regulatory Configuration Service, siga las instrucciones de autorización.
4. En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **BACS (UK)**.
5. En la ficha desplegable **Versiones**, seleccione la versión **3.3** de la configuración de ER seleccionada.
6. Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a la instancia actual de Finance.

![Página de configuración del repositorio](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> Si tiene problemas para acceder al [Repositorio global](er-download-configurations-global-repo.md), puede [descargar configuraciones](download-electronic-reporting-configuration-lcs.md) de LCS en su lugar.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Revisar las configuraciones de formato importadas de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido)**.
4. En la ficha desplegable **Versiones**, seleccione la versión **3.3**.
5. Seleccione **Diseñador**.
6. Sobre la página **Diseñador de formatos** página, expanda el elemento de formato **BACSReportsFolder**.
7.  Tenga en cuenta que la versión 3.3 contiene el elemento de formato **PaymentAdviceReport** que se utiliza para generar un informe de aviso de pago cuando se procesa un pago de proveedor.

    ![Elemento de formato PaymentAdviceReport en el diseñador de operaciones de ER](./media/er-quick-start2-imported-solution2.png)

8. Cierre la página del diseñador.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Adoptar los cambios en la nueva versión de un formato importado en un formato personalizado

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Completar la versión actual de borrador de un formato personalizado

Si desea mantener el estado actual de su formato personalizado, complete el borrador de la versión 1.1.1 cambiando su estado de **Borrador** a **Completado**.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago**, expanda **BACS (Reino Unido)** y seleccione **BACS (Reino Unido personalizado)**.
4. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 1.1.1 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 1.1.2, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en su formato ER personalizado.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Reorganizar un formato personalizado a una nueva versión base

Para comenzar a utilizar la nueva funcionalidad de la versión 3.3 del formato **BACS (Reino Unido)** en su personalización, debe cambiar la versión de configuración básica para la configuración personalizada, **BACS (personalizado del Reino Unido)**. Este proceso se conoce como [reorganización](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase). En lugar de la versión 1.1 de **BACS (Reino Unido)**, use la nueva versión 3.3.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **BACS (Reino Unido personalizado)**.
3. En la ficha desplegable **Versiones**, seleccione versión **1.1.2** y luego seleccione **Reorganizar**.
4. En el cuadro de diálogo **Reorganizar**, en el campo **Versión de destino**, seleccione la versión **3.3** de la configuración base para aplicarla como la nueva base y usarla para actualizar la configuración.

    ![Cuadro de diálogo Cambiar de base](./media/er-quick-start2-rebase1.png)

5. Seleccione **Aceptar**.
6. Observe que el número de la versión borrador ha cambiado de **1.1.2** a **3.3.2** para reflejar el cambio en la versión base.

    Cuando se combinaron la versión personalizada y la nueva versión base, puede que se hayan descubierto algunos conflictos debidos a los cambios de formato que no se pueden combinar automáticamente.

    ![Configuración reorganizada con conflictos en la página Configuraciones](./media/er-quick-start2-rebase2.png)

    Si se descubren conflictos, deben resolverse manualmente en el diseñador de formatos.

7. En la ficha desplegable **Versiones**, seleccione la versión **3.3.2**.
8. Seleccione **Diseñador**.
9. En la página **Diseñador de formatos**, en la ficha desplegable **Detalles**, seleccione un registro de conflicto de reorganización y luego seleccione **Aplicar valor base**.

    ![Registro de conflicto de reorganización en el diseñador de operaciones de ER](./media/er-quick-start2-rebase3.png)

10. Seleccione **Guardar**.

    El registro de conflicto de reorganización ya no debería aparecer en la ficha desplegable **Detalles**.

    ![Conflicto resuelto en el diseñador de operaciones de ER](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Usted resolvió el conflicto confirmando que la versión 3 del modelo base debe usarse en este formato ER.

11. Expandir **BACSReportsFolder** \> **archivo** \> **transacciones** \> **transacción**.
12. En la pestaña **Asignación**, observe que la versión 3.3.2 de su formato ER personalizado contiene tanto su personalización (el elemento de formato **vendBankSWIFT** y su vinculación) y la nueva funcionalidad de la versión 3.3 del formato ER básico que proporcionó Microsoft (el elemento de formato **PaymentAdviceReport** junto con sus elementos anidados y enlaces configurados). Con solo unas pocas pulsaciones del ratón, adoptó las modificaciones de una nueva versión base fusionándolas con su personalización.

    ![Formato combinado en el diseñador de operaciones ER](./media/er-quick-start2-rebase5.png)

13. Cierre la página del diseñador.

> [!NOTE]
> La acción de reorganización es reversible. Para cancelar esta reorganización, seleccione la versión **1.1.1** del formato **BACS (Reino Unido personalizado)** en la ficha desplegable **Versiones** y luego seleccione **Obtener esta versión**. La versión 3.3.2 se volverá a numerar 1.1.2 y el contenido de la versión borrador 1.1.2 coincidirá con el contenido de la versión 1.1.1.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Procesar un pago de proveedor utilizando un formato de ER reorganizado

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos a proveedores**.
2. En la página **Diario de pagos a proveedores**, seleccione el diario de pagos que creó anteriormente.
3. Seleccionar **Líneas**.
4. En la página **Pagos de proveedores**, sobre la cuadrícula, seleccione **Estado de pago** \> **Ninguno**.
5. Seleccione **Generar pago**.
6. En el cuadro de diálogo **Generar pagos**, especifique la siguiente información:

    - En el campo **Método de pago**, seleccione **Electrónico**.
    - En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.

7. Seleccione **Aceptar**.
8. En el cuadro de diálogo **Parámetros de informe electrónico**, especifique la siguiente información:

    - Establezca la opción **Imprimir informe de control** en **Sí**.
    - Establezca la opción **Imprimir** en **Sí**.

    ![Cuadro de diálogo Parámetros de notificación electrónica](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > Además del archivo de pago, ahora puede generar tanto el informe de control como el informe de aviso de pago.

9. Seleccione **Aceptar**.
10. Descargue el archivo zip y luego extraiga los siguientes archivos:

    - El informe de control en formato Excel
    - El informe de aviso de pago en formato Excel

        ![Informe de aviso de pago en formato Excel](./media/er-quick-start2-payment-advice-report.png)

    - El archivo de pago en formato TXT

        Observe que la línea de pago en el archivo generado ahora empieza con el código SWIFT que introdujo para la cuenta bancaria de un proveedor cuyo pago ha sido procesado.

        ![Archivo de pago en formato TXT](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Descargar configuraciones ER de Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Descargue las configuraciones de ER del repositorio global del servicio de configuración](er-download-configurations-global-repo.md)
