---
title: Goteo en la creación de pedidos basados en fuente para transacciones de tienda
description: En este artículo se describe el goteo de la creación de pedidos basados en fuente para las transacciones de tienda en Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0f0ee361df8c565761e79f5b0ecf519c149f2ec0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873261"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Goteo en la creación de pedidos basados en fuente para transacciones de tienda

[!include [banner](includes/banner.md)]

En Microsoft Dynamics 365 Commerce versión 10.0.5 y posteriores, le recomendamos que realice la transición de todos los procesos de registro para el goteo de los procesos de registros de extractos basados en fuente. Se asocian importantes beneficios comerciales y de rendimiento con el uso de la funcionalidad de goteo basado en fuente. Las transacciones de ventas se procesan a lo largo del día. Las transacciones de licitación y gestión del efectivo se procesan en el informe financiero al final del día. La funcionalidad de goteo basado en fuente permite el procesamiento continuo de pedidos de venta, facturas y pagos. Por tanto, el inventario, los ingresos y los pagos se pueden actualizar y reconocer casi en tiempo real.

## <a name="use-trickle-feed-based-posting"></a>Usar el goteo del registro basado en fuente

> [!IMPORTANT]
> Para habilitar el goteo en el registro basado fuente, debe asegurarse de que no haya extractos no calculados o no registrados. Registre todos los extractos antes de habilitar la característica. Puede comprobar si hay extractos abiertos en el espacio de trabajo **Operaciones financieras de tienda**.

Para habilitar el goteo del registro basado en fuente de transacciones comerciales, habilite la característica denominada **Extractos comerciales - Fuente de goteo** del espacio de trabajo **Administración de características**. Los extractos se dividirán en dos tipos: extractos transaccionales e informes financieros.

### <a name="transactional-statements"></a>Extractos transaccionales

El procesamiento de extractos transaccionales está pensado para ejecutarse en una frecuencia alta a lo lardo del día, de manera que se creen documentos cuando se carguen las transacciones en la sede central de Commerce. Las transacciones se cargan desde las tiendas en la sede central de Commerce cuando ejecuta el **trabajo P**. También debe ejecutar el trabajo **Validar transacciones de la tienda** para validar transacciones para que el informe de transacción las recoja.

Programe los siguientes trabajos para que se ejecuten con alta frecuencia:

- Para calcular un informe transaccional, ejecute el trabajo **Calcular extractos transaccionales por lote** (**Retail y Commerce \> TI de Retail y Commerce \> Registro de PDV \> Calcular extractos transaccionales por lotes**). Este trabajo recogerá todas las transacciones validadas y no registradas, y las agregará a un nuevo extracto transaccional.
- Para registrar informes de transacción en un lote, ejecute el trabajo **Registrar extractos transaccionales por lotes** (**Retail y Commerce \> TI de Retail y Commerce \> Registro de PDV \> Registrar extractos transaccionales por lotes**). Este trabajo ejecutará el proceso de registro y creará pedidos de ventas, facturas de ventas, diarios de pago, diarios de descuentos y transacciones de ingresos y gastos para extractos no registrados que no contienen ningún error. 

### <a name="financial-statements"></a>Informes financieros

El procesamiento de informes financieros está pensado para ser un proceso de final del día. Este tipo de procesamiento de extractos solo admite el método de cierre **Turno** y solo recogerá turnos cerrados. Los extractos se limitan a la conciliación financiera. Solo crearán los diarios para los importes de diferencia entre el importe contado y el importe de la transacción para las diferentes formas de pago, junto con los diarios para otras transacciones de gestión del efectivo.

Los informes financieros también permiten revisar las siguientes transacciones: transacciones de declaración por forma de pago, transacciones de pago, transacciones de forma de pago bancarias y transacciones de forma de pago en caja fuerte. La página de detalles de forma de pago solo es visible cuando se selecciona un informe financiero.

![Una imagen que muestra la sección de detalles de forma de pago del formulario de informes registrados solo es visible cuando se selecciona un informe financiero.](./media/Trickle-feed-posted-statements-transaction-view.png)

Programe las horas de inicio y finalización de los siguientes trabajos de informes financieros en función del final del día previsto:

- Para calcular un informe financiero, ejecute el trabajo **Calcular informes financieros por lote** (**Retail y Commerce \> TI de Retail y Commerce \> Registro de PDV \> Calcular informes financieros por lote**). Este trabajo recopilará todas las transacciones financieras no registradas y las agregará a un nuevo informe financiero.
- Para registrar informes financieros en un lote, ejecute el trabajo **Registrar informes financieros por lote** (**Retail y Commerce \> TI de Retail y Commerce \> Registro de PDV \> Registrar informes financieros por lote**).

### <a name="manually-create-statements"></a>Crear extractos manualmente

Los tipos de informes financieros y de transacción también se pueden crear manualmente. 

1. Vaya a **Retail y Commerce \> Canales \> Tiendas** y seleccione **Extractos**. 
2. Seleccione **Nuevo** y, a continuación, el tipo de extracto que desea crear. Los campos de la página **Extractos** mostrarán los datos relevantes para el tipo de extracto seleccionado y las acciones del **Grupo de extracto** mostrarán las acciones pertinentes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
