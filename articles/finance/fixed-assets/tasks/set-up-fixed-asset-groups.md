---
title: Configurar grupos de activos fijos
description: En ese tema se explica cómo crear un nuevo grupo de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bcb78158afbf7bb0e9b83b35e37b1532a7c6283
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138193"
---
# <a name="set-up-fixed-asset-groups"></a>Configurar grupos de activos fijos

[!include [banner](../../includes/banner.md)]

En ese tema se explica cómo crear un nuevo grupo de activos fijos. Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.

1. En el panel de navegación, vaya a **Módulos > Activos fijos > Configuración > Grupos de activos fijos**.
2. Seleccione **Nuevo**.
3. En el campo **Grupo de activos fijos**, escriba un valor.
4. En el campo **Nombre**, escriba un valor. Las opciones Enumerar automáticamente los activos fijos y Código de secuencia numérica del grupo de **Activos fijos** reemplazarán la configuración de los parámetros de activos fijos. Puede cambiarlo aquí si los activos de este grupo de activos fijos tendrán una numeración diferente a la de otros grupos.  
5. Seleccione **Libros**.
6. En el campo **Libro**, especifique o seleccione un valor. El campo **Calcular depreciación** se establece en **Sí** para que el libro del activo se incluya en las propuestas de depreciación. Si **Calcular la depreciación** se establece en **No**, el activo no se depreciará automáticamente.  
7. Establezca el tiempo de vida del activo, en años. Tenga en cuenta que el valor del campo **Períodos de depreciación** se calcula después de definir el tiempo de vida.  
8. En el campo **Convención de amortizaciones**, seleccione una opción.
9. Cierre la página.

