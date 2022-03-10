---
title: Crear entidades jurídicas
description: En este tema se describe cómo crear entidades jurídicas en Microsoft Dynamics 365 Commerce, que deben crearse y configurarse antes de crear canales.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: bc5f097a7f941dfa05f4011d9be5caffbb7f01b5f6e67cd7535ef3d1b13f59fe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740440"
---
# <a name="create-legal-entities"></a>Crear entidades jurídicas

[!include [banner](includes/banner.md)]

En este tema se describe cómo crear entidades jurídicas en Microsoft Dynamics 365 Commerce, que deben crearse y configurarse antes de crear canales.

Una entidad jurídica es una organización que tiene una estructura jurídicas registrada o legislada. Las entidades jurídicas pueden realizar contratos legales y tienen la obligación de preparar declaraciones para dar a conocer su rendimiento.

Una empresa en un tipo de entidad jurídica. Actualmente, las empresas son el único tipo de entidad jurídica que se puede crear y todas las entidades jurídicas están asociadas a un identificador de empresa. Esta asociación existe porque algunas áreas funcionales del programa usan un id. de empresa, o *DataAreaId*, en sus modelos de datos. En estas áreas funcionales, las empresas se usan como un límite para la seguridad de datos. Los usuarios sólo pueden acceder a los datos de la empresa en la que han iniciado sesión en ese momento. 

Al crear un canal debe especificar a qué entidad jurídica pertenece.

## <a name="create-a-new-legal-entity"></a>Crear una nueva entidad jurídica

Para crear una nueva entidad jurídica en Dynamics 365 Commerce, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Configuración de sede central \> Entidades jurídicas**.
1. En el panel de acciones, seleccione **Nueva**. El panel **Nueva entidad jurídica** aparece a la derecha.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Empresa**, escriba un valor.
1. En el campo **País o región**, especifique o seleccione un valor.
1. Seleccione **Aceptar**. 

   ![Creación de entidad jurídica.](media/legal-entities.png)

1. En la sección **General**, proporcione la siguiente información general sobre la entidad jurídica: 
   1. Especifique un nombre de búsqueda, si es necesario. Un nombre de búsqueda es un nombre alternativo que puede usarse para buscar esta entidad jurídica. 
   1. Seleccione si la entidad jurídica se usa como una empresa de consolidación.
   1. Seleccione si la entidad jurídica se usa como una empresa de eliminación. 
   1. Seleccione el **idioma predeterminado** de la entidad. 
   1. Seleccione la **zona horaria** para la entidad.
1. En la sección **Direcciones**, seleccione **Editar** para especificar la información de dirección, como la calle y el número, el código postal y la ciudad.
1. En la sección **Información de contacto**, especifique información sobre los métodos de comunicación, como direcciones de correo electrónico, URL y números de teléfono.
1. En la sección **Informes estatutarios**, especifique los números de registro que se usan para informes estatutarios.
1. En la sección **Números de registro**, especifique cualquier información requerida por la entidad jurídica.
1. En la sección **Información de cuenta bancaria**, especifique las cuentas bancarias y los números de enrutamiento para la entidad jurídica.
1. En la sección **Comercio exterior y logística**, especifique la información de envío para la entidad jurídica.
1. En la sección **Secuencias numéricas**, se pueden ver las secuencias numéricas asociadas a la entidad jurídica. Estará vacía para empezar.
1. En la sección **Imagen de panel de información**, vea o cambie el logotipo o la imagen del panel asociados a la entidad jurídica.
1. En la sección **Registro de impuestos**, especifique los números de registro que se usan para hacer declaraciones a las autoridades fiscales.
1. En la sección **IRPF**, especifique la información de IRPF de la entidad jurídica.
1. En la sección **Información fiscal** introduzca la información fiscal de la entidad jurídica.
1. Seleccione **Guardar**.

En la imagen siguiente se muestran los detalles de una entidad jurídica de ejemplo.

![Sección general de entidad jurídica.](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>Recursos adicionales

[Información general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planificación de su jerarquía organizativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Jerarquías organizativas](channels-org-hierarchies.md)

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
