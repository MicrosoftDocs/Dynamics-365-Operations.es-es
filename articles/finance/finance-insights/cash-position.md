---
title: Posición de efectivo (versión preliminar)
description: Este tema describe cómo la característica de pronóstico de flujo de efectivo predice la posición de efectivo de una organización para momentos específicos. También describe las opciones que están disponibles para mostrar pronósticos para diferentes períodos.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: ffe91d7ca273de36c2fae58a39d3a3d306496990
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208590"
---
# <a name="cash-position-preview"></a>Posición de efectivo (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La posición de efectivo es la proyección del flujo de efectivo que se prevé para el corto plazo. Se basa en la proyección de los recibos de efectivo de los clientes que pagan facturas y pedidos pendientes, y también en la proyección de los desembolsos de efectivo que se pagan a los proveedores por las facturas y los pedidos de compra.

Cuando el sistema predice los pagos de los clientes, utiliza las predicciones de pago de la función de predicción de pagos del cliente. Sin predicciones de pago, el tiempo promedio que se requiere para convertir una factura de cliente en un pago para cada cliente se usa para calcular una fecha de pago. Para los pedidos abiertos de clientes, el sistema calcula la fecha de la factura utilizando el número promedio de días para que se facturen las líneas de pedido por cliente. A continuación, utiliza la fecha de la factura como entrada para la función de predicción de pagos. La función de predicción de pagos del cliente calcula una fecha de pago para cada línea de pedido. 

<*Necesita texto de Jarek o Dave sobre cómo las predicciones de pago se convierten en una fecha*> La fecha de pago de las facturas pendientes se [*estima*] aproximadamente a partir de las predicciones de pago, seleccionando una fecha que corresponda al percentil cincuenta de la función de distribución acumulativa que se obtiene a partir de las probabilidades del caso predicho.

Se utiliza un enfoque similar para predecir los pagos a los proveedores. Para cada proveedor, el sistema calcula el tiempo promedio que se requiere para convertir una factura de proveedor en un pago. Ese número de días se usa después para calcular la fecha de pago. Para los pedidos de proveedores abiertos, el sistema calcula la fecha de la factura considerando el número promedio de días que se requieren para convertir las líneas de pedido en una factura para cada proveedor. Luego, el sistema calcula la fecha de pago usando el tiempo promedio para convertir una factura de proveedor en un pago para cada proveedor.

La sección superior de la pestaña **Posición de efectivo** incluye un gráfico de posición de efectivo. Este gráfico muestra las entradas y salidas de efectivo y su impacto en el saldo de liquidez total. Los detalles del gráfico de posición de efectivo se pueden ver en períodos diarios, semanales, mensuales o trimestrales. Cuando selecciona **Diario**, puede ver las previsiones para los próximos 21 días. Cuando selecciona **Semanal**, puede ver las previsiones para las próximas 20 semanas. Cuando selecciona **Mensual**, puede ver las previsiones para los próximos 12 meses. Cuando selecciona **Trimestral**, puede ver las previsiones para los próximos 12 trimestres. Puede ocultar el gráfico si necesita espacio adicional en su pantalla para ver el contenido en la pestaña **Posición de efectivo**.

La sección inferior de la pestaña **Posición de efectivo** muestra los detalles de la posición, el flujo de efectivo, los pagos proyectados y la cuenta bancaria.

- La información de la cuadrícula **Detalles de posición** se presenta en tres secciones: una lista de cuentas de liquidez, una lista de documentos que conforman las entradas de efectivo y una lista de documentos que conforman las salidas de efectivo. La cuadrícula también muestra los saldos de posición de efectivo. Para el primer período que está viendo, el saldo de las cuentas de liquidez es el saldo de apertura. Para períodos posteriores, los saldos de las cuentas de liquidez se calculan con base en la suma de las entradas de efectivo y la resta de las salidas de efectivo de períodos anteriores. Para ver detalles de las transacciones que componen el saldo, seleccione el vínculo **Saldo**.
- La cuadrícula **Flujo de efectivo** muestra las entradas de efectivo, las salidas de efectivo agregadas por período y su impacto en los saldos de las cuentas de liquidez. Para el primer período, el saldo de las cuentas de liquidez es el saldo de apertura. Para períodos posteriores, los saldos de las cuentas de liquidez se calculan con base en la suma de las entradas de efectivo y la resta de las salidas de efectivo de períodos anteriores.
- La cuadrícula **Saldo bancario proyectado** muestra las salidas de efectivo esperadas y su impacto en las cuentas de liquidez.
- La cuadrícula **Cuenta bancaria** muestra el impacto de las entradas y salidas de efectivo esperadas en el saldo bancario.

Para guardar y editar la posición de efectivo, cree una instantánea. Para obtener más información sobre cómo trabajar con instantáneas, consulte [Información general sobre instantáneas](payment-snapshots.md).

#### <a name="privacy-notice"></a>Aviso de privacidad
Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]