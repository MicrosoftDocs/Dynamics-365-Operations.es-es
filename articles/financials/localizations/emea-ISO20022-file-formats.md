---
title: "Importación de archivos ISO20022"
description: "Este tema explica cómo importar archivos de pago de formatos camt.054 y pain.002 ISO 20022 a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: neserovleo
manager: AnnBe
ms.date: 07/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode, CustBankAccounts, VendPaymMode, VendBankAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Italy, Latvia, Lithuania, Norway, Poland, Spain, Sweden, Switzerland, United Kingdom
ms.author: v-lenest
ms.search.validFrom: 2017-06-01
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 07d09512ef612b41bf527b74496fa440f23851fc
ms.openlocfilehash: 1492e4d8220a3d515145d97ef8dad048727d97c8
ms.contentlocale: es-es
ms.lasthandoff: 02/14/2018

---

# <a name="import-iso20022-files"></a>Importar archivos ISO20022

[!include[banner](../includes/banner.md)]

Puede importar archivos de pago que tienen los siguientes formatos:

 - **Aviso de crédito ISO20022 camt.054**: se importan pagos entrantes de un archivo en este formato al diario de pagos de cliente.
 - **Devolución del estado ISO20022 pain.002** y **Aviso de débito ISO20022 camt.054**: se importan archivos de devolución al diario de transferencia de pagos de proveedores.

## <a name="prerequisites-for-importing-the-camt054-credit-advice-file"></a>Requisitos previos para importar el archivo de aviso de crédito camt.054
Debe completar los requisitos previos siguientes para importar mensajes de notificación del banco en el formato camt.054.001.002 al diario de pagos de cliente.

1. Importe la configuración de informes electrónicos (ER) **ISO20022 camt.054** de Microsoft Dynamics Lifecycle Services (LCS). A continuación, en la página **Método de pago del cliente**, en el campo **Configuración de formato de importación**, seleccione esa configuración. Para obtener más información, consulte [Formatos de archivo para métodos de pago](emea-select-file-formats-for-the-method-of-payments.md).
2. En la página **Todos los clientes**,escriba un nombre y un número de organización para cada cliente.
3. En la página **Cuenta bancaria de cliente**, configure un registro de cuenta bancaria del cliente especificando la siguiente información: IBAN o número de cuenta bancaria, y código SWIFT o número de ruta.
4. En la página **Cuentas bancarias**, configure cuentas bancarias de entidades jurídicas especificando la siguiente información: IBAN o número de cuenta bancaria, y código SWIFT o número de ruta, divisa y dirección.

    > [!NOTE]
        > Si tiene previsto usar la conciliación bancaria avanzada, en la ficha desplegable **Conciliación**, establezca la opción **Conciliación bancaria avanzada** en **Sí**. Si pretende conciliar pagos importados sin registrar, establezca la opción **Usar extractos bancarios como confirmación de pagos electrónicos** en **Sí**.

5. Opcional: En la página **Asignación de código de transacción**, configure la asignación entre los códigos de transacción bancaria en los tipos de archivo y de transacción bancaria.
6. Si el archivo contiene gastos de transacción que desea registrar junto con el pago de entrada, cree una cuota de pago en la página **Cuota de pago del cliente**. A continuación, en la página **Formas de pago**, asocie la cuota de pago con la cuenta bancaria en la configuración de cuota de pago.
7. Si los pagos ESR son importados y contienen las referencias de ISR (aplicables para las entidades jurídicas en Suiza), complete la configuración siguiente:

    - En el campo **Pagos de cliente, longitud de la cuenta** , especifique la longitud del código de cliente que se usa en las referencias de ISR o para la identificación automática del cliente.
    - Asegúrese de que el número de cliente y el número de factura (secuencias numéricas) contienen únicamente dígitos. No deben contener ningún otro carácter. El número de factura no debe tener ceros iniciales.
    - Escriba el ESR, el BESR y el número de ruta de la cuenta bancaria de la entidad jurídica. Para obtener más información consulte la [característica ESR heredada](emea-che-esr-customer-payments-import.md), ya que se requiere una configuración similar.
    
