---
title: Problemas de sincronización de pedidos asincrónicos
description: Este artículo describe las razones comunes por las que falla la creación de pedidos asincrónicos en Microsoft Dynamics 365 Commerce y brinda pasos para la solución de problemas para ayudar a los usuarios del sistema y a los socios a comprender qué salió mal.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815766"
---
# <a name="asynchronous-order-synchronization-issues"></a>Problemas de sincronización de pedidos asincrónicos

[!include [banner](../../includes/banner.md)]

Este artículo describe las razones comunes por las que falla la creación de pedidos asincrónicos en Microsoft Dynamics 365 Commerce y brinda pasos para la solución de problemas para ayudar a los usuarios del sistema y a los socios a comprender qué salió mal.

## <a name="symptom"></a>Síntoma

Los pedidos asincrónicos que se crean a partir de comercio electrónico o punto de venta (PDV) de Dynamics 365 Commerce no se reflejan en Commerce headquarters.

## <a name="troubleshooting"></a>Solución de problemas

La creación de pedidos puede fallar en la sede central por diferentes motivos, según la etapa en la que falle el proceso de creación de pedidos. Los siguientes pasos de solución de problemas analizan las posibles causas principales.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Validar que la transacción relacionada con el pedido asincrónico ha llegado a la sede central

Para pedidos de comercio electrónico, en la sede central, vaya a **Venta minorista y comercio \> Consultas e informes \> Transacciones de la tienda en línea**. Si tiene un número de confirmación para el pedido, filtre las transacciones ingresando el número de confirmación en el campo **Id. de referencia del canal** . Si no tiene el número de confirmación, filtre las transacciones ingresando el número de cuenta del cliente.

Para pedidos en PDV, abra la página **Transacciones de la tienda** y filtre los registros por el número de recibo o el número de cuenta del cliente. Si no se encuentra la transacción, ejecute el trabajo de transacciones de canal **P-0001**, que sincroniza las transacciones de los canales con la sede central. Si falla el trabajo **P-0001**, abra un ticket de soporte técnico para el error del trabajo. Si el trabajo **P-0001** se realiza correctamente, pero las transacciones aún no aparecen en la sede central, abra un ticket de soporte técnico que incluya la información relevante.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>Verifique el estado de sincronización si la transacción está presente en la sede central pero no está vinculada con un pedido de venta

Si la transacción está presente en la sede central, pero el pedido de venta no se ha creado, abra la página **Transacciones de la tienda en línea** y seleccione la ficha rápida **Estado de sincronización**. Si el trabajo **Sincronizar pedidos** ha intentado sincronizar esta transacción, el campo **Estado del pedido pendiente** debe mostrar un estado de **Correcto** o **Error**. Si el estado es **Correcto**, el campo de pedido de venta debe estar presente en esta transacción. Si el estado es **Error**, puede ver los detalles del error en el campo **Detalles del error del pedido** en la ficha rápida **Estado de sincronización**. Si no se muestra ninguno de estos estados, no se ha intentado procesar la transacción. En este caso, puede seleccionar **Sincronizar pedido** en la parte superior de la página para ejecutar el trabajo de sincronización.

Asegúrese de que el trabajo **Sincronizar pedidos** está programado para ejecutarse periódicamente, de modo que las transacciones asincrónicas se puedan crear como pedidos en la sede.

Las siguientes secciones brindan información sobre algunos errores comunes y sus soluciones propuestas.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>El campo Detalles del error del pedido muestra el siguiente mensaje de error: "Se ha excedido la secuencia numérica"

Las secuencias numéricas se utilizan para crear pedidos de venta en la sede central. Si se agotan todos los números permitidos para una secuencia numérica, el sistema genera este mensaje de error. La secuencia numérica que se utiliza para crear pedidos de venta se puede encontrar en **Parámetros de clientes \> Secuencias numéricas \> Pedido de venta**. Para corregir este error, corrija la secuencia numérica existente o reemplácela con una nueva secuencia numérica.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>El campo Detalles de errores del pedido muestra el siguiente mensaje de error: "Debe haber un servicio de pago predeterminado para procesar transacciones con tarjeta de crédito"

Para corregir este error, confirme que se haya definido un pago predeterminado en la sede central. Si no se define ningún pago predeterminado, debe definir uno. Vaya a **Clientes \> Configuración de pago \> Servicios de pago** y asegúrese de que la opción **Procesador predeterminado para nuevas tarjetas de crédito** está establecida en **Sí** para un servicio de pago.
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>El campo Detalles de errores de pedido muestra un mensaje de error de estructura de cuenta

El texto del mensaje de error de la estructura de cuenta puede variar, como muestran los siguientes ejemplos. Sin embargo, los errores comparten una causa raíz común que está relacionada con la configuración de la estructura de la cuenta.

- "El registro de resultados para el número de lote del diario 0009656328 Asiento ARP-000959899 1.00 para el asiento ARP-000959899 en la empresa usrt se contabilizará como sobrepago o pago insuficiente"
- "El registro de resultados para la estructura de la cuenta del número de lote del diario 0009656328 Asiento ARP-000959899 Asiento ARP-000959901, para la combinación 618160, no es válida para Cuenta principal corporativa compartida del libro mayor"
- "El registro resultados para el número de lote del diario 0009656328 Asiento ARP-000959899 Asiento ARP-000959901 presentado desde las cuentas de la empresa usrt"
- "El registro de resultados para el registro del número de lote del diario 0009656328 Asiento ARP-000959899 ha sido cancelado"
    
Para corregir estos errores, revise la precisión de las estructuras de la cuenta. Para obtener más información, consulte [Configurar estructuras contables](/dynamics365/finance/general-ledger/configure-account-structures).
    
Después de corregir el error, seleccione la transacción fallida y luego seleccione **Sincronizar pedido** en la parte superior de la página para ejecutar el trabajo de sincronización.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Otros tipos de errores que pueden requerir que se corrijan los datos de la transacción

Para corregir otros tipos de errores que pueden requerir que se corrijan los datos de la transacción, puede usar la capacidad de "editar y auditar transacciones". Para obtener más información, consulte [Editar y auditar transacciones](../edit-order-trans.md).
