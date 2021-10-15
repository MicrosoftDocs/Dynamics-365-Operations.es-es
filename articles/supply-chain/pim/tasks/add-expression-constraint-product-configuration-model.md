---
title: Agregar una restricción de expresión a un modelo de configuración de producto
description: Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569658"
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