## <a name="import-the-camt054-credit-advice-file-into-the-customer-payment-journal"></a>Importación del archivo de aviso de crédito camt.054 al diario de pagos de cliente
1. En la página **Líneas de diario de pago del cliente** , haga clic en **Funciones** > **Pagos de importación**.
2. Seleccione el método de pago que tenga la configuración necesaria para el formato ISO20022 camt.054.
3. Especifique los parámetros exigidos y la ruta del archivo y, a continuación, haga clic en **Aceptar**. El archivo se importa.

## <a name="prerequisites-for-importing-files-in-the-pain002-status-return-and-camt054-debit-advice-formats-into-the-ap-payment-transfer-journal"></a>Requisitos previos para importar archivos en los formatos de aviso de débito camt.054 y devolución de estado pain.002 al diario de transferencia de pagos de proveedores.
Debe completar los requisitos previos siguientes para importar mensajes del banco en los siguientes formatos ISO20022 a la página **Transferencia de pago de proveedor**: mensajes de devolución de estado pain.002.001.003 y aviso de débito camt.054.001.002.

1. Importe las configuraciones de ER **ISO20022 camt.054** e **ISO20022 pain.002** del LCS.
2. En la página **Método de pago de proveedor** , en los campos **Configuración del formato de devolución** y **Configuración secundaria del formato de devolución** , seleccione las configuraciones de ER que importó. Tendrá que activar el formato de devolución genérico electrónico de la forma de pago seleccionada.
3. En la página **Asignación del estado del formato de la devolución**, configure la asignación de códigos de estado entre los estados pain.002 y los estados del diario de pagos a proveedores.

    A continuación se muestra un ejemplo de una configuración de estado.

    Restablecer estado | Estado de pago
    --------------|---------------
    RJCT          | Rechazado
    ACCP          | Aceptada
    ACSP          | Recibida

4. En la página **Códigos de error del formato de devolución**, configure los códigos de error de pain.002 y las descripciones de acuerdo con códigos de motivo de estado ISO20022 externos.

    A continuación se indica un ejemplo de una parte de una configuración de código de error.

    Código | Nombre
    -----|-----
    AC01 | IncorrectAccountNumber
    AC02 | InvalidDebtorAccountNumber
    AC03 | InvalidCreditorAccountNumber
    AC04 | ClosedAccountNumber
    AC05 | ClosedDebtorAccountNumber
    AC06 | BlockedAccount

5. Si el archivo camt.054 contiene gastos de transacción que desea registrar junto con el pago de entrada, cree una cuota de pago en la página **Cuota de pago a proveedores**. A continuación, en la página **Formas de pago**, asocie la cuota de pago con la cuenta bancaria en la configuración de cuota de pago.

## <a name="import-the-pain002-status-return-or-camt054-debit-advice-files-into-the-vendor-payment-journal"></a>Importe los archivos de retorno de estado pain.002 o de aviso de débito camt.054 al diario de pagos a proveedores
1. Abra la página **Transferencias de pago** en el menú Proveedores.
2. En la página **Transferencias de pagos**, haga clic en **Devolver archivo - Proveedor**.
3. Seleccione el método de pago que tenga la configuración necesaria para los archivos ISO20022 y haga clic en **Aceptar**.
4. Seleccione el formato de archivo que pretende importar y, a continuación haga clic en **Aceptar**.
5. Especifique los parámetros exigidos y la ruta del archivo y, a continuación, haga clic en **Aceptar**.

Si está importando el archivo pain.002, se actualizarán el estado de líneas de pago del proveedor, basándose en la información del archivo importado.

Si está importando el archivo camt.054, especifique los parámetros adicionales siguientes:

