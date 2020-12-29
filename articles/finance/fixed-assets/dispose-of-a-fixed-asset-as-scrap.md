---
title: Retirar un activo fijo como desechado
description: El tema describe el proceso de eliminar transacciones para un activo fijo que se ha desechado como residuo.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447544"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Retirar un activo fijo como desechado

[!include [banner](../includes/banner.md)]

El tema describe el proceso de eliminar transacciones para un activo fijo que se ha desechado como residuo. Los tipos de transacción que se pueden eliminar incluyen la adquisición de un activo y las transacciones de depreciación acumuladas y otras transacciones de activos fijos. La eliminación de estas transacciones afecta a las cuentas de balance de situación, como el ajuste de adquisición, el ajuste de depreciación, la revalorización, y las cuentas de revalorización y de devaluación.

| Transacción                                         | Débito (Dr.) | Crédito (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Depreciación acumulada Dr.                        | X           |              |
| Ganancia/pérdida de activos fijos cr.                          |             | X            |
| Ganancia/pérdida de activos fijos dr.                          | X           |              |
| Cuenta de adquisición de activos fijos cr.                 |             | X            |
| Ganancia/Pérdida de activos fijos dr. (valor neto en los libros \[NBV\]) | X           |              |
| Ganancia/pérdida de activos fijos cr. (NBV)                    |             | X            |

> [!NOTE]
> Recomendamos que trabaje estrechamente con el director financiero (CFO) de su empresa o controlador para identificar las cuentas correctas que se deben usar para cada tipo de transacción, y para comprobarlas que el proceso de desecho y las transacciones que genera actualiza dichas cuentas correctamente.

Antes de desechar un activo fijo como residuo, debe crear cuentas contables asociadas al valor de adquisición del activo, la depreciación durante del año actual, la depreciación de los años anteriores, y el NBV del activo. Los tipos de transacción de activos fijos figuran en la página **Perfil de contabilización de activos fijos**. Vaya a **Activos fijos \> Configuración \> Perfiles de contabilización de activos fijos** y, en la ficha desplegable **Cancelación**, seleccione **Residuo** en el campo que está encima de la cuadrícula. La ilustración siguiente muestra la lista de tipos de transacciones de activos fijos en la página **Perfiles de contabilización de activos fijos**.


[![Desechar un activo como residuo, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

Para el siguiente ejemplo, un activo fijo se adquirió el 1 de enero de 2018, y se dará de baja el 31 de marzo de 2019.

- **Precio de adquisición:** 24.000,00 Dólares estadounidenses (USD)
- **Tiempo de vida:** dos años
- **método de depreciación**: vida de servicio de depreciación lineal
- **Importe de depreciación:** 1000,00 USD por mes

El NBV de un activo fijo se calcula mediante la fórmula siguiente:

Valor neto en los libros = Precio de adquisición – depreciación

En este ejemplo, se adquirió el activo fijo y se depreció durante 15 meses, de enero de 2018 a marzo de 2019. Por lo tanto, el NBV del activo es 9000,00 USD (24.000,00 USD – 15.000,00 USD).

[![Ejemplo de depreciación para activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


Para crear un diario de cancelación, vaya a **Activos fijos \> Entradas de diario \> Diario de activos fijos** y, a continuación, en el panel de acciones, seleccione **Líneas**. Seleccione **Cancelación – residuos**, y a continuación, seleccione un identificador de activos fijos. Para cancelar completamente el activo, no inserte un valor en el campo **Débito** o el campo **Crédito** .

[![Diario de activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

La transacción de cancelación de activos fijos cambia los valores de campo del libro de activos fijos de las siguientes formas:

- En la sección **Saldo** , el campo **Estado** se actualizará **Desechado**.
- En la sección **Emisión** , el campo **Fecha de cancelación** se establece en la fecha en la que el activo se dio de baja.

[![Detalle del diario de activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

La ilustración siguiente muestra el saldo de activos fijos.

[![Saldo de activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

La ilustración siguiente muestra el asiento que se registra.

[![Valor neto en los libros](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)
