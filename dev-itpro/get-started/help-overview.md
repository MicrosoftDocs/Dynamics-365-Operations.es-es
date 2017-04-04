---
title: "Visión general de la ayuda"
description: "Este artículo proporciona una visión general de los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations. También se explica cómo puede proporcionar la formación y la documentación personalizadas a su organización."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 240060606c8a2955c3f0a0d47fb25b0cde64c187
ms.lasthandoff: 03/31/2017


---

# <a name="help-overview"></a>Visión general de la ayuda

Este artículo proporciona una visión general de los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations. También se explica cómo puede proporcionar la formación y la documentación personalizadas a su organización. 

Dynamics 365 for Operations incluye un sistema de Ayuda que se basa en dos componentes principales:

-   Un sitio de la documentación
-   Guías de tareas

Puede obtener acceso a ambos artículos y listas a las guías del panel de ayuda en Dynamics 365 para las operaciones como se muestra en la captura de pantalla siguiente. [panel de la Ayuda de![] (. /media/help-pane-ops-task-guides-1024x741.png])(. Este artículo de /media/help-pane-ops-task-guides.png) describe el sistema de ayuda, y explica cómo puede crear documentación personalizada y recursos de formación de su organización.

## <a name="help-on-docsmicrosoftcom"></a>Ayuda en docs.microsoft.com
El sitio de docs.microsoft.com (docs.microsoft.com/dynamics365/operations [] (https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) es el origen principal de la documentación de Dynamics 365 para las operaciones. El sitio proporciona características siguientes:

-   ** El acceso al contenido más actualizado – ** el sitio nos da un modo más rápida y mayor flexibilidad de crear, para entregar, y actualizar la documentación del producto. Por lo tanto, ayuda a garantizar que puede acceder a la información técnica más reciente.
-    ** Panel que es escrito por expertos – ** el sitio ofrece un conjunto más rico de documentación de producto que se pueda ampliado por miembros de (antiguamente tanto en el interior como en el exterior Microsoft.
-   ** El acceso a los diferentes tipos de contenido – ** el sitio le permite rápidamente tener acceso a diferentes tipos de contenido sobre Dynamics 365 para las operaciones, como presentaciones de la combinación de Microsoft Office, guías de la tarea, vídeos, y wiki de artículos.
-    ** Panel que admite los procesos empresariales – ** el sitio incluye información proceso- enfocado negocio que aprovecha del modelador (BPM) del proceso empresarial de servicios (LCS) del ciclo de vida de Microsoft Dynamics.

Hemos migrado todo el contenido de nuestro wiki anterior de la ayuda a los documentos. Somos muy emocionados acerca de nuestro nuevo sitio y esperamos que estará también.

### <a name="when-can-we-use-it"></a>¿Cuándo podemos utilizarla?

Puede leer el contenido de documentos ahora núcleo está completamente público y de búsqueda sin requerir inicio en. Puede usar cualquiera de sus motores de búsqueda favoritos para buscar contenido. Puede comentar relación con los artículos en el sitio si lo desea, firmando en una cuenta de GitHub.


## <a name="task-guides"></a>Guías de tareas
Guía de la tarea es una experiencia que le conduce a través de los pasos de una tarea, o un proceso empresarial, controla dirigida, interactiva. Puede abrir (coincidencia) una guía de la tarea del panel de la Ayuda. Al primero hacer clic en una guía de la tarea, el panel de la Ayuda mostrará las instrucciones paso a paso para la tarea. Localizadas le orienta acerca de la tarea están disponibles ahora. [vista de la lectura de la guía de la tarea![] (. /media/task-guide-ops-1024x742.png])(. /media/task-guide-ops.png) Para comenzar la experiencia dirigida, interactiva, haga clic ** inicie la guía de la tarea ** en la parte inferior del panel de la Ayuda. Se abre un puntero negro e indica la acción que debe realizar. Siga las indicaciones que aparecen en la IU y especifique los datos como se indica. [instrucción del paso de la guía de la tarea![] (. /media/task-guide-step-1-ops.png])(. /media/task-guide-step-1-ops.png) ** importante: ** Los datos que se especifica cuando se tiene una guía de la tarea es real. Si está en un entorno de producción, los datos se especificarán en la empresa que está usando actualmente.

### <a name="it-all-begins-with-task-recorder"></a>Todo comienza el Grabador de tareas

Las guías de tareas se crean mediante el Grabador de tareas. Al usar el Grabador de tareas, se graban todas las acciones que realiza en la interfaz de usuario de Dynamics 365 for Operations (como hacer clic en menús, cambiar la configuración y especificar cambios). Los pasos que grabe se denominan conjuntamente grabación de tareas. Como explicamos en la sección anterior, las grabaciones de tareas se pueden mostrar en el panel Ayuda y reproducir como guías de tareas. Sin embargo, hay otras maneras en que puede usar grabaciones de tareas:

-   **Guardar grabaciones de tareas en BPM**: puede guardar una grabación de tareas en una línea de una jerarquía en una biblioteca de BPM en LCS. Al guardar una grabación de tareas en BPM, se genera y se guarda un diagrama de flujo, junto con los pasos de la grabación. **Nota:** Para mostrar una grabación de tareas en el panel de Ayuda de Dynamics 365 for Operations y reproducirla como guía de tareas, deberá guardar la grabación en una biblioteca de BPM.
-   **Guardar grabaciones de tareas como documentos de Word**: al guardar una grabación de tareas como documento de Microsoft Word, puede producir con facilidad guías de formación imprimibles para su organización.

Para obtener más información acerca del Grabador de tareas, consulte [Grabador de tareas en Dynamics 365 para las operaciones (.]. /user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Creación de grabaciones de tareas personalizadas

Puede crear sus propias grabaciones de tareas o descargar y personalizar grabaciones de tareas que proporcione Microsoft. Por lo tanto, puede crear una Ayuda personalizada para su organización que refleje su implementación específica de Dynamics 365 for Operations. Para mostrar una tarea que registra en Dynamics 365 para el panel de la Ayuda de las operaciones y jugarla como una guía de la tarea, tendrá que guardar el registro a una biblioteca de BPM en el CD. Si es un socio, y se asciende a una biblioteca una biblioteca corporativa y la incluye en una solución, estarán disponibles a sus clientes. Para obtener instrucciones detalladas, consulte [mediante los registros de la tarea para crear documentación o la formación.] (. /user-interface/task-recorder.md).

## <a name="in-product-help"></a>Ayuda en el producto
¿Para obtener acceso al contenido de la Ayuda dentro de Dynamics 365 para las operaciones, o haga clic en ** Ayuda ** (**? ** el icono) y después elige Ayuda o presione Ctrl+Shift+?. En ambos casos, se abre el panel Ayuda. Desde el panel de ayuda, puede tener acceso a los artículos o tarea a las guías. [![](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Artículos de acceso del panel de la Ayuda

Desde el panel de ayuda, puede tener acceso a los artículos que se aplican a Dynamics 365 cliente entre las operaciones. Cuando se abren el panel de la Ayuda y hace clic en ** wiki ** la ficha, verá los artículos que se aplican a la página que está actualmente en Dynamics 365 para las operaciones. Si no se encuentra ningún artículos, puede especificar palabras clave para limitar la búsqueda. Al hacer clic en un artículo en el panel de la Ayuda, una nueva ficha abre en su explorador y aparece el artículo. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Guías de acceso de la tarea del panel de la Ayuda

Para poder tener acceso a las guías de la tarea del panel de la Ayuda, un administrador del sistema debe atravesar a ** los parámetros del sistema ** páginas correspondientes en Dynamics 365 para las operaciones y configurar algunos parámetros. **Notas:**

-   Para configurar la ayuda, debe iniciar sesión con una cuenta en el mismo poseedor que el poseedor en que se implementa Dynamics 365 for Operations.
-   No es posible conectarse a una biblioteca de LCS desde una instancia de Dynamics 365 for Operations que se ejecuta en un disco duro virtual (VHD) local.

[formulario Parámetros del sistema![con los valores de la Ayuda] (. /media/system-parameters_ops-1024x437.png])(. /media/system-parameters_ops.png) ** En los parámetros del sistema ** la página, siga estos pasos:

1.  **Importante: **La primera vez que abra la ficha de la Ayuda, debe conectar con Lifecycle Services. Asegúrese de haga clic en el vínculo del medio del formulario, espere la conexión, cierre el cuadro de diálogo, y haga clic en Aceptar para obtener los parámetros el formulario. [![conectar con el CD] (. /media/connect-to-lcs-crop-1024x365.png])(. /media/connect-to-lcs-crop.png)
2.  Seleccione el proyecto de Lifecycle Services al que conectarse.
3.  Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.
4.  Establezca el orden de visualización de las bibliotecas de BPM. Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel Ayuda.

Una vez que un administrador del sistema complete estos pasos, puede abrir el panel Ayuda y hacer clic en la pestaña **Guías de tareas**. Ahora verá a las guías de la tarea que se aplican a la página que está actualmente en Dynamics 365 para las operaciones. Si no se encuentra ninguna guías de la tarea, puede especificar palabras clave para limitar la búsqueda. Después de hacer clic en una guía de la tarea en el panel de la Ayuda, el panel de la Ayuda muestra instrucciones paso a paso, y sabe jugar la guía de la tarea. [vista de la lectura de la guía de la tarea![] (. /media/task-guide-ops-1024x742.png])(. /media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Lugar son las guías traducidas de la tarea?

Traducidas le orienta acerca de la tarea se liberan en “bibliotecas con todos los idiomas” en el puesto. En Dynamics 365 para las operaciones, consultar ayuda localizada de la guía de la tarea, asegúrese de que está conectado a una biblioteca de apppropriate. El idioma que una guía de la tarea aparece en se controla para cada usuario por la configuración de idioma ** bajo las opciones ** &gt; ** preferencias **. 
-   Si se ha traducido una guía de la tarea, cuando se abre que la guía de la tarea todo el texto de la guía de la tarea aparecerá en el idioma seleccionado.
-   Si una guía de la tarea aún no se ha traducido, cuando lo abre, sólo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="additional-resources"></a>Recursos adicionales
En la tabla siguiente se muestran los sitios web que proporcionan el contenido de Dynamics 365 for Operations. Nuestros sitios web de contenido están organizados para admitir el ciclo de vida del cliente. Cada fase se admite con otro conjunto de sitios. Los sitios que tienen un asterisco (\*) situado junto al nombre requieren que se firme en mediante una cuenta que está asociada a un plan de servicio.

| Sitio                                                                     | Descripción                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com (https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations)] | Hospeda o vincula toda la documentación del producto para Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Proporciona un espacio de trabajo de colaboración basado en la nube que los clientes y los socios pueden utilizar para gestionar los proyectos de Dynamics 365 for Operations, desde preventas hasta implementación y operaciones. Este sitio es útil en todas las fases de una implementación. |
| CustomerSource [] (http://www.customersource.com/)\*                       | Hospeda amplios recursos de formación y es el sitio de soporte principal de Dynamics 365 for Operations. Puede que sea necesario iniciar sesión para obtener acceso a recursos específicos en el sitio.                                                                      |
| [Blog admiten (http://aka.ms/AXSupportBlog)]                              | Proporciona sugerencias y trucos que publica el Equipo de soporte de Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN (http://aka.ms/AXMSDN)]                                             | Hospeda contenido de versiones anteriores que se escriben para desarrolladores.                                                                                                                                                                       |
| [TechNet (http://aka.ms/TechNet)]                                         | Hospeda contenido de versiones anteriores que se escriben para los profesionales de TI y los usuarios de aplicación.                                                                                                                                           |
| Comunidad [] de Dynamics (http://community.dynamics.com/en/)                  | Hospeda blogs, foros y vídeos.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/ (http://www.microsoft.com/dynamics/)]                 | Ofrece información de evaluación y ventas.                                                                                                                                                                                                 |



<a name="see-also"></a>Consulte también
--------

[365 Dinámica para el sistema de ayuda de las operaciones (hoja de datos transferible)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Grabador de tareas en Microsoft Dynamics 365 para las operaciones (.]. /user-interface/task-recorder.md)

[Crear documentación o formación con las grabaciones de tareas](../user-interface/task-recorder.md)

[Nuevas o actualizadas guías de la tarea (noviembre de 2016)]new-task-guides-november-2016.md (
) [nuevas o actualizadas guías de la tarea (agosto de 2016)]new-updated-task-guides-available-august-2016.md (
) [nuevas o actualizadas guías de la tarea (mayo de 2016)]new-updated-task-guides-available-may-2016.md (
) [nuevas guías de la tarea (febrero de 2016)](new-task-guides-available-february-2016.md)