- **Id. de cuota**: permite especificar el identificador de cuota que definirá las nuevas líneas de cuota de pago, que se crearán en la línea del diario de pagos a proveedores si hay un importe de gasto en el archivo camt.054.
- **Nuevo nombre de diario** y **Descripción del nuevo diario** permiten especificar el nombre y la descripción del diario al que las transacciones procesadas se transferirán. Después de la transferencia, deben asignarse nuevos números de asiento al nuevo diario.
- **Importar transacciones de adeudo directo** Establezca esta opción en **Sí** si los débitos directos salientes deben importarse al diario de pagos a proveedores.
- **Nombre del diario** Permite definir un nuevo nombre de diario para transacciones de débito directo importadas.
- **Liquidar transacciones** Establezca esta opción en **Sí** si los pagos importados de proveedor se deben liquidar con las facturas que se encuentran en el sistema.

Puede ver la información importada en la página **Transferencias de pago**. 

## <a name="additional-details"></a>Más detalles

Al importar una configuración del formato de LCS, se importa el árbol entero de la configuración, lo que significa que las configuraciones Modelo y asignaciones Modelo se incluyen. En el modelo de pago a partir de la versión 8, las asignaciones están ubicadas en distintas configuraciones de ER en la solución de árbol (asignación modelo 1611 de pago, asignación modelo al destino ISO20022 de pago, etc.). Hay muchos diversos formatos de pago en un modelo (modelo de pago), por lo que el administrar las asignaciones por separado es una clave para el mantenimiento fácil de la solución. Por ejemplo, considere este escenario: utiliza los pagos ISO20022 para generar archivos de transferencia de crédito y a continuación se importan los mensajes de respuesta del banco. En este escenario, debe utilizar las siguientes configuraciones:

 - **Modelo de pago**
 - **Asignaciones modelo 1611 de pago** esta asignación se usará para generar el archivo de exportación
 - **Asignación modelo al destino ISO20022 de pago** esta configuración incluye todas las asignaciones que se usarán para importar los datos (“al destino" dirección de asignación)
 - **Transferencia de crédito ISO20022** esta configuración incluye un componente de formato que es responsable de la generación del archivo de exportación (pain.001) en función de la asignación modelo 1611 de pago, así como un formato para modelar el componente de la asignación que se usará junto con la asignación modelo al destino ISO20022 de pago para registrar pagos exportados en el sistema para futuros propósitos más de importación (la importación en la tabla técnica de CustVendProcessedPayments)
 - **Transferencia de crédito ISO20022 (CE)**, dondel CE corresponde a la extensión del país – formato derivado a la transferencia de crédito ISO20022 con la misma estructura y con determinadas diferencias específicas del país
 - **Pain.002** este formato se usará junto con la asignación modelo de pago al destino ISO20022 para importar el archivo pain.002 en el diario de transferencias de los pagos de proveedor
 - **Camt.054** este formato se usará junto con la asignación modelo de pago al destino ISO20022 para importar el archivo Camt.054 en el diario de transferencias de los pagos de proveedor La misma configuración del formato se usará en la funcionalidad de importación de los pagos de clientes, pero la asignación diferente se usará en la asignación modelo de pago al destino ISO20022.

Para obtener más información acerca de las informes electrónicos, consulte [Información general de informes electrónicos](../../dev-itpro/analytics/general-electronic-reporting.md).

## <a name="additional-resources"></a>Recursos adicionales
- [Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022](./tasks/create-export-vendor-payments-iso20022-payment-format.md)
- [Importación de la configuración de transferencia de crédito ISO20022](./tasks/import-iso20022-credit-transfer-configuration.md)
- [Importación de la configuración de domiciliación bancaria ISO20022](./tasks/import-iso20022-direct-debit-configuration.md)
- [Configurar cuentas bancarias de la empresa para transferencias de crédito ISO20022](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)
- [Configurar cuentas bancarias de empresa para débitos directos ISO20022](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)
- [Configuración de clientes y cuentas bancarias de cliente para domiciliaciones bancarias ISO20022](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)
- [Configuración forma de pago para transferencias de crédito ISO20022](./tasks/set-up-method-payment-iso20022-credit-transfer.md)
- [Configuración de la forma de pago para domiciliaciones bancarias ISO20022](./tasks/setup-method-payment-iso20022-direct-debit.md)
- [Configurar proveedores y cuentas bancarias de los proveedores para las transferencias de crédito ISO20022](./tasks/set-up-vendor-iso20022-credit-transfers.md)

