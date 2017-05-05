---
title: "Descripción de las domiciliaciones SEPA"
description: "La Zona única de Pagos en Euros (SEPA) lo establece la Comisión Europea y dicta que todos los pagos electrónicos se consideran como nacionales, independientemente del país o región donde se encuentren el individuo, la empresa o la organización y el banco. No hay diferencia entre los pagos nacionales y transfronterizos. SEPA incluye a los 28 estados miembros de la Unión Europea (UE), además de Islandia, Liechtenstein, Noruega, Suiza, Mónaco y San Marino. SEPA ayuda a formar un mercado único para las transacciones de pago en el Área Económica Europea (AEE). En última instancia, se espera que SEPA reduzca el número de formatos de pago con los que deben trabajar los bancos, las empresas y las personas."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 849fea6030c665e1724c3fc8f31353dd4bafed27
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-direct-debit-overview"></a>Descripción de las domiciliaciones SEPA

[!include[banner](../includes/banner.md)]


La Zona única de Pagos en Euros (SEPA) lo establece la Comisión Europea y dicta que todos los pagos electrónicos se consideran como nacionales, independientemente del país o región donde se encuentren el individuo, la empresa o la organización y el banco. No hay diferencia entre los pagos nacionales y transfronterizos. SEPA incluye a los 28 estados miembros de la Unión Europea (UE), además de Islandia, Liechtenstein, Noruega, Suiza, Mónaco y San Marino. SEPA ayuda a formar un mercado único para las transacciones de pago en el Área Económica Europea (AEE). En última instancia, se espera que SEPA reduzca el número de formatos de pago con los que deben trabajar los bancos, las empresas y las personas.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>¿Cuál es el objetivo de las domiciliaciones SEPA?
---------------------------------------

Una domiciliación SEPA permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y que se lo haya entregado al acreedor. El cliente firma una orden que autorice el acreedor a cobrar un pago y da instrucciones al banco del cliente para pagar el cobro. 

Las domiciliaciones SEPA crean, por primera vez, un instrumento de pago que se puede utilizar para las domiciliaciones nacionales y transfronterizas en Euros en los 32 países o regiones de SEPA. 

Existen dos esquemas disponibles: el esquema de domiciliación base SEPA y el esquema de domiciliación entre empresas (B2B) SEPA. Ambos esquemas usan el mismo formato de archivo.

## <a name="what-is-the-core-direct-debit-scheme"></a>¿Qué es el esquema de domiciliación base?
El esquema de domiciliación base SEPA es el esquema básico. Contiene los atributos siguientes:
-   La transferencia de fondos es en Euros (aunque las cuentas bancarias puedan contener fondos en otras divisas).
-   El cliente y el acreedor deben ser titular de una cuenta con una institución de crédito ubicada dentro de SEPA.
-   El cliente debe conceder una orden firmada al acreedor.
-   Las órdenes caducarán 36 meses después del último cobro iniciado.
-   El acreedor debe almacenar las órdenes durante la vigencia de este y por lo menos 14 meses después del último cobro.
-   El esquema se puede usar para cobros por domiciliación individuales (una sola vez) o periódicos.
-   Los clientes tienen un derecho de "sin preguntas" de recibir una devolución dentro de un plazo de hasta ocho semanas después del débito de su cuenta.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>¿Qué es el esquema de domiciliación entre empresas (B2B) SEPA?
El esquema de domiciliación B2B SEPA se aplica a las transacciones entre empresas y se basa en el esquema de domiciliación base SEPA. Las diferencias principales son:
-   El esquema de domiciliación B2B SEPA no se permite cuando el cliente es una persona individual (consumidor).
-   El cliente no tiene derecho de obtener una devolución de una transacción autorizada.
-   Los bancos de cliente deben asegurarse de que el cobro está autorizado, verificando el cobro con la información de la orden. Los bancos de cliente y los clientes deben acordar la verificación de que se realizará para cada domiciliación.
-   El esquema ofrece un período más corto para presentar domiciliaciones y reduce el período de devolución.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>¿Se puede usar el esquema COR1 para las órdenes de domiciliación bancaria?
Sí. Puede usar el esquema COR1 para las órdenes de domiciliación bancaria SEPA en Austria, Alemania, Bélgica, Francia, Italia, España y Países Bajos. El esquema proporciona un período previo a la notificación más corto para el cobro por domiciliación bancaria para el acreedor.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>¿Qué son los números internacionales de cuenta bancaria (IBAN) y los códigos de identificador del banco (BIC)?
El número internacional de cuenta bancaria (IBAN) y el código de identificador del banco (BIC) se usan para identificar las cuentas en los 32 países o regiones de SEPA. Especifique el BIC en el campo Código SWIFT y el IBAN en el campo IBAN. Ambos campos se encuentran en la ficha desplegable Identificación adicional de la ficha de Cuenta bancaria de la página Cuentas bancarias. Esto ocurre para la cuenta bancaria del acreedor y la cuenta bancaria del cliente.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>¿Dónde se especifican los identificadores de acreedor (identificadores de domiciliación)?
En SEPA, cada acreedor se identifica con un identificador único de acreedor. Este identificador permite al cliente y al banco del cliente filtrar cada domiciliación y, a continuación, procesar o rechazar esta según las instrucciones del cliente. Los acreedores deben solicitar este identificador a su banco. Especifique este identificador en el campo Id. de domiciliación bancaria para la cuenta bancaria de la entidad jurídica.

## <a name="what-are-mandates"></a>¿Qué son las órdenes?
El cliente firma una orden que autorice el acreedor a cobrar un pago y da instrucciones al banco del cliente para pagar el cobro. El cliente puede emitir la orden en formato papel o electrónicamente. De forma predeterminada, la orden vence 36 meses después de que se haya iniciado la última domiciliación.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>¿Dónde se especifica el formato de archivo de domiciliación SEPA (ISO 20022)?
Los formatos de datos de SEPA se basan en la normativa de mensajes ISO 20022. Activará la casilla Informes electrónicos genéricos y seleccionará el formato de domiciliación bancaria SEPA como configuración de formato de exportación al configurar los métodos de pago de clientes. Usará dicho método de pago cuando genere un archivo de pago en un diario de pago de cliente.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>¿En qué formatos de archivo se pueden generar archivos de pago por domiciliación SEPA?
Puede generar archivos de pago electrónico para domiciliaciones bancarias SEPA en los formatos siguientes:
-   Archivos de pago por domiciliación bancaria SEPA en el formato de archivo XML PAIN.008.001.02 para Bélgica, Alemania, España, Francia, Italia y Países Bajos.
-   Archivos de pago por domiciliación bancaria SEPA en formato de archivo XML PAIN.008.001.02 para Austria, y en formato de archivo XML PAIN.008.003.02 para Alemania.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>¿Cómo funcionan los reembolsos y las devoluciones con las domiciliaciones SEPA?
En ambos esquemas de domiciliación SEPA, los clientes tienen determinados derechos a devoluciones. Se permite al cliente invertir cualquier transacción autorizada durante un período de ocho semanas después de la fecha de vencimiento, sin tener que dar un motivo. En el caso de las transacciones no autorizadas, el período se amplía a 13 meses después de la fecha de vencimiento. Los pagos realizados se pueden revertir manualmente mediante el botón Cancelar pago de la página Transacciones de clientes.






