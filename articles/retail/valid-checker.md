---
title: Comprobador de coherencia de transacción comercial
description: Este tema describe la funcionalidad del comprobador de coherencia de transacción comercial en Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8b373ce3cfd1183a082e2b1ebaf8c907b16e581e
ms.sourcegitcommit: ca4562fafa33b3512f0a5e246b15545fcf53e834
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "380002"
---
# <a name="retail-transaction-consistency-checker"></a>Comprobador de coherencia de transacción comercial


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

Este tema describe la funcionalidad del comprobador de coherencia de transacción comercial presentada en la versión 8.1.3. de Microsoft Dynamics 365 for Finance and Operations. El comprobador de coherencia identifica y aísla transacciones incoherentes antes de que sean recogidos por el proceso de registro de extractos.

Cuando un extracto se registra en Retail, el registro puede fallar debido a datos incoherentes en las tablas de transacción comercial. El problema de los datos puede ser causado por problemas imprevistos en la aplicación de punto de venta (PDV) o si las transacciones se importaron incorrectamente de los sistemas PDV de terceros. Entre los ejemplos de cómo estas incoherencias pueden aparecer se incluyen: 

  - El total de la transacción en la tabla de encabezado no coincide con el total de la transacción en las líneas.
  - El recuento de líneas en la tabla de encabezado no coincide con el número de líneas en la tabla de transacción.
  - Los impuestos de la tabla de encabezado no coinciden con el importe de impuestos en las líneas. 
  
Cuando las transacciones incoherentes son recogidas por el proceso de registro de extractos, se crean facturas de ventas y diarios de pagos incoherentes y, como resultado, el proceso completo de registro de extractos da error. Recuperar los extractos de ese estado implica correcciones de datos complejos en varias tablas de transacción. El comprobador de coherencia de transacción comercial evita estos problemas.

El siguiente gráfico ilustra el proceso de registro con el comprobador de coherencia de transacción.

![Proceso de registro de extractos con comprobador de coherencia de transacción comercial](./media/validchecker.png "Proceso de registro de extractos con comprobador de coherencia de transacción comercial")

El proceso por lotes **Validar transacciones de la tienda** comprueba la coherencia de las tablas de transacción comercial para los siguientes escenarios.

- Cuenta de cliente: valida que la cuenta de cliente en las tablas de transacción comercial existe en el maestro de clientes de la sede.
- Recuento de líneas: valida que el número de líneas, como se recoge en la tabla de encabezado de transacción, coincide con el número de líneas en las tablas de transacción de ventas.

## <a name="set-up-the-consistency-checker"></a>Configurar el comprobador de coherencia
Configurar el proceso por lotes "Validan transacciones de la tienda", en **Venta minorista \> TI de venta minorista \> Registro de PDV**, para ejecuciones periódicas. El trabajo por lotes se puede programar según la jerarquía organizativa de la tienda, similar a cómo se configuran los procesos "Calcular extracto en lote" y "Registrar extracto en lote". Es recomendable que configure este proceso por lotes para ejecutar varias veces en un día y programarlo de modo que se ejecute al final de cada ejecución de trabajo P.

## <a name="results-of-validation-process"></a>Resultados del proceso de validación
Los resultados de la comprobación de validación por el proceso por lotes se etiquetan en la transacción comercial adecuada. El campo **Estado de validación** en el registro de transacción comercial se establece en **Correcto** o **Error** y la fecha de la última ejecución de validación aparece en el campo **Hora de la última validación**.

Para ver un texto de error más descriptivo relativo a un error de validación, seleccione el registro de transacción de tienda relevante y haga clic en el botón **Errores de validación**.

Las transacciones que producen un error en la comprobación de validación y las transacciones que aún no se han validado no se incluirán en los extractos. Durante el proceso "Calcule extracto", se notificará a los usuarios si hay transacciones que se habrían podido incluir en el extracto pero no se incluyeron.

Si se encuentra un error de validación, la única forma de corregir el error es contactar el Soporte técnico de Microsoft. En una versión futura, se agregará una capacidad para que los usuarios puedan corregir los registros que produjeron error a través de la interfaz de usuario. Las capacidades de registro y auditoría también estarán disponibles para realizar un seguimiento del historial de las modificaciones.

> [!NOTE]
> En una versión futura se agregarán reglas de validación adicionales para admitir más escenarios.
