---
title: "Visión general de la ayuda"
description: "Este artículo proporciona una visión general de los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations. También se explica cómo puede proporcionar la formación y la documentación personalizadas a su organización."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 181ad9a7ab4e83ce9eb34312e93b1ebdeb2e04eb
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="help-overview"></a>Visión general de la ayuda

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general de los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations. También se explica cómo puede proporcionar la formación y la documentación personalizadas a su organización. 

Dynamics 365 for Operations incluye un sistema de Ayuda que se basa en dos componentes principales:

-   Un sitio de documentación
-   Guías de tareas

Puede obtener acceso a los artículos y a las guías de tareas del panel de Ayuda de Dynamics 365 for Operations como se muestra en la siguiente captura de pantalla.

![Panel Ayuda](./media/help-pane-ops-task-guides-1024x741.png)

Este artículo describe el sistema de ayuda y explica cómo puede crear documentación personalizada y recursos de formación para su organización.

## <a name="help-on-docsmicrosoftcom"></a>Ayuda en docs.microsoft.com
El sitio docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](/dynamics365/#pivot=solutions&panel=solutions_operations)) es el origen principal de la documentación del producto para Dynamics 365 for Operations. El sitio ofrece las características siguientes:

-   **Acceso al contenido más actualizado**: el sitio nos ofrece una manera más rápida y flexible de crear, entregar y actualizar documentación del producto. Por lo tanto, ayuda a garantizar que puede acceder a la información técnica más reciente.
-   **Contenido escrito por expertos**: el sitio proporciona un conjunto enriquecido de documentación de producto que se puede mejorar por los miembros de la comunidad tanto dentro como fuera de Microsoft.
-   **Acceso a diferentes tipos de contenido**: el sitio proporciona acceso rápido a diferentes tipos de contenido sobre Dynamics 365 for Operations, como presentaciones combinadas de Microsoft Office, guías de tareas, vídeos y temas.
-   **Contenido que admite sus procesos empresariales**: el sitio incluye contenido centrado en procesos empresariales que aprovecha el Modelador de procesos empresariales (BPM) de Microsoft Dynamics Lifecycle Services (LCS).

Hemos migrado todo el contenido de nuestra anterior wiki de ayuda a docs. Estamos entusiasmados con nuestro nuevo sitio y esperamos que usted también lo esté.

### <a name="searching-on-docsmicrosoftcom"></a>Cómo buscar en docs.microsoft.com
Recibimos muchas preguntas sobre cómo realizar búsquedas en nuestro contenido. En nuestro sitio, si empieza desde una página sobre Dynamics 365 for Operations, la búsqueda se limitará a contenido sobre Dynamics 365 for Operations. Para quitar esta restricción de ámbito, haga clic en la X situada junto a Operations en el cuadro de búsqueda. 
![Buscar pedidos](./media/search-scope.png)

También puede encontrar nuestro contenido con cualquier motor de búsqueda. Para obtener los mejores resultados, recomendamos utilizar una búsqueda en sitio con el parámetro site, como site: docs.microsoft.com “término buscado”  
![Búsqueda en sitio](./media/site-search.png)

![Resultados de la búsqueda en sitio](./media/site-search-results.png)


### <a name="how-can-i-contribute"></a>¿Cómo puedo contribuir? 

Déjenos aquí un comentario 

1 Haga click en **Comentarios** para ir a los comentarios en la parte inferior de la página.

![Comentarios](./media/comments.png)

2 Empiece a escribir sus comentarios y, continuación, haga clic en **Publicar comentario**.

![Publicar comentario](./media/before-signin.png)

3 Seleccione el tipo de cuenta con el que desea iniciar sesión:  
Haga clic en uno de los iconos de la izquierda para asociar este sitio con una cuenta existente, como una cuenta de Twitter, Facebook o Microsoft. 

O 

A la derecha, escriba una dirección de correo electrónico y una nueva contraseña para crear una cuenta nueva para el sitio. 

![Opciones de inicio de sesión](./media/signin-options.png)


## <a name="task-guides"></a>Guías de tareas
Una guía de tareas es una experiencia guiada, interactiva y controlada que le lleva por los pasos de una tarea o de un proceso empresarial. Puede abrir (reproducir) una guía de tareas desde el panel Ayuda. Al hacer clic por primera vez en una guía de tareas, el panel Ayuda mostrará instrucciones detalladas para la tarea. Ahora dispone de guías de tareas localizadas. 

![Vista de lectura de la guía de tareas](./media/task-guide-ops-1024x742.png)

Para comenzar la experiencia interactiva y guiada, haga clic en **Iniciar guía de tareas** en la parte inferior del panel Ayuda. Se abre un puntero negro e indica la acción que debe realizar. Siga las indicaciones que aparecen en la IU y especifique los datos como se indica. 
![Instrucción de pasos de la guía de tareas](./media/task-guide-step-1-ops.png)

> [!IMPORTANT] 
> Los datos que especifica al reproducir una guía de tareas son reales. Si está en un entorno de producción, los datos se especificarán en la empresa que está usando actualmente.

### <a name="it-all-begins-with-task-recorder"></a>Todo comienza el Grabador de tareas

Las guías de tareas se crean mediante el Grabador de tareas. Al usar el Grabador de tareas, se graban todas las acciones que realiza en la interfaz de usuario de Dynamics 365 for Operations (como hacer clic en menús, cambiar la configuración y especificar cambios). Los pasos que grabe se denominan conjuntamente grabación de tareas. Como explicamos en la sección anterior, las grabaciones de tareas se pueden mostrar en el panel Ayuda y reproducir como guías de tareas. Sin embargo, hay otras maneras en que puede usar grabaciones de tareas:

-   **Guardar grabaciones de tareas en BPM**: puede guardar una grabación de tareas en una línea de una jerarquía en una biblioteca de BPM en LCS. Al guardar una grabación de tareas en BPM, se genera y se guarda un diagrama de flujo, junto con los pasos de la grabación. **Nota:** Para mostrar una grabación de tareas en el panel de Ayuda de Dynamics 365 for Operations y reproducirla como guía de tareas, deberá guardar la grabación en una biblioteca de BPM.
-   **Guardar grabaciones de tareas como documentos de Word**: al guardar una grabación de tareas como documento de Microsoft Word, puede producir con facilidad guías de formación imprimibles para su organización.

Para obtener más información sobre el Grabador de tareas, consulte [Grabador de tareas de Dynamics 365 for Operations](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Creación de grabaciones de tareas personalizadas

Puede crear sus propias grabaciones de tareas o descargar y personalizar grabaciones de tareas que proporcione Microsoft. Por lo tanto, puede crear una Ayuda personalizada para su organización que refleje su implementación específica de Dynamics 365 for Operations. Para mostrar una grabación de tareas en el panel de Ayuda de Dynamics 365 for Operations y reproducirla como guía de tareas, deberá guardar la grabación en una biblioteca de BPM en LCS. Si es socio, y promociona una biblioteca para ser biblioteca corporativa e incluirla en una solución, esta quedará a disposición de sus clientes. Para obtener instrucciones completas, consulte [Uso de grabaciones de tareas para crear documentación o formación](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Ayuda en el producto
Para obtener acceso al contenido de la Ayuda dentro de Dynamics 365 for Operations, haga clic en el icono **Ayuda** (**?**) y después elija Ayuda, o presione Ctrl+Mayús+?. En ambos casos, se abre el panel Ayuda. En el panel Ayuda, puede obtener acceso a los artículos del sitio o las guías de tareas. 

![Panel Ayuda](./media/help-pane-wiki-1024x684.png)

### <a name="accessing-articles-from-the-help-pane"></a>Acceso a artículos del sitio desde el panel Ayuda

En el panel Ayuda, puede obtener acceso a artículos del sitio que se aplican al cliente de Dynamics 365 for Operations. Al abrir el panel de la Ayuda por primera vez y hacer clic en la pestaña **Wiki**, verá los artículos que se aplican a la página en la que se encuentra actualmente en Dynamics 365 for Operations. Si no encuentra ningún artículo, puede escribir palabras clave para limitar la búsqueda. Al hacer clic en un artículo del panel Ayuda, se abre una nueva pestaña en el explorador y se muestra el artículo. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Acceso a guías de tareas desde el panel Ayuda

Para acceder a las guías de tareas desde el panel de Ayuda, un administrador del sistema tiene que ir a la página **Parámetros del sistema** en Dynamics 365 for Operations y configurar algunos parámetros. 

> [!NOTE]
> -   Para configurar la ayuda, debe iniciar sesión con una cuenta en el mismo poseedor que el poseedor en que se implementa Dynamics 365 for Operations.
> -   No es posible conectarse a una biblioteca de LCS desde una instancia de Dynamics 365 for Operations que se ejecuta en un disco duro virtual (VHD) local.

![Formulario Parámetros del sistema con configuración de Ayuda](./media/system-parameters_ops-1024x437.png)

En la página **Parámetros del sistema**, siga estos pasos:

1.  **Importante:**La primera vez que abra la ficha de la Ayuda, debe conectar con Lifecycle Services. Asegúrese de hacer clic en el vínculo que hay en el medio del formulario, espere por la conexión, cierre el cuadro de diálogo y haga clic en Aceptar para obtener los parámetros del formulario.
![Conectarse a LCS](./media/connect-to-lcs-crop-1024x365.png)
2.  Seleccione el proyecto de Lifecycle Services al que conectarse.
3.  Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.
4.  Establezca el orden de visualización de las bibliotecas de BPM. Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel Ayuda.

Una vez que un administrador del sistema complete estos pasos, puede abrir el panel Ayuda y hacer clic en la pestaña **Guías de tareas**. Ahora verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en Dynamics 365 for Operations. Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda. Tras hacer clic en una guía de tareas en el panel Ayuda, el panel Ayuda muestra las instrucciones detalladas y puede reproducir la guía de tareas. 
![Vista de lectura de la guía de tareas](./media/task-guide-ops-1024x742.png)

### <a name="where-are-the-translated-task-guides"></a>¿Dónde están las guías de tareas traducidas?

Las guías de tareas traducidas se publican en bibliotecas que llevan "Todos los idiomas" en el título. En Dynamics 365 for Operations, para ver la ayuda de la guía de tareas localizada, asegúrese de que está conectado a la biblioteca adecuada. El idioma en el que aparece una guía de tareas se controla para cada usuario mediante la configuración de idioma en **Opciones** &gt; **Preferencias**. 
-   Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.
-   Si aún no se ha traducido una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="additional-resources"></a>Recursos adicionales
En la tabla siguiente se muestran los sitios web que proporcionan el contenido de Dynamics 365 for Operations. Nuestros sitios web de contenido están organizados para admitir el ciclo de vida del cliente. Cada fase se admite con otro conjunto de sitios. Los sitios que tienen un asterisco (\*) junto al nombre requieren que inicie sesión con una cuenta asociada a un plan de servicio.

| Sitio                                                                     | Descripción                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](/dynamics365/#pivot=solutions&panel=solutions_operations) | Hospeda o vincula toda la documentación del producto para Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Proporciona un espacio de trabajo de colaboración basado en la nube que los clientes y los socios pueden utilizar para gestionar los proyectos de Dynamics 365 for Operations, desde preventas hasta implementación y operaciones. Este sitio es útil en todas las fases de una implementación. |
| [CustomerSource](http://www.customersource.com/)\*                       | Hospeda amplios recursos de formación y es el sitio de soporte principal de Dynamics 365 for Operations. Puede que sea necesario iniciar sesión para obtener acceso a recursos específicos en el sitio.                                                                      |
| [Blog de soporte](http://aka.ms/AXSupportBlog)                              | Proporciona sugerencias y trucos que publica el Equipo de soporte de Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Hospeda contenido de versiones anteriores que se escriben para desarrolladores.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Hospeda contenido de versiones anteriores que se escriben para los profesionales de TI y los usuarios de aplicación.                                                                                                                                           |
| [Comunidad de Dynamics](http://community.dynamics.com/)                  | Hospeda blogs, foros y vídeos.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Ofrece información de evaluación y ventas.                                                                                                                                                                                                 |



<a name="see-also"></a>Consulte también
--------

[Sistema de ayuda de Dynamics 365 for Operations (hoja informativa descargable)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Grabador de tareas de Microsoft Dynamics 365 for Operations](../user-interface/task-recorder.md)

[Crear documentación o formación con las grabaciones de tareas](../user-interface/task-recorder.md)

[Guías de tareas nuevas o actualizadas (noviembre de 2016)](new-task-guides-november-2016.md)
[Guías de tareas nuevas o actualizadas (agosto de 2016)](new-updated-task-guides-available-august-2016.md)
[Guías de tareas nuevas o actualizadas (mayo de 2016)](new-updated-task-guides-available-may-2016.md)
[Nuevas guías de tareas (febrero de 2016)](new-task-guides-available-february-2016.md)








