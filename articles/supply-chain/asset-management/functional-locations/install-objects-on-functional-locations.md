---
title: Instalar activos en ubicaciones funcionales
description: En este tema se explica cómo instalar activos en ubicaciones funcionales en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ea67e2392d8e25a2a5f3cb7e1ff5032322f2c48
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022039"
---
# <a name="install-assets-on-functional-locations"></a>Instalar activos en ubicaciones funcionales

[!include [banner](../../includes/banner.md)]

 

Una vez creadas las estructuras de ubicaciones funcionales, el paso siguiente es instalar activos en las ubicaciones funcionales relevantes. En este tema se explica cómo instalar activos en esas ubicaciones funcionales en Administración de activos. Para obtener información sobre cómo crear activos, consulte [Introducción a los activos](../objects/introduction-to-objects.md).

Si ha creado una estructura de activos, la estructura de activos completa debe estar instalada en una ubicación funcional. Por lo tanto, sólo los activos principales (activos de nivel superior que no tienen ningún activo principal) se pueden seleccionar en una ubicación funcional. Todos los activos secundarios relacionados (subactivos) también se instalarán en la ubicación funcional. Al instalar activos en una ubicación funcional, las dimensiones financieras de la ubicación funcional se pueden transferir automáticamente a ellos, en función de la configuración del tipo de ubicación funcional seleccionada para la ubicación funcional. Para obtener más información sobre cómo configurar tipos de ubicaciones técnicas, consulte [Tipos de ubicación técnicas](../setup-for-functional-locations/functional-location-types.md).

> [!NOTE]
> Puede configurar tipos de activos en el tipo de ubicación funcional que se usa para una ubicación funcional. En este caso, al instalar activos en la ubicación funcional, sólo los activos principales que tienen el mismo tipo del activo se muestran en la lista de activos que se pueden instalar en la ubicación funcional.

Una vez que haya instalado activos en una ubicación funcional, puede sustituir un activo principal o una estructura de activos, según sea necesario. Como sucede al instalar los activos, seleccione un activo principal para reemplazar. Todos los activos relacionados secundarios también se sustituirán. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Instale una estructura de activos en una ubicación funcional.

1. Seleccione **Administración de activos** \> **Común** \> **Ubicaciones funcionales** \> **Todas las ubicaciones funcionales** o **Ubicaciones funcionales activas**.
2. Seleccione la ubicación funcional en la que instalar un activo.
3. Seleccione **Instalar activo**.

    La sección **Atributos** muestra una lista de los requisitos de atributos de activos que se configuran en el tipo de ubicación funcional que se selecciona para la ubicación funcional. La finalidad de los atributos es meramente informativa. El sistema no valida los atributos con los atributos de activos que se configuran en el activo que se va a instalar. Debe hacer la validación después de seleccionar un activo en el campo **Activo**.

4. En el campo **Activo**, seleccione el activo principal para instalar. Todos los activos secundarios relacionados se incluyen automáticamente en la instalación.

    La sección **Atributos de activo** a la derecha de la lista de activos muestra los atributos de activos relacionados con el activo seleccionado.

5. En el campo **Vigencia**, seleccione la fecha y la hora a partir de las cuales es válida la instalación de los activos. Después de esa fecha y hora, los costes del activo y los subactivos relacionados estarán relacionados con la ubicación funcional.

    > [!NOTE]
    > Los atributos de activos que se configuran en el activo se agregan a la sección **Atributos**. Por ejemplo, el requisito del atributo **Peso** se ha agregado como un requisito tanto en el activo como en la ubicación funcional. Si el activo tiene requisitos de atributo del mismo tipo que la ubicación funcional, los valores de los requisitos de atributo del activo se introducen en los campos **Valor**. Por lo tanto, puede validar la los valores dle activo con los requisitos de atributo que se configuran en la ubicación funcional. Los requisitos de atributo que se configuran en la ubicación funcional se marcan con una marca de verificación.

6. Seleccione **Aceptar**.

    > [!NOTE]
    > Para cambiar la instalación de un activo instalándolo en una nueva ubicación funcional, siga los pasos del 1 al 6 de este procedimiento. Al instalar un activo en una nueva ubicación funcional, el activo se desinstala automáticamente de la ubicación funcional anterior. Las solicitudes de mantenimiento o las órdenes de trabajo activas que se hayan creado en el activo antes de instalarlo en una nueva ubicación funcional **no** se transfieren automáticamente a la nueva ubicación funcional. Si dichas solicitudes de mantenimiento y órdenes de trabajo aún se requieren para el activo, deben volver a crearse manualmente después de instalar el activo en la nueva ubicación.

7. Para ver una lista de todos los activos, incluidos los subactivos, instalados en la ubicación funcional, seleccione la ubicación funcional en la página **Todas las ubicaciones funcionales** y, a continuación, seleccione **Activos**.
8. Para ver una lista de solicitudes de mantenimiento activas, órdenes de trabajo activas o registros de defectos relacionados con los activos que están instalados en una ubicación funcional, seleccione la ubicación funcional en la página **Todas las ubicaciones funcionales** y, a continuación, seleccione **Solicitudes**, **Pedidos de trabajo** o **Defectos**.

> [!NOTE]
> Cuando se cambian los datos relacionados con el activo, se actualiza automáticamente en la ubicación funcional en la que el activo está instalado. Esta actualización automática está relacionada con los cambios en las solicitudes de mantenimiento, órdenes de trabajo, registros de defectos del activo, registros de tiempo de inactividad de mantenimiento y registros de medidas del activo.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Crear un activo automáticamente en una ubicación funcional

Puede configurar las etapas de ubicación funcional y los tipos de ubicación funcional para gestionar la creación automática de *un* activo en una ubicación funcional. El activo obtiene el mismo identificador y nombre que la ubicación funcional. Esta funcionalidad podría ser de utilidad cuando está administrando el mantenimiento de un activo grande, estático, como un edificio.

Para poder crear automáticamente un activo en una ubicación funcional, los datos de configuración siguientes deben estar disponibles:

- Cree un tipo de ubicación funcional para gestionar la creación automática de un activo. En el campo **Tipo de activo**, seleccione un tipo de activo. Para obtener más información, consulte [Tipos de ubicación funcional](../setup-for-functional-locations/functional-location-types.md).
- Cree un estado de ciclo de vida de ubicación funcional para gestionar la creación automática de un activo. Establezca la opción **Crear activo** en **Sí**. Para obtener más información, consulte [Estados de ciclo de vida de una ubicación funcional](../setup-for-functional-locations/functional-location-stages.md).

Una vez que los datos de configuración estén disponibles, todo está listo para crear un activo.

1. En la página **Todas las ubicaciones funcionales**, asegúrese de que la ubicación funcional en la que desea que se cree el activo automáticamente use el tipo de ubicación funcional que ha creado con este propósito.
2. Seleccione la ubicación funcional en la lista.
3. Seleccione **Actualizar estado de ubicación funcional** y, a continuación, seleccione el estado de ciclo de vida que ha creado con este propósito. Ahora se instala un activo automáticamente en la ubicación funcional. Este activo tiene el mismo nombre que la ubicación funcional.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]