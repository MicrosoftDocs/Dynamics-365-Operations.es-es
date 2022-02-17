---
title: Configurar la aplicación móvil Warehouse Management para unidades de escalado en el perímetro y en la nube.
description: Este tema explica cómo configurar sus aplicaciones móviles Warehouse Management para almacenes que son atendidos por una unidad de escala en la nube o perimetral.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 1fa00b40db2f6246029876964dca9d3229567848
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071662"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Configurar la aplicación móvil Warehouse Management para unidades de escalado en el perímetro y en la nube.

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar sus aplicaciones móviles de Warehouse Management de modo que se puedan usar en almacenes que son atendidos por una unidad de escala en la nube o perimetral.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar a configurar sus dispositivos móviles para conectarse a una unidad de escala de borde o en la nube, confirme que pueden conectarse al centro empresarial. Para obtener instrucciones, consulte [Instale y conecte la aplicación móvil Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Configuración adicional cuando ejecuta la aplicación móvil Warehouse Management en una unidad de báscula

Como parte del [proceso de implementación para cargas de trabajo de unidades a escala de almacén](cloud-edge-landing-page.md#scale-unit-manager-portal), la mayoría de los datos necesarios para conectar los dispositivos de la aplicación móvil Warehouse Management se sincronizan automáticamente desde el centro empresarial a la unidad de escalado. Sin embargo, debe ingresar los datos en la paǵina **Aplicaciones de Azure Active Directory** (**Administracion del sistema \> Configuración \> Aplicaciones de Azure Active Directory**) en el despliegue de la unidad de escala. Además, es posible que deba actualizar el valor predeterminado **Compañía** para el ID de usuario o crear un nuevo usuario. Los usuarios que están asociados con una empresa que no existe en una implementación de unidad de escala no podrán iniciar sesión cuando la aplicación móvil Warehouse Management esté conectada a esa unidad de escala.

> [!NOTE]
> Porque los datos de la paǵina **Aplicaciones de Azure Active Directory** no está sincronizada, debe mantener manualmente estos datos si desea mover las cargas de trabajo de su almacén a otra unidad de escala.

Recuerde que, como parte de la configuración de la conexión de cada aplicación móvil Warehouse Management, la URL de recurso de Azure Active Directory especificada debe ser para la unidad de escalado en lugar del centro empresarial.
