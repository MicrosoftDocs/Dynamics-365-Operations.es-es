---
title: Acumulación de suscripciones
description: Con las suscripciones de servicios, puede acumular ingresos manualmente en los períodos siguientes a la fecha de facturación de una transacción de gastos.
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d17737c415f6204359dae3ea4b2a0cb4ebb5d65
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580489"
---
# <a name="accruing-subscriptions"></a>Acumulación de suscripciones 

[!include [banner](../includes/banner.md)]


Con las suscripciones de servicios, puede acumular ingresos manualmente en los períodos siguientes a la fecha de facturación de una transacción de gastos.

Los períodos de acumulación se crean para el período de factura que configure para la cuota de suscripción y los períodos de acumulación se basan en el código de período de la suscripción.

Puede acumular e invertir ingresos acumulados.

## <a name="reverse-accruals-of-credit-amounts"></a>Invertir las provisiones de importes de crédito

Si abona importes de suscripción facturados, puede usar dos métodos diferentes para invertir los importes de acumulación:

  - puede invertir cada transacción de ingreso acumulado individualmente antes de crear la propuesta de nota de abono para la transacción. Este es el método manual. (manual)

  - Puede tener los importes acumulados invertidos en la fecha en la que la nota de abono se registra o en la fecha de registro original de acumulación.

Para obtener más información, consulte [Parámetros de suscripción (formulario)](/dynamicsax-2012//subscription-parameters-form).

## <a name="setup-requirements"></a>Configurar requisitos

Para acumular ingresos, asegúrese de que se cumplen los siguientes requisitos de datos:

## <a name="account-setup"></a>Configuración de cuenta

Las cuentas **Trabajo en proceso - suscripción** y **Ingresos acumulados - suscripción** deben configurarse en el módulo **Proyecto**.

Al registrar el ingreso acumulado, se carga en la cuenta **Trabajo en proceso - suscripción** el importe de acumulación y se abona el importe a acumulación en la cuenta **Ingresos acumulados - suscripción**.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Configuración de cuentas para la acumulación de ingresos de suscripción

1.  Haga clic en **Administración de proyectos y contabilidad** \> **Configurar** \> **Registrar** \> **Configuración de registro**.

2.  Haga clic en la pestaña **Cuentas de ingresos** , y seleccione **Trabajo en curso - Suscripción** o **Ingresos acumulados - Suscripción** para configurar las cuentas.

## <a name="subscription-group-setup"></a>Configuración del grupo de suscripciones

Para poder acumular ingresos para suscripciones, debe activarse la casilla **Acumular ingresos**. Esto se encuentra en el formulario **Grupos de suscripción** para el grupo vinculado a la suscripción. Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Habilitar acumulación de ingresos en un grupo de suscripciones

Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.

## <a name="periods"></a>Períodos

Debe configurar un código de período de facturación. A menos que desee acumular ingresos dentro de los mismos intervalos de tiempo que utiliza para la facturación, también deberá configurar un período de acumulación.

La tabla siguiente proporciona una visión general de los períodos de acumulación que se pueden configurar para cada período de facturación:

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Período de facturación</p></th>
<th><p>Período de acumulación</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Años</strong></p></td>
<td><ul>
<li><p><strong>Años</strong></p></li>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mes</strong></p></li>
<li><p><strong>Día</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Trimestre</strong></p></td>
<td><ul>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mes</strong></p></li>
<li><p><strong>Día</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Mes</strong></p></td>
<td><ul>
<li><p><strong>Mes</strong></p></li>
<li><p><strong>Día</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Semana</strong></p></td>
<td><ul>
<li><p><strong>Día</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Día</strong></p></td>
<td><ul>
<li><p><strong>Día</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

La configuración del período de facturación es una parte obligatoria de toda la configuración del grupo de suscripciones. Puede decidir si también configurar un período de acumulación para el grupo de suscripciones. Si lo hace, se sugiere este período en el campo **Código del período**. Este campo se encuentra en el formulario **Acumular ingresos de suscripción**, cuando se acumulan ingresos de suscripción. Sin embargo, el período de acumulación es información opcional acerca del grupo de suscripciones.


> [!NOTE]
> <P>Use la siguiente ruta para abrir el formulario <STRONG>Acumular ingresos de suscripción</STRONG>. Haga clic en <STRONG>Gestión de servicio</STRONG> &gt; <STRONG>Periódica</STRONG> &gt; <STRONG>Suscripciones de servicio</STRONG> &gt; <STRONG>Acumular ingresos de suscripción</STRONG>.</P>


## <a name="transactions"></a>Transacciones

Puede controlar el número de transacciones contables que se crean al registrar ingresos acumulados. En las suscripciones, defina si las transacciones contables se deben crear como total o por línea.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>Especificar el nivel de detalles de registro que se muestra para transacciones acumuladas

1.  Haga clic en **Gestión de proyectos y contabilidad** \> **Configurar** \> **Parámetros de gestión de proyectos y contabilidad**.

2.  En la ficha **Financiero**, en el campo **Factura**, seleccione **Total** o **Línea**.


## <a name="see-also"></a>Consulte también

[Acumular ingresos de suscripción](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]