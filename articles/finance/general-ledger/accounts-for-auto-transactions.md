---
title: Cuentas para transacciones automáticas
description: Este tema explica cómo se utilizan las cuentas para transacciones automáticas para registrar a través de Microsoft Dynamics 365 y proporciona ejemplos de cuentas clave para transacciones automáticas.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cecbeb769235e525390cc7a66800a9b0d55d78a9
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014059"
---
# <a name="accounts-for-automatic-transactions"></a>Cuentas para transacciones automáticas

La página **Cuentas para transacciones automáticas** (**Contabilidad general &gt; Configuración del registro &gt; Cuentas para transacciones automáticas**), se usa para definir la cuenta principal predeterminada que se usa para cada tipo de registro en el sistema. Aunque la mayoría de los tipos de registro se pueden configurar en una página específica de un módulo o de una característica, algunos solo se pueden configurar en la página **Cuentas para transacciones automáticas**.

Por ejemplo, puede especificar la cuenta principal que se utiliza para el tipo de registro **Saldo del cliente** en el campo **Resumen** en la página **Perfil de contabilización del cliente** y utilizar una cuenta principal diferente para cada perfil de cliente. De esta manera, tiene un control más granular sobre las publicaciones. Por otro lado, puede especificar la cuenta del error en la página **Cuentas para transacciones automáticas**.

Cuando abre la página **Cuentas para transacciones automáticas** en una nueva entidad jurídica, la lista de cuentas estará vacía. Puede agregar los tipos de registro más comunes que deben configurarse en la página seleccionando el botón **Crear tipos predeterminados** botón. Luego, para cada fila, puede seleccionar la cuenta principal en el campo **Cuenta principal**. Si deja el campo **Cuenta principal** en blanco para un tipo de registro y no ha configurado una cuenta principal en una página específica de un módulo o de una característica, recibirá un mensaje de error cuando registre una transacción que utilice el tipo de registro. Por lo general, el mensaje será "La cuenta para el \[tipo de registro\] no se ha encontrado".

## <a name="default-posting-types"></a>Tipos de registro predeterminados

La siguiente tabla muestra ejemplos de los tipos de registro predeterminados que se crean cuando selecciona **Crear tipos predeterminados** en la página **Cuentas para transacciones automáticas**. Muestra ejemplos de cuentas principales y descripciones. La columna "¿Debe/Haber?" indica si la transacción generalmente registra un débito o un crédito. En algunos casos, una transacción puede registrar un débito o un crédito. La columna "Cuenta de compensación" indica si el tipo de contabilización es una cuenta de compensación. Si el tipo de registro es una cuenta de compensación, el importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diferencia de decimales en la divisa de notificación | 618160 | Gastos varios | Gasto | Ambas | No | Este tipo de registro se usa cuando se produce una diferencia de decimales cuando el importe de una transacción en una divisa extranjera se convierte a la divisa de notificación. |
| Diferencia de decimales en la divisa de contabilidad | 618160 | Gastos varios | Gasto | Ambas | No | Este tipo de registro se usa cuando se produce una diferencia de decimales cuando el importe de una transacción en una divisa extranjera se convierte a la divisa de contabilidad. |
| Cuenta de errores | 999999 | Cuenta de errores | Gasto | Ambas | No | Este tipo de registro se utiliza cuando se produce un error en el sistema. La cuenta debe validarse cada periodo y cualquier error debe resolverse. |
| Resultado de fin de año | 300160 | Ganancias retenidas | Recursos propios | Ambas | No | Este tipo de registro se utiliza cuando se ejecuta el proceso de cierre de fin de año para mover el saldo de cuentas del tipo **pérdidas y ganancias** en la cuenta principal que se selecciona para el resultado de fin de año. |
| Descuento por pronto pago del cliente | No aplicable | No aplicable | No aplicable | No aplicable | No | El tipo de registro que se define en la página **Cuentas para transacciones automáticas** no se utiliza. Se requiere una cuenta principal cuando se configuran descuentos por pronto pago en Clientes.|
| Descuento por pronto pago del proveedor | No aplicable | No aplicable | No aplicable | No aplicable | No | El tipo de registro que se define en la página **Cuentas para transacciones automáticas** no se utiliza. Se requiere una cuenta principal cuando se configuran descuentos por pronto pago en Proveedores. |

## <a name="additional-posting-types"></a>Tipos de registro adicionales

La siguiente tabla muestra ejemplos de tipos de registro adicionales que deben configurarse si planea utilizar las funciones relacionadas. Para estos tipos de registro, no hay configuración de perfil de registro disponible en otro módulo. La columna "¿Debe/Haber?" indica si la transacción generalmente registra un débito o un crédito. En algunos casos, una transacción puede registrar un débito o un crédito. La columna "Cuenta de compensación" indica si el tipo de contabilización es una cuenta de compensación. Si el tipo de registro es una cuenta de compensación, el importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Cuenta de saldo por diferencia de consolidación | 801200 | Pérdidas y ganancias - Revaluación | Gasto | Ambas | No | Este tipo de registro se utiliza cuando realiza una consolidación que implica una revaluación de divisa y se producen diferencias de decimales durante la revaluación. |
| Cuenta de pérdidas y ganancias para las diferencias de consolidación | 801200 | Pérdidas y ganancias - Revaluación | Gasto | Ambas | No | Este tipo de registro se utiliza cuando realiza una consolidación que implica una revaluación de divisa y se producen diferencias de decimales durante la revaluación. |
| Interunidad: débito | 133500 | Cliente interunidad | Activo | Débito | No | Este tipo de registro se utiliza cuando selecciona una dimensión de equilibrio en la página **Contabilidad** y la dimensión no cuadra en una transacción que se registra. |
| Interunidad: crédito | 233500 | Proveedor interunidad | Pasivo | Crédito | No | Este tipo de registro se utiliza cuando selecciona una dimensión de equilibrio en la página **Contabilidad** y la dimensión no cuadra en una transacción que se registra. |
