---
title: Aprovisionar un entorno de espacio aislado de Dynamics 365 Commerce
description: Este artículo explica cómo aprovisionar un entorno de espacio aislado de Microsoft Dynamics 365 Commerce para demostración o uso del espacio aislado con datos de demostración integrados.
author: psimolin
ms.date: 06/14/2022
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
ms.openlocfilehash: 3ada30fc9d86d236b71d018ef77f2ae8573f2285
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013145"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Aprovisionar un entorno de espacio aislado de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artículo explica cómo aprovisionar un entorno de espacio aislado de Microsoft Dynamics 365 Commerce para demostración o uso del espacio aislado con datos de demostración integrados. El proceso para configurar un entorno de producción es similar, pero más elaborado, ya que muchos de los requisitos previos del entorno de espacio aislado ya se proporcionan en los datos de demostración.

Antes de comenzar, le recomendamos que lea rápidamente este artículo para tener una idea de lo que requiere el proceso.

Para aprovisionar correctamente un entorno de espacio aislado de Commerce, debe especificar algunos parámetros para el entorno y la Commerce Scale Unit (CSU) que se usarán cuando aprovisione Commerce más adelante. Las instrucciones de este artículo describen todos los pasos que son necesarios para completar el aprovisionamiento y los parámetros que debe usar.

Tras el aprovisionamiento correcto del entorno de Commerce, debe completar algunos pasos posteriores al aprovisionamiento a fin de prepararse para usarlo. Algunos pasos son opcionales, en función de los aspectos del sistema que desee utilizar. Siempre puede completar los pasos opcionales más adelante.

Para obtener información sobre cómo configurar su entorno de Commerce después de aprovisionarlo, consulte [Configurar un entorno de espacio aislado de Commerce](cpe-post-provisioning.md). Para obtener información sobre cómo configurar características opcionales para su entorno de Commerce, consulte [Configurar características opcionales para un entorno de espacio aislado de Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Requisitos previos

Deben cumplirse los siguientes requisitos previos para poder aprovisionar su entorno de Commerce:

- Tiene acceso al portal de Microsoft Dynamics Lifecycle Services (LCS).
- Usted es un socio o cliente de Microsoft Dynamics 365 y tiene un proyecto de implementación ya creado y disponible para usar en LCS.  
- Usted ha creado un grupo de seguridad de Azure Active Directory (Azure AD) que se puede utilizar como un grupo de administración del sistema Commerce y tiene su id. disponible
- Usted ha creado un grupo de seguridad de Azure AD que se puede utilizar como un grupo moderador de clasificaciones y revisiones y tiene su id. disponible. (Este grupo de seguridad puede ser el mismo que el grupo de administración del sistema de Commerce).
- Usted ha implementado una instancia de sede dentro de LCS. Para obtener más información, consulte [Implementar un nuevo entorno](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Tenga en cuenta que esta lista no es exhaustiva. Si tiene algún problema, póngase en contacto con su partner de Microsoft para obtener ayuda.

## <a name="provision-your-commerce-environment"></a>Aprovisionar su entorno de Commerce

Los siguientes procedimientos explican cómo aprovisionar un entorno de Commerce. Una vez completados correctamente los pasos, su entorno de Commerce estará listo para la configuración. Todos los pasos que se describen abajo tienen lugar en el portal de LCS.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inicializar la Commerce Scale Unit (nube)

Para inicializar la CSU, siga estos pasos.

1. En LCS, seleccione el entorno de la lista.
1. En la vista **ENTORNOS**, a la derecha, seleccione **Detalles completos**. Aparecerá la vista de detalles del entorno.
1. En la sección **Administrar entorno**, bajo **CARACTERÍSTICAS DEL ENTORNO**, seleccione **Administrar**.
1. En la pestaña **Commerce Scale Unit**, seleccione **Inicializar**. Aparecerá la vista **Agregar unidad de escalado**.
1. En el campo **REGIÓN**, seleccione la región que sea la misma que la región en la que implementó el entorno o que esté cerca de esta.
1. En la lista desplegable **Versión**, seleccione la última versión disponible.
1. Seleccione **Inicializar**.
1. En el cuadro de diálogo de advertencia que le pide que confirme la inicialización de Commerce Scale Unit, seleccione **Sí**. Ya se ha puesto CSU en cola para el aprovisionamiento.
1. Antes de continuar, asegúrese de que el estado de CSU sea **CORRECTO**. La inicialización dura aproximadamente de dos a cinco horas.

Si no puede encontrar el vínculo **Administrar** en la vista de detalles del entorno, póngase en contacto con su persona de contacto de Microsoft para obtener ayuda.

### <a name="initialize-e-commerce"></a>Inicializar comercio electrónico

Para inicializar Commerce, siga estos pasos.

1. En la pestaña **Comercio electrónico**, seleccione **Configuración**.
1. En el campo **Nombre de entorno de comercio electrónico**, escriba un nombre. Tenga en cuenta que este nombre aparecerá en algunas de las direcciones URL que apuntan a su instancia de la plataforma de comercio electrónico.
1. En el campo **Nombre de Commerce Scale Unit**, seleccione su CSU en la lista. (La lista debe tener una sola opción).

    El campo **Geografía de comercio electrónico** se establece automáticamente.

1. Seleccione **Siguiente** para continuar.
1. En el campo **Nombres de hosts admitidos**, especifique cualquier dominio válido, como `www.fabrikam.com`.
1. En el campo **Grupo de seguridad de AAD para administrador del sistema**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda. Seleccione un grupo de seguridad correcto en la lista.
1.  En el campo **Grupo de seguridad de AAD para moderadores de clasificaciones y opiniones**, introduzca las primeras letras del nombre del grupo de seguridad que desea usar y, a continuación, seleccione el símbolo de lupa para ver los resultados de la búsqueda. Seleccione un grupo de seguridad correcto en la lista.
1. Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.
1. Seleccione **Inicializar**. La vista **Administración de comercio electrónico** vuelve a aparecer, donde la pestaña **Comercio electrónico** está seleccionada. Comienza la inicialización del comercio electrónico.
1. Antes de continuar, espere hasta que el estado de inicialización de Commerce sea **INICIALIZACIÓN CORRECTA**.
1. En **Vínculos**, en la esquina inferior derecha, tome nota de las direcciones URL de los siguientes vínculos:

    * **Sitio de comercio electrónico**: el vínculo a la raíz de su sitio de comercio electrónico.
    * **Generador de sitios de Commerce**: el vínculo a la herramienta de administración del sitio.

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de aprovisionamiento y configurar su entorno Commerce, consulte [Configurar un entorno de espacio aislado de Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un entorno de espacio aislado de Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS en un entorno de espacio aislado de Dynamics 365 Commerce](cpe-bopis.md)

[Configurar características opcionales para un entorno de espacio aislado de Dynamics 365 Commerce](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (nube)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
