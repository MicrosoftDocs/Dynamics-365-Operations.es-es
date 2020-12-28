---
title: El usuario no puede encontrar en el selector de personas en Attract u Onboard
description: Este tema explica qué hacer cuando los usuarios en la compañía arrendataria no aparecen en el selector de personas en Dynamics 365 Talent - Attract u Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a6d916f87ca30aa7405a51841e56ab31bbe31ac8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462516"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a>El usuario no puede encontrar en el selector de personas en Attract u Onboard

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Emisión

Algunos usuarios válidos en Microsoft Azure Active Directory (Azure AD) para el arrendatario no aparecen al buscar el nombre en el selector de personas en las aplicaciones Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard.

## <a name="cause"></a>Causa

Determinados tipos de usuario no se admiten actualmente en Attract u Onboard. Compruebe que el usuario no sea un usuario invitado de Azure AD Business to Business (B2B). La información del "tipo de usuario” se puede encontrar en la sección Azure Active Directory en el portal de Azure.

Para obtener más información sobre Azure B2B, consulte [Qué es acceso de usuario invitado en Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

Para los usuarios de no-B2B, hay algunos usuarios que pueden tener una propiedad "Tipo de usuario" incompleta en el objeto **Usuario**. Esto se puede comprobar y corregir a través del módulo Azure AD Powershell. Para obtener más información, vea [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Resolución

Para completar los pasos siguientes y resolver el problema, deberá disponer de permisos "Administrador global” en el arrendatario de Azure Active Directory o permisos para **User.ReadWrite.All**.

Para comprobar el "Tipo de usuario" para el usuario afectado.

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
El comando devuelve la siguiente información.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Tenga en cuenta la propiedad **UserType** en el usuario. Si **UserType** está en blanco, por ejemplo no "Miembro “o “Invitado,” actualice **UserType** mediante el comando siguiente.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
