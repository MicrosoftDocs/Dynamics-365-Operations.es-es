---
title: Quitar entornos de Talent
description: Este tema recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: 904c8eb1254a65e1627c33f14488a1a8e12f7c2b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519029"
---
# <a name="remove-talent-environments"></a>Quitar entornos de Talent

[!include [banner](includes/banner.md)]

Este tema recorre con el usuario el proceso de eliminar una unidad de prueba o un entorno de producción para Microsoft Dynamics 365 for Talent.

## <a name="removing-a-test-drive-environment"></a>Quitar un entorno de unidad de prueba

Las unidades de prueba de Talent se aprovisionan con una directiva de caducidad de 60 días. Sin embargo, los propietarios de entornos de la prueba de conducción tienen la opción de finalizar la prueba antes siguiendo los pasos siguientes. 

1. Vaya al [Centro de administración de PowerApps](https://admin.businessplatform.microsoft.com/).
2. Seleccione **entornos**.
3. Seleccione el entorno de unidad de prueba, que tiene un patrón de denominación del tipo: TestDrive - alias@domain
4. Seleccione **Eliminar** y confirme la decisión. 

El entorno existente de la unidad de prueba se eliminará. Cuando se elimina, puede iniciar sesión en un nuevo entorno de unidad de prueba. 

## <a name="removing-a-production-environment"></a>Quitar un entorno de producción

Este tema asume que ha comprado Talent a un proveedor de soluciones de nube (CSP) o mediante un contrato de arquitectura empresarial (EA). 

Dado que un solo entorno de Talent está “contenido” dentro de un único entorno de PowerApps, hay dos opciones que deben tenerse en cuenta. La primera opción implica quitar todo el entorno de PowerApps; la segunda opción implica sólo quitar Talent. Se prefiere la primera opción cuando ha creado un entorno de PowerApps expresamente con el fin de aprovisionar Talent y que acaba de empezar la implementación, o no tiene ninguna integración establecida. La segunda opción es adecuada cuando tiene un entorno PowerApps establecido cumplimentado con datos enriquecidos que se optimizan en PowerApps y flujos.

> [!Important]
> Antes de eliminar el entorno de PowerApps, asegúrese de que no se está utilizando para integraciones de datos enriquecidos fuera del ámbito de Talent. Tenga también en cuenta que los entornos de PowerApps predeterminados no se pueden quitar. 

Para quitar el entorno completo de PowerApps, incluidos Talent y las aplicaciones y los flujos asociados:

1. Vaya al [Centro de administración de PowerApps](https://admin.businessplatform.microsoft.com/).
2. Seleccione **entornos**.
3. Seleccione el entorno que se van a eliminar.
4. Seleccione **Eliminar** y confirme la decisión. 
5. Espere hasta que se complete la eliminación.
6. Inicie sesión en [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) mediante la cuenta que ha utilizado para suscribirse a Talent. 
7. Seleccione el proyecto de Talent que contiene el entorno. 
8. En su proyecto de LCS seleccione el mosaico **Gestión de la app Talent**. 
9. Seleccione la instancia que desea quitar. 
10. Seleccione **Quitar instancia** y confirme la decisión.  

Para quitar un entorno de Talent de un entorno de PowerApps existente, complete estos pasos. Tenga en cuenta que la necesidad de incluir al soporte y de contactar al equipo de Talent DevOps es temporal hasta que esta característica se habilite directamente en el LCS.

1. Póngase en contacto con el soporte para iniciar una solicitud de eliminación.
2. El equipo de soporte iniciará una solicitud de eliminación con el equipo de Talent DevOps. 
3. Continúe tras recibir notificación de que se ha eliminado el entorno.
4.  Inicie sesión en LCS mediante la cuenta que ha utilizado para suscribirse a Talent. 
5. Seleccione el proyecto de Talent que contiene el entorno. 
6. En su proyecto de LCS seleccione el mosaico **Gestión de la app Talent**. 
7. Seleccione la instancia que desea quitar, que debe estar marcada con un estado de implementación **No superado**.
8. Seleccione **Quitar instancia** y confirme la decisión. 

