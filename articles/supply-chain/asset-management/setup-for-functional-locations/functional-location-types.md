---
title: Tipos de ubicaciones funcionales
description: En este tema se describe cómo crear tipos de ubicación técnica en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb758f9ef205c06cbb9d18b498a5cd7c36012714
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783582"
---
# <a name="functional-location-types"></a>Tipos de ubicaciones funcionales

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En este tema se describe cómo crear tipos de ubicación técnica en Administración de activos. Los tipos de ubicación funcional se usan para administrar los requisitos de las ubicaciones técnicas, incluido cómo se instalan los activos en esta. Puede configurar tipos de activos, planes de mantenimiento, atributos funcionales de ubicación y requisitos de atributo del activo que deben usarse en una ubicación funcional que usa el tipo de ubicación funcional específico. Al crear una ubicación funcional, el tipo de ubicación funcional es obligatorio.

>[!NOTE] 
>Para trabajar con ubicaciones funcionales, debe crear una ubicación funcional predeterminada que solo debe usarse con el fin de crear nuevos activos. Para dicha ubicación funcional predeterminada, debe crear un tipo de ubicación funcional predeterminado que sea realmente sencillo y que permita instalar múltiples activos en la ubicación funcional predeterminada. Consulte [Crear ubicación técnicas](../functional-locations/create-functional-locations.md) para obtener más información sobre cómo configurar ubicaciones técnicas.

## <a name="create-a-default-functional-location-type"></a>Crear un tipo de ubicación técnica predeterminada

Este procedimiento muestra cómo crear un tipo de ubicación funcional predeterminada que se utilizará para una ubicación funcional predeterminada.

1. Seleccione **Administración de activos** > **Configuración** > **Ubicaciones técnicas** > **Tipos de ubicaciones técnicas**.
2. Seleccione **Nuevo** para crear un tipo de ubicación técnica.
3. Inserte un identificador de tipo de ubicación funcional en el campo **Tipo de ubicación funcional**, por ejemplo, el “Predeterminado” y un nombre en el campo **Nombre**.
4. Seleccione un modelo del ciclo de vida en el campo **Modelo de ciclo de vida de ubicación funcional**.
5. Seleccione "Sí" en el botón de alternar **Múltiples activos** para permitir instalar más activos en una ubicación funcional (la ubicación funcional predeterminada) usando este tipo.

Ahora se crea el tipo de ubicación funcional predeterminada que se utilizará para una ubicación funcional predeterminada. No debe agregar más requisitos o restricciones a este tipo de ubicación funcional predeterminado.


## <a name="create-functional-location-types"></a>Crear tipos de ubicaciones funcionales

1. Seleccione **Administración de activos** > **Configuración** > **Ubicaciones técnicas** > **Tipos de ubicaciones técnicas**.
2. Seleccione **Nuevo** para crear un tipo de ubicación técnica.
3. Inserte un identificador de tipo de ubicación funcional en el campo **Tipo de ubicación funcional** y un nombre en el campo **Nombre**.
4. Seleccione un modelo del ciclo de vida en el campo **Modelo de ciclo de vida de ubicación funcional**. Consulte [Estados de ciclo de vida de ubicaciones funcionales](../setup-for-functional-locations/functional-location-stages.md) para obtener más información sobre los estados y modelos de ciclo de vida de ubicación funcional.
5. Seleccione "Sí" en el botón de alternar **Múltiples activos** si es posible instalar varios activos en una ubicación funcional usando este tipo de ubicación funcional. Si selecciona “No”, solo puede instalar *un* activo en una ubicación funcional usando este tipo de ubicación funcional.
6. Seleccione "Sí" en el botón de alternar **Dimensión del activo de actualización** si desea que los activos instalados en una ubicación funcional de este tipo se establezcan automáticamente para usar las dimensiones financieras relacionadas con la ubicación funcional. Esto significa que si cambia las dimensiones financieras en el formulario [Ubicación funcional](../functional-locations/create-functional-locations.md) y la ubicación funcional usa un tipo de ubicación funcional con este botón de alternar establecido en "Sí“, las dimensiones financieras se actualizan automáticamente en todos los activos instalados en dicha ubicación funcional.
7. Se utiliza el campo **Tipo de activo** si desea crear automáticamente *un* activo para la ubicación funcional con el mismo identificador y nombre que la ubicación funcional que está creando. Por ejemplo, esto puede ser importante si crea una ubicación funcional estática, como un edificio o un proceso. En ese caso, seleccione el activo que desee usar para el activo creado automáticamente. Recuerde que, si hace una selección en este campo, el botón de alternar **Múltiples activos** debe establecerse en “No”.
8. En el FastTab **Tipos del activo**, seleccione los tipos de activos que se relacionarán con el tipo de ubicación funcional. Seleccione **Agregar línea** y seleccione los tipos de activos. Si agrega tipos del activo aquí, solo los activos que usen esos tipos del activo se pueden instalar en una ubicación funcional usando este tipo de ubicación funcional. Si no se selecciona ningún tipo de activos en el FastTab **Tipos de activo**, todos los tipos del activo se pueden instalar.
9. En el FastTab **Planes de mantenimiento**, seleccione los planes de mantenimiento que se deben configurar automáticamente en las nuevas ubicaciones funcionales usando este tipo de ubicación funcional. Seleccione **Agregar línea** y seleccione los planes de mantenimiento. Si agrega planes de mantenimiento aquí, solo se pueden usar esos planes en una ubicación funcional usando este tipo de ubicación funcional.
10. En el FastTab **Requisitos de atributo de activo**, seleccione los atributos de activo que se deben configurar automáticamente en las nuevas ubicaciones funcionales usando este tipo de ubicación funcional. Seleccione **Agregar línea** y seleccione el atributo. Estos requisitos de atributo funcionan como guías. No se validan con los atributos configurados en un activo (**Administración de activos** > **Campo común** > **Activos** > **Todos los activos** > seleccione el activo en la página de lista > pestaña **General** > botón **Atributos**). Se mostrarán los requisitos de atributo al instalar los activos en las ubicaciones funcionales.
11. En el FastTab **Tipos permitidos**, seleccione los tipos de ubicación funcional que deben ser válidos para los tipos de ubicación subfuncional relacionados con un tipo de ubicación funcional principal que use el tipo de ubicación funcional seleccionado.
12. En el FastTab **Atributos**, seleccione los atributos de la ubicación funcional que se deben configurar automáticamente en las nuevas ubicaciones funcionales usando este tipo de ubicación funcional. Seleccione **Agregar línea** y seleccione el atributo.


>[!NOTE] 
>En el FastTab **General** , puede obtener una visión general del número de tipos de activos, planes de mantenimiento, requisitos de atributos de activos, tipos permitidos, atributos, y ubicaciones funcionales configuradas en el tipo de ubicación funcional. El campo **Ubicaciones funcionales** muestra el número de ubicaciones técnicas que están utilizando el tipo de ubicación funcional. Puede usar el botón **Copiar** para copiar la configuración de un tipo de ubicación funcional en el tipo de ubicación funcional seleccionado.
