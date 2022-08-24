---
title: Copiar un sitio de comercio electrónico
description: Este artículo describe cómo copiar un sitio de comercio electrónico existente dentro o entre entornos de comercio electrónico en el creador de sitios de Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 9b74e0d48be29272b893c855c229e4003f0c161e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276302"
---
# <a name="copy-an-e-commerce-site"></a>Copiar un sitio de comercio electrónico

[!include [banner](../includes/banner.md)]

Este artículo describe cómo copiar un sitio de comercio electrónico existente dentro o entre entornos de comercio electrónico en el creador de sitios de Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce admite la copia o clonación de sitios como una operación de autoservicio en el creador de sitios de Commerce. Los sitios se pueden copiar dentro de un solo entorno de comercio electrónico o entre dos entornos de comercio electrónico. El usuario que inicia la operación de copia del sitio debe ser un administrador de inquilinos en los entornos de comercio electrónico tanto de origen como de destino.

La operación de copia del sitio copia todo el contenido de comercio electrónico del sitio de origen. Este contenido incluye páginas, fragmentos, plantillas, direcciones URL y recursos. Para que se pueda usar un sitio nuevo, se debe inicializar a través del proceso de experiencia de primera ejecución (FRE). Los canales se pueden asignar y administrar en el creador de sitios, en **Configuración del sitio \> Canales**.

La duración de la operación de copia del sitio depende principalmente de la cantidad de activos en el sitio de origen. Para sitios excepcionalmente grandes, le recomendamos que se plantee usar la operación de copia del entorno en su lugar. (Esta operación también se conoce como operación de portabilidad de datos).

> [!NOTE]
> - El sitio de origen será de solo lectura durante la operación de copia del sitio.
> - Solo se copian las versiones publicadas de los documentos. Si no se han publicado versiones, solo se copian las últimas.
> - El historial de versiones del contenido no estará disponible en el sitio de destino.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Copiar un sitio dentro de un entorno de comercio electrónico

Para copiar un sitio dentro de un entorno de comercio electrónico, siga estos pasos.

1. Inicie sesión en el creador de sitios para el entorno en el que desea realizar la operación de copia.
1. Para abrir la vista de lista de sitios, seleccione **Conmutador de sitios** en la esquina superior derecha y luego seleccione **Administrar sitios**.
1. Encuentre el sitio que desea copiar o clonar, y selecciónelo activando la casilla junto al nombre del sitio.
1. En la barra de comandos, seleccione **Copiar sitio**.
1. En el menú flotante **Copiar sitio**, en el campo **Nuevo nombre de sitio** introduzca un nombre para el nuevo sitio. El nuevo nombre del sitio debe ser único en el entorno de comercio electrónico. Los campos **Inquilino de origen** y **Sitio de origen** se configuran automáticamente con la información del inquilino actual y del sitio seleccionado.
1. Seleccione **Crear copia**.

