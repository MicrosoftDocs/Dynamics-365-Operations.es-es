---
title: Aprovisionar un entorno de evaluación de Dynamics 365 Commerce
description: En este tema se explica cómo aprovisionar un entorno de evaluación de Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8b288a0d6b7516faf635486fbaad885344d2cc6f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352093"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Aprovisionar un entorno de evaluación de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

En este tema se explica cómo aprovisionar un entorno de evaluación de Microsoft Dynamics 365 Commerce.

Antes de comenzar, le recomendamos que lea rápidamente este tema para tener una idea de lo que requiere el proceso.

> [!NOTE]
> Los entornos de evaluación de Commerce no suelen estar disponibles y se conceden a socios y clientes por solicitud. Para obtener más información, póngase en contacto con su partner de Microsoft.

Para aprovisionar correctamente un entorno de evaluación de Commerce, debe crear un proyecto que tenga un nombre y tipo de producto específicos. El entorno y Commerce Scale Unit (CSU) también tienen algunos parámetros específicos que necesita usar posteriormente cuando prevea el aprovisionamiento de comercio electrónico. Las instrucciones de este tema describen todos los pasos que son necesarios para completar el aprovisionamiento y los parámetros que debe usar.

Tras el aprovisionamiento correcto del entorno de evaluación de Commerce, debe completar algunos pasos posteriores al aprovisionamiento a fin de prepararse para usarlo. Algunos pasos son opcionales, en función de los aspectos del sistema que desee evaluar. Siempre puede completar los pasos opcionales más adelante.

