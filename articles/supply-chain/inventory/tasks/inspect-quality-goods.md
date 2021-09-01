---
title: Inspeccionar la calidad de las mercancías
description: Este tema explica cómo procesar los pedidos de calidad.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceb5547b6c1d4c44e53faba0d6e2c1f0368fb95768a2520ecc39066ff73a03d2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755379"
---
# <a name="inspect-the-quality-of-goods"></a>Inspeccionar la calidad de las mercancías

[!include [banner](../../includes/banner.md)]

Este tema explica cómo procesar los pedidos de calidad. Las inspecciones de calidad las realiza normalmente un empleado de control de calidad.

Si los datos de demostración estándar están instalados, puede utilizarlos para completar los procedimientos de este tema. Para usar los datos de demostración, seleccione la entidad legal *USMF* antes de empezar. A continuación, debe confirmar la orden de compra *000016* y registrar una recepción de producto. Se genera automáticamente un pedido de calidad.

## <a name="step-1-select-a-quality-order"></a>Paso 1: seleccionar un pedido de calidad

Para seleccionar un pedido de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Seleccione el pedido de calidad que se generó antes de empezar este procedimiento.

## <a name="step-2-record-test-results"></a>Paso 2: registrar resultados de prueba

Para registrar los resultados de prueba, siga estos pasos.

1. Seleccione **Resultados**.
1. Seleccione **Editar**.
1. En el campo **Cantidad de resultado**, especifique un número.
1. En el campo **Resultado**, seleccione el registro deseado. En este ejemplo, el resultado se basa en un resultado predefinido. Normalmente, registrará un resultado de prueba más específico, como el tamaño u otra dimensión.
1. Seleccione **Guardar**.
1. Cierre la página.

## <a name="step-3-validate-the-quality-order"></a>Paso 3: validar el pedido de calidad

Para validar el pedido de calidad, siga estos pasos.

1. Seleccione **Validar**.
1. En el campo **Validado por**, seleccione el usuario que está realizando la inspección.
1. Seleccione **Seleccionar**.
1. Seleccione **Aceptar**.
1. Cierre la página.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
