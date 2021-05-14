---
title: Agregar una restricción de expresión a un modelo de configuración de producto
description: Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920890"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Agregar una restricción de expresión a un modelo de configuración de producto

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos. Muestra cómo puede ordenar que la protección de la esquina se aplique a un altavoz si el usuario ha seleccionado una parrilla delantera metálica. El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.

## <a name="create-an-expression-constraint"></a>Crear una restricción de expresión

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
3. En la lista, busque y seleccione el registro deseado.
    * Este ejemplo usa el modelo de altavoz superior.  
4. En la lista, seleccione el vínculo de la fila seleccionada.
5. Expandir la sección **Restricciones**.
6. Seleccione **Agregar**.
7. Seleccione **Crear**.
8. En el campo **Nombre**, escriba un valor.

## <a name="enter-expression"></a>Introducir expresión

1. Seleccione **Editar expresión**.
    * Si desbloquea la interfaz del usuario en la grabación de tareas en esta fase, puede usar IntelliSense y la lista de símbolos para crear la expresión de la restricción.  
2. En el campo **ConstraintBody**, especifique 'Implies[FrontGrill=="Metal", CornerProtection] '.
    * Esta lógica de la expresión indica: Si la parrilla delantera es metálica, se debe seleccionar la opción de protección de la esquina.  
3. Seleccione **Validar**.
    * La función validar se ejecuta a través de la expresión de restricción y comprueba los errores de sintaxis.  
4. Seleccione **Cerrar**.
5. Seleccione **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]