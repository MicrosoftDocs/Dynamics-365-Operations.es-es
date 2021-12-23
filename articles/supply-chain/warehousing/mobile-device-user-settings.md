---
title: Configuración de usuario del dispositivo móvil
description: Este tema explica cómo administrar la configuración de usuario de dispositivos móviles para los trabajadores del almacén.
author: Mirzaab
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 13c99854224a6d220e73a43636d85ec1951f8149
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901905"
---
# <a name="mobile-device-user-settings"></a>Configuración de usuario del dispositivo móvil

[!include [banner](../../includes/banner.md)]

La nueva aplicación móvil Warehouse Management tiene un conjunto de configuraciones específicas de la aplicación que ayudan a personalizar la experiencia del usuario. Debido a que la aplicación se puede usar en dispositivos con diferentes tamaños de pantalla y configuraciones (como una tableta, un teléfono o un brazo), puede ser útil administrar de forma centralizada estas configuraciones desde Microsoft Dynamics 365 Supply Chain Management.

La función *Configuración de usuario del dispositivo móvil* le permite definir la configuración de usuario global que se utilizará en todos los dispositivos. También puede definir configuraciones de usuario más granulares para marcas de dispositivos individuales, modelos de dispositivos y / o trabajadores. Cuando un trabajador inicia sesión en la aplicación móvil Warehouse Management, la aplicación busca y aplica el perfil de configuración más específico que está almacenado en Supply Chain Management para la marca, el dispositivo y / o el ID de usuario coincidentes.

Esta función puede ayudar a los trabajadores a comenzar más rápidamente cada vez que comiencen a usar un dispositivo nuevo. A continuación, encontrará algunos ejemplos:

- Los administradores pueden establecer un conjunto estándar de preferencias que funcionan mejor para dispositivos de un fabricante específico y / o para modelos de dispositivos específicos. Por lo tanto, los trabajadores pueden comenzar con un nuevo dispositivo sin tener que cambiar necesariamente la configuración.
- Si su empresa tiene un grupo de dispositivos idénticos que se comparten entre los trabajadores, los trabajadores verán su configuración preferida cada vez que inicien sesión, incluso si nunca han utilizado el dispositivo físico específico que seleccionaron en un día determinado.
- En Supply Chain Management, los administradores pueden ver y editar todas las configuraciones almacenadas, incluso para trabajadores individuales. Esta capacidad puede ayudarlos a solucionar problemas o ajustar nuevas funciones.

> [!IMPORTANT]
> La función *configuración de usuario del dispositivo móvil* se aplica solo a la nueva aplicación móvil Warehouse Management. No funciona con la antigua aplicación de almacén.

## <a name="turn-on-the-mobile-device-user-settings-feature"></a>Active la función de configuración de usuario del dispositivo móvil

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Configuración de usuario, iconos y títulos de pasos para la nueva aplicación de almacén*

## <a name="create-and-manage-user-settings"></a>Crear y administrar configuraciones de usuario

Use la página **Configuración de usuario del dispositivo móvil** para crear, ver y administrar perfiles de configuración en todos los niveles de granularidad. La primera vez que un trabajador edita su configuración de usuario en un nuevo dispositivo, se agrega automáticamente un nuevo perfil en esta página, si aún no existe. Luego, ese perfil se actualiza cada vez que el trabajador realiza un cambio.

También puede definir un perfil de configuración que se aplique a todas las marcas de dispositivos, modelos de dispositivos y / o trabajadores. Luego, puede aumentar la granularidad aplicando configuraciones más específicas para marcas, modelos y / o trabajadores individuales.

Siga estos pasos para crear y administrar la configuración de usuario para sus dispositivos móviles.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. Seleccione un perfil de configuración de usuario existente en el panel de lista para abrir su registro. Alternativamente, seleccione **Nuevo** en el Panel de acciones para crear un nuevo perfil.

    Cada perfil en el panel de lista está etiquetado para indicar la marca, modelo y / o ID de usuario al que se aplica el perfil. Los perfiles más generales tienen un valor de *Todos* para algunas o todas estas características.

1. En la sección de encabezado del registro para el perfil de configuración nuevo o seleccionado, configure los siguientes campos:

    - **Nombre de la marca del dispositivo** - Seleccione el nombre de la marca del dispositivo al que se debe aplicar el perfil. Si el perfil debe aplicarse a todas las marcas, deje este campo en blanco. La lista de valores incluye todas las marcas que se han definido en su sistema. Para obtener información sobre cómo definir la lista de marcas, consulte la siguiente sección.
    - **Id. de modelo de dispositivo** - Seleccione el modelo del dispositivo al que se debe aplicar el perfil. Si el perfil debe aplicarse a todos lo smodelos de la marca seleccionada, deje este campo en blanco. La lista de valores incluye todos los modelos que se han definido para la marca que se selecciona en el campo **Nombre de la marca del dispositivo**. Para obtener información sobre cómo definir la lista de modelos para cada marca, consulte la siguiente sección.
    - **ID de usuario** - Seleccione el ID de usuario del trabajador del almacén al que se debe aplicar el perfil de configuración. Si el perfil debe aplicarse a todos los trabajadores, deje este campo en blanco.

