---
title: Inspeccionar la calidad de las mercancías
description: Este tema explica cómo procesar un pedido de calidad.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e37ac8c9320d427b9f9a3ca32b0e4667c7023339
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244432"
---
# <a name="inspect-the-quality-of-goods"></a>Inspeccionar la calidad de las mercancías

[!include [banner](../../includes/banner.md)]

Este tema explica cómo procesar un pedido de calidad. Puede ejecutar esta guía en la empresa de datos de demostración USMF. Antes de comenzar este procedimiento de ejemplo, debe confirmar el pedido de compra "000016" y registrar una recepción de producto. Esto crea automáticamente un pedido de calidad. Las inspecciones de calidad las lleva a cabo normalmente un empleado de control de calidad.


## <a name="select-a-quality-order"></a>Selección de un pedido de calidad
1. En el panel de navegación, vaya a **Módulos > Gestión de inventario > Tareas periódicas > Administración de calidad > Pedidos de calidad**.
2. Seleccione el pedido de calidad que se creó antes de empezar este procedimiento.  

## <a name="record-test-results"></a>Registrar resultados de prueba
1. Seleccione **Resultados**.
2. Seleccione **Editar**.
3. En el campo **Cantidad de resultado**, especifique un número.
4. En el campo **Resultado**, seleccione en el menú desplegable el registro que desee.  
- En este ejemplo, el resultado se basa en un resultado predefinido. Normalmente, registrará un resultado de prueba más específico, como el tamaño u otra dimensión.  
5. Seleccione **Guardar**.
6. Cierre la página.

## <a name="validate-the-quality-order"></a>Validar el pedido de calidad
1. Seleccione **Validar**.
2. En el campo **Validado por** , seleccione el usuario que estaba realizando la inspección en el menú desplegable.  
3. Haga clic en **Seleccionar**.
4. Seleccione **Aceptar**.
5. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]