---
title: Seguridad de usuario del portal de proveedores
description: "Este artículo explica cómo configurar la seguridad para proveedores externos que usan el Portal de proveedor. Esta información solo se aplica a las versiones &amp; de febrero de 2016 en mayo de 2016 de las Dynamics AX."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 3a5c6a256f8330ba238ea3c0c25f14b10a9a58e6
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-portal-user-security"></a>Seguridad de usuario del portal de proveedores

Este artículo explica cómo configurar la seguridad para proveedores externos que usan el Portal de proveedor. Esta información solo se aplica a las versiones &amp; de febrero de 2016 en mayo de 2016 de las Dynamics AX.

La funcionalidad del portal de proveedores se ha sustituido por la funcionalidad extendida de colaboración del proveedor en Dynamics 365 para la versión 1611 de las operaciones. Para obtener más información acerca de la seguridad de la configuración de la colaboración de proveedor, vea [la configuración y mantiene la colaboración] del proveedor (setup-maintain-vendor-collaboration.md). El portal de proveedores expone un sistema limitado de información acerca de los pedidos de compra a los proveedores externos. Es importante configurar correctamente los permisos de usuario del portal de proveedores en Microsoft Dynamics AX, de modo que los proveedores no tengan acceso involuntario a información adicional en la instalación de Dynamics AX. **Importante:** a diferencia de otros usuarios, los proveedores externos no deben tener el rol de **SystemUser**. El rol de **SystemUser** concede acceso a un conjunto de privilegios que no son convenientes para los usuarios externos.

## <a name="setting-up-a-vendor-portal-user"></a>Configuración de un usuario del portal de proveedores
Antes de crear una cuenta de usuario para alguien que utilizará el portal de proveedores, debe configurar el proveedor para que pueda colaborar con el portal de proveedores. Use el campo **Colaboración del pedido de compra** en la pestaña **General** en la página **Proveedores**. Los proveedores externos que usan el portal de proveedores deben tener la configuración siguiente:

-   Una cuenta de usuario de azul de Microsoft Azure Active Directory (AAD) se debe registrar para el proveedor en la página **Usuarios** de Dynamics AX.
-   El proveedor debe tener el rol de seguridad **Proveedor (externo)**, no el rol de **SystemUser **. **Nota:** el rol **SystemUser** se concede automáticamente cuando se crea una nueva cuenta de usuario en Dynamics AX. Por lo tanto, debe quitar dicho rol y reconocer el mensaje de advertencia que reciba.
-   Al usuario proveedor no se le debe conceder permiso para agregar campos adicionales de las tablas de PO para la vista de PO. En la pestaña **Personalización**, en la pestaña **Usuarios**, defina la opción **Personalización explícita permitida** para el usuario en **No**.
-   La cuenta de usuario se debe asociar con una persona de contacto registrada. En la página **Usuarios**, seleccione una persona de contacto en el campo **Nombre**. La persona que seleccione debe tener el rol de **Contacto** para el proveedor correspondiente.

Si la misma persona requiere el acceso al portal de proveedores para varias cuentas de proveedor (para distintas entidades jurídicas, quizás), cada una de las cuentas de usuario de dicha persona debe estar asociada a la misma persona de contacto registrada. El rol de **Proveedor (externo)** incluye todas las capacidades básicas que se requieren para usar la funcionalidad que está disponible en el portal de proveedores. Esta configuración ayuda a garantizar que la interfaz de usuario que el usuario externo verá está centrada únicamente en la situación planificada.

<a name="see-also"></a>Consulte también
--------

[Vendor collaboration](collaborate-vendors-vendor-portal.md)


