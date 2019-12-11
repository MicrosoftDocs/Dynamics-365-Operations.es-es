---
title: Configurar un entorno de evaluación de comercio electrónico
description: Esta guía ofrece instrucciones detalladas para aprovisionar y configurar su entorno de versión preliminar de Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771689"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>Configurar un entorno de evaluación de comercio electrónico

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Esta guía ofrece instrucciones detalladas para aprovisionar y configurar su entorno de versión preliminar de Microsoft Dynamics 365 Commerce. Antes de empezar, recomendamos que al menos eche un vistazo a la documentación para tener una idea de lo que conlleva el proceso y de lo que contiene la guía.

*Nota: Si no se le ha concedido acceso a la versión preliminar de Microsoft Dynamics 365 Commerce todavía, puede solicitar acceso a la versión preliminar desde el [Sitio web de Commerce](https://aka.ms/Dynamics365CommerceWebsite).*

## <a name="summary"></a>Resumen
Para aprovisionar el entorno correctamente, el proyecto tiene que crearse con un tipo y nombre de producto específicos. El entorno y Retail Cloud Scale Unit también tienen algunos parámetros específicos que necesita usar para iniciar el aprovisionamiento de comercio electrónico posteriormente. Las instrucciones de esta guía contienen todos los pasos necesarios que necesita tomar y los parámetros que necesita usar.

Tras el aprovisionamiento correcto, hay algunos pasos posterior a él que necesita llevar a cabo para preparar su entorno de versión preliminar. Algunos pasos son opcionales, en función de los aspectos del sistema que desee evaluar. En caso de que cambie de parecer posteriormente, siempre podrá ejecutar los pasos opcionales posteriormente.

Si tiene preguntas acerca de los pasos de aprovisionamiento o tiene problemas, indíquenoslo en el [grupo de Microsoft Dynamics 365 Commerce Preview Yammer](https://aka.ms/Dynamics365CommercePreviewYammer). 

## <a name="prerequisites"></a>Requisitos previos
Los siguientes son requisitos previos para aprovisionar su entorno de Dynamics 365 (Versión preliminar):
* Tiene acceso al **portal de Lifecycle Services (LCS)**.
* Se le ha **aceptado en el programa Dynamics 365 Commerce (Versión preliminar)**.
* Tiene los permisos necesarios para crear un proyecto para **Preventa de cliente potencial** o **Migrar, crear soluciones y obtener información sobre**.
* Es miembro del rol **Administrador de entornos** o **Propietario de proyecto** en el proyecto en el que aprovisionará el entorno.
* Tiene acceso de administrador a su suscripción de Azure o póngase en contacto con un administrador de suscripción que pueda realizar los dos pasos que requieren permisos de administración en su nombre.
* Tiene su **Id. de inquilino de AAD** disponible.
* Ha creado un **Grupo de seguridad de AAD** que se utilizará como **Grupo de las administradores del sistema de comercio electrónico** y tiene su id. disponible
* Ha creado un **Grupo de seguridad de AAD** que se utilizará como **Grupo del moderador de calificaciones y de revisiones** y tiene su id. disponible (puede ser el mismo GS que el grupo de administradores del sistema anterior).
## <a name="provisioning-preview-environment"></a>Entorno de versión preliminar de aprovisionamiento
Estas instrucciones abarcan el aprovisionamiento de un entorno de versión preliminar de Microsoft Dynamics 365 Commerce. Tras completar correctamente estos pasos, dispondrá de un entorno de versión preliminar que está preparado para configurarse. Todas las actividades que se describen aquí tienen lugar en el portal de LCS.

*Tenga en cuenta que el acceso de versión preliminar está asociado a la cuenta de LCS y a la organización que especificó en su aplicación de versión preliminar. Tiene que usar esa misma cuenta para aprovisionamiento. Si tiene que usar una cuenta de LCS o inquilino diferente para el entorno de versión preliminar, necesita proporcionarnos dichos detalles. Para obtener información de contacto, consulte "Recursos adicionales” a continuación.*
### <a name="before-starting"></a>Antes de comenzar
##### <a name="grant-access-to-e-commerce-applications"></a>Conceder acceso a aplicaciones de comercio electrónico

*Nota: **La persona que inicia sesión tiene que ser administrador de inquilino de AAD**. Sin completar correctamente este paso, se producirá un error en el resto de pasos de abastecimiento.*

1. Para este paso, necesita su **Id. de inquilino de AAD**. Es necesario que autorice aplicaciones de comercio electrónico para obtener acceso a su suscripción de Azure. La forma más sencilla de lograr esto es ensamblar una dirección URL como esta:

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **No haga clic en la dirección URL directamente**, en su lugar, cópiela y péguela en el explorador o editor de texto y reemplace **\{AAD_TENANT_ID\}** por su **Id. de inquilino de AAD**, antes de navegar a la dirección URL.
3. Se le presentará el cuadro de diálogo de inicio de sesión de Microsoft AAD en el que confirmará que desea conceder el acceso de la versión preliminar de Dynamics 365 Commerce a su suscripción.
4. Se le enviará a una página que confirme si la operación fue correcta.

##### <a name="log-in-to-the-lcs"></a>Iniciar sesión en LCS
1. Inicie sesión en el portal de LCS; https://lcs.dynamics.com
1. Asegúrese de que ha iniciado sesión con la misma cuenta de LCS que usó para solicitar acceso a la versión preliminar.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Confirmar que las características de versión preliminar están disponibles y habilitadas
1. En la página de información, desplácese totalmente a la derecha y haga clic en el icono **Administración de características de vista previa**.
1. Desplácese hacia abajo hasta "CARACTERÍSTICAS DE VISTA PREVIA PRIVADA” y asegúrate de que las siguientes características están disponibles y habilitadas:
    1. **Evaluación de comercio electrónico**
    1. **Entornos de programa de versión preliminar de Commerce**
1. Si no ve estas características en la lista, póngase en contacto con nosotros con su correo electrónico de trabajo, cuenta de LCX y detalles de inquilino. Para más información sobre cómo ponerse en contacto con notros, consulte **Recursos adicionales** a continuación.

![Icono de administración de vista previa](./media/preview1.png)

![Características de vista previa](./media/preview2.png)
### <a name="create-project"></a>Crear proyecto
##### <a name="creating-new-project"></a>Creación de un proyecto nuevo
1. Haga clic en **+** para crear un proyecto nuevo.
1. Si es socio, elija **Migrar, crear soluciones y obtener información sobre**.
1. Si es cliente, elija **Preventa de cliente potencial**.
1. Escriba un nombre, una descripción y una industria como vea más adecuado.
1. Para **Nombre del producto**, seleccione **Dynamics 365 Retail**.
1. Para **Versión del producto**, seleccione **Dynamics 365 Retail**.
1. Para **Metodología**, seleccione **Metodología de implementación de Dynamics Retail**.
1. Puede importar roles y usuarios de un proyecto existente si lo desea.
1. Haga clic en **Crear**.
1. Se le envía a la vista del proyecto.
##### <a name="add-azure-connector"></a>Agregar conector de Azure
1. Si es socio, haga clic en **Configuración del proyecto** desde los iconos de herramientas hasta la parte más situada a la derecha.
1. Si es cliente, elija **Configuración del proyecto** en el menú superior.
1. Seleccione **Conectores de Azure**.
1. Haga clic en **+ Agregar** para agregar el conector de Azure.
1. Escriba un nombre.
1. Introduzca su **Id. de suscripción de Azure**.
1. Habilite **Configurar para usar Azure Resource Manager (ARM)**.
1. Compruebe que **Dominio (o id.) de inquilino de AAD de suscripción de Azure** es correcto. Consulte su administración de suscripción de Azure, en caso necesario.
1. Haga clic en **Siguiente**.
1. Siga las instrucciones en pantalla para conceder acceso a las aplicaciones necesarias para su suscripción. Consulte su administración de suscripción de Azure, en caso necesario:
    1. Inicie sesión en el portal de Azure: https://portal.azure.com/
    1. Asegúrese de que ha seleccionado el directorio correcto.
    1. Haga clic en **Suscripciones** en el menú de la izquierda.
    1. Encuentre la suscripción correcta en la lista y selecciónela. Use la búsqueda si procede.
    1. Elija **Control de acceso (IAM)** en el menú.
    1. Haga clic en **Agregar** en **Agregar una asignación de roles** en la parte derecha. Se abrirá el panel **Agregar asignación de roles**.
    1. Para **Rol**, seleccione **Colaborador**.
    1. Para **Asignar acceso a**, deje como **Entidad de servicio, grupo o usuario de Azure AD**.
    1. En **Seleccionar**, especifique **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Seleccione **Servicios de implementación de Dynamics [wsfed-enabled]** en la lista.
    1. Haga clic en **Guardar**.
1. Haga clic en **Siguiente**.
1. Siga las instrucciones en pantalla para conceder acceso a las aplicaciones necesarias para su suscripción. Consulte su administración de suscripción de Azure, en caso necesario.
1. Haga clic en **Siguiente**.
1. Para **Región de Azure**, elija **Este de EE. UU.**, **Este de EE. UU. 2**, **Oeste de EE. UU.** o **Oeste de EE. UU.**.
1. Haga clic en **Conectar**.
1. Su conector de Azure debe aparecer en la lista.
### <a name="import-extension"></a>Extensión de importación
1. Desplácese de nuevo a la página del información de proyecto haciendo clic en el nombre del proyecto en la parte superior.
1. Si es socio, haga clic en **Biblioteca de activos** desde los iconos de herramientas hasta la parte más situada a la derecha.
1. Si es cliente, elija **Biblioteca de activos** en el menú superior.
1. Seleccione **Paquete de software implementable** en la lista de la izquierda.
1. En el panel de acciones, haga clic en **IMPORTAR**.
1. Seleccione **Extensión de demostración de vista previa de Commerce** en la lista de activos en **BIBLIOTECA DE ACTIVOS COMPARTIDOS**.
1. Haga clic en **Recoger**.
1. Se le devolverá a la biblioteca de activos y debería ver la extensión en la lista.

![Creación de proyecto: versiones](./media/import.png)
### <a name="deploy-environment"></a>Implementar entorno

*Nota: Es posible que no se muestren los pasos 6, 7 y 8, ya que se omiten las pantallas con la opción única. Cuando se encuentre en la vista **Parámetros ambientales**, confirme que dispone del texto “Dynamics 365 Commerce (Versión preliminar): demostración (10.0.6 con la Platform update 30)” directamente encima del campo **Nombre del entorno**. Consulte la captura de pantalla siguiente.*

1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Haga clic en **+ Agregar** para agregar un entorno.
1. Para **Versión de la aplicación**, seleccione **10.0.6**.
1. Para **Versión de la plataforma**, seleccione **Platform Update 30**.
1. Haga clic en **Siguiente**.
1. Para la topología del entorno, seleccione **DEMOSTRACIÓN**.
1. Para la topología del entorno, elija **Dynamics 365 Commerce (Versión preliminar): demostración**.
1. Si ha configurado un conector de Azure antes, se usará para este entorno. Si ha configurado varios conectores de Azure, tiene la opción de seleccionar qué conector desea utilizar: **Este de EE. UU. 2**, **Este de EE. UU. 2**, **Oeste de EE. UU.** o **Oeste de EE. UU.** (recomendado para un mejor rendimiento integral).
1. Especifique un **Nombre del entorno**.
1. Ajuste el tamaño de máquina virtual como vea más adecuado. (Se recomienda VM SKU **D13 v2**).
1. Deje **Configuración avanzada** como está.
1. Después de revisar los términos de precios y licencias en la pantalla, seleccione la casilla para indicar el acuerdo.
1. Haga clic en **Siguiente**.
1. En la pantalla de confirmación de la implementación, después de comprobar que los detalles son correctos, haga clic en **Implementar**.
1. Volverá a la vista **Entornos hospedados en la nube** y su entorno debe aparecer en la lista.
1. Su entorno solicitado se mostrará como en cola y, a continuación, en implementación. Se tardará algún tiempo en completarse todos los flujos de trabajo, por lo que vuelva a comprobarlo tras unas horas (6 – 9 horas, aproximadamente).
1. Antes de continuar, asegúrese de que el estado del entorno es **Implementado**.

![Creación de proyecto: versiones](./media/project1.png)

![Creación de proyecto: topología 1](./media/project2.png)

![Creación de proyecto: topología 2](./media/project3.png)

![Creación de proyecto: parámetros de entorno](./media/project4.png)
### <a name="initialize-rcsu"></a>Inicializar RCSU
1. Mientras se encuentre en la vista **Entornos hospedados en la nube**, seleccione el entorno en la lista.
1. En la vista del entorno de la derecha de la pantalla, haga clic en **Detalles completos**. Aparecerá la vista de detalles del entorno.
1. En **CARACTERÍSTICAS DEL ENTORNO**, haga clic en **Administrar**.
1. En la pestaña **Retail**, haga clic en **Inicializar**. La vista de parámetros de la inicialización de RCSU se mostrará.
1. Para **REGIÓN**, seleccione **Este de EE. UU.**, **Este de EE. UU. 2**, **Oeste de EE. UU.** o **Oeste de EE. UU.**.
1. Para **VERSIÓN**, primero seleccione **Especificar una versión** en la lista desplegable y, a continuación, especifique **9.16.19262.5** en el campo de texto que aparece a continuación. *Nota: Asegúrese de **especificar la versión versión** que se muestra aquí para evitar tener que actualizar RCSU posteriormente para corregir la versión.*
1. Habilite **Aplicar extensión**.
1. En la lista de extensiones, elija **Extensión de demostración de vista previa de Commerce**.
1. Haga clic en **Inicializar**.
1. En la pantalla de confirmación de la implementación, después de comprobar que los detalles son correctos, haga clic en **Sí**.
1. Se le devuelve a la vista **Administración de Retail** con la pestaña **Retail** activada. Su RCSU ha estado en cola para aprovisionamiento.
1. Espere hasta que su estado de RCSU sea **CORRECTO** antes de continuar (tardará de 2 a 5 horas).
### <a name="initialize-e-commerce"></a>Inicializar comercio electrónico
1. Cambie a la pestaña **Comercio electrónico (versión preliminar)**.
1. Tras revisar el consentimiento de la versión preliminar, haga clic en **Configuración**.
1. Escriba un nombre para **Nombre de inquilino de comercio electrónico**. Sin embargo, tenga en cuenta que esto será visible en algunas de las direcciones URL que apuntan a su instancia de comercio electrónico.
1. Para **Nombre de Retail Cloud Scale Unit**, seleccione la RCSU en la lista (la lista solo debe tener una opción).
1. **Geografía de comercio electrónico** se rellena automáticamente y no se puede cambiar.
1. Haga clic en **Siguiente** para continuar.
1. Para **Nombres de hosts admitidos**, escriba cualquier dominio válido (por ejemplo, www.fabrikam.com).
1. Para **Grupo de seguridad de AAD para administrador del sistema**, especifique el id. de GS de AAD que desea usar como grupo de administradores del sistema de comercio electrónico.
1. Para **Grupo de seguridad de AAD para moderadores de clasificaciones y opiniones**, especifique el id. de GS de AAD que desea usar como grupo de moderadores de clasificaciones y opiniones.
1. Deje los valores **B2C** vacíos (7 campos que comienzan por B2C).
1. Deje la opción **Habilitar servicio de calificaciones y revisiones** habilitada.
1. Haga clic en **Inicializar**.
1. Se le devuelve a la vista **Administración de Retail** con la pestaña **Comercio electrónico (versión preliminar)** activada. Ha comenzado su inicialización de comercio electrónico.
1. Antes de continuar, espere hasta que su estado de inicialización de comercio electrónico sea **INICIALIZACIÓN CORRECTA**.
1. En **VÍNCULOS** en la parte inferior.
    * Anote el vínculo **Sitio de comercio electrónico**. Este es el vínculo a la raíz del sitio C2.
    * Anote el vínculo **Herramienta de administración del sitio de comercio electrónico**. Este es el vínculo a la herramienta de administración del sitio (herramienta de creación C1).
## <a name="post-provisioning-steps"></a>Pasos posteriores al aprovisionamiento
En esta etapa, el entorno se ha aprovisionado de manera integral, pero sigue habiendo pasos de configuración que es necesario atender para poder comenzar la evaluación del entorno.
### <a name="before-starting"></a>Antes de comenzar
1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Seleccione el entorno en la lista.
1. Haga clic en **Detalles completos** en la información del entorno de la derecha.
1. Haga clic en **Iniciar sesión** para abrir un menú y elija **Iniciar sesión en el entorno**.

Asegúrese de que la entidad jurídica **USRT** está seleccionada (esquina superior derecha).

### <a name="configure-pos"></a>Configurar POS
##### <a name="associate-worker-with-your-identity"></a>Asociar el trabajador con su identidad
1. Mediante el menú de la izquierda, vaya a **Módulos > Retail> Empleados > Trabajadores**.
1. En la lista, busque y seleccione el registro **000713 - Andrew Collette**.
1. En el panel de acciones, haga clic en **Retail**.
1. Haga clic en **Asociar identidad existente**.
1. En el campo **Correo electrónico** (a la derecha de **Buscar mediante correo electrónico**), escriba su dirección de correo electrónico.
1. Haga clic en **Buscar**.
1. Seleccione el registro con su nombre.
1. Haga clic en **Aceptar**.
1. Haga clic en **Guardar**.
##### <a name="activate-cloud-pos"></a>Activar PDV en la nube
1. Inicie sesión en el portal de LCS.
1. Vaya al proyecto.
1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Seleccione el entorno en la lista.
1. Haga clic en **Detalles completos** en la información del entorno de la derecha.
1. Haga clic en **Iniciar sesión** para abrir un menú, elija **Iniciar sesión en el punte de venta de nube**, PDV debería cargarse.
1. Haga clic en **Siguiente**.
1. Inicie sesión con su cuenta de AAD.
1. En **Nombre de tienda**, elija **San Francisco**.
1. Haga clic en **Siguiente**.
1. En **Caja registradora y dispositivo**, seleccione **SANFRAN-1**.
1. Haga clic en **Activar**.
1. Debería de cerrar sesión y terminar en la pantalla de inicio de sesión de PDV.
1. Ahora puede iniciar sesión en la experiencia de PDV de nube mediante el id. de operador **000713** y contraseña **123**.
### <a name="site-setup"></a>Configuración del sitio
1. Inicie sesión en la **herramienta de administración del sitio** mediante la dirección URL que anotó antes.
1. Haga clic en el sitio de **Fabrikam** para abrir el cuadro de diálogo de configuración del sitio.
1. Para el dominio, seleccione el dominio que especificó anteriormente al inicializar el comercio electrónico.
1. Para el canal predeterminado, seleccione **Tienda en línea extendida de Fabrikam**. *Nota: Asegúrese de seleccionar la tienda en línea **extendida***
1. Para el idioma predeterminado, seleccione **es-es**.
1. Deje **Ruta** como está.
1. Haga clic en **Aceptar**.
1. Se le enviará a la lista de páginas del sitio.
### <a name="enable-jobs"></a>Habilitar trabajos
1. Inicie sesión en el entorno (sede).
1. Con el menú de la izquierda, vaya a **Retail > Consultas e informes > Trabajos por lotes**.
1. Realice los pasos siguientes para cada uno de los trabajos de la lista siguiente:
    * **Procesar notificación por correo electrónico de pedido comercial**.
    * **Disponibilidad del producto**.
    * **P-0001**.
    * **Trabajo de sincronización de pedidos**.
1. Use el filtro rápido para buscar el trabajo por su nombre (mostrados anteriormente).
1. Si el Estado del trabajo **Retenido**, realice los siguientes pasos:
    1. Seleccione el registro.
    1. En el panel de acciones, abra **Trabajo por lotes**-cinta de opciones y haga clic en **Cambiar estado**.
    1. Seleccione **Esperando** y haga clic en **Aceptar**.
### <a name="run-full-data-sync"></a>Ejecutar sincronización de datos completa
1. Mediante el menú de la izquierda, vaya a **Módulos > Retail > Configuración de sede central > Programador de tareas Retail > Base de datos de canales**.
1. El canal**Predeterminado** está seleccionado en la lista de la izquierda. *Seleccione el otro canal disponible (con el nombre **scXXXXXXXXX**)*.
1. Haga clic en **Sincronización de datos completa** en el panel de acciones.
1. Introduzca **9999** como la programación de distribución.
1. Haga clic en **Aceptar**.
1. Haga clic en **Aceptar**.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Después de estos pasos, estará preparado para iniciar la evaluación de su entorno de versión preliminar.
Use la dirección URL **Herramienta de administración del sitio de comercio electrónico** para navegar hasta la experiencia de creación de C1 y la dirección URL de **Sitio de comercio electrónico** para navegar hasta la experiencia de sitio de C2.

## <a name="additional-resources"></a>Recursos adicionales
### <a name="how-to-find-your-aad-tenant-id"></a>Cómo encontrar su id. de inquilino de AAD
El id. de inquilino de AAD es GUID y se parece a este ejemplo: **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>Desde le portal de Azure
1. Inicie sesión en el portal de Azure: https://portal.azure.com/
1. Asegúrese de que ha seleccionado el directorio correcto.
1. Haga clic en **Azure Active Directory** en el menú de la izquierda.
1. Elija **Propiedades** en **Gestionar**.
1. El id. de inquilino de AAD se muestra en **Id. de directorio**.
##### <a name="from-openid-connect-metadata"></a>Desde los metadatos de Open ID Connect
Cree **Dirección URL de OpenID** reemplazando **\{SU_DOMINIO\}** por su dominio, por ejemplo, microsoft.com: https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration sería https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration

1. Vaya hasta **Dirección URL de OpenID** con su dominio en él.
1. El id. de inquilino de AAD se puede ver en varios valores de propiedades.
1. Localice **authorization_endpoint** y extraiga el GUID justo después de **login.microsoftonline.com/**.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Cómo encontrar el id. de su grupo de seguridad de AAD
El id. del grupo de seguridad de AAD es un GUID y se parece a este ejemplo: **436ea7f5-ee6c-40c1-9f08-825c5811066a**

Este paso asume que el usuario es miembro del grupo para el que intenta localizar el id.
1. Desplácese hasta el Explorador de gráficos: https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Haga clic en **Iniciar sesión con Microsoft** e inicie sesión con sus credenciales.
1. Después de iniciar sesión, haga clic en **mostrar más ejemplos** desde la izquierda.
1. Habilite **Grupos** desde el panel derecho.
1. Cierre el panel derecho.
1. Haga clic en **todos los grupos a los que pertenezco**.
1. Localice su grupo en el cuadro de texto **Vista previa de respuesta**.
1. El id. del grupo de seguridad se encuentra debajo del **id.** de la propiedad.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>Probar la información de la tarjeta de crédito para realizar compras de prueba
Para realizar transacciones de prueba en el sitio, puede usar esta información de la tarjeta de crédito de prueba:

Número de tarjeta: 4111-1111-1111-1111, vencimiento: 20/10, CVV: 737

*Nota: No debe intentar utilizar la información de la tarjeta de crédito real en el sitio de prueba en ninguna circunstancia.*
### <a name="useful-links"></a>Vínculos útiles
* [LCS (Lifecycle services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Portal de Microsoft Azure](https://azure.microsoft.com/en-us/features/azure-portal)
* [Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
* [Recursos de ayuda para Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Soporte técnico de la versión preliminar de Microsoft Dynamics 365 Commerce
Si tiene problemas mientras realiza los pasos de aprovisionamiento, visite el [grupo de Microsoft Dynamics 365 Commerce Preview Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) para obtener ayuda. 

Si tiene problemas para obtener acceso al grupo Yammer, también puede ponerse en contacto por correo electrónico en **Dynamics365Commerce@microsoft.com**. Esta dirección de correo electrónico no se controla de manera activa, por lo que puede esperar un retraso en la respuesta.
***
## <a name="prerequisites-for-optional-features"></a>Requisitos previos para las características opcionales
Si desea evaluar las características transaccionales de correo electrónico, se deben cumplir los requisitos previos siguientes:
* Tiene un servidor de correo electrónico disponible (servidor SMTP), que se puede usar desde la suscripción de Azure donde aprovisiona el entorno de la versión preliminar.
* Tiene el FQDN/IP del servidor, el número de puerto de SMTP y detalles de autenticación disponibles.

Si desea evaluar características de la administración de activos digitales, ingerir de manera específica nuevas imágenes de omnicanal, se deben cumplir los requisitos previos siguientes:
* Necesita debe tener su **Nombre de inquilino de CMS** disponible. A continuación se indican directrices para encontrar este nombre.
### <a name="configure-image-backend-optional"></a>Configuración de back-end de imagen (opcional)
##### <a name="finding-your-media-base-url"></a>Búsqueda de URL base de medios
*Nota: Para poder completar este paso, debe completar **Configuración del sitio**.*
1. Inicie sesión en la herramienta de administración del sitio mediante la dirección URL que anotó antes.
1. Abra el sitio de **Fabrikam**.
1. Elija **Activos** en el menú de la izquierda.
1. Seleccione cualquier activo de imagen único.
1. Localice **Dirección URL pública** del inspector de propiedades de la derecha. Tiene una dirección URL incluida.
    * Dirección URL de ejemplo: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. Reemplazar el último identificador en la dirección URL (MA1nQC en la dirección URL del ejemplo anterior) por la siguiente cadena: **search?fileName=**
    * Dirección URL de ejemplo después de la sustitución: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * Esta es su **URL base de medios**: anótela.
##### <a name="updating-the-media-base-url"></a>Actualizar la URL base multimedia
1. Inicie sesión en el entorno (sede).
1. Mediante el menú de la izquierda, vaya a **Módulos > Retail > Configuración de canal > Programador de tareas Retail > Perfiles del canal**.
1. Haga clic en **Editar**.
1. En **Propiedades del perfil**, reemplace el valor de propiedad para **Dirección URL base del servidor multimedia** por la **URL base de medios** que creó anteriormente.
1. Seleccione el otro canal de la lista de la izquierda canal, en el canal **Predeterminado**.
1. En **Propiedades del perfil**, haga clic en **+Agregar**.
1. Para la propiedad que se ha agregado, elija **Dirección URL base del servidor multimedia** como clave de propiedad y para el valor de la propiedad, introduzca la **URL base de medios** que creó anteriormente.
1. Haga clic en **Guardar**.

### <a name="configure-email-server-optional"></a>Configurar el servidor de correo electrónico (opcional)
Tenga en cuenta que el servidor SMTP o servicio de correo electrónico que especifica aquí debe ser accesible dentro de la suscripción de Azure que está usando para el entorno.
1. Inicie sesión en el entorno (sede).
1. Mediante el menú de la izquierda, vaya a **Módulos > Retail > Configuración de sede central > Parámetros > Parámetros de correo electrónico**.
1. Haga clic en la pestaña **Configuración de SMTP**.
1. En el campo **Servidor de correo saliente**, escriba el FQDN o la dirección IP de su servicio de correo electrónico o servidor SMTP.
1. En el campo **Número de puerto SMTP**, especifique el número de puerto (el valor predeterminado es 25 cuando no se usa SSL).
1. En el campo **Nombre de usuario**, escriba un valor (si se requiere autenticación).
1. En el campo **Contraseña**, escriba un valor (si se requiere autenticación).
1. Haga clic en **Guardar**.
1. Haga clic en **Actualizar**.
1. Haga clic en la pestaña **Correo electrónico de prueba**.
1. En el campo Proveedor de correo electrónico, elija **SMTP**.
1. En el campo **Enviar a**, escriba la dirección de correo electrónico donde desea que se entregue el correo electrónico de prueba.
1. Haga clic en **Enviar correo electrónico de prueba**.
### <a name="configure-email-templates-optional"></a>Configurar plantillas de correo electrónico (opcional)
La plantilla de correo electrónico para cada evento transaccional para el que desea enviar mensajes de correo electrónico se tiene que actualizar con una dirección de correo electrónico de remitente válida.
1. Mediante el menú de la izquierda, vaya a **Módulos > Administración de la organización > Configuración > Plantillas de correo electrónico de organización**.
1. Haga clic en **Mostrar lista**.
1. Para cada una de las plantillas de la lista:
    1. En el campo **Correo electrónico de remitente**, escriba la dirección de correo electrónico del remitente para esta plantilla de correo electrónico.
    1. (Opcional) En el campo **Nombre del remitente**, escriba un nombre que se usará como remitente para esta plantilla de correo electrónico.
1. Haga clic en **Guardar**.
### <a name="customizing-email-templates-optional"></a>Personalización de plantillas de correo electrónico (opcional)
Es posible que desee personalizar las plantillas de correo electrónico para utilizar diferentes imágenes o actualizar los vínculos de la plantilla para volver a vincular a su entorno de versión preliminar. Los pasos siguientes explican cómo descargar plantillas predeterminadas, personalizarlas y actualizar las plantillas en el sistema.
1. Con un explorador, descargue [el archivo .zip de correo electrónico predeterminado de la versión preliminar de Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) que contiene los siguientes documentos HTML en su equipo local.
    1. Plantilla de confirmación de pedido
    1. Emitir plantilla de tarjeta regalo
    1. Nueva plantilla de pedido
    1. Empaquetar plantilla de pedido
    1. Recoger plantilla de pedido
1. Personalice las plantillas mediante un editor HTML o de texto. Consulte una lista a continuación de los tokens admitidos.
1. Inicie sesión en el entorno (sede).
1. Mediante el menú de la izquierda, vaya a **Módulos > Retail > Configuración de sede central > Parámetros > Plantillas de correo electrónico de organización**.
1. Expanda la lista de la izquierda para ver todas las plantillas.
1. Para cada una de las plantillas que desea personalizar, realice los pasos siguientes:
    1. Seleccione la plantilla en la lista.
    1. En **Contenido del mensaje de correo electrónico**, seleccione la versión de idioma adecuada en la lista (**es-es** predeterminado).
    1. En **Contenido del mensaje de correo electrónico**, haga clic en **Editar**, debe ver que se abre el panel **Cargar plantilla de correo electrónico**.
    1. Haga clic en **Examinar** y encuentre el archivo HTML con el contenido personalizado.
    1. Haga clic en **Cargar**, su plantilla se carga en el sistema y se muestra una vista previa.
    1. Haga clic en **Aceptar**.
    1. (Opcional) Personalice la propiedad **Asunto** de la plantilla.
    1. Haga clic en **Guardar**.

#### <a name="supported-tokens-in-the-email-template"></a>Tokens compatibles en la plantilla de correo electrónico
Estos tokens se reemplazarán en el momento de la representación de correo electrónico con los valores reales que se aplican al cliente y su pedido.

**Pedido de ventas**: los siguientes testigos se aplican al pedido de ventas general.

|Nombre del token|Token de |
|---|---|
|Número de pedido|%salesid%|
|Nombre del cliente|%customername%|
|Dirección de entrega|%deliveryaddress%|
|Dirección de facturación|%customeraddress%|
|Fecha del pedido|%shipdate%|
|Modo de entrega|%modeofdelivery%|
|Descuento|%discount%|
|Impuestos|%tax%|
|Total del pedido|%total%|

**Línea de ventas**: los siguientes tokens se rellenan para cada producto del pedido.

*Nota: Coloque los tokens **Lista de productos: inicio** y **Lista de productos: inicio** al comienzo y el final del bloque HTML que se repite para cada producto.*

|Nombre del token|Token de |
|---|---|
|Lista de productos: inicio|\<!--%tablebegin.salesline% -->|
|Lista de productos: final|\<!--%tableend.salesline%-->|
|Nombre de producto|%lineproductname%|
|Descripción|%lineproductdescription%|
|Cantidad|%linequantity%|
|Unidad de precio de línea|%lineprice% (comprobar)|
|total de artículo de línea|%linenetamount%|
|descuento de línea|%linediscount%|
|Fecha de envío|%lineshipdate%|
|Método de compras|%linedeliverymode%|
|dirección de entrega|%linedeliveryaddress%|
|Unidad de ventas de la línea|%lineunit%|

