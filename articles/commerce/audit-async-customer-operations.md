---
title: Sincronización de auditoría de operaciones de clientes en la sede central
description: Este artículo explica cómo auditar la sincronización de las operaciones del cliente en Microsoft Dynamics 365 Commerce headquarters para ayudar a solucionar cualquier problema de los usuarios del sitio.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691112"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Sincronización de auditoría de operaciones de clientes en la sede central

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artículo explica cómo auditar la sincronización de las operaciones del cliente en Microsoft Dynamics 365 Commerce headquarters para ayudar a solucionar cualquier problema de los usuarios del sitio.

A medida que las organizaciones comienzan a adoptar la capacidad de crear y editar clientes de forma asincrónica, los administradores del sitio necesitan una forma de ver y solucionar problemas de operaciones, en función de las solicitudes de los usuarios del sitio o las fallas del proceso. En esos escenarios, los administradores del sitio deberían poder auditar las operaciones de creación y edición de clientes, y corregir cualquier falla mediante el uso de un modelo de autoservicio.

## <a name="customer-synchronization-status"></a>Estado de sincronización de clientes

Cuando se elige el modo asincrónico de administración de clientes y sus características correspondientes, los administradores de Commerce headquarters deben crear y programar un trabajo por lotes periódico para el **trabajo P**, el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico** y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes sincrónicos en Commerce headquarters. La sincronización de las operaciones de gestión de clientes se produce cada vez que se ejecutan estos trabajos. Para más información, vea [Modo de creación de clientes asíncrono](async-customer-mode.md).

Como propietario de un negocio, puede realizar las siguientes operaciones:

- Ver todas las operaciones de creación/edición de los usuarios del sitio. Los detalles incluyen el estado y una marca de tiempo.
- Filtre las operaciones utilizando cualquiera de los campos y valores de la tabla de clientes para restringir el registro de auditoría.
- Vea breves descripciones de los cambios junto con los detalles del estado para comprender las operaciones a un alto nivel.
- En caso de fallas, edite y corrija campos problemáticos y luego guarde y sincronice operaciones específicas del cliente.

### <a name="elements-on-the-customer-synchronization-status-page"></a>Elementos de la página de estado de sincronización del cliente

Para ver una lista de todas las operaciones de sincronización, en la Commerce headquarters vaya a **Comercio y Retail \> Clientes \> Estado de sincronización del cliente**. La siguiente ilustración muestra un ejemplo de la página **Estado de sincronización del cliente**.

![Página de estado de sincronización del cliente en la Commerce headquarters.](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

De forma predeterminada, la lista de operaciones de sincronización de clientes en el lado izquierdo de la página **Estado de sincronización del cliente** incluye las siguientes columnas:

- Nombre del canal
- Cuenta de cliente
- Cuenta de cliente asincrónico
- Marca de tiempo de operaciones
- Estado de sincronización de clientes

La parte superior derecha de la página muestra los detalles de la cuenta del cliente, como los valores **Cuenta de cliente**, **Operación asíncrona minorista**, **Estado de sincronización del cliente** y **Último error conocido**.

La sección **Cambiar descripción** contiene una descripción del tipo de operación de administración de clientes que se ejecutó (por ejemplo, creación de clientes, actualización de cuentas o falla de sincronización con detalles).

La sección **Atributos del cliente** contiene una cuadrícula que muestra todos los atributos del cliente, junto con los valores antiguos y nuevos. Puede editar esta sección si desea cambiar los valores de los atributos de sus clientes para corregir errores y luego sincronizar nuevamente.
