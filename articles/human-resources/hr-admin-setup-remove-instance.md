---
title: Quitar una instancia
description: Este artículo recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6f23adedc287b85018fe0b0af445677f6dc597c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889917"
---
# <a name="remove-an-instance"></a>Quitar una instancia

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Quitar un entorno de unidad de prueba

Las unidades de prueba de Human Resources se aprovisionan con una directiva de caducidad de 60 días. Sin embargo, los propietarios de entornos de la prueba de conducción tienen la opción de finalizar la prueba antes siguiendo los pasos siguientes. 

1. Ir al [Centro de administración de Power Apps](https://admin.businessplatform.microsoft.com/)
2. Seleccione **entornos**.
3. Seleccione el entorno de unidad de prueba, que tiene un patrón de denominación del tipo: TestDrive - alias@domain
4. Seleccione **Eliminar** y confirme la decisión. 

El entorno existente de la unidad de prueba se eliminará. Cuando se elimina, puede iniciar sesión en un nuevo entorno de unidad de prueba. 

## <a name="remove-a-production-environment"></a>Quitar un entorno de producción

Este artículo asume que ha comprado Human Resources a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). 

Dado que un solo entorno de Human Resources está “contenido” dentro de un único entorno de Power Apps, hay dos opciones que deben tenerse en cuenta. La primera opción implica quitar todo el entorno de Power Apps; la segunda opción implica sólo quitar Human Resources. Se prefiere la primera opción cuando ha creado un entorno de Power Apps expresamente con el fin de aprovisionar Human Resources y que acaba de empezar la implementación, o no tiene ninguna integración establecida. La segunda opción es adecuada cuando tiene un entorno Power Apps establecido cumplimentado con datos enriquecidos que se optimizan en Power Apps y Power Automate.

> [!Important]
> Antes de eliminar el entorno de Power Apps, asegúrese de que no se está utilizando para integraciones de datos enriquecidos fuera del ámbito de Human Resources. Tenga también en cuenta que los entornos de Power Apps predeterminados no se pueden quitar. 

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

Si elimina el entorno Power Apps al que está conectado su entorno de Human Resources el estado del entorno de Human Resources en Lifecycle Services será **Eliminado temporalmente**. En este caso, los usuarios no pueden conectarse a Human Resources.

Para restaurar el entorno:

1. Siga las instrucciones en [Recuperar el entorno de Power Apps](/power-platform/admin/recover-environment.md).

2. Póngase en contacto con el soporte técnico para restaurar el entorno de Human Resources. Para obtener más información, consulte [Obtener soporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Los entornos de Power Apps solo se guardan durante siete días después de la eliminación. Debe recuperar el entorno dentro de un período de siete días.


[!INCLUDE[footer-include](../includes/footer-banner.md)]