---
title: Cancelar trabajo de almacén para control de excepciones
description: En este artículo se describe la funcionalidad cancelar trabajo que permite a los supervisores de almacén gestionar el trabajo bloqueado.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b1e2036e4e7a8a47d6df029f285df7aca0fa74e6
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403708"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Cancelar trabajo de almacén para control de excepciones

[!include [banner](../includes/banner.md)]

La funcionalidad cancelar trabajo en Microsoft Dynamics 365 Supply Chain Management permite al usuario administrador cancelar un determinado trabajo de almacén que está actualmente en curso, pero que está bloqueado por el sistema o no se puede completar debido a circunstancias excepcionales. Esta funcionalidad es una alternativa segura y atractiva a las secuencias de comandos correctivos de SQL que corrigen datos incoherentes. Sin embargo, mientras que estas secuencias de comandos se suelen solicitar a los profesionales de TI, los usuarios de la empresa que tengan derechos de administrador pueden usar la funcionalidad cancelar trabajo.

Puede acceder a la funcionalidad cancelar trabajo en **Gestión de almacenes** \> **Tareas periódicas** \> **Limpiar \> Cancelar trabajo**. En el cuadro de diálogo **Cancelar trabajo**, especifique el id. de trabajo del trabajo que desee cancelar y, a continuación, seleccione **Aceptar**.

## <a name="warehouse-work-that-can-be-canceled"></a>Trabajo de almacén que se puede cancelar

Durante las operaciones de picking de almacén, un trabajador puede encontrarse situaciones en las que ha registrado cantidades como seleccionadas desde una ubicación de almacenamiento a su ubicación de usuario, pero que no puede registrar la operación de colocación. Los datos incoherentes del almacén suelen ser, pero no siempre, el motivo por el que se bloquea el trabajo.

A diferencia de la funcionalidad habitual de cancelar a la que se puede acceder mediante el botón **Cancelar** en el encabezado de trabajo, la funcionalidad cancelar trabajo no requiere que la última línea de trabajo completada sea una línea de trabajo del tipo **colocación**. Es decir, para la funcionalidad cancelar trabajo, la lógica de cancelación se puede ejecutar incluso si la cantidad de artículos en una línea del trabajo está en una ubicación de usuario.

> [!NOTE]
> Para el trabajo que se debe cancelar por razones operativas, los usuarios de almacén deben seguir usando la funcionalidad cancelar en la página de trabajo.

Solo se puede cancelar el trabajo del tipo **Ventas**, **Emisión de transferencia**, **Picking de materia prima** o **Reabastecimiento** mediante la funcionalidad cancelar trabajo. La lógica de cancelación no se ejecutará para un trabajo de picking de materia prima ni para un trabajo que se puede cancelar mediante la funcionalidad habitual cancelar (consulte la nota anterior).

Para desbloquear el trabajo, el sistema cancela cualquier línea de trabajo restante y corrige los datos de almacén que se asocian al id. de trabajo que especificó el usuario. A continuación, se puede reanudar cualquier operación habitual de manipulación en el almacén que implique la cantidad de artículos afectada.

Para poner el artículo afectado en una ubicación concreta después de que se cancele el trabajo, el usuario debe usar una operación de movimiento de inventario o de ajuste de cantidad en un dispositivo móvil.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]