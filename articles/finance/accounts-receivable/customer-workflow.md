---
title: Flujo de trabajo de cliente
description: Este tema proporciona información sobre el flujo de trabajo de cliente. Cambia campos específicos para un cliente y, a continuación, envía esos cambios para su aprobación mediante el flujo de trabajo antes de que se añadan al cliente.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 8ff91a1df82d6195da266b97c347ef27afec662d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176085"
---
# <a name="customer-workflow"></a>Flujo de trabajo de cliente

[!include [banner](../includes/banner.md)]

El flujo de trabajo del cliente se ha agregado a la versión 8.0.4. Puede cambiar campos específicos para un cliente y, a continuación, envía esos cambios para su aprobación mediante el flujo de trabajo antes de que se añadan al cliente.

## <a name="set-up-the-customer-workflow"></a>Configurar el flujo de trabajo de cliente

Antes de poder usar la función de flujo de trabajo de cliente, debe habilitarla.

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
2. En la pestaña **General**, en la ficha desplegable **Aprobación del cliente**, establezca la opción **Habilitar aprobaciones de cliente** en **Sí** para habilitar la función.
3. En el campo **Comportamiento de entidad de datos**, seleccione el comportamiento que las entidades de datos deben usar cuando se importan los datos:

    - **Permitir cambios sin aprobación** – Una entidad puede actualizar el registro del cliente sin procesarlo mediante el flujo de trabajo.
    - **Rechazar cambios** – No se pueden hacer cambios en el registro del cliente. La importación no se realizará correctamente para los campos que están habilitados para el flujo de trabajo.
    - **Crear propuestas de cambio** – Se cambiarán todos los campos excepto los que están habilitados para el flujo de trabajo. Los nuevos valores para esos campos se añadirán al cliente como cambios propuestos, y el flujo de trabajo comenzará automáticamente.

4. En la lista de campos del cliente, seleccione la casilla **Habilitar** para cada campo que debe aprobarse antes de que se puedan hacer los cambios.
5. Vaya a **Clientes \> Configuración \> Flujos de trabajo de clientes**.
6. Seleccione **Nuevo**.
7. Seleccione **Flujo de trabajo de cambio de cliente propuesto**. 
8. Configurar el flujo de trabajo para que coincida con su proceso de aprobación. El elemento de aprobación del flujo de trabajo **Aprobación de flujo de trabajo para el cambio de cliente propuesto** aplicará los cambios al cliente.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Cambiar la información del cliente y enviar los cambios al flujo de trabajo

Cuando cambie un campo que está habilitado para el flujo de trabajo, aparece la página **Cambios propuestos**. Esta página muestra el valor original del campo y el nuevo valor que introdujo. El campo que cambió se revierte a su valor original. Un mensaje de estado en la página le informa de que sus cambios no se han enviado.

Cada vez que cambie un campo que está habilitado para el flujo de trabajo, ese campo se añade a la lista de cambios propuestos. Para descartar el valor propuesto para un campo, use el botón **Descartar** al lado del campo en la lista. Para descartar todos los cambios, use el botón **Descartar todos los cambios** en la parte inferior de la página. Seleccione **Aceptar** para cerrar la página.

Una vez que tenga al menos un cambio propuesto, aparecen dos menús adicionales en el panel de acción: **Cambios propuestos** y **Flujo de trabajo**.

1. Seleccione **Cambios propuestos** para abrir la página **Cambios propuestos** y revise sus cambios.
2. Seleccione **Flujo de trabajo \> Enviar** para enviar los cambios en el flujo de trabajo.

    El estado en la página se cambia a **Cambios pendientes de aprobación**.

El flujo de trabajo sigue el proceso de flujo de trabajo estándar en la aplicación. El aprobador es dirigido a la página **Cliente**, donde puede revisar los cambios en la página **Cambios propuestos** y, a continuación, seleccionar **Flujo de trabajo \> Aprobar** para aprobar el flujo de trabajo. Una vez que se completan todas las aprobaciones, los campos se actualizan con los valores que propuso.
