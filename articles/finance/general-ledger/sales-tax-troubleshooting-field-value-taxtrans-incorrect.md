---
title: Valor de campo incorrecto en TaxTrans
description: Este artículo proporciona información sobre la resolución de problemas de valores de campo incorrectos en TaxTrans.
author: EricWangChen
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6e7329ffdc04207116c92cb42e02750b176713fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899825"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Valor de campo incorrecto en TaxTrans

[!include [banner](../includes/banner.md)]

Si un valor de campo en **TaxTrans** es incorrecto, utilice la información de este artículo para intentar resolver el problema.

## <a name="overview-of-values"></a>Resumen de valores
La siguiente lista muestra cómo **TaxTrans**, **TaxUncommitted** y **TmpTaxWorkTrans** son conjuntos de datos similares, pero funcionan de manera diferente.

  - **TaxTrans** es el resultado final de la transacción fiscal registrada que se conservaba en la base de datos.
  - **TaxUncommitted** es el resultado del impuesto calculado intermedio que se conservaba en la base de datos (si corresponde), y que se utilizará más adelante en el registro.
  - **TmpTaxWorkTrans** es el resultado del impuesto calculado temporalmente en la tabla en memoria (Tipo de tabla = InMemory).

Si encuentra la causa raíz de una columna **TaxTrans** incorrecta, también ha encontrado la causa raíz de un error de columna de **TaxUncommitted** o **TmpTaxWorkTrans**. Esto se debe a que las tres columnas se copian entre sí.

Normalmente, durante el cálculo de impuestos, se genera **TmpTaxWorkTrans** y luego, si corresponde, se genera **TaxUncommitted**. Durante el registro de impuestos, se genera **TaxTrans**.


## <a name="add-breakpoints"></a>Agregar puntos de interrupción
Para ajustar un punto de interrupción, complete los siguientes pasos: 

1. Agregue extensiones y puntos de interrupción en *insert()* y *update()* en las extensiones, como se muestra a continuación.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. Alternativamente, puede agregar puntos de interrupción directamente cuando **TaxUncommitted** no esta incluido.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Reproducir y depurar

Una vez establecidos los puntos de interrupción, todos los cambios de persistencia de datos son visibles durante la depuración. Para encontrar la causa raíz de una columna incorrecta de **TaxTrans**, **TaxUncommitted** o **TmpTaxWorkTrans**, revise y anote los siguientes elementos:

- El último punto de interrupción donde la columna es correcta.
- El primer punto de interrupción donde la columna es incorrecta.
- Qué sucede entre esos dos puntos.

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización
Si ha completado los pasos de las secciones anteriores pero no ha podido resolver el problema, determine si existe personalización. Si no existe personalización, comuníquese con el Soporte de Microsoft para obtener ayuda.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

