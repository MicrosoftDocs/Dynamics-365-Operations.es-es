---
title: Concesiones del proyecto
description: Este tema explica cómo crear o modificar una concesión.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282848"
---
# <a name="project-grants"></a>Concesiones del proyecto

[!include [banner](../includes/banner.md)]

Una concesión es una dotación económica para un propósito o proyecto específico. Normalmente, existen restricciones sobre la forma de gastarla. En Gestión y contabilidad de proyectos, puede especificar y realizar un seguimiento de las concesiones y definir sus relaciones con los proyectos y contratos de proyecto. Por ejemplo, puede realizar las tareas siguientes:

- Asocie concesiones a proyectos y fuentes de financiación a través de enlaces a las páginas de **Proyecto** y **Detalles del contrato del proyecto**.
- Especificar y realizar un seguimiento de los cambios de una concesión a medida que cambia de estado.
- Especificar y realizar un seguimiento de los costes, importes solicitados e importes de primas otorgadas.
- Crear concesiones maestras y asociarles subconcesiones.

Para crear una concesión, puede especificar todos los detalles en un registro nuevo o copiar y modificar los detalles de una concesión existente y luego actualizar.

## <a name="create-a-new-grant"></a>Crear una nueva concesión

1. Vaya a **Gestión y contabilidad de proyectos** \> **Concesiones** \> **Concesiones**.
2. Seleccione **Nueva** \> **Concesión**.
3. En la página de detalles de la subvención, en la ficha desplegable **General**, en el campo **ID de concesión**, introduzca un identificador alfanumérico para la concesión.
4. En el campo **Nombre de concesión**, especifique un nombre para la concesión.
5. En el campo **Descripción**, agregue detalles sobre la nueva concesión.

    La mayoría de los otros campos de la página son opcionales y puede especificar tanta información como desee.

    La siguiente lista describe la información que se especifica en cada ficha desplegable de la página de detalles de la concesión:

    - **General**: ingrese el nombre de la concesión, el estado, la descripción, el propósito y la cantidad.
    - **Información de contacto**: especifique detalles sobre los miembros del personal, el departamento que administra la concesión y el cliente de la concesión o la organización origen de la concesión. También puede indicar si la organización es una entidad de paso que recibe la concesión y la pasa a otro destinatario. Seleccione **Agregar** para agregar información de contacto como números de teléfono y direcciones de correo electrónico de la organización que proporciona la concesión.
    - **Fechas y plazos**: especifique las fechas relacionadas con la concesión y la solicitud de concesión. Algunos ejemplos incluyen la fecha de vencimiento de la solicitud, la fecha de presentación y la fecha en que se aprueba o rechaza la concesión.
    - **Proyectos asociados y contratos de proyectos**: puede ingresar información en esta ficha desplegable solo si el campo **Estado de concesión** de la ficha desplegable **General** se establece en **Activo** o **Concedido**. Seleccione entre las siguientes opciones para completar la tarea relacionada:

        - **Agregar fuente de financiación**: agregue una nueva fuente de financiación para la concesión. Puede especificar todos los detalles en este momento o usar la información predeterminada y actualizarla posteriormente.
        - **Agregar contrato de proyecto**: agregue o actualice la información del contrato del proyecto.
        - **Agregar proyecto**: agregue o actualice los detalles del proyecto.

    - **Configuración**: ingrese detalles sobre fondos equivalentes, si se requiere esta información. Muchas organizaciones que otorgan concesiones requieren que los destinatarios gasten un importe específico de su propio dinero o recursos que coincida con lo otorgado en la concesión. En el campo **Proyecto local o ID de seguimiento**, puede ingresar un identificador que difiera del identificador del proyecto.

        > [!NOTE]
        > Si parte de la concesión se otorgará a una organización diferente, establezca la opción **Subconcesionario** en **Sí**. En el caso de concesiones otorgadas en los Estados Unidos, puede especificar si se otorgará bajo una orden estatal o federal.

    - **Detalles de reducción**: agregue o actualice la información acerca de la frecuencia con la que se pueden retirar, facturar o gastar los fondos de concesión.

## <a name="create-a-new-grant-from-a-copy"></a>Crear una nueva concesión a partir de una copia

1. Vaya a **Gestión y contabilidad de proyectos** \> **Concesiones** \> **Concesiones**.
2. Seleccione **Nuevo** \> **Copia de la subvención**.
3. Especifique un identificador alfanumérico y un nombre para la concesión nueva y seleccione **Aceptar**.
4. En la página de detalles de la concesión, revise los detalles de la concesión copiada y realice los cambios necesarios. La mayoría de los campos de la página son opcionales.

## <a name="view-or-modify-grant-details"></a>Ver o modificar detalles de la concesión

1. Vaya a **Gestión y contabilidad de proyectos** \> **Concesiones** \> **Concesiones**.
2. Seleccione la concesión que va a modificar.
3. En el Panel de acciones, en la ficha **Concesión**, en el grupo **Mantener**, haga clic en **Editar**.
4. Revise los detalles de la concesión y realice los cambios necesarios.
