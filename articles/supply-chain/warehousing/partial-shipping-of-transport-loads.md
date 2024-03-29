---
title: Envío parcial de una carga de transporte
description: Este artículo explica cómo puede registrar parcialmente una carga y posponer la planificación de capacidad para la carga.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 09e35b8ee39b3635938f46e174e6ba98db7fa627
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907040"
---
# <a name="partial-shipment-of-a-transport-load"></a>Envío parcial de una carga de transporte

[!include[banner](../includes/banner.md)]

Si configura el envío parcial de cargas, podrá gestionar las cargas en las que la capacidad no se pueda determinar hasta que todas las líneas de ventas se hayan agregado a una carga. El proceso puede ser concluido cuando ya se conoce el recuento exacto del pallet. Por lo tanto, no es necesario decidir qué pallets se asignarán a qué transporte hasta el momento en que un transporte se carga físicamente fuera del inventario.

Esta característica permite una alternativa al cumplimiento de una estructura más rígida, donde debe determinar qué pallets se asignarán a qué transporte antes de que se cree el trabajo de picking o el trabajo de carga. En su lugar, los usuarios pueden configurar cargas individuales para una confirmación de envío parcial. Los procesos de carga del transporte para esas cargas pueden ocurrir continuación. Por lo tanto, el departamento de planificación de transporte puede planificar las cargas sin tener que tener en cuenta la capacidad de transportes individuales.

En el momento de la carga, los trabajadores pueden definir una nueva carga de transporte que se puede cargar a un pallet. Como alternativa, puede identificar una carga de transporte existente. Estos datos se pueden registrar mediante un dispositivo móvil. Por lo tanto, varios trabajadores de almacén pueden cargar el inventario desde las mismas cargas o distintas de cargas sobre el mismo camión. Las cargas a continuación pueden enviarse total o parcialmente.

> [!NOTE] 
> Para cargar el inventario de una carga a una carga específica de transporte y registrar parcialmente la carga, el trabajo se debe generar mediante una clase de carga en una plantilla de trabajo. El trabajo habitual de picking del tipo **Picking** no se puede cargar a una carga de transporte como un camión.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Configurar cargas de transporte para envío parcial

La configuración del envío parcial de cargas consta de los dos procedimientos siguientes.

### <a name="set-the-loading-strategy"></a>Establecer la estrategia de carga

Debe habilitar la carga parcial estableciendo la estrategia de carga. Puede establecer la estrategia de carga después de que haya creado una carga.

1. Seleccione **Gestión de almacenes** \> **Cargas** \> **Todos cargas**.
2. Seleccione una carga y, a continuación, haga clic en **Encabezado**.
3. En el campo **Estrategia de carga**, seleccione **Envío parcial de carga permitido**.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Crear un artículo de menú para carga de las cargas de transporte

Debe crear un nuevo artículo de menú que habilite las cargas de transporte que se cargarán. Una carga de transporte le permite agrupar líneas del grupo de trabajo a partir de una carga o de múltiples cargas. Todo lo que se agrega a la carga de transporte se puede enviar usando un escáner móvil.

1. Seleccione **Gestión de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil**.
2. Seleccione **Nuevo** y, en el campo **Modo**, seleccione **Trabajo**.
3. Establezca la opción **Usar trabajo existente** en **Sí**.
4. En la ficha **General**, en el campo **Dirigido por**, seleccione **Carga de transporte**.
5. Para habilitar la confirmación de envío en un escáner móvil, en el campo **Tipo de confirmación de envío permitida**, seleccione **Carga de transporte**.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Confirmar el envío de una carga de transporte desde el cliente

Esta configuración le permite confirmar una carga de transporte que incluya una carga completa o una carga parcial cargada que ser enviada

1. Seleccione **Gestión de almacenes** \> **Cargas** \> **Cargas de transporte**.
2. En el panel de acciones, en la ficha **Enviar y recibir**, en el grupo **Confirmar**, seleccione **Transporte**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]