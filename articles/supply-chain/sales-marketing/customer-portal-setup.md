---
title: Instalar, configurar y actualizar el portal del cliente
description: Este tema proporciona detalles sobre licencias e instrucciones de configuracion del Portal del cliente.
author: dasani-madipalli
manager: tfehr
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 2153bbca2be7c72e48b9dc51b1f7fdbe2ab89903
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977747"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Instalar, configurar y actualizar el portal del cliente

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Requisitos de licencia

Para implementar el portal del Cliente, debe tener las siguientes licencias:

- **Portales Power Apps**: esta licencia es necesaria para alojar el portal del Cliente. Los portales tienen licencia en función del uso. Para más información, consulte los [requisitos de licencia de portales Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Doble escritura**: debe tener las licencias necesarias para habilitar la escritura dual para las tablas de Supply Chain Management. Para obtener más información, consulte los [requisitos del sistema para escritura dual](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Dependencias de doble escritura y los portales Power Apps

El portal del cliente depende de los portales Power Apps portales y la doble escritura, como se muestra en la siguiente ilustración.

![Dependencias del portal del cliente](media/customer-portal-elements.png "Dependencias del portal del cliente")

A diferencia de otras características de Supply Chain Management, la plantilla del portal del cliente reside en los portales Power Apps. Por lo tanto, el portal del Cliente está limitado por la funcionalidad y las capacidades proporcionadas por los portales Power Apps y las tablas en doble escritura.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Configuración requerida para habilitar el portal del cliente

Después de asegurarse de que tiene las licencias requeridas, puede configurar la escritura dual como se describe en [instrucciones de sincronización inicial de doble escritura](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).

Asegúrese de habilitar las siguientes asignaciones de tablas en doble escritura:

- Encabezado de pedido de ventas
- Detalles de pedido de ventas
- Cuentas
- Contactos
- Productos

Una vez completada esta configuración, puede aprovisionar la plantilla del portal del Cliente.

## <a name="provision-the-customer-portal"></a>Aprovisionar el portal del cliente

Antes de comenzar, asegúrese de haber completado la [configuración requerida](#required-setup). Luego, siga estos pasos para aprovisionar el portal del Cliente.

1. Vaya a [make.powerapps.com](https://make.powerapps.com/).
2. Asegúrese de estar utilizando el entorno donde habilitó la escritura dual.
3. En la pestaña **Crear**, desplácese hacia abajo a la sección **Comenzar desde plantilla** y seleccione la plantilla que se llama **Portal del cliente**.
4. Siga las instrucciones en pantalla.

Después de completar el aprovisionamiento, puede acceder al portal del Cliente en la sección **Sus aplicaciones** de la página **Inicio**.

> [!NOTE]
> Si la solución de doble escritura no está instalada en el entorno en el que está trabajando, recibirá un mensaje de error y no se aprovisionará el portal del Cliente.

## <a name="update-the-customer-portal"></a>Actualizar el portal del cliente

Se podría agregar más funcionalidad al portal del Cliente más adelante. Cualquier cambio que Microsoft realice en los componentes de la solución subyacente aparecerá automáticamente en su entorno. Sin embargo, el sitio web aprovisionado en su entorno no reflejará automáticamente los cambios realizados en los datos de configuración. Tendrá que aplicar manualmente esos cambios obteniendo el código de la nueva plantilla y fusionándolo con el sitio web aprovisionado.

## <a name="additional-resources"></a>Recursos adicionales

Para saber cómo puede configurar y personalizar el portal del Cliente, debe comenzar por revisar la siguiente documentación para las tecnologías subyacentes:

- [Documentación de portales Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Documentación de doble escritura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Para gestionar eficazmente sus portales, debe conocer los portales Power Apps y el ciclo de vida de Microsoft Dataverse. Para obtener más información, consulte los siguientes recursos:

- [Sobre el ciclo de vida del portal](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Actualizar un portal](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migrar la configuración del portal](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Administración de ciclo de vida de solución: Dynamics 365 para aplicaciones de Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)
