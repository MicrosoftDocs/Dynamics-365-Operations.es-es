---
title: No puede aplicar una plantilla a un producto lanzado
description: No puede aplicar una plantilla a un producto lanzado.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026874"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>No puede aplicar una plantilla para crear un producto lanzado

Número de KB: 4612097

## <a name="symptoms"></a>Síntomas

Cuando crea un nuevo producto lanzado utilizando el cuadro de diálogo **Nuevo producto lanzado**, puede seleccionar una plantilla. La plantilla debe proporcionar la configuración predeterminada para muchos campos del nuevo producto lanzado. Sin embargo, algunos o todos los campos no se configuran después de seleccionar la plantilla.

## <a name="cause"></a>Causa

Muchas páginas en Microsoft Dynamics 365 Supply Chain Management le permiten crear una plantilla que establece la configuración inicial para los registros que se muestran en esas páginas. Puede crear una de estas plantillas seleccionando **Información de registro** en la pestaña **Opciones** del Panel de acciones. Sin embargo, los productos lanzados son mucho más complejos que la mayoría de los otros tipos de registros. Aunque puede seleccionar **Información de registro** en la página **Productos lanzados** para crear una plantilla y, aunque puede seleccionar esa plantilla cuando crea un producto lanzado, la plantilla no proporcionará los valores de campo esperados para el nuevo producto lanzado. Por lo tanto, no puede usar plantillas de "información de registro" para productos lanzados. En su lugar, debe crear plantillas de productos dedicadas.

## <a name="resolution"></a>Resolución

Para crear una plantilla de producto, use el menú **Plantilla** en la pestaña **Producto** del Panel de acciones, no el botón **Información de registro** en la pestaña **Opciones**.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En el panel de acciones, en la pestaña **Producto**, en el grupo **Nuevo**, seleccione **Plantilla** y luego seleccione **Crear plantilla personal** o **Crear plantilla compartida**, según le convenga.