Para obtener información sobre cómo configurar su entorno de evaluación de Commerce después de aprovisionarlo, consulte [Configurar un entorno de evaluación de Commerce](cpe-post-provisioning.md). Para obtener información sobre cómo configurar características opcionales para su entorno de evaluación de Commerce, consulte [Configurar características opcionales para un entorno de evaluación de Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Requisitos previos

Deben cumplirse los siguientes requisitos previos para poder aprovisionar su entorno de evaluación de Commerce:

- Se le ha incorporado al programa de evaluación y se le ha otorgado la capacidad para un entorno de evaluación.
- Tiene acceso al portal de Microsoft Dynamics Lifecycle Services (LCS).
- Usted es un socio o cliente de Microsoft Dynamics 365 existente y puede crear un proyecto de Dynamics 365 Commerce.
- Tiene acceso de administrador a su suscripción de Microsoft Azure o está en contacto con un administrador de suscripción que puede ayudarlo si es necesario.
- Tiene su id. de suscriptor de Azure Active Directory (Azure AD) disponible.
- Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo de administración del sistema de comercio electrónico y tiene su id. disponible
- Ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo moderador de Clasificaciones y revisiones y tiene su id. disponible. (Este grupo de seguridad puede ser el mismo que el grupo de administración del sistema de comercio electrónico).

Tenga en cuenta que esta lista no es exhaustiva. Si tiene algún problema, póngase en contacto con su partner de Microsoft para obtener ayuda.

## <a name="provision-your-commerce-evaluation-environment"></a>Aprovisionar su entorno de evaluación de Commerce

Estos procedimientos explican cómo aprovisionar un entorno de evaluación de Commerce. Una vez completados correctamente, el entorno de evaluación de Commerce estará listo para la configuración. Todas las actividades que se describen aquí tienen lugar en el portal de LCS.

### <a name="create-a-new-project"></a>Crear un proyecto nuevo

Para crear un proyecto nuevo en LCS, siga estos pasos.

1. En la página de inicio de LCS, seleccione el signo más (**+**) para crear un proyecto.
1. En el panel derecho, siga uno de estos pasos:

    - Si es un partner, seleccione **Migrar, crear soluciones y obtener información sobre**.
    - Si es cliente, seleccione **Preventa de cliente potencial**.

1. Escriba un nombre, una descripción y un sector.
1. En el campo **Nombre del producto**, seleccione **Dynamics 365 Commerce**.
1. En el campo **Versión del producto**, seleccione **Dynamics 365 Commerce**.
1. En el campo **Metodología**, seleccione **Metodología de implementación de Dynamics Retail**.
1. Opcional: puede importar roles y usuarios de un proyecto existente.
1. Seleccione **Crear**. Aparece la vista del proyecto.

### <a name="add-the-azure-connector"></a>Agregar el conector de Azure

Para agregar Azure Connector a su proyecto LCS, siga los pasos en [Completar el proceso de incorporación de Azure Resource Manager (ARM)](../fin-ops-core/dev-itpro/deployment/arm-onboarding.md).

### <a name="deploy-the-environment"></a>Implementar el entorno

Para implementar el entorno, siga estos pasos.

> [!NOTE]
> Es posible que no tenga que completar los pasos 6, 7 u 8, ya que las páginas que tienen una sola opción se omiten. Cuando está en la vista **Parámetros del entorno**, confirme que el texto **Dynamics 365 Commerce - Demostración (10.0.* x* con Platform update *xx*)** aparece directamente encima del campo **Nombre del entorno**. Para obtener detalles, consulte la ilustración que aparece después del paso 8.

1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Seleccione **Agregar** para agregar un entorno.
1. En el campo **Versión de la aplicación**, seleccione la versión más actual. Si tiene una necesidad específica de seleccionar una versión de la aplicación que no sea la versión más actual, no seleccione una versión anterior a **10.0.14**.
1. En el campo **Versión de la plataforma**, use la versión de plataforma que se elige automáticamente para la versión de la aplicación que ha seleccionado. 

    ![Seleccionar las versiones de la aplicación y la plataforma.](./media/project1.png)

1. Seleccione **Siguiente**.
1. Seleccione **Demostración** como topología del entorno.

    ![Seleccionar la topología del entorno 1.](./media/project2.png)

1. En la página **Implementar entorno**, escriba un nombre de entorno. Deje la configuración avanzada tal cual.

    ![Página Implementar entorno.](./media/project4.png)

1. Ajuste el tamaño de la máquina virtual si es necesario. (Recomendamos la referencia de almacén de VM \[SKU\]**D13 v2**).
1. Revise los términos de precios y licencias y, a continuación, active la casilla para indicar que los acepta.
1. Seleccione **Siguiente**.
1. En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Implementar**. Volverá a la vista **Entornos hospedados en la nube** y su entorno debe aparecer en la lista.

    Su entorno solicitado se mostrará como en cola y, a continuación, en implementación. Los flujos de trabajo del entorno tardarán un tiempo en completarse. Por ello, vuelva a comprobarlo después de aproximadamente seis a nueve horas.

1. Antes de continuar, asegúrese de que el estado del entorno es **Implementado**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicializar la Commerce Scale Unit (nube)

Para inicializar la CSU, siga estos pasos.

1. En la vista **Entornos hospedados en la nube**, seleccione el entorno en la lista.
1. En la vista del entorno a la derecha, seleccione **Detalles completos**. Aparecerá la vista de detalles del entorno.
1. En **Características del entorno**, seleccione **Administrar**.
1. En la pestaña **Commerce**, seleccione **Inicializar**. Aparece la vista de parámetros de inicialización de CSU.
1. En el campo **Región**, seleccione la región que es la misma o cercana a la región en la que implementó el entorno.
1. Deje el campo **Versión** tal cual.
1. Seleccione **Inicializar**.
1. En la pantalla de confirmación de la implementación, compruebe que los detalles sean correctos y haga clic en **Sí**. La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Commerce** está seleccionada. Su CSU ha estado en cola para aprovisionamiento.
1. Antes de continuar, asegúrese de que el estado del CSU es **Correcto**. La inicialización dura aproximadamente de dos a cinco horas.

Si no puede encontrar el vínculo **Administrar** en la vista de detalles del entorno, póngase en contacto con su persona de contacto de Microsoft para obtener ayuda.

Durante el proceso de implementación puede aparecer el siguiente mensaje de error:

> Los entornos de evaluación (demostración/prueba) deben registrar la aplicación de conector de unidad de escalado \<application ID\> en la sede central.

En caso de error de inicialización de la CSU con este mensaje de error, anote el id. de la aplicación, que es un identificador único global (GUID), y siga los pasos de la siguiente sección para registrar la aplicación de implementación de CSU en la sede central de Commerce.

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a>Registrar la aplicación de implementación de CSU en la sede central de Commerce (si es necesario)

Para registrar la aplicación de implementación de CSU en la sede central de Commerce, siga estos pasos.

1. En la sede central de Commerce, vaya a **Administración del sistema \> Configuración \> Aplicaciones de Azure Active Directory**.
1. En la columna **Id. de cliente**, introduzca el id. de aplicación del mensaje de error de inicialización de CSU que ha recibido.
1. En la columna **Nombre**, escriba texto descriptivo (por ejemplo, **Evaluación de CSU**).
1. En la columna **Id. de usuario**, escriba **RetailServiceAccount**.
1. Vuelva a intentar la inicialización y la implementación de CSU desde LCS.

### <a name="initialize-e-commerce"></a>Inicializar comercio electrónico

Para inicializar la plataforma de comercio electrónico, siga estos pasos.

1. En la pestaña **Comercio electrónico**, revise el consentimiento de evaluación y, a continuación, seleccione **Configuración**.
1. En el campo **Nombre de entorno de comercio electrónico**, escriba un nombre. Tenga en cuenta que este nombre aparecerá en algunas de las direcciones URL que apuntan a su instancia de la plataforma de comercio electrónico.
1. En el campo **Nombre de Commerce Scale Unit**, seleccione su CSU en la lista. (La lista debe tener una sola opción).

    El campo **Geografía de comercio electrónico** se establece automáticamente.

1. Seleccione **Siguiente** para continuar.
1. En el campo **Nombres de hosts admitidos**, especifique cualquier dominio válido, como `www.fabrikam.com`.
1. En el campo **Grupo de seguridad de AAD para administrador del sistema**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda. Seleccione un grupo de seguridad correcto en la lista.
1.  En el campo **Grupo de seguridad de AAD para moderadores de clasificaciones y opiniones**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda. Seleccione un grupo de seguridad correcto en la lista.
1. Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.
1. Seleccione **Inicializar**. La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Comercio electrónico** está seleccionada. Comienza la inicialización del comercio electrónico.
1. Antes de continuar, espere hasta que el estado de inicialización de comercio electrónico sea **Inicialización correcta**.
1. En **Vínculos**, en la esquina inferior derecha, tome nota de las direcciones URL de los siguientes vínculos:

    * **Sitio de comercio electrónico**: el vínculo a la raíz de su sitio de comercio electrónico.
    * **Generador de sitios de Commerce**: el vínculo a la herramienta de administración del sitio.

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de aprovisionamiento y configurar su entorno de evaluación de Commerce, consulte [Configurar un entorno de evaluación de Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Recursos adicionales

[Información general del entorno de evaluación de Dynamics 365 Commerce](cpe-overview.md)

[Configurar un entorno de evaluación de Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce](cpe-bopis.md)

[Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce](cpe-optional-features.md)

[Preguntas más frecuentes sobre el entorno de evaluación Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (nube)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]