Una vez validada la información, una notificación indica que se ha creado un nuevo trabajo de copia del sitio. Puede controlar el progreso del trabajo en el [panel derecho de la página **Trabajos de inquilino**](#monitor-the-site-copy-operation). Cuando la operación de copia se ha completado correctamente, el nuevo sitio aparece en la lista de sitios de la vista de lista de sitios.

La siguiente ilustración muestra un ejemplo del menú flotante **Copiar sitio** en el generador de sitios.

![Menú flotante Copiar sitio en el creador de sitios.](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Copiar un sitio entre dos entornos de comercio electrónico

Para copiar un sitio entre dos entornos de comercio electrónico, siga estos pasos.

1. Inicie sesión en el generador de sitios para el entorno de comercio electrónico.
1. En la barra de comandos, seleccione **Copiar sitio**.
1. En el menú flotante **Copiar sitio**, en el campo **Nuevo nombre de sitio** introduzca un nombre para el nuevo sitio. El nuevo nombre del sitio debe ser único en el entorno de comercio electrónico.
1. En e campo **Inquilino de origen**, seleccione el nombre del inquilino de origen.
1. En el campo **Sitio de origen**, seleccione el sitio de origen.
1. Seleccione **Crear copia**.

> [!NOTE]
> Se requieren permisos de administrador de inquilinos para los entornos de comercio electrónico tanto de origen como de destino.

Una vez validada la información, una notificación indica que se ha creado un nuevo trabajo de copia del sitio. Puede controlar el progreso del trabajo en el [panel derecho de la página **Trabajos de inquilino**](#monitor-the-site-copy-operation). Cuando la operación de copia se ha completado correctamente, el nuevo sitio aparece en la lista de sitios de la vista de lista de sitios.

## <a name="map-channels-during-the-site-copy-operation-optional"></a>Asignar canales durante la operación de copia del sitio (opcional)

Los canales y las configuraciones regionales de origen se pueden asignar a canales y configuraciones regionales de destino como parte de la operación de copia del sitio. Si la asignación de canales se realiza como parte de la operación de copia del sitio, no es necesario inicializar el sitio mediante el proceso FRE ni configurar los canales en la configuración del sitio. 

Para asignar todos los canales y configuraciones regionales "tal cual" (1 a 1) en el generador de sitios, siga estos pasos.

1. Para abrir la vista de lista de sitios, seleccione **Conmutador de sitios** en la esquina superior derecha y luego seleccione **Administrar sitios**.
1. Encuentre el sitio que desea copiar o clonar, y selecciónelo activando la casilla junto al nombre del sitio.
1. En la barra de comandos, seleccione **Copiar sitio**.
1. En el menú flotante **Copiar sitio**, introduzca valores para **Nuevo nombre del sitio**, **Suscriptor de origen** y **Sitio de origen** (si no están presentes ya).
1. Seleccione **Agregar asignación de canales**.
1. En el menú flotante **Configurar canales y configuraciones regionales del sitio**, seleccione **Canal de origen** y luego seleccione el canal de origen.  
1. Seleccione **Canal de destino** y luego seleccione el mismo canal que el canal de origen. 
1. Seleccione **Agregar configuración regional**.
1. Seleccione **Configuración regional del origen** y, a continuación, seleccione la configuración regional de origen.
1. Seleccione **Configuración regional del destino** y luego seleccione la misma configuración regional que la configuración regional de origen. 
1. En **Ruta de URL**, ingrese una ruta URL única que no se use actualmente en el entorno de destino.
1. Repita los pasos del 8 al 11 para cada configuración regional que desee asignar al canal.
1. Seleccionar **Aplicar**.
1. Repita los pasos 6 a 11 para cada canal de origen.
1. Seleccione **Cerrar**.
1. Revise la configuración para verificar su precisión y luego seleccione **Copiar sitio**.

> [!NOTE]
> Todos los canales y las configuraciones regionales de origen deben asignarse y solo pueden asignarse una vez.

## <a name="monitor-the-site-copy-operation"></a>Supervisar la operación de copia del sitio

Para supervisar el progreso de la operación de copia del sitio, siga estos pasos.

1. Inicie sesión en el generador de sitios para el entorno de comercio electrónico.
1. En el panel de izquierdo, seleccione **Trabajos de inquilino**.
1. En la página **Trabajos de inquilino**, busque y seleccione el trabajo de copia del sitio en la lista. Aparece un panel a la derecha que muestra el estado y los detalles del trabajo seleccionado.

Puede cancelar un trabajo que tenga un estado de **En curso**. Seleccione el trabajo en la lista y luego seleccione **Cancelar** en la barra de comandos.

Puede volver a intentar un trabajo que tenga un estado de **Con error** o **Completado con errores**. Seleccione el trabajo en la lista y luego seleccione **Reintentar** en la barra de comandos.

> [!NOTE]
> El procesamiento de recursos de vídeo puede continuar después de que se complete un trabajo de copia del sitio.

La siguiente ilustración muestra un ejemplo del panel correcto de la página **Trabajos de inquilino** en el creador de sitios.

![Detalles del trabajo en el panel derecho de la página Trabajos de inquilino en el creador de sitios.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Inicializar un nuevo sitio usando el proceso FRE

Para que se pueda usar el sitio nuevo, se debe inicializar a través del proceso de FRE.

Para inicializar un sitio nuevo mediante el proceso FRE, siga estos pasos.

1. Inicie sesión en el creador de sitios para el nuevo sitio.
1. Para abrir la vista de lista de sitios, seleccione **Conmutador de sitios** en la esquina superior derecha y luego seleccione **Administrar sitios**.
1. Busque y seleccione el nuevo sitios que desea inicializar.
1. En el cuadro de diálogo **Configurar su sitio**, en el campo **Seleccionar un dominio**, seleccione un dominio. Todos los dominios que se asociaron con el entorno de comercio electrónico durante la inicialización están disponibles para su selección.
1. En el campo **Seleccionar un canal predeterminado**, seleccione el canal de tienda en línea asociado. El canal seleccionado proporcionará surtidos y otra información que se almacena en la sede central de Commerce.
1. En el campo **Seleccionar un idioma predeterminado**, seleccione el idioma de creación predeterminado. Todos los idiomas que se configuraron para el canal de tienda en línea seleccionado están disponibles para su selección.
1. En el campo **Ruta**, el valor consta del dominio base y una ruta de URL opcional que puede introducir. Puede dejar la ruta de la URL en blanco si el canal se servirá desde la raíz de dominio o si desea introducir esta información más tarde en la vista de configuración del canal en el creador de sitios. La ruta del sitio debe ser único en el entorno de comercio electrónico.
1. Seleccione **Aceptar**. El sitio se inicializa con la información que proporcionó y se le vuelve a enviar a la vista de administración del sitio.

En la siguiente ilustración se muestra un ejemplo en el cuadro de diálogo **Configurar su sitio** en el creador de sitios.

![Cuadro de diálogo Configurar su sitio en el creador de sitios.](media/site-copy_3.png)

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-b2c-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)
