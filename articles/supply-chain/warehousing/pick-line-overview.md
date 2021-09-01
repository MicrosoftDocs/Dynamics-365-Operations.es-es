---
title: Configurar un elemento de menú de dispositivo móvil para proporcionar una descripción general de la línea de selección
description: Este tema explica cómo definir cuándo se mostrará una lista de todas las líneas de trabajo a los trabajadores del almacén que están procesando el trabajo del almacén en un dispositivo móvil. Esta capacidad puede ser útil para los trabajadores del almacén que a menudo requieren una descripción general de las líneas de selección en una orden de trabajo para poder optimizar su secuencia de selección.
author: MarkusFogelberg
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: bec9c779399b252277c7688d4bdaf9794c050c18925eebaec0a8c0ffe2b3df28
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763900"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Configurar un elemento de menú de dispositivo móvil para proporcionar una descripción general de la línea de selección

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar las opciones relacionadas con la descripción general de la línea de selección para los elementos del menú del dispositivo móvil que se utilizan para procesar el trabajo de preparación. La descripción general de la línea de selección permite a los trabajadores del almacén ver y seleccionar de una lista todas las líneas de trabajo relacionadas con su tarea actual. Esta capacidad puede ayudar a los trabajadores a optimizar su secuencia de selección. La característica proporciona opciones que reemplazan el botón **Omitir** estándar que permite a los trabajadores recorrer las líneas de una en una, en un orden fijo. (Sin embargo, la opción de usar ese botón sigue estando disponible).

Los administradores pueden configurar cada elemento de menú individualmente para controlar cómo, cuándo y dónde la aplicación móvil Warehouse Management presenta la descripción general de la línea de selección.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>Activar la característica de detalles de la línea de selección de trabajo

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** _Gestión de almacén_
- **Nombre de la característica**: _detalles de la línea de selección de trabajo_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Configurar elementos del menú para mostrar una lista de todas las líneas de trabajo

Para configurar un elemento de menú de dispositivo móvil a fin de proporcionar una descripción general de la línea de selección, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Seleccione o cree un elemento de menú que esté relacionado con el trabajo de selección y establezca los siguientes valores:

    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*
    - **Dirigido por:** *Dirigido por el usuario* o *Dirigido por el sistema*

    Para obtener más información sobre cómo crear elementos de menú y utilizar las distintas opciones de configuración que están disponibles en la página **Elementos del menú del dispositivo móvil**, vea [Configurar dispositivos móviles para el trabajo de almacén](configure-mobile-devices-warehouse.md).

1. En la ficha desplegable **General**, configure la característica estableciendo el campo **Mostrar lista de líneas de trabajo** en uno de los siguientes valores:

    - **Mostrar solo a petición**: los trabajadores pueden elegir ver la lista de líneas de selección mediante el botón **Saltar a** en la aplicación móvil Warehouse Management.
    - **Mostrar al comienzo de cada selección**: los trabajadores ven la lista cada vez que comienzan o finalizan una línea de selección. También pueden volver a ver la lista mediante el botón **Saltar a** en la aplicación móvil Warehouse Management.
    - **Mostrar solo al comienzo de la primera selección**: los trabajadores ven la lista cada vez que comienzan un nuevo trabajo de selección, pero no después de cada línea. También pueden volver a ver la lista mediante el botón **Saltar a** en la aplicación móvil Warehouse Management.
    - **No mostrar nunca**: el botón **Omitir** estándar aparece en la aplicación móvil Warehouse Management y se desactiva la visualización de la lista de líneas de trabajo. El botón **Omitir** permite a los trabajadores recorrer las líneas una por una, en un orden fijo. También pueden recorrer la lista tantas veces como lo necesiten, hasta que se hayan procesado todas las líneas.

1. En el panel Acciones, seleccione **Guardar**.

    Si configura el campo **Mostrar lista de líneas de trabajo** a cualquier valor excepto *No mostrar nunca*, el botón **Lista de campos** del panel de acciones pasa a estar disponible.

1. En el panel de acciones, seleccione **Lista de campos**.
1. En la página **Lista de campos**, configure la información que muestra la aplicación móvil Warehouse Management para cada línea de la lista.

    - El campo **Control principal** del campo siempre se establece en *LineNum*. Por lo tanto, cada fila de la lista comienza con un número de línea.
    - Use los demás campos del **Campo de visualización** para agregar hasta siete campos de visualización adicionales, según sea necesario. En cada campo de **Campo de visualización**, seleccione el nombre de un campo de línea de trabajo. Cada línea mostrará un valor para ese campo. Los valores se mostrarán en el orden que seleccione aquí. Puede dejar en blanco algunos de los campos de **Campo de visualización** si no necesita los siete valores.

1. En el la panel de acciones, seleccione **Guardar** y después cierre la página **Lista de campos**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]