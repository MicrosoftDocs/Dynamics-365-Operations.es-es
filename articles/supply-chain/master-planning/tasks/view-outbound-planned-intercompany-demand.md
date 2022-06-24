---
title: Ver la demanda planificada de empresas vinculadas saliente
description: Este artículo proporciona un procedimiento que muestra cómo ver la demanda de empresas vinculadas planificada saliente.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcdea0af5cb522646bc63c7e5ef1d4e54e0a3547
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895652"
---
# <a name="view-outbound-planned-intercompany-demand"></a>Ver la demanda planificada de empresas vinculadas saliente

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas. La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.

1. Seleccione **Planificación maestra**.
2. En el campo **Plan**, especifique o seleccione un valor.
    * En el campo **Plan** seleccione plan *10*.  
3. Seleccione *Ejecutar*.
4. En el campo **Número de subprocesos**, especifique un número.
    * Esto representa el número de subprocesos paralelos que se utilizarán para la planificación maestra.  
5. Seleccione **Aceptar**.
    * Esto puede tardar unos minutos.  
6. Seleccione en **Demanda planificada de empresa vinculada**.
7. Seleccione **Demanda planificada de empresas vinculadas saliente**.
    * Esta página ofrece una visión general de toda la demanda planificada que cumplirá un proveedor interno de la cadena de suministro.  
8. Expanda la sección **Detalles de la demanda de nivel superior**.
    * En esta sección, puede ver detalles acerca de cómo se cumplirá con la demanda. Es posible que tenga que esperar la planificación maestra que se ejecutará en la empresa de aprovisionamiento antes de que se pueda ver información adicional aquí.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
