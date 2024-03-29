---
title: Flujo de trabajo de proveedor
description: Modifique la información del proveedor y use el flujo de trabajo para aprobarla.
author: sunfzam
ms.date: 11/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: cfc255265df48e4a47aee4f13016356fb4775aa7
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799474"
---
# <a name="vendor-workflow"></a>Flujo de trabajo de proveedor

[!include [banner](../includes/banner.md)]

Cuando se usa el flujo de trabajo de proveedor, los cambios que se realizan a campos específicos se envían al flujo de trabajo para su aprobación antes de que se agreguen al proveedor.

## <a name="set-up-the-vendor-workflow"></a>Configurar el flujo de trabajo del proveedor

Para poder utilizar la funcionalidad de flujo de trabajo debe activarla.

1. Vaya a **Proveedores \> Configuración \> Parámetros de proveedores**.
2. En la pestaña **General**, en la ficha desplegable **Aprobación del proveedor**, establezca la opción **Habilitar aprobaciones de proveedor** en **Sí**.
3. En el campo **Comportamiento de entidad de datos**, seleccione el comportamiento que se debe usar cuando se importan datos:

    - **Permitir cambios sin aprobación** La entidad de datos puede actualizar el registro de proveedor sin procesarlo con el flujo de trabajo.
    - **Rechazar cambios** – Los cambios no se pueden introducir en el registro de proveedor. La importación fallará para los campos habilitados para el flujo de trabajo.
    - **Crear propuestas de cambio** – Todos los campos se cambiarán excepto los campos habilitados para el flujo de trabajo. Los nuevos valores para estos campos se agregarán al proveedor como cambios propuestos y el flujo de trabajo se iniciará automáticamente.

4. En la lista de campos de proveedor, seleccione la casilla de verificación **Habilitar** para cada campo que debe aprobarse antes de que los cambios se puedan realizar.
5. Vaya a **Proveedores \> Configuración \> Flujos de trabajo de proveedores**.
6. Seleccione **Nuevo**.
7. Seleccione **Flujo de trabajo de cambios de proveedor propuestos**. 
8. Configure el flujo de trabajo para que coincida con el proceso de aprobación. El elemento de aprobación del flujo de trabajo **Aprobación de flujo de trabajo para el cambio del proveedor propuesto** aplicará los cambios al proveedor.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>Cambie la información del proveedor y registre los cambios en el flujo de trabajo

Cuando se cambia un campo que está habilitado para el flujo de trabajo, la página **Cambios propuestos** aparece. Esta página muestra el valor original del campo y el nuevo valor que introdujo. El campo que ha cambiado se revierte a su valor original. Un mensaje de estado también le informará de que los cambios no se han enviado. 

Cada vez que se cambia un campo que está habilitado para el flujo de trabajo, dicho campo se agrega a la lista en la página **Cambios propuestos**. Para descartar el valor propuesto para un campo, use el botón **Descartar** junto al campo de la lista. Para descartar todos los cambios, use el botón **Descartar todos los cambios** en la parte inferior de la página. Seleccione **Aceptar** para cerrar la página.

Tras tener al menos un cambio propuesto, dos fichas adicionales aparecen en el panel de acciones: **Cambios propuestos** y **Flujo de trabajo**.

1. Seleccione **Cambios propuestos** para abrir la página **Cambios propuestos** y revisar los cambios.
2. Seleccione **Flujo de trabajo \> Enviar para enviar los cambios al flujo de trabajo**.

    El estado en la página se cambia a **Cambios pendientes de aprobación**.

El flujo de trabajo sigue el proceso de flujo de trabajo estándar. El aprobador es dirigido a la página **Proveedor**, donde se pueden revisar los cambios en la página **Cambios propuestos** y, a continuación, seleccionar **Flujo de trabajo \> Aprobar** para aprobar el flujo de trabajo. Una vez que se completan todas las aprobaciones, los campos se actualizan con los valores que propuso.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
