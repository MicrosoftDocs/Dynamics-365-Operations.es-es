---
title: "Información general de la gestión de recursos"
description: "En este tema se describe la manera de usar el servicio de gestión de recursos (WFM) para sacar el máximo partido de los clientes de los puntos de venta (PDV), los PDV modernos y los PDV en la nube, para que los jefes de tienda puedan administrar fácilmente los recursos."
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="workforce-management-overview"></a>Información general de la gestión de recursos

[!include[banner](includes/banner.md)]
    
El servicio de gestión de recursos (WFM) saca el máximo partido a los clientes de los puntos de venta (PDV), los PDV modernos y los PDV en la nube, para que los jefes de tienda puedan administrar fácilmente los recursos. El servicio WFM utiliza el marco de extensión para descargar en PDV los paquetes adecuados. Estos paquetes se descargan cuando se cierra y se vuelve abrir el PDV. Por lo tanto, si Microsoft publica las nuevas características para WFM, debe cerrar y volver a abrir la aplicación del PDV.

Al usar este servicio, los encargados de las tiendas pueden crear fácilmente y publicar semanalmente el programa de trabajo de sus tiendas. Los trabajadores de tienda pueden ver rápidamente sus propios horarios y los de sus compañeros. De esa manera, pueden saber quién trabajará con ellos durante los turnos asignados. Igualmente, los trabajadores de tienda pueden crear solicitudes de ausencia y cambiar y proponer turnos. Todas estas solicitudes activan un flujo de trabajo definido.

Durante el turno, los trabajadores de la tienda pueden aprovechar la característica que les permite fichar a la entrada y salida del trabajo y que está integrada en los clientes de los PDV. Estos datos se envían a la sede central (HQ) para el procesamiento de la nómina. La característica que permite fichar a la entrada y la salida, es una capacidad existente de los PDV. Para obtener más información sobre la configuración y los escenarios admitidos, consulte [Horas de entrada y salida](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Escenarios admitidos
En esta sección se proporciona más información acerca de los escenarios compatibles.

- **Crear y publicar horarios**: el servicio WFM utiliza los permisos de los PDV que se configuran en la sede centrar para determinar si un trabajador tiene privilegios de administrador de tienda. Solo los encargados de la tienda pueden crear y publicar horarios mediante la operación de gestión de los mismos. Pueden crear rápidamente un horario copiando y pegando los turnos de trabajo de un empleado a otro. Asimismo, también pueden crear un horario si lo importan de semanas anteriores.

    Si no se publica un horario, querrá decir que está en estado de borrador y tendrá una apariencia diferente a un horario publicado. Los encargados de tienda pueden publicar un horario haciendo clic en el botón **Publicar** de cualquier semana. Después de publicar el horario de la semana, cualquier cambio se publicará automáticamente. Los ejemplos de los cambios incluyen el modo de agregar, eliminar o editar turnos o ausencias. Los trabajadores de la tienda solo pueden ver los horarios de las semanas que se hayan publicado.
    
- **Crear y aprobar solicitudes**: los trabajadores de la tienda pueden crear tres tipos de solicitud:

    - Solicitud de ausencia
    - Solicitud para cambiar turnos
    - Solicitud para proponer turnos

    Estas solicitudes se pueden realizar mediante la operación de solicitudes de horario. Cada solicitud sigue un flujo de trabajo definido y los trabajadores pueden ver fácilmente el estado actual de sus solicitudes.
    
    Las solicitudes de ausencia se envían automáticamente al encargado de tienda para su aprobación. Si hay varios encargados de tienda, todos ellos podrán ver una solicitud determinada, pero solo uno de ellos podrá aprobarla o rechazarla. Los tipos de ausencia se configuran en la sede de la tienda mediante la página **Tipos de bajas y ausencias** en el módulo **Tienda al por menor**. Una vez que el encargado de tienda apruebe o rechace la solicitud, esta se guarda en la ficha **Historial** de la operación de solicitudes de horario.
    
    En el caso de una solicitud para cambiar o proponer un turno, esta se envía primero al trabajador al cual afecta el cambio. El encargado de la tienda solo puede ver la solicitud una vez que el trabajador la haya aprobado. Por lo tanto, si el trabajador rechaza el cambio o la propuesta, el encargado no podrá verla. Asimismo, el trabajador que creó la solicitud puede cancelarla antes de que el encargado la apruebe o la rechace.

- **Mostar los trabajadores de tienda activos en la vista del horario**: al agregar a un trabajador a una tienda (por ejemplo, asociándolo a la libreta de direcciones del empleado de la tienda), el trabajador aparecerá como disponible en el horario del servicio WFM. Un trabajo por lotes periódico denominado **Procesar los datos del trabajador para la administración de recursos** se ejecuta en la sede central. Este trabajo prepara las asociaciones tienda/trabajador que se enviarán al servicio Common Data Service (CDS).

    Se utiliza el mismo proceso cuando un trabajador se quita de una tienda. Sin embargo, el trabajador que se quitó se mostrará en las semanas pasadas, la semana actual y las semanas futuras si tiene asignado un turno de trabajo o ausencia activa. Por lo tanto, a menos que se eliminen estos turnos de trabajo y ausencias, el trabajador que se quitó seguirá apareciendo durante esas semanas.

