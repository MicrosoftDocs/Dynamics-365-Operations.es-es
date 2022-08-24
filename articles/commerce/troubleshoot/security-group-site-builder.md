---
title: No se puede configurar un grupo de seguridad para el creador de sitios de Commerce durante la implementación inicial
description: Este artículo proporciona una guía de solución de problemas que puede ayudar cuando el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) para el creador de sitios de Commerce no aparece como una opción al crear componentes de comercio electrónico en Microsoft Dynamics Lifecycle Services (LCS) durante la implementación inicial de un nuevo inquilino de comercio electrónico.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 7098c853c262fd7e0d48231634b232eef71c2b8d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292010"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>No se puede configurar un grupo de seguridad para el creador de sitios de Commerce durante la implementación inicial

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía de solución de problemas que puede ayudar cuando el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) para el creador de sitios de Commerce no aparece como una opción al crear componentes de comercio electrónico en Microsoft Dynamics Lifecycle Services (LCS) durante la implementación inicial de un nuevo inquilino de comercio electrónico.

## <a name="description"></a>Descripción

Cuando crea los componentes de comercio electrónico como parte del proceso de implementación de un nuevo inquilino de comercio electrónico que incluye el componente de creación de sitios de Commerce, el grupo de seguridad de Azure AD no aparece como opción en el cuadro de diálogo.

## <a name="resolution"></a>Resolución

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Aprovisionar el sitio de comercio electrónico con un usuario en el inquilino correcto

1. Vaya a [Azure Portal](https://portal.azure.com/).
1. En el inquilino para el que se aprovisionó el proyecto LCS para su sitio de comercio electrónico, siga las instrucciones en [Crear un grupo básico y agregar miembros usando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Vaya a [LCS](https://lcs.dynamics.com/) e inicie sesión con una cuenta que comparta el mismo inquilino que el grupo de seguridad de Azure AD que acaba de crear. La cuenta debe tener acceso para ver el grupo de seguridad de Azure AD.
1. Complete los pasos de configuración para configurar el sitio de comercio electrónico. Cuando aprovisiona los componentes de comercio electrónico, el grupo de seguridad ahora debería aparecer como una opción en el cuadro de diálogo.

> [!NOTE]
> Para asegurarse de que el campo del cuadro de diálogo se rellene con la lista de grupos de seguridad, debe seleccionar **Entrar** después de introducir el nombre del grupo de seguridad de Azure AD que creó. Los resultados de la búsqueda enumerarán todos los grupos de seguridad de Azure AD que comienzan con el texto de búsqueda y a los que el usuario tiene acceso. Puede utilizar un término de búsqueda más corto para permitir resultados de búsqueda más amplios.

## <a name="additional-resources"></a>Recursos adicionales

[Crear un grupo básico y agregar miembros usando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Implementar un inquilino nuevo de comercio electrónico](../deploy-ecommerce-site.md)
