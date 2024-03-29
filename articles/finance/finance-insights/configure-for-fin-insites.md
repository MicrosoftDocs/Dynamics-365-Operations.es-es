---
title: Configuración de Finance Insights
description: Este artículo explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights.
author: ShivamPandey-msft
ms.date: 09/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 07edea234839a477802e5cd875620509c8f92d69
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644124"
---
# <a name="configuration-for-finance-insights"></a>Configuración de Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights combina la funcionalidad de Microsoft Dynamics 365 Finance con Dataverse, Azure y AI Builder para proporcionar potentes herramientas de pronóstico para su organización. Este artículo explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights. Para completar con éxito los procedimientos de este artículo, debe tener acceso de administrador del sistema y personalizador del sistema en el [Centro de administración de Power Portal](https://admin.powerplatform.microsoft.com/), acceso de Administrador del sistema en Dynamics 365 Finance y acceso para crear entornos en Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Los siguientes procedimientos para configurar Finance Insights son válidos para las versiones de Dynamics 365 Finance version 10.0.21 y posteriores.

## <a name="deploy-dynamics-365-finance"></a>Implementar Dynamics 365 Finance

Para implementar los entornos, siga estos pasos.

1. En LCS, cree o actualice un entorno de Dynamics 365 Finance. El entorno requiere una aplicación versión 10.0.21 o posterior.

    > [!NOTE]
    > El entorno debe ser un entorno de alta disponibilidad (HA). (Este tipo de entorno también se conoce como entorno de nivel 2). Para obtener más información, consulte [Planificación de entornos](/fin-ops-core/fin-ops/imp-lifecycle/environment-planning).

2. Si está configurando Finance Insights en un entorno de espacio aislado, es posible que deba copiar los datos de producción en ese entorno para que funcionen las predicciones. El modelo de predicción utiliza varios años de datos para generar predicciones. Los datos de la demostración de Contoso no contienen suficientes datos históricos para entrenar adecuadamente el modelo de predicción. 

## <a name="configure-your-azure-ad-tenant"></a>Configurar el inquilino de Azure AD

Azure Active Directory (Azure AD) debe configurarse para que se pueda utilizar con Dataverse y las aplicaciones de Microsoft Power Platform. Esta configuración requiere la asignación del rol **Propietario del proyecto** o **Administrador del entorno** al usuario en el campo **Rol de seguridad del proyecto** en LCS.

Verifique que se complete la siguiente configuración:

- Usted tiene acceso de **Administrador de sistema** y **Personalizador del sistema** en el Centro de administración de Power Portal.
- Se aplica una licencia de Dynamics 365 Finance o equivalente al usuario que está instalando el complemento Finance Insights.
- Las siguientes aplicaciones de Azure AD están registradas en Azure AD.

    |  Aplicación                             | Id. de aplicación                               |
    |------------------------------------------|--------------------------------------|
    | CDS de microservicios de Microsoft Dynamics ERP | 703e2651-d3fc-48f5-942c-74274233dba8 |

    Para verificar que la aplicación está registrada en Azure AD, compruebe la lista **Todas las aplicaciones**. Para más detalles, consulte [Ver aplicaciones empresariales](/azure/active-directory/manage-apps/view-applications-portal).
  
    Si la aplicación no está registrada en Azure AD, contacte con soporte.
  
## <a name="configure-dataverse"></a>Configurar Dataverse

Siga estos pasos para configurar Dataverse para Finance Insights.

- En LCS, abra la página del entorno y verifique que la sección **Integración de Power Platform** ya está configurada.

    - Si Dataverse ya se ha configurado, el nombre del entorno de Dataverse vinculado al entorno de Finance debe enumerarse.
    - Si aún no se ha configurado Dataverse, seleccione **Configuración**. La configuración del entorno Dataverse puede tardar hasta una hora. Cuando termine la configuración, el entorno de Dataverse vinculado al entorno de Finance deberá mostrarse.
    - Si esta integración se configuró con un entorno de Microsoft Power Platform, póngase en contacto con su administrador para asegurarse de que el entorno vinculado no está en el estado deshabilitado.

        Para obtener más información, consulte la sección [Habilitar la integración de Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md). 

        Para acceder al sitio de administración de Microsoft Power Platform, vaya a <https://admin.powerplatform.microsoft.com/environments>.

## <a name="configure-the-finance-insights-add-in"></a>Configurar el complemento Finance Insights

Si instaló anteriormente el complemento Finance Insights, desinstálelo antes de completar el siguiente procedimiento.

> [!NOTE]
> Si ya instaló el complemento data lake en LCS, Finance Insights lo usará para guardar los datos necesarios para las predicciones. Si aún no ha instalado el complemento de data lake en LCS, el complemento de Finance Insights creará un data lake administrado para usted.

Siga estos pasos para instalar el complemento Finance Insights.

1. Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.
2. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
3. Seleccione el complemento **Finance Insights**.
4. Acepte los términos y condiciones, y luego seleccione **Instalar**.

El complemento puede tardar varios minutos en instalarse.

## <a name="one-last-thing"></a>Una última cosa...

Una vez que el complemento se haya instalado correctamente, puede que tarde hasta una hora antes de que pueda habilitar las características de Finance Insights en el espacio de trabajo **Administración de características** en Dynamics 365 Finance. Si no desea esperar tanto, puede ejecutar manualmente el proceso **Comprobación del estado de aprovisionamiento de conclusiones**. 

1. En Dynamics 365 Finance, vaya a **Administración del sistema \> Configuración \> Automatización de procesos**.
2. En la pestaña **Procesos en segundo plano**, busque **Comprobación del estado de aprovisionamiento de conclusiones** y seleccione **Editar**.
3. Establezca el campo **Próxima ejecución** en 30 minutos antes de la hora actual.

   Este cambio debería forzar la ejecución inmediata del proceso **Comprobación del estado de aprovisionamiento de conclusiones**.

   Después de la ejecución correcta de **Comprobación del estado de aprovisionamiento de conclusiones** puede habilitar las funciones de Finance Insights en el espacio de trabajo **Administración de características**.

> [!NOTE]
> Si no se ejecuta el proceso **Comprobación del estado de aprovisionamiento de conclusiones**, vaya a **Administración del sistema** > **Consultas** > **Trabajos por lotes**. En el campo **Sistema de sondeo de automatización de procesos**, cambie el valor a **Espera** para iniciar el proceso. 
> 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
