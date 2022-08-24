---
title: Informe de la declaración de inflación de ajuste
description: Los usuarios de Microsoft Dynamics 365 Finance pueden procesar ajustes de inflación mediante coeficientes de INPC, distintos métodos (como saldos de apertura, saldo, saldo mensual y fecha de transacción) y diversas dimensiones.
author: AdamTrukawka
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 9391
ms.assetid: 9076bf16-0021-47ad-a3b9-1bab75c583ec
ms.search.form: InflationAdjJournal_MX, InpcRateTable_MX, LedgerParameters, MainAccount
ms.openlocfilehash: 570cb06bf0087dd61a8ae7a3d82f96b2e654ffe2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283404"
---
# <a name="adjustment-inflation-declaration-report"></a>Informe de la declaración de inflación de ajuste

[!include [banner](../includes/banner.md)]

Puede procesar ajustes de inflación mediante coeficientes de INPC, distintos métodos (como saldos de apertura, saldo, saldo mensual y fecha de transacción) y diversas dimensiones.

Todas las empresas de México deben aplicar el proceso de NIF B-10 para reconocimiento de inflación en informes financieros si la tasa de inflación acumulativa durante los tres últimos años es igual o supera el 26 por ciento. Al usar las tasas de índice del Índice Nacional de Precios al Consumidor (INPC) cada mes, puede expresar los valores de transacción en la fecha de cierre de la hoja del saldo general. Cuando se ejecuta el proceso de ajuste de inflación, se ajustan los saldos contables y las entradas de asiento se registran de acuerdo con los coeficientes de INPC. Se definen los métodos de ajuste y puede ver el efecto del ajuste de inflación generando informes de simulación antes de ejecutar el proceso real.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra la configuración que debe existir antes de comenzar el registro de efectos inflacionistas en la contabilidad general.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instalación</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Coeficientes de INPC</td>
<td>Cree o edite la tabla de coeficiente de INPC para registrar la tasa de inflación por año y mes para calcular los importes de ajuste de inflación. Solo puede cambiar los importes si no hay ningún ajuste de inflación para el ejercicio y el mes concretos, y cuando se abre y se invierte el estado del proceso de ajuste de inflación. Esta tabla está disponible en el sitio del gobierno (SAT).</td>
</tr>
<tr class="even">
<td>Parámetros de inflación</td>
<td>En los parámetros de contabilidad general, debe configurar la cuenta principal en la que se registra el resultado de la posición monetaria.
<ul>
<li><strong>Cuenta REPOMO para la corrección de la inflación:</strong> Esta es la cuenta principal que se usa para registrar la inflación de ajuste. Use esta cuenta para registrar el importe que se recibe para las cuentas de resultado en cuentas de Resultado por Posición Monetaria (REPOMO). Esta cuenta debe ser siempre del tipo pérdidas y ganancias, ingresos o gastos.</li>
<li><strong>Cuenta principal de contrapartida:</strong> La cuenta principal de contrapartida que se usa para las transacciones de ajuste de inflación.</li>
<li><strong>Números de serie:</strong> debe especificar un número de serie para <strong>Asiento de ajuste de inflación</strong> y<strong> Asiento de inversión de ajuste de inflación</strong>. Estos asientos se usan para generar las transacciones de ajuste y las transacciones de ajuste de inversión cuando se invierten las transacciones de ajuste de inflación.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Cuentas principales</td>
<td>Debe configurar parámetros específicos por cuenta principal para habilitar la generación de transacciones de inflación de ajuste.
<ul>
<li><strong>Ajuste de B-10:</strong> seleccione <strong>Sí</strong> si desea revalorizar esta cuenta durante el proceso de ajuste de inflación.</li>
<li><strong>Tipo de REPOMO:</strong> si esta cuenta principal es parte del cálculo de REPOMO, debe indicar el tipo: <strong>Activo</strong> o <strong>Pasivo</strong>. <strong>No aplicable</strong> se selecciona cuando la cuenta principal no forma parte del cálculo de REPOMO.</li>
<li><strong>Método de ajuste:</strong> seleccione el método de ajuste que se usará cuando se ejecute el proceso de inflación de ajuste. Solo se usan las cuentas contables activas cuando se ejecuta el proceso de inflación de ajuste.
<ul>
<li>Ninguna</li>
<li>Fecha de la transacción</li>
<li>Saldo de apertura</li>
<li>Saldo mensual</li>
<li>Saldo</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="start-the-adjustment-inflation-process"></a>Iniciar el proceso de inflación de ajuste
Para iniciar el proceso, haga clic en <strong>Contabilidad general</strong> &gt; <strong>Tareas de período</strong> &gt; <strong>Ajuste de inflación B-10</strong>. Puede** <strong>crear la entrada de un período específico e incluir la fecha inicial y final. El estado predeterminado para la entrada es **Abierto</strong>. También puede incluir notas adicionales acerca del proceso de ajuste de inflación. Hay diversas maneras de ejecutar el proceso:

