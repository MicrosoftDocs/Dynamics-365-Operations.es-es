---
title: Generar un documento de transferencia para una transferencia de inventario interna
description: Este procedimiento muestra cómo crear documentos de transferencia para movimiento de mercancías dentro de una empresa.
author: EvgenyPopovMBS
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
ms.openlocfilehash: bb58337f7e0a269392c7969cf24d196b030d576d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275191"
---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a>Generar un documento de transferencia para una transferencia de inventario interna

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear documentos de transferencia para movimiento de mercancías dentro de una empresa. Este procedimiento sólo está disponible para entidades jurídicas con dirección principal en Lituania. Este procedimiento se ha creado con los datos de demostración de la empresa DEMF, con una dirección principal en Lituania. Antes de completar este procedimiento, deberá completar el procedimiento de “Configuración de los documentos de transferencia de mercancías dentro de una empresa”. Este procedimiento está dirigido a contables de inventario. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-a-transfer-order"></a>Creación de un pedido de transferencia
1. Vaya a Gestión del inventario > Pedidos de entrada > Orden de transferencia.
2. Haga clic en Nuevo.
3. En el campo Desde almacén, especifique o seleccione un valor.
4. En el campo Hasta almacén, especifique o seleccione un valor.
5. Haga clic en Agregar.
6. En la lista, marque la fila seleccionada.
7. En el campo Número de artículo, especifique o seleccione un valor.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Especificar los detalles de transporte para el pedido de transferencia
1. Haga clic en Guardar.
2. En el panel de acciones, haga clic en Enviar.
3. Haga clic en Detalles de transporte.
4. Seleccione Sí en el campo Imprimir detalles de transporte.
5. En el campo Mercancías emitidas por, especifique o seleccione un valor.
6. En el campo Paquete, escriba un valor.
7. En el campo Nivel de riesgo de la carga, escriba un valor.
8. En el campo Transportista, especifique o seleccione un valor.
9. En el campo Modelo, especifique o seleccione un valor.
10. En el campo Número de registro, escriba un valor.
11. En el campo Número de registro del tráiler, escriba un valor.
12. En el campo Conductor, especifique o seleccione un valor.
13. En el campo Nombre de conductor, escriba un valor.
14. Haga clic en Guardar.
15. Cierre la página.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Ver el albarán para el pedido de transferencia sin registrar
1. Haga clic en Albarán.
2. Haga clic en Aceptar
3. Cierre la página.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Ver el albarán para el pedido de transferencia registrado
1. En el panel de acciones, haga clic Transferir pedido.
2. En el panel de acciones, haga clic en Enviar.
3. Haga clic en Enviar pedido de transferencia.
4. Haga clic en la pestaña General.
5. En el campo Actualizar, seleccione una opción.
6. Haga clic en la ficha Visión general.
7. En el campo Albarán, escriba un valor.
8. Haga clic en Aceptar
9. En el panel de acciones, haga clic en Enviar.
10. Haga clic en Albarán.
11. Haga clic en Aceptar



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
