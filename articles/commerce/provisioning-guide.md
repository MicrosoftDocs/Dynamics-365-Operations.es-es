---
title: Aprovisionar un entorno de vista previa de Dynamics 365 Commerce
description: En este tema se explica cómo aprovisionar un entorno de vista previa de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 06/02/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c109c2326cf01739255b49587c15aa34ad884f6a
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426474"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a>Aprovisionar un entorno de vista previa de Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

En este tema se explica cómo aprovisionar un entorno de vista previa de Dynamics 365 Commerce.

Antes de comenzar, le recomendamos que lea rápidamente este tema para tener una idea de lo que requiere el proceso.

> [!NOTE]
> Si aún no se le ha concedido acceso a la vista previa de Dynamics 365 Commerce, puede solicitar acceso a la vista previa desde el [Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite).

## <a name="overview"></a>Visión general

Para aprovisionar correctamente su entorno de vista previa de Commerce, debe crear un proyecto que tenga un nombre y tipo de producto específicos. El entorno y Commerce Scale Unit (CSU) también tienen algunos parámetros específicos que necesita usar posteriormente para el aprovisionamiento de comercio electrónico. Las instrucciones de este tema describen todos los pasos necesarios para completar el aprovisionamiento y los parámetros que debe usar.

Tras el aprovisionamiento correcto del entorno de vista previa de Commerce, debe completar algunos pasos posteriores al aprovisionamiento. Algunos pasos son opcionales, en función de los aspectos del sistema que desee evaluar. Siempre puede completar los pasos opcionales más adelante.

Para obtener información sobre cómo configurar su entorno de vista previa de Commerce después de aprovisionarlo, consulte [Configurar un entorno de vista previa de Commerce](cpe-post-provisioning.md). Para obtener información sobre cómo configurar características opcionales para su entorno de vista previa de Commerce, consulte [Configurar características opcionales para un entorno de vista previa de Commerce ](cpe-optional-features.md).

Si tiene preguntas acerca de los pasos de aprovisionamiento o si tiene problemas, hágaselo saber a Microsoft en el [grupo de Yammer de la vista previa de Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer).

## <a name="prerequisites"></a>Requisitos previos

Deben cumplirse los siguientes requisitos previos para poder aprovisionar su entorno de vista previa de Commerce:

- Tiene acceso al portal de Microsoft Dynamics Lifecycle Services (LCS).
- Usted es un socio o cliente de Microsoft Dynamics 365 existente y puede crear un proyecto de Dynamics 365 Commerce.
- Se le ha aceptado en el programa vista previa de Dynamics 365 Commerce.
- Tiene los permisos necesarios para crear un proyecto para **Migrar, crear soluciones y obtener información sobre**.
- Es miembro del rol **Administrador de entornos** o **Propietario de proyecto** en el proyecto en el que aprovisionará el entorno.
- Tiene acceso de administrador a su suscripción de Microsoft Azure o está en contacto con un administrador de suscripción que pueda realizar los dos pasos que requieren permisos de administración en su nombre.
- Tiene su id. de suscriptor de Azure Active Directory (Azure AD) disponible.
- Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo de administración del sistema de comercio electrónico y tiene su id. disponible
- Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo moderador de Clasificaciones y revisiones y tiene su id. disponible. (Este grupo de seguridad puede ser el mismo que el grupo de administración del sistema de comercio electrónico).

## <a name="provision-your-commerce-preview-environment"></a>Aprovisionar su entorno de vista previa de Commerce

Estos procedimientos explican cómo aprovisionar un entorno de vista previa de Commerce. Una vez completados correctamente, el entorno de vista previa de Commerce estará listo para la configuración. Todas las actividades que se describen aquí tienen lugar en el portal de LCS.

