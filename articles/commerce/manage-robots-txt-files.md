---
title: Administrar archivos robots.txt
description: En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2e25a584121b700e566c29dbfe3fbbd72bf998cc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982550"
---
# <a name="manage-robotstxt-files"></a>Administrar archivos robots.txt


[!include [banner](includes/banner.md)]

En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El estándar de exclusión de robots, o robots.txt, es un estándar que los sitios web utilizan para comunicarse con los robots web. Da instrucciones a los robots web sobre las áreas de un sitio web que no se deben visitar. Los motores de búsqueda suelen utilizar robots para indexar sitios web.

Para excluir el acceso de los robots a un servidor se crea un archivo en el servidor. En este archivo se especifica una directiva de acceso para robots. El archivo debe ser accesible a través de HTTP en la URL local **/robots.txt**. El archivo robots.txt ayuda a los motores de búsqueda a indexar el contenido de su sitio.

Dynamics 365 Commerce le permite cargar un archivo robots.txt para su dominio. En cada dominio en su entorno de Commerce puede cargar un archivo robots.txt y asociárselo a ese dominio.

Para obtener más información sobre el archivo robots.txt, visite [Las páginas de robots web](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Cargar un archivo robots.txt

Después de haber creado y editado su archivo robots.txt de acuerdo con el [estándar de exclusión de robots](https://www.robotstxt.org/orig.html), asegúrese de que el archivo sea accesible en el equipo en el que va a utilizar las herramientas de creación de Commerce. El archivo debe llamarse **robots.txt**. Para obtener los mejores resultados debe tener en el formato que se indica en el estándar. Cada cliente de Commerce es responsable de validar y mantener el contenido de su archivo robots.txt. Para cargar un archivo robots.txt debe iniciar sesión en Commerce como administrador del sistema.

Para cargar un archivo robots.txt en Commerce, siga estos pasos.

1. Inicie sesión en Commerce como administrador del sistema.
2. En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.
3. En **Configuración del suscriptor**, seleccione **Robots.txt**. En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.
4. Seleccione **Administrar** para cargar un archivo robots.txt en un dominio de su entorno.
5. En el menú de la derecha, seleccione el botón **Cargar** (la flecha que apunta hacia arriba) situado junto al dominio asociado con el archivo robots.txt. Se abre un cuadro de diálogo de explorador de archivos.
6. En el cuadro de diálogo, busque y seleccione el archivo robots.txt que desea cargar para el dominio asociado y, a continuación, seleccione **Abrir** para completar la carga.

> [!NOTE] 
> Durante la carga, Commerce comprueba que el archivo sea un archivo de texto, pero no valida el contenido del archivo.

## <a name="download-a-robotstxt-file"></a>Descargar un archivo robots.txt

Para descargar un archivo robots.txt en Commerce, siga estos pasos.

1. Inicie sesión en Commerce como administrador del sistema.
2. En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.
3. En **Configuración del suscriptor**, seleccione **Robots.txt**. En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.
4. Seleccione **Administrar** para descargar un archivo robots.txt en un dominio de su entorno.
5. En el menú de la derecha, seleccione el botón **Descargar** (la flecha que apunta hacia abajo) situado junto al dominio asociado con el archivo robots.txt. Se abre un cuadro de diálogo de explorador de archivos.
6. En el cuadro de diálogo, vaya a la ubicación deseada en su unidad local, confirme o escriba un nombre de archivo y, a continuación, seleccione **Guardar** para completar la descarga.

> [!NOTE]
> Este procedimiento se puede utilizar para descargar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.

## <a name="delete-a-robotstxt-file"></a>Eliminar un archivo robots.txt

Para eliminar un archivo robots.txt en Commerce, siga estos pasos.

1. Inicie sesión en Commerce como administrador del sistema.
2. En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.
3. En **Configuración del suscriptor**, seleccione **Robots.txt**. En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.
4. Seleccione **Administrar** para eliminar un archivo robots.txt en un dominio de su entorno.
5. En el menú de la derecha, seleccione el botón **Eliminar** (el símbolo de la papelera) situado junto al dominio asociado con el archivo robots.txt. Aparece una ventana del Explorador de archivos.
6. En la ventana del explorador de archivos, busque y seleccione el archivo robots.txt que desea eliminar para el dominio y, a continuación, seleccione **Abrir**. Aparece un mensaje de advertencia.
7. En el cuadro de mensaje, seleccione **Eliminar** para confirmar la eliminación del archivo robots.txt.

> [!NOTE] 
> Este procedimiento se puede utilizar para eliminar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]