-   **Simular**: antes de ejecutar el proceso de ajuste de inflación, puede ejecutar una simulación de los efectos generales de ejecutar el ajuste de inflación. Si se encuentran diferencias en el informe **Simulación**, puede cambiar solo los campos **Capa de registro** y **Notas** en la página **Ajuste por inflación B-10**. El proceso de simulación no registra las transacciones contables de ajuste de inflación. El proceso genera un informe que muestra las transacciones contables de ajuste de inflación generadas por el sistema.
-   **Registrar**: puede registrar definitivamente el ajuste de inflación para generar los asientos de inflación de ajuste relacionados. También puede especificar la capa de registro donde se generan las transacciones. La entrada de inflación de ajuste tiene un estado de **Registrado**.
-   **Invertir**: puede invertir las transacciones de ajuste de inflación que se han registrado y ejecutar el proceso de nuevo si es necesario. Tras la inversión, el estado del proceso de inflación de ajuste se cambia a **Invertido**.

## <a name="available-report-types"></a>Tipos de informes disponibles
Hay varios tipos de informes de inflación de ajuste disponibles para fines de control cuando la entrada de inflación de ajuste tiene un estado de **Registrado**.

### <a name="repomo-report"></a>Informe REPOMO

Este informe se basa en los siguientes valores de parámetros:

-   El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.
-   El tipo de cuenta para la cuenta principal es **Activo**, **Pasivo** o **Balance**.
-   El tipo REPOMO para la cuenta principal es **Activo** o **Pasivo**.
-   El tipo de ajuste de la cuenta principal es **Saldo de** **apertura**.

### <a name="profit-and-loss-report"></a>Informe de pérdidas y ganancias

Este informe muestra el cálculo del ajuste de inflación de pérdidas y ganancias para el intervalo del período seleccionado. Muestra los detalles de todas las cuentas principales que tienen los siguientes valores de parámetros:

-   El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.
-   El tipo de cuenta para la cuenta principal es **Pérdidas y ganancias**, **Ingresos** o **Gasto**.
-   El tipo de ajuste de la cuenta principal es **Saldo** **mensual**.

### <a name="inventory-report"></a>Informe de inventario

Este informe muestra el cálculo del ajuste de inflación del código de cuenta de inventario para el período seleccionado. Debe mostrar todas las cuentas principales que tiene los siguientes valores de parámetros:

-   El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.
-   El tipo de ajuste de la cuenta principal es **Saldo**

### <a name="capital-and-result-report"></a>Informe de capital y resultado

Este informe muestra el cálculo del ajuste de inflación del código de cuenta de capital y resultado para el período seleccionado. Debe mostrar todas las cuentas principales que tiene los siguientes valores de parámetros:

-   El control deslizante **Ajuste de B-10** se encuentra para la cuenta principal.
-   El tipo de cuenta para la cuenta principal es **Balance** **de situación**, **Activo**, **Pasivo** o **Recursos propios**.
-   El tipo de ajuste de la cuenta principal es **Fecha** **de la transacción**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