> [!IMPORTANT]
> El acceso de vista previa está vinculado a la cuenta y organización de LCS que especificó en su aplicación de vista de Commerce. Debe usar la misma cuenta para aprovisionar el entorno de vista previa de Commerce. Si tiene que usar una cuenta o inquilino de LCS diferente para el entorno de vista previa de Commerce, debe proporcionar esos detalles a Microsoft. Para obtener información de contacto, consulte la sección [Compatibilidad con el entorno de vista previa de Commerce](#commerce-preview-environment-support) más adelante en este tema.

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>Confirmar que las características de vista previa están disponibles y activadas en LCS

Para confirmar que las características de vista previa están disponibles y activadas en LCS, siga estos pasos.

1. Inicie sesión en el [portal de LCS](https://lcs.dynamics.com) con la misma cuenta de LCS que utilizó para solicitar acceso a la vista previa.
1. En la página de inicio de LCS, desplácese totalmente a la derecha y seleccione el icono **Administración de características de vista previa**.

    ![Icono de administración de vista previa](./media/preview1.png)

1. Desplácese hacia abajo hasta **Características de vista previa privada** y confirme que las siguientes características están disponibles y activadas:

    - Evaluación de comercio electrónico
    - Entornos de programa de versión preliminar de Commerce

    ![Características de vista previa privada](./media/preview2.png)

1. Si estas características no aparecen en la lista, póngase en contacto con Microsoft y especifique su dirección de correo electrónico de trabajo, su cuenta de LCS y sus detalles de suscriptor. Para obtener información de contacto, consulte la sección [Compatibilidad con el entorno de vista previa de Commerce](#commerce-preview-environment-support).

### <a name="create-a-new-project"></a>Crear un proyecto nuevo

Para crear un proyecto nuevo en LCS, siga estos pasos.

1. En la página de inicio de LCS, seleccione el signo más (**+**) para crear un proyecto.
1. En el panel derecho, siga uno de estos pasos:

    - Si es un partner, seleccione **Migrar, crear soluciones y obtener información sobre**.
    - Si es cliente, seleccione **Preventa de cliente potencial**.

1. Escriba un nombre, una descripción y un sector.
1. En el campo **Nombre del producto**, seleccione **Dynamics 365 Retail**.
1. En el campo **Versión del producto**, seleccione **Dynamics 365 Retail**.
1. En el campo **Metodología**, seleccione **Metodología de implementación de Dynamics Retail**.
1. Opcional: puede importar roles y usuarios de un proyecto existente.
1. Seleccione **Crear**. Aparece la vista del proyecto.

### <a name="add-the-azure-connector"></a>Agregar el conector de Azure

Para agregar el conector de Azure a su proyecto LCS, siga estos pasos.

1. Siga uno de estos pasos:

    - Si es un partner, seleccione el icono **Configuración del proyecto** en el extremo derecho.
    - Si es un cliente, seleccione **Configuración del proyecto** en el menú de nivel superior.

1. Seleccione **Conectores de Azure**.
1. Seleccione **Agregar** para agregar el conector de Azure.
1. Escriba un nombre.
1. Introduzca su id. de suscripción de Azure.
1. Active la opción **Configurar para usar Azure Resource Manager (ARM)**.
1. Compruebe que el valor de **Dominio de inquilino ADD (o Id.) para suscripción de Azure** es correcto. Consulte con su administrador de suscripción de Azure, si es necesario.
1. Seleccione **Siguiente**.
1. Siga las instrucciones de la página para otorgar a las aplicaciones necesarias acceso a su suscripción. Consulte con su administrador de suscripción de Azure, si es necesario.

    1. Inicie sesión en el [portal de Azure](https://portal.azure.com/).
    1. Asegúrese de seleccionar el directorio correcto y, a continuación, en el menú de la izquierda, seleccione **Suscripciones**.
    1. Encuentre la suscripción correcta en la lista y selecciónela. Use la funcionalidad de búsqueda si es necesario.
    1. En el menú, seleccione **Control de acceso (IAM)**.
    1. A la derecha, en **Agregar una asignación de roles**, seleccione **Agregar**. Aparece el panel **Agregar asignación de roles**.
    1. En el campo **Rol** seleccione **Colaborador**.
    1. En el campo **Asignar acceso a**, deje el valor predeterminado, **Entidad de servicio, grupo o usuario de Azure AD**.
    1. En **Seleccionar**, especifique **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Seleccione **Servicios de implementación de Dynamics \[wsfed-enabled\]** en la lista.
    1. Seleccione **Guardar**.

1. Seleccione **Siguiente**.
1. Siga las instrucciones de la página para otorgar a las aplicaciones necesarias acceso a su suscripción. Consulte con su administrador de suscripción de Azure, si es necesario.
1. Seleccione **Siguiente**.
1. En el campo **Región de Azure**, seleccione **Este de EE. UU.**, **Este de EE. UU. 2**, **Oeste de EE. UU.** u **Oeste de EE. UU. 2**.
1. Seleccione **Conectar**. Su conector de Azure debe aparecer en la lista.

### <a name="import-the-commerce-preview-demo-base-extension"></a>Importar la extensión base de demostración de la vista previa de Commerce

Para importar la extensión base de demostración de la vista previa de Commerce en su proyecto, siga estos pasos.

1. Abra la página de inicio de su proyecto seleccionando el nombre del proyecto en la parte superior.
1. Siga uno de estos pasos:

    - Si es un partner, seleccione el icono **Biblioteca de activos** en el extremo derecho.
    - Si es un cliente, seleccione **Biblioteca de activos** en el menú de nivel superior.

1. En la lista de la izquierda, seleccione **Paquete de software implementable**.
1. Seleccione **Importar**.
1. En **Biblioteca de activos compartidos**, seleccione **Extensión base de demostración de la vista previa de Commerce** en la lista de activos.
1. Seleccione **Seleccionar**. Se le devolverá a la Biblioteca de activos y debería ver la extensión en la lista.

La siguiente ilustración muestra las acciones que se deben tomar en la página **Biblioteca de activos** de LCS.

![Importar la extensión base de demostración de la vista previa de Commerce](./media/import.png)

### <a name="deploy-the-environment"></a>Implementar el entorno

Para implementar el entorno, siga estos pasos.

> [!NOTE]
> Es posible que no tenga que completar los pasos 6, 7 u 8, ya que las páginas que tienen una sola opción se omiten. Cuando está en la vista **Parámetros del entorno**, confirme que el texto **Dynamics 365 Commerce - Demostración (10.0.* x* con Platform update *xx*)** aparece directamente encima del campo **Nombre del entorno**. Para obtener detalles, consulte la ilustración que aparece después del paso 8.

1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Seleccione **Agregar** para agregar un entorno.
1. En el campo **Versión de la aplicación**, seleccione la versión más actual. Si tiene una necesidad específica de seleccionar una versión de la aplicación que no sea la versión más actual, no seleccione una versión anterior a **10.0.8**.
1. En el campo **Versión de la plataforma**, use la versión de plataforma que se elige automáticamente para la versión de la aplicación que ha seleccionado. 

    ![Seleccionar las versiones de la aplicación y la plataforma](./media/project1.png)

1. Seleccione **Siguiente**.
1. Seleccione **Demostración** como topología del entorno.

    ![Seleccionar la topología del entorno 1](./media/project2.png)

1. Seleccione **Demostración de Dynamics 365 Commerce** como topología del entorno. Si ha configurado antes un conector de Azure , se usará para este entorno. Si configuró varios conectores de Azure, puede seleccionar el conector que desea usar: **Este de EE. UU.**, **Este de EE. UU. 2**, **Oeste de EE. UU.** u **Oeste de EE. UU. 2**. (Para obtener el mejor rendimiento de extremo a extremo, le recomendamos que seleccione **Oeste de EE. UU. 2** .)

    ![Seleccionar la topología del entorno 2](./media/project3.png)

1. En la página **Implementar entorno**, escriba un nombre de entorno. Deje la configuración avanzada tal cual.

    ![Página Implementar entorno](./media/project4.png)

1. Ajuste el tamaño de la máquina virtual si es necesario. (Recomendamos la referencia de almacén de VM \[SKU\]**D13 v2**).
1. Revise los términos de precios y licencias y, a continuación, active la casilla para indicar que los acepta.
1. Seleccione **Siguiente**.
1. En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Implementar**. Volverá a la vista **Entornos hospedados en la nube** y su entorno debe aparecer en la lista.

    Su entorno solicitado se mostrará como en cola y, a continuación, en implementación. Los flujos de trabajo del entorno tardarán un tiempo en completarse. Por ello, vuelva a comprobarlo después de aproximadamente seis a nueve horas.

1. Antes de continuar, asegúrese de que el estado del entorno es **Implementado**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicializar la Commerce Scale Unit (nube)

Para inicializar CSU, siga estos pasos.

1. En la vista **Entornos hospedados en la nube**, seleccione el entorno en la lista.
1. En la vista del entorno a la derecha, seleccione **Detalles completos**. Aparecerá la vista de detalles del entorno.
1. En **Características del entorno**, seleccione **Administrar**.
1. En la pestaña **Commerce**, seleccione **Inicializar**. Aparece la vista de parámetros de inicialización de CSU.
1. En el campo **Región**, seleccione **Este de EE. UU.**, **Este de EE. UU. 2**, **Oeste de EE. UU.** u **Oeste de EE. UU. 2**.
1. En el campo **Versión**, seleccione **Especificar una versión** en la lista y luego especifique **9.18.20014.4** en el campo que aparece. Asegúrese de especificar la versión exacta que se indica aquí. De lo contrario, deberá actualizar RCSU a la versión correcta más adelante.
1. Active la opción **Aplicar extensión**.
1. En la lista de extensiones, seleccione **Extensión base de demostración de la vista previa de Commerce**.
1. Seleccione **Inicializar**.
1. En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Sí**. La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Commerce** está seleccionada. Su CSU ha estado en cola para aprovisionamiento.
1. Antes de continuar, asegúrese de que el estado del CSU es **Correcto**. La inicialización dura aproximadamente de dos a cinco horas.

### <a name="initialize-e-commerce"></a>Inicializar comercio electrónico

Para inicializar la plataforma de comercio electrónico, siga estos pasos.

1. En la pestaña **Comercio electrónico**, revise el consentimiento de vista previa y, a continuación, seleccione **Preparar**.
1. En el campo **Nombre de inquilino de comercio electrónico**, escriba un nombre. Sin embargo, tenga en cuenta que este nombre aparecerá en algunas de las direcciones URL que apuntan a su instancia de la plataforma de comercio electrónico.
1. En el campo **Nombre de Commerce Scale Unit**, seleccione su CSU en la lista. (La lista debe tener una sola opción).

    El campo **Geografía de comercio electrónico** se establece automáticamente y el valor no se puede cambiar.

1. Seleccione **Siguiente** para continuar.
1. En el campo **Nombres de hosts admitidos**, especifique cualquier dominio válido, como `www.fabrikam.com`.
1.  En el campo **Grupo de seguridad de AAD para administrador del sistema**, escriba las primeras letras del nombre del grupo de seguridad que desea usar. Seleccione el ícono de lupa para mostrar los resultados de la búsqueda. Seleccione un grupo de seguridad correcto en la lista.
2.  En el campo **Grupo de seguridad de AAD para moderadores de clasificaciones y opiniones**, escriba las primeras letras del nombre del grupo de seguridad que desea usar. Seleccione el ícono de lupa para mostrar los resultados de la búsqueda. Seleccione un grupo de seguridad correcto en la lista.
1. Mantenga activada la opción **Habilitar servicio de calificaciones y revisiones**.
1. Seleccione **Inicializar**. La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Comercio electrónico** está seleccionada. Comienza la inicialización del comercio electrónico.
1. Antes de continuar, espere hasta que el estado de inicialización de comercio electrónico sea **Inicialización correcta**.
1. En **Vínculos**, en la esquina inferior derecha, tome nota de las direcciones URL de los siguientes vínculos:

    * **Sitio de comercio electrónico**: el vínculo a la raíz de su sitio de comercio electrónico.
    * **Herramienta de administración del sitio de comercio electrónico**: el vínculo a la herramienta de administración del sitio.

## <a name="commerce-preview-environment-support"></a>Compatibilidad con el entorno de vista previa de Commerce

Si tuviera problemas al realizar los pasos de aprovisionamiento, visite el [grupo de Yammer de la vista previa de Microsoft Dynamics 365 Commerce](https://aka.ms/Dynamics365CommercePreviewYammer) para obtener ayuda.

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de aprovisionamiento y configurar su entorno de vista previa de Commerce, consulte [Configurar un entorno de vista previa de Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Recursos adicionales

[Información general del entorno de vista previa de Dynamics 365 Commerce](cpe-overview.md)

[Configurar un entorno de vista previa de Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar características opcionales para un entorno de vista previa de Dynamics 365 Commerce](cpe-optional-features.md)

[Preguntas frecuentes sobre el entorno de vista previa de Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (nube)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

