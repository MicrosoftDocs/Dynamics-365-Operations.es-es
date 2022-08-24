---
title: Mantener la certificación de proveedores
description: Este artículo describe los pasos que los proveedores pueden seguir para mantener sus certificaciones mediante el espacio de trabajo de colaboración de proveedores.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: v-kiarnd
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e6742037d04cb21c153af3cd22d1dcb91e3d64e8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268514"
---
# <a name="maintain-vendor-certification"></a>Mantener la certificación de proveedores

[!include [banner](../includes/banner.md)]

Este artículo describe los pasos que sus proveedores pueden seguir para mantener sus certificaciones mediante el **Espacio de trabajo de colaboración de proveedores**. Los ejemplos de certificaciones pueden incluir una empresa de negocios de mujeres (WBE) o una empresa de liderazgo en energía y diseño ambiental (LEED). Los proveedores deberán introducir la información de certificación en el espacio de trabajo **Informacion del proveedor**. A partir de ahí, los proveedores seleccionarán **Más detalles** y luego seleccionarán **Certificaciones**.

## <a name="turn-on-the-vendor-certification-feature"></a>Activar la función de certificación de proveedores

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo** - *Proveedores*
- **Nombre de la función** - *Activar la gestión de certificación de colaboración de proveedores*

## <a name="add-a-new-certification"></a>Agregar una nueva certificación

Para agregar una nueva certificación, seleccione el botón **Agregar** que se encuentra encima de la cuadrícula **Certificación** del espacio de trabajo **Informacion del proveedor**. Especifique la siguiente información:

- Número de certificación
- Tipo de certificación
- Organización certificadora
- Fecha de certificación
- Montante de responsabilidad, si corresponde
- Fecha desde
- Fecha de expiración
- Comentarios opcionales

Si existen documentos relacionados con la certificación específica, puede adjuntarlos seleccionando el botón **Documento**.

A las certificaciones que introduzcan sus proveedores en esta página se les asignará un origen de “Proveedor”. Puede introducir la información del certificado en nombre de su proveedor en las cuentas bancarias del proveedor. La información se mostrará aquí y la fuente se mostrará como **Cliente**.

Los proveedores pueden editar o eliminar sus certificaciones según sea necesario.

## <a name="vendor-collaboration-generated-certification-records"></a>Registros de certificación generados por la colaboración de proveedor

Después de que un proveedor haya agregado la información de certificación, dicha información será visible en la página **Certificaciones generadas por la colaboración de proveedor**. Para abrir la página, vaya a **Proveedores > Consultas > Informes de proveedores > Certificaciones generadas por la colaboración de proveedor**. De forma predeterminada, todos los registros de certificación nuevos o modificados están visibles. Un contable de proveedores puede ver los cambios y validar la información a través de su proceso de confirmación para validar. Cuando se haya confirmado la información, el registro de certificación que figura en la página se puede seleccionar y marcar como revisado. Marcar el registro como revisado lo eliminará de la lista predeterminada.

Todos los cambios de certificación son visibles en la página **Certificaciones generadas por la colaboración de proveedor**. Si un cambio no se muestra en la página, puede verlo ajustando los filtros para la cuenta del proveedor, el período de fecha de vigencia o eligiendo si incluir información para los cambios de certificación que se han revisado.

