---
title: Especificación de impuestos por informe de transacción contable
description: Este artículo explica cómo usar la especificación de impuestos por libro mayor de la transacción contable que desea ver e imprimir información sobre transacciones contables que los impuestos se calcularán para.
author: EricWang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: c96f457a0ea24aef1769f370c3c0657ada31eebf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898102"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Especificación de impuestos por informe de transacción contable
[!include [banner](../includes/banner.md)]

Este artículo explica cómo usar la **Especificación de impuestos por libro mayor de la transacción contable** que desea ver e imprimir información sobre transacciones contables que los impuestos se calcularán para.

## <a name="tax-accounts-vs-non-tax-accounts"></a>Cuentas de impuestos contra cuentas no fiscales

El informe **Especificación de impuestos por transacción de libro mayor** muestra las transacciones de impuestos para las cuentas de impuestos y las no fiscales. Estas cuentas se clasifican así:

- **Cuenta de impuestos**- Una cuenta se considera una cuenta de impuestos cuando se registra una transacción de impuestos, y la cuenta principal en la línea de diario **Impuestos** es una cuenta de impuestos, como una cuenta de impuestos repercutidos o una cuenta de impuestos soportados.
- **Cuenta no fiscal**- Una cuenta se considera una cuenta no fiscal cuando se registra una transacción de impuestos, y la cuenta principal en la transacción original es una cuenta no fiscal, como una cuenta de ingresos o de gastos.

Para las cuentas de impuestos, las columnas **Origen**, **Impuestos soportados** e **Impuesto repercutidos** en el informe muestran **0** (cero). Para las cuentas no fiscales, las columnas muestran importes.

## <a name="filtering-the-data-on-the-report"></a>Filtrar los datos del informe

Cuando genere el informe, los siguientes campos predeterminados estarán disponibles. Puede usar estos campos para filtrar los datos que se muestran en el informe.

| Campo                      | Descripción |
|----------------------------|-------------|
| Fecha                       | Use los campos en las secciones **De** y **A** para definir un intervalo de fechas para las transacciones de impuestos. |
| Cuenta principal               | Use los campos en las secciones **De** y **A** para definir un intervalo de cuentas principales. |
| Código de impuestos             | Use los campos en las secciones **De** y **A** para definir un intervalo de códigos de impuestos. |
| Agrupación                   | Seleccione si se debe agrupar por cuenta contable o código de impuestos. |
| Subtotal por código de impuestos | Establezca esta opción a **Sí** para mostrar los subtotales por código de impuestos. |
| Solo totales                | Establezca esta opción a **Sí** para mostrar únicamente los totales. |
| Solo cuentas principales         | Establezca esta opción a **Sí** para incluir sólo las cuentas principales en el informe. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Mostrar únicamente las cuentas no fiscales en el informe

Para mostrar únicamente las cuentas no fiscales en el informe, configure una condición de filtro, como un asterisco (\*), como se muestra en la siguiente ilustración.

![Informe que muestra cuentas no fiscales.](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
