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
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294169"
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