1. En la ficha rápida **General**, establezca los siguientes campos:

    - **Posición del botón** - Seleccione cómo se deben colocar los botones en el dispositivo. Los elementos de la aplicación se moverán para adaptarse mejor a la preferencia o disposición del trabajador. Las opciones disponibles son *Abajo a la derecha (predeterminado)*, *Abajo a la izquierda*, *Parte superior derecha*, y *Arriba a la izquierda*.
    - **Orientación de la pantalla** - Seleccione la orientación de la pantalla que se debe aplicar de forma predeterminada en la aplicación.
    - **Escanear con cámara** - Establezca esta opción en *Sí* para usar la cámara del dispositivo para escanear campos de entrada donde el modo de entrada preferido está configurado en *Exploración*. Si su dispositivo tiene un escáner incorporado, configure esta opción en *No* para usar el escáner en su lugar.
    - **Mostrar foto del producto** - Seleccione si se deben mostrar las fotos del producto si están disponibles para el producto lanzado. Para obtener más información sobre cómo agregar imágenes de productos, consulte [Agregar una imagen a un producto](../pim/tasks/add-image-product.md).
    - **Mostrar tema de color** - Seleccione un tema de color para el dispositivo.
    - **Nivel de sonido** - Seleccione el nivel de sonido del dispositivo. Seleccione un valor entre 0 (cero) y 10. Un valor de *0* representa ningún sonido, y un valor de *10* representa el volumen máximo. El valor predeterminado es *4*.
    - **Nivel de vibración** - Seleccione el nivel de vibración del dispositivo. Seleccione un valor entre 0 (cero) y 5. Un valor de *0* representa ninguna vibración, y un valor de *5* representa la vibración máxima. El valor predeterminado es *1*.
    - **Porcentaje de escala de texto** - Especifique el tamaño del texto como porcentaje del tamaño estándar. Especifique un valor entre 70 y 400. Un valor de *70* representa la escala de texto más pequeña y un valor de *400* representa la escala de texto más grande. El valor predeterminado es *100*.
    - **Porcentaje de escala de botón** - Especifique el tamaño del botón como porcentaje del tamaño estándar. Especifique un valor entre 50 y 200. Un valor de *50* representa la escala de botón más pequeña y un valor de *200* representa la escala de botón más grande. El valor predeterminado es *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Cree y administre marcas de dispositivos móviles

Utilice la página **Marcas de dispositivos móviles** para ver, crear y administrar las marcas y modelos de dispositivos que se pueden usar con sus perfiles de configuración. La aplicación móvil obtiene y envía automáticamente el nombre de la marca local y la identificación del modelo la primera vez que un trabajador edita su configuración en un dispositivo determinado. Por lo tanto, la mayoría de estos registros generalmente se generarán automáticamente. Sin embargo, también puede administrar todos los registros en esta página. Por ejemplo, puede proporcionar descripciones más útiles a cada marca y modelo para ayudar a distinguir ID de modelos similares o crípticos.

Siga estos pasos para crear y administrar las marcas y modelos de los dispositivos móviles.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Marcas del dispositivo móvil**.
1. En el panel de lista, seleccione una marca de dispositivo móvil para abrir su registro. Alternativamente, seleccione **Nuevo** en el Panel de acciones para crear una nueva marca.
1. En la sección de encabezado del registro para la marca de dispositivo nueva o seleccionada, configure los siguientes campos:

    - **Nombre de la marca del dispositivo** - La marca del dispositivo, como *Microsoft Corporation*.
    - **Descripción** - Puede ingresar una descripción para ayudar a distinguir las marcas.

1. La ficha desplegable **Modelos de dispositivos móviles** muestra todos los modelos para la marca de dispositivo seleccionada. Use los botones de la barra de herramientas para agregar filas a la cuadrícula o eliminar filas. Para cada fila, puede configurar los siguientes campos:

    - **ID de modelo de dispositivo** - El ID del modelo del dispositivo, como *Surface Book 2*.
    - **Descripción** - Puede ingresar una descripción para ayudar a distinguir los id. de los modelos.

## <a name="additional-resources"></a>Recursos adicionales

- [Instalar y conectar la aplicación móvil Gestión de almacenes](install-configure-warehouse-management-app.md)
- [Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management](step-icons-titles.md)