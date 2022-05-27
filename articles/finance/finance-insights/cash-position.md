---
title: Posición de efectivo
description: Este tema describe cómo la característica de pronóstico de flujo de efectivo predice la posición de efectivo de una organización para momentos específicos. También describe las opciones que están disponibles para mostrar pronósticos para diferentes períodos.
author: ShivamPandey-msft
ms.date: 12/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1c6d394cb192a88316beb2e8746b558eb8dd184b
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711670"
---
# <a name="cash-position"></a>Posición de efectivo

[!include [banner](../includes/banner.md)]

La posición de efectivo es la proyección del flujo de efectivo que se prevé para el corto plazo. Se basa en la proyección de los recibos de efectivo de los clientes que pagan facturas y pedidos pendientes, y también en la proyección de los desembolsos de efectivo que se pagan a los proveedores por las facturas y los pedidos de compra.

Cuando el sistema predice los pagos de los clientes, utiliza las predicciones de pago de la función de predicción de pagos del cliente. Sin predicciones de pago, el tiempo promedio que se requiere para convertir una factura de cliente en un pago para cada cliente se usa para calcular una fecha de pago. Para los pedidos abiertos de clientes, el sistema calcula la fecha de la factura utilizando el número promedio de días para que se facturen las líneas de pedido por cliente. A continuación, utiliza la fecha de la factura como entrada para la función de predicción de pagos. La función de predicción de pagos del cliente calcula una fecha de pago para cada línea de pedido. 

La fecha de pago de las facturas pendientes se estima aproximadamente a partir de las predicciones de pago, seleccionando una fecha que corresponda al percentil cincuenta de la función de distribución acumulativa que se obtiene a partir de las probabilidades del caso predicho.

Se utiliza un enfoque similar para predecir los pagos a los proveedores. Para cada proveedor, el sistema calcula el tiempo promedio que se requiere para convertir una factura de proveedor en un pago. Ese número de días se usa después para calcular la fecha de pago. Para los pedidos de proveedores abiertos, el sistema calcula la fecha de la factura considerando el número promedio de días que se requieren para convertir las líneas de pedido en una factura para cada proveedor. Luego, el sistema calcula la fecha de pago usando el tiempo promedio para convertir una factura de proveedor en un pago para cada proveedor.

La sección superior de la pestaña **Posición de efectivo** incluye un gráfico de posición de efectivo. Este gráfico muestra las entradas y salidas de efectivo y su impacto en el saldo de liquidez total. Los detalles del gráfico de posición de efectivo se pueden ver en períodos diarios, semanales, mensuales o trimestrales. Cuando selecciona **Diario**, puede ver las previsiones para los próximos 21 días. Cuando selecciona **Semanal**, puede ver las previsiones para las próximas 20 semanas. Cuando selecciona **Mensual**, puede ver las previsiones para los próximos 12 meses. Cuando selecciona **Trimestral**, puede ver las previsiones para los próximos 12 trimestres. Puede ocultar el gráfico si necesita espacio adicional en su pantalla para ver el contenido en la pestaña **Posición de efectivo**.

La sección inferior de la pestaña **Posición de efectivo** muestra los detalles de la posición, el flujo de efectivo, los pagos proyectados y la cuenta bancaria.

- La información de la cuadrícula **Detalles de posición** se presenta en tres secciones: una lista de cuentas de liquidez, una lista de documentos que conforman las entradas de efectivo y una lista de documentos que conforman las salidas de efectivo. La cuadrícula también muestra los saldos de posición de efectivo. Para el primer período que está viendo, el saldo de las cuentas de liquidez es el saldo de apertura. Para períodos posteriores, los saldos de las cuentas de liquidez se calculan con base en la suma de las entradas de efectivo y la resta de las salidas de efectivo de períodos anteriores. Para ver detalles de las transacciones que componen el saldo, seleccione el vínculo **Saldo**.
- La cuadrícula **Flujo de efectivo** muestra las entradas de efectivo, las salidas de efectivo agregadas por período y su impacto en los saldos de las cuentas de liquidez. Para el primer período, el saldo de las cuentas de liquidez es el saldo de apertura. Para períodos posteriores, los saldos de las cuentas de liquidez se calculan con base en la suma de las entradas de efectivo y la resta de las salidas de efectivo de períodos anteriores.
- La cuadrícula **Saldo bancario proyectado** muestra las salidas de efectivo esperadas y su impacto en las cuentas de liquidez.
- La cuadrícula **Cuenta bancaria** muestra el impacto de las entradas y salidas de efectivo esperadas en el saldo bancario.

Para guardar y editar la posición de efectivo, cree una instantánea. Para obtener más información sobre cómo trabajar con instantáneas, consulte [Información general sobre instantáneas](payment-snapshots.md).

## <a name="details-of-the-cash-position-capability"></a>Detalles de la capacidad de posición de efectivo 

La función de posición de efectivo incluye la siguiente funcionalidad. 

- La función de posición de caja muestra el flujo de caja según los documentos existentes en el sistema y las líneas de entrada y salida de caja importadas de sistemas externos.
- Facilita la integración de datos de flujo de efectivo de sistemas externos en Dynamics 365 Finance. La posición de efectivo también pueden utilizar el marco de importación y exportación de datos. Este marco facilita la integración con Excel OData. También puede combinar datos de varias fuentes para crear una solución integral de posición de efectivo.
- Introduce una posición de efectivo inteligente. La posición de efectivo se crea en función del comportamiento de pago del cliente para predecir cuándo una empresa puede esperar que llegue efectivo a sus cuentas.
- Para los pedidos y facturas de los clientes, la función de inteligencia artificial de predicción de pagos del cliente se utiliza para determinar el comportamiento histórico de pago del cliente cuando se pagará un pedido o una factura.
- Para pedidos y facturas de proveedores, usamos el tiempo promedio entre el envío y la factura y el pago de una factura por proveedor para determinar cuándo se pagará un pedido o factura de proveedor, lo que hace que las salidas de efectivo sean más precisas.

Esto crea una vista más precisa del flujo de efectivo basada en el comportamiento de pago histórico del tesorero. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
