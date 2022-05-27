---
title: Diseñador de fórmulas para cálculos de TDS
description: Este tema proporciona un ejemplo de cómo se calcula el impuesto deducido en el origen (TDS) según la fórmula definida para cada código de impuestos de TDS en el grupo de TDS que se adjunta a la transacción.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e60db55fd3bbcfb8dc34670b3bbbd39336b04efb
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720094"
---
# <a name="formula-designer-for-tds-calculations"></a>Diseñador de fórmulas para cálculos de TDS

[!include [banner](../includes/banner.md)]

Este tema proporciona un ejemplo de cómo se calcula el impuesto deducido en el origen (TDS) según la fórmula definida para cada código de impuestos de TDS. Los códigos de impuestos de TDS se definen en el grupo de TDS que se adjunta a la transacción. Antes de diseñar fórmulas de TDS, complete la configuración básica necesaria para los TDS como se indica en los siguientes pasos. 

- Configure los grupos de componentes de TDS en la página **Grupos de componentes de retención de impuestos**. 
- Configure los componentes de TDS y adjunte el grupo de componentes de TDS a los componentes de TDS mediante la página **Componentes de retención de impuestos**. 
- Configure los códigos de impuestos de TDS y adjunte los componentes de TDS a los códigos de impuestos mediante la página **Códigos de retención de impuestos**. 
- Configure los grupos de impuestos de TDS en la página **Grupos de retención de impuestos**. Después, adjunte los códigos de impuestos de TDS al grupo de impuestos y defina la fórmula, utilizando la página **Diseñador de fórmulas**. 

**Fórmula de ejemplo**

En este ejemplo, el grupo de TDS, Alquiler, se adjunta a una factura de compra que se crea para el proveedor A. El importe de la factura es 100 000 $. Consulte la siguiente tabla para ver el cálculo de TDS para la factura.

| Grupo de TDS                                                   | Códigos de impuestos de TDS adjuntos al grupo de TDS | Valor              | Base imponible (diseñador de fórmulas) | Expresión de cálculo (diseñador de fórmulas) | Importe base | Importe de TDS calculado |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Alquiler                                                         | TDS (componente de TDS-TDS)                | 10%                | Importe bruto                      |                                            | 100,000      | 10,000                 |
| Suplemento (componente de TDS-Suplemento)                         | 10%                                     | Excl. importe bruto | +TDS                              |                   10000                    | 1.000        |                       |
| PE-Cess (componente de TDS-PE-Cess)                            | 2%                                      | Excl. importe bruto | +TDS+suplemento                    |                   11000                    | 220         |                       |
| SHE Cess (componente de TDS-SHE Cess)                          | +1 %                                      | Excl. importe bruto | +TDS+suplemento                    |                   11000                    | 110         |                       |
| **Todal** **de TDS** **calculado** **para** **la** **factura** | **11,330**                               |                    |                                   |                                            |             |                       |

Las entradas de asiento se crean de la siguiente manera.

| Cuenta           | Débito  | Crédito |
| ----------------- | ------ | ------ |
| Alquiler              | 100,000 |        |
| Proveedor A          |        | 100,000 |
| Proveedor A          | 11,330  |        |
| TDS repercutidos       |        | 10,000  |
| Suplemento a pagar |        | 1.000   |
| PE-Cess repercutido   |        | 220    |
| SHE Cess repercutido  |        | 110    |
