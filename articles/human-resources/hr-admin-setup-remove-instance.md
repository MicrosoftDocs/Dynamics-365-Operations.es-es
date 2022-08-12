---
title: Quitar una instancia
description: En este artículo se explica el proceso de quitar una versión de prueba o un entorno de producción de Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ce676c93e133cc04ad9c49417ed2ca0d6791e93
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178484"
---
# <a name="remove-an-instance"></a>Quitar una instancia

_**Se aplica a:** Recursos humanos en la infraestructura independiente_ 

> [!NOTE]
> A partir de julio de 2022, los nuevos entornos de Human Resources no se pueden aprovisionar en la infraestructura de Human Resources independiente y los nuevos proyectos de Microsoft Dynamics Lifecycle Services (LCS) no se pueden crear en ella. Los clientes pueden desplegar entornos de Human Resources en la infraestructura de finanzas y operaciones. Para más información, vea [Aprovisionamiento de Human Resources en la infraestructura de finanzas y operaciones](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> La infraestructura de aplicaciones de finanzas y operaciones admite la eliminación de un entorno. Para obtener más información sobre cómo eliminar un entorno, vea [Eliminar un entorno](../fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure.md#delete-an-environment).

En este artículo se explica el proceso de quitar una versión de prueba o un entorno de producción de Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Quitar un entorno de unidad de prueba

Las unidades de prueba de Human Resources se aprovisionan con una directiva de caducidad de 60 días. Sin embargo, los propietarios de entornos de la prueba de conducción tienen la opción de finalizar la prueba antes siguiendo los pasos siguientes. 

1. Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)
2. Seleccione **entornos**.
3. Seleccione el entorno de unidad de prueba, que tiene un patrón de denominación del tipo: TestDrive - alias@domain
4. Seleccione **Eliminar** y confirme la decisión. 

El entorno existente de la unidad de prueba se eliminará. Cuando se elimina, puede iniciar sesión en un nuevo entorno de unidad de prueba. 

## <a name="remove-a-production-environment"></a>Quitar un entorno de producción

Este artículo asume que ha comprado Human Resources a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). 

Dado que un solo entorno de Human Resources está “contenido” en un único entorno de Power Apps, hay dos opciones que deben tenerse en cuenta al eliminar un entorno: 
- **Quitar todo el entorno de Power Apps.** Se prefiere esta opción cuando se ha creado el entorno de Power Apps con el fin de aprovisionar Human Resources, acaba de empezar la implementación o no tiene ninguna integración establecida.  
- **Quitar solo Human Resources.** Esta opción es adecuada cuando hay un entorno de Power Apps establecido cumplimentado con datos enriquecidos que se utilizan en Microsoft Power Apps y Power Automate.


> [!Important]
> Antes de eliminar el entorno de Power Apps, asegúrese de que no se está utilizando para integraciones de datos fuera del ámbito de Human Resources. Tenga también en cuenta que los entornos de Power Apps predeterminados no se pueden quitar. 

Para quitar el entorno completo de Power Apps, incluidos Human Resources y las aplicaciones y los flujos asociados:

1. Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)
2. Seleccione **entornos**.
3. Seleccione el entorno que se van a eliminar.
4. Seleccione **Eliminar** y confirme la decisión. 
5. Espere hasta que se complete la eliminación.
6. Inicie sesión en [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) mediante la cuenta que ha utilizado para suscribirse a Human Resources. 
7. Seleccione el proyecto de Human Resources que contiene el entorno. 
8. En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**. 
9. Seleccione la instancia que desea quitar. 
10. Seleccione **Quitar instancia** y confirme la decisión.  

Para quitar un entorno de Human Resources de un entorno de Power Apps existente, complete estos pasos. Tenga en cuenta que la necesidad de incluir al soporte y de contactar al equipo de Human Resources DevOps es temporal hasta que esta característica se habilite directamente en el LCS.

1. Póngase en contacto con el soporte para iniciar una solicitud de eliminación.
2. El equipo de soporte iniciará una solicitud de eliminación con el equipo de Human Resources DevOps. 
3. Continúe tras recibir notificación de que se ha eliminado el entorno.
4. Inicie sesión en LCS mediante la cuenta que ha utilizado para suscribirse a Human Resources. 
5. Seleccione el proyecto de Human Resources que contiene el entorno. 
6. En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**. 
7. Seleccione la instancia que desea quitar, que debe estar marcada con el estado de implementación **Eliminada**.
8. Seleccione **Quitar instancia** y confirme la decisión. 

## <a name="recover-a-soft-deleted-environment"></a>Recuperar un entorno eliminado temporalmente

Si elimina el entorno Power Apps al que está conectado su entorno de Human Resources el estado del entorno de Human Resources en LCS será **Eliminado temporalmente**. En este caso, los usuarios no pueden conectarse a Human Resources.

Para restaurar el entorno:

1. Siga las instrucciones en [Recuperar el entorno de Power Apps](/power-platform/admin/recover-environment).

2. Póngase en contacto con el soporte técnico para restaurar el entorno de Human Resources. Para obtener más información, consulte [Obtener soporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Los entornos de Power Apps solo se guardan durante siete días después de la eliminación. Debe recuperar el entorno dentro de un período de siete días.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
