---
title: Trabajadores responsables de aprobar disconformidades
description: Este artículo describe cómo configurar trabajadores que son responsables de aprobar disconformidades.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a108fc1f8954e32719c93656a64d1d27fda03fb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907417"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>Trabajadores responsables de aprobar disconformidades

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar trabajadores que son responsables de aprobar disconformidades.

Las disconformidades deben aprobarse antes de que los usuarios puedan comenzar a introducir detalles como correcciones u operaciones. Antes de que los usuarios puedan aprobar o rechazar las disconformidades, su id. de usuario (registro de usuario) debe estar vinculado a un registro de trabajador. Opcionalmente, puede configurar trabajadores que son responsables de la calidad y luego permitir que un trabajador apruebe el trabajo en nombre de otro trabajador.

## <a name="enable-a-user-for-nonconformance-processing"></a>Habilitar a un usuario para el procesamiento de disconformidades

Antes de que un usuario pueda aprobar o rechazar las disconformidades, se debe vincular su id. de usuario a un registro de trabajador. Los campos de aprobación se pueden configurar automáticamente, y el usuario actual se puede completar automáticamente para la hoja de tiempos. Para que el usuario pueda utilizar las notas de documento, es necesario activar el manejo de documentos en sus opciones de usuario.

1. Vaya a **Administración del sistema \> Usuarios \> Usuarios**.
1. Busque y abra el usuario que debería poder aprobar o rechazar las disconformidades.
1. Establezca el campo **Persona** con el nombre del trabajador que está relacionado con el registro de usuario actual.
1. En el panel de acciones, seleccione **Opciones de usuario**.
1. En la página **Opciones** del registro de usuario actual, en la pestaña **Preferencias**, establezca la opción **Habilitar el manejo de documentos** en *Sí*.
1. Cierre las páginas.

## <a name="define-workers-that-are-responsible-for-quality"></a>Definir trabajadores responsables de la calidad

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Trabajadores responsables de la calidad**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Trabajador**, seleccione el trabajador que introduce los datos de calidad.
4. En el campo **Trabajador responsable**, seleccione el trabajador en nombre del cual el trabajador seleccionado introduce el trabajo. Cuando se crean y actualizan disconformidades, este trabajador se introducirá de orma predeterminada en los campos **Trabajador**.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Gastos de calidad](quality-charges.md)
- [Zonas de cuarentena para disconformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico de disconformidades](quality-diagnostic-types.md)
- [Cargos de calidad para disconformidades](quality-charges.md)
- [Operaciones para disconformidades](quality-operations.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
