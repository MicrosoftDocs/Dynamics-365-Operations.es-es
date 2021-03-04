---
title: Configuración de un técnico preferido
description: Puede seleccionar cualquier trabajador como técnico preferido para un acuerdo de servicio o un pedido de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 850d91372fb1a918840ebc316a4479f4a70bdc24
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436531"
---
# <a name="set-up-a-preferred-technician"></a>Configuración de un técnico preferido 

[!include [banner](../includes/banner.md)]


Puede seleccionar cualquier trabajador como técnico preferido para un acuerdo de servicio o un pedido de servicio. Sin embargo, es una buena idea agregar el trabajador al equipo de distribución apropiado de modo que el trabajador esté incluido en el **Panel de distribución**.

## <a name="assign-employee-to-a-dispatch-team"></a>Asignar el empleado a un equipo de distribución

1.  Haga clic en **Recursos humanos** \> **Común** \> **Trabajadores** \> **Trabajadores**. Haga doble clic en un trabajador para abrir la página de detalles. En el **Panel de acciones**, haga click en **Configuración** \>**Equipo de distribución** para abrir el formulario **Remitir trabajadores** .

2.  En el campo **Equipo de distribución**, seleccione el equipo al que se va a asignar el trabajador.

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>Asignar un técnico preferido a un acuerdo de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**. Haga doble clic en un acuerdo de servicio para abrir el formulario de detalles.

2.  En la ficha **General**, seleccione el campo **Técnico preferido** y, a continuación, seleccione el miembro del equipo de distribución apropiado como técnico preferido para el acuerdo de servicio.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>Asignar un técnico preferido a un pedido de servicio

1.  Haga clic en **Gestión de servicios** \> **Periódico** \> **Panel de distribución**.
    

    > [!NOTE]
    > <P>En el formulario <STRONG>Panel de distribución</STRONG>, especifique el intervalo de fechas de las actividades de distribución que desea ver. Especifique también si desea ver las actividades cerradas y si se debe restringir la lista de actividades de distribución a los equipos a los que pertenece o los equipos que está autorizado a supervisar. Haga clic en <STRONG>Aceptar</STRONG> para abrir el formulario <STRONG>Panel de distribución</STRONG>.</P>



2.  Seleccione la línea de la actividad del servicio que desea modificar.

3.  En la ficha **Relacionado**, utilice la lista **Trabajador** para asignar un miembro del equipo de distribución apropiado como técnico preferido a la llamada de servicio.

## <a name="see-also"></a>Consulte también

[Visión general del desarrollo y establecimiento de acuerdos de servicio](service-agreements.md)

[Crear pedidos de servicio manualmente](create-service-orders-manually.md)

[Acuerdos de servicio (formulario)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]