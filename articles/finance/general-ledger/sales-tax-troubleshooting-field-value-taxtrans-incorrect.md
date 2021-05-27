---
title: Valor de campo incorrecto en TaxTrans
description: Este tema proporciona información sobre la resolución de problemas de valores de campo incorrectos en TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020172"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="5f0aa-103">Valor de campo incorrecto en TaxTrans</span><span class="sxs-lookup"><span data-stu-id="5f0aa-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5f0aa-104">Si un valor de campo en **TaxTrans** es incorrecto, utilice la información de este tema para intentar resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="5f0aa-105">Resumen de valores</span><span class="sxs-lookup"><span data-stu-id="5f0aa-105">Overview of values</span></span>
<span data-ttu-id="5f0aa-106">La siguiente lista muestra cómo **TaxTrans**, **TaxUncommitted** y **TmpTaxWorkTrans** son conjuntos de datos similares, pero funcionan de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="5f0aa-107">**TaxTrans** es el resultado final de la transacción fiscal registrada que se conservaba en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="5f0aa-108">**TaxUncommitted** es el resultado del impuesto calculado intermedio que se conservaba en la base de datos (si corresponde), y que se utilizará más adelante en el registro.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="5f0aa-109">**TmpTaxWorkTrans** es el resultado del impuesto calculado temporalmente en la tabla en memoria (Tipo de tabla = InMemory).</span><span class="sxs-lookup"><span data-stu-id="5f0aa-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="5f0aa-110">Si encuentra la causa raíz de una columna **TaxTrans** incorrecta, también ha encontrado la causa raíz de un error de columna de **TaxUncommitted** o **TmpTaxWorkTrans**.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="5f0aa-111">Esto se debe a que las tres columnas se copian entre sí.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="5f0aa-112">Normalmente, durante el cálculo de impuestos, se genera **TmpTaxWorkTrans** y luego, si corresponde, se genera **TaxUncommitted**.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="5f0aa-113">Durante el registro de impuestos, se genera **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="5f0aa-114">Agregar puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="5f0aa-114">Add breakpoints</span></span>
<span data-ttu-id="5f0aa-115">Para ajustar un punto de interrupción, complete los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5f0aa-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="5f0aa-116">Agregue extensiones y puntos de interrupción en *insert()* y *update()* en las extensiones, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="5f0aa-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="5f0aa-117">**TaxTrans**</span></span>

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

     - <span data-ttu-id="5f0aa-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="5f0aa-118">**TaxUncommitted**</span></span>

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

     - <span data-ttu-id="5f0aa-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="5f0aa-119">**TmpTaxWorkTrans**</span></span>

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

2. <span data-ttu-id="5f0aa-120">Alternativamente, puede agregar puntos de interrupción directamente cuando **TaxUncommitted** no esta incluido.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="5f0aa-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="5f0aa-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="5f0aa-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="5f0aa-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="5f0aa-123">Reproducir y depurar</span><span class="sxs-lookup"><span data-stu-id="5f0aa-123">Reproduce and debug</span></span>

<span data-ttu-id="5f0aa-124">Una vez establecidos los puntos de interrupción, todos los cambios de persistencia de datos son visibles durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="5f0aa-125">Para encontrar la causa raíz de una columna incorrecta de **TaxTrans**, **TaxUncommitted** o **TmpTaxWorkTrans**, revise y anote los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="5f0aa-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="5f0aa-126">El último punto de interrupción donde la columna es correcta.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="5f0aa-127">El primer punto de interrupción donde la columna es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="5f0aa-128">Qué sucede entre esos dos puntos.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="5f0aa-129">Determinar si existe personalización</span><span class="sxs-lookup"><span data-stu-id="5f0aa-129">Determine whether customization exists</span></span>
<span data-ttu-id="5f0aa-130">Si ha completado los pasos de las secciones anteriores pero no ha podido resolver el problema, determine si existe personalización.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="5f0aa-131">Si no existe personalización, comuníquese con el Soporte de Microsoft para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="5f0aa-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

