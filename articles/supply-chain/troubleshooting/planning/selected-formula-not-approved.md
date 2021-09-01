---
title: El número de fórmula seleccionado no está aprobado para pedidos de lote
description: Cuando intenta confirmar un pedido planificado, recibe un mensaje de error que indica que el número de fórmula seleccionado no está aprobado para un pedido por lotes.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a41cf955d151726348bea83e52a24bc8784352c2d07268ced944e4cc6bf35491
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712919"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>El número de fórmula seleccionado no está aprobado para pedidos de lote

Código de error: PRO2614

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un pedido planificado, recibe el siguiente mensaje de error:

> El número de fórmula seleccionado no está aprobado para pedidos de lote.

## <a name="cause"></a>Causa

El sistema valida la operación de endurecimiento para asegurarse de que haya una fórmula aprobada disponible para el artículo activo. Probablemente debas aprobar la fórmula.

## <a name="resolution"></a>Resolución

Para aprobar una fórmula, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Listas de materiales y fórmulas \> Fórmulas**.
1. Seleccione la fórmula relevante.
1. En el Panel de acciones, en la ficha **Fórmula**, en el grupo **Mantener**, haga clic en **Aprobar fórmula**.
1. En el cuadro de diálogo **Aprobar lista de materiales o fórmula**, seleccione un aprobador y luego seleccione **Aceptar**.
