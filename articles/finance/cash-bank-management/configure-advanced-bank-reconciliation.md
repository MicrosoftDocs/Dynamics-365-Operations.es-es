---
title: Configuración del proceso de conciliación bancaria avanzada
description: Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 Finance. En este artículo se explicará la configuración de los procesos de conciliación.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7103cb93ad0d9ea0f1b92e317bee7454eb08d1f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447745"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>Configuración del proceso de conciliación bancaria avanzada

[!include [banner](../includes/banner.md)]

Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 Finance. En este artículo se explicará la configuración de los procesos de conciliación.  

Varias partes deben estar configuradas antes de utilizar la funcionalidad avanzada de conciliación bancaria. Para obtener más información sobre la configuración de la importación del extracto bancario, consulte [Configurar el proceso de importación de conciliación bancaria avanzado](set-up-advanced-bank-reconciliation-import-process.md).  Los requisitos para la configuración del proceso de conciliación se detallan a continuación.

## <a name="transaction-codes"></a>Códigos de transacción
Los códigos de transacción se pueden usar como parte de las reglas de coincidencia de conciliación bancaria. Los códigos de transacción ayudarán a asignar solo los mismos tipos de transacciones entre Finances y el extracto bancario. Para hacer este tipo de asignación, primero es necesario definir los tipos de transacción utilizados para las transacciones bancarias desde Finance y después asignar los tipos a los códigos de transacción del extracto usados por el banco. Los tipos de transacción para las transacciones bancarias están definidos en la página **Tipo de transacción bancaria**. Aquí también se define la cuenta principal que se utilizará para los registros asociados a ese tipo de transacción. 

Una vez que haya definido los códigos de transacción bancaria, asígnelos a los códigos de transacción utilizados en sus extractos bancarios electrónicos. Este proceso de asignación se realiza mediante la página **Asignación de código de transacción**. La asignación del código de transacción se completa de forma independiente para cada cuenta bancaria.

## <a name="matching-rules-and-matching-rule-sets"></a>Reglas de coincidencia y conjuntos de reglas de coincidencia
Las reglas de coincidencia le permiten definir los criterios para la conciliación automática entre las transacciones bancarias de Finance y las transacciones del extracto bancario. La configuración de las reglas de coincidencia se efectúa en la página **Reglas de coincidencia de conciliación**. Para obtener más información, consulte [Configurar las reglas de coincidencia de conciliación bancaria](set-up-bank-reconciliation-matching-rules.md). 

Un conjunto de reglas de coincidencia se usa para definir grupo de reglas de coincidencia de conciliación que se ejecutan en secuencia durante el proceso de conciliación de bancaria.  Los conjuntos de reglas de coincidencia se configuran en la página **Conjuntos de reglas de coincidencia de conciliación**.

## <a name="cash-and-bank-management-parameters"></a>Parámetros de gestión de efectivo y bancos
Hay varios parámetros específicos en el proceso de conciliación bancaria avanzado en la página **Parámetros de gestión de efectivo y bancos**.  **Mostrar el importe de la línea de extracto en débito/crédito** cambia la vista de los importes en la página **Extracto bancario**. Si se selecciona esta opción, los importes de transacción del extracto bancario se mostrarán en columnas independientes de crédito y débito. Si no se selecciona, los importes de transacción del extracto bancario se mostrarán en una columna de importe única con el signo adecuado. 

Las opciones de validación establecidas en la página de los parámetros anulan las establecidas en reglas coincidentes. Por ejemplo, no puede asignar documentos manual o automáticamente aparte de la diferencia de fecha establecida en la página de los parámetros. Además, si se selecciona la opción para **Validar asignación de tipo de transacción**, los tipos de transacción deben asignarse entre las transacciones bancarias de Finance y las transacciones del extracto bancario para que las transacciones se asignen manual o automáticamente. 

También debe configurar las secuencias numéricas necesarias en la página **Parámetros de gestión de efectivo y bancos**.  En la ficha **Secuencias numéricas**, establezca los códigos de secuencia numérica para las referencias de descarga **id., id. de extracto, id. de conciliación y conciliación bancaria**.

## <a name="bank-account-reconciliation-options"></a>Opciones de conciliación de cuenta bancaria
Primero debe habilitar la conciliación bancaria avanzada de la cuenta bancaria. Existen varias opciones adicionales disponibles en la página **Cuenta bancaria** una vez que la funcionalidad avanzada de conciliación bancaria está habilitada. 

La funcionalidad **Usar extractos bancarios como confirmación de pagos electrónicos** integra la funcionalidad de conciliación bancaria con los estados de pago electrónico. Cuando se habilita, se crea un documento bancario automáticamente para el estado de pago electrónico establecido en **Enviado**. Además, el estado de un pago electrónico se actualizará de **Enviado** a **Recibido** una vez que se haya hecho coincidir el pago, y se haya conciliado y registrado. 

El campo **Nombre de cuenta bancaria en extractos** es el nombre utilizado para la cuenta bancaria en sus extractos bancarios electrónicos. Dicho nombre se usa al determinar qué transacciones deben importarse a una cuenta bancaria desde un extracto que puede contener información de varias cuentas bancarias. 

La opción **Conciliar tras la importación** validará automáticamente el extracto bancario, creará una nueva conciliación bancaria y una hoja de cálculo nueva, y ejecutará el conjunto de reglas coincidentes predeterminado. Esta funcionalidad automatiza el proceso hasta el punto en que deben conciliarse manualmente transacciones. Al importar se obtendrá de forma predeterminada la configuración de la cuenta bancaria.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]