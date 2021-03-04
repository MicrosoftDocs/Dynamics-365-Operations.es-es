---
title: Importar usuarios de Azure Active Directory
description: Este procedimiento se puede utilizar por administradores del sistema para importar manualmente usuarios seleccionados o para importar a un gran número de usuarios desde Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679823"
---
# <a name="import-users-from-azure-active-directory"></a>Importar usuarios de Azure Active Directory

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Importar usuarios seleccionados

Este procedimiento se puede utilizar por administradores del sistema para importar usuarios seleccionados desde Azure Active Directory (Azure AD).

1. El usuario se importará con la empresa de la sesión actual como empresa predeterminada. Cambie la compañía actual si corresponde antes de importar usuarios.
2. Vaya a **Administración del sistema > Usuarios > Usuarios**.
3. Haga clic en **Importar usuarios**.
4. Seleccione los usuarios que se deben importar y seleccione **Importar usuarios**.

Una vez completada la importación, será necesario asignar roles a los usuarios.

## <a name="import-users-in-bulk"></a>Importar usuarios en grandes cantidades

Este procedimiento se puede utilizar por administradores del sistema para importar a un gran número de usuarios desde Azure Active Directory.
Tenga en cuenta que no es posible seleccionar usuarios cuando se utiliza la opción de importación por lotes.

## <a name="run-the-import-as-a-batch-job"></a>Ejecute la importación como un trabajo por lotes
1. El usuario se importará con la empresa de la sesión actual como empresa predeterminada. Cambie la compañía actual si corresponde antes de importar usuarios.
2. Vaya a **Administración del sistema > Usuarios > Usuarios**.
3. Haga clic en **Importación por lotes**.
4. Expanda la sección **Ejecutar en segundo plano**.
4. Seleccione **Sí en el campo **Procesamiento por lotes**.
6. En el campo **Grupo de lotes**, especifique o seleccione un valor. Este paso es opcional.  
7. Seleccione **Sí** en el campo **Privado**. Este paso es opcional.  
8. Seleccione **Sí** en el campo **Trabajo crítico**. Este paso es opcional.  
9. En el campo **Categoría de supervisión, seleccione una opción.
10. Haga clic en **Aceptar**.

Una vez completada la importación, será necesario asignar roles a los usuarios.

## <a name="run-in-a-sandbox-environment"></a>Ejecutar un entorno de espacio aislado
1. Seleccione **Importación por lotes**.
2. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]