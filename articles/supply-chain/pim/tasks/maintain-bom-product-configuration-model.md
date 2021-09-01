---
title: Mantener L. MAT. para un modelo de configuración de producto
description: La ejecución de este procedimiento requiere un modelo de configuración de producto existente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 173022d40a5c1354cbe05c171a8921e733d908d065b10889f9cbe0e87f3e98fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781474"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Mantener L. MAT. para un modelo de configuración de producto

[!include [banner](../../includes/banner.md)]

La ejecución de este procedimiento requiere un modelo de configuración de producto existente. El modelo Altavoz superior de la empresa de demostración USMF se usa para crear este procedimiento.

## <a name="add-a-bom-line"></a>Adición de una línea de L. MAT

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. En la lista, busque y seleccione el registro deseado.
    * Seleccione el Altavoz superior para este procedimiento.  
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Expanda la sección **Líneas de L. MAT**.
1. Seleccione **Agregar**.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Descripción**, escriba un valor.
1. Seleccione **Guardar**.

## <a name="add-bom-line-details"></a>Agregar detalles de línea de L. MAT

1. Seleccione **Detalles de línea de L. MAT.**.
2. En el campo **Número de artículo**, especifique o seleccione un valor.
    * Por ejemplo, puede seleccionar el artículo M0055.  
    * Para cada propiedad de la línea de L. MAT, puede seleccionar si toma un valor fijo o se asigna a un atributo.  
3. Seleccione la casilla **Establecer**.
4. Seleccione *Sí* en el campo **Cálculo**.
    * La configuración de la propiedad **Cálculo** en *Sí* garantiza que se incluye la línea de L. MAT en los cálculos de coste.  
5. Seleccione la pestaña **Configuración**.
6. Seleccione la casilla **Establecer**.
7. En el campo **Cantidad**, especifique un número.
    * El campo de cantidad determina qué cantidad del artículo se incluirá en la L. MAT. Esto podría ser un candidato obvio para una asignación de atributos.  
8. Seleccione la pestaña **Dimensión**.
    * Compruebe si cualquiera de las dimensiones del producto está activas y, por tanto, debe tener un valor o atributo asignado.  
9. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]