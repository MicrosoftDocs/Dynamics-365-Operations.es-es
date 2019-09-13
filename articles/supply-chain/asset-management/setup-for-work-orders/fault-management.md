---
title: Administración de defectos
description: Este tema explica la administración de defectos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 48c90a8b776cc16804de8e20ada7d8ca347fa5b9
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874748"
---
# <a name="fault-management"></a>Administración de defectos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, puede usar el diseñador de defectos para configurar síntomas de defectos, áreas de defectos y tipos de defectos en los tipos de activos. De esta manera, puede administrar los defectos que se detectan en los activos. Además, las causas del defecto y las sugerencias para corregir defectos se pueden registrar en una orden de trabajo.

El proceso para el registro y la administración de defectos consiste en estos pasos.

1. Cree una lista de síntomas del defecto, áreas del defecto y tipos de defecto que puedan aparecer en sus tipos de activo.
2. En el diseñador del defectos, configure los síntomas, las áreas del defecto y los tipos del defecto.

A continuación se muestran algunos ejemplos para ayudarle a comprender la diferencia entre los síntomas del defecto, las áreas del defecto y los tipos de defecto.

**Síntomas de defecto:**

- Voltajes desequilibrados
- Cortocircuito
- Ruido
- Escape
- Vibraciones

**Áreas de defecto:**

- Eléctrica
- Mecánica
- Hidráulica
- Neumática

**Tipos de defecto:**

- Bobina principal de estator defectuosa
- Diodo defectuoso
- Bobinas con suciedad
- Generador defectuoso
- Sensor defectuoso

## <a name="create-fault-symptoms"></a>Crear síntomas del defecto

Siga estos pasos para crear una lista de los síntomas que se pueden utilizar en el diseñador de defectos.

1. Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Síntomas del defecto**.
2. Seleccione **Nuevo** para crear un registro.
3. En el campo **Síntoma del defecto**, especifique un nombre para el síntoma del defecto.
4. En el campo **Descripción**, escriba una descripción.
5. Seleccione **Guardar**.

## <a name="create-fault-areas"></a>Crear áreas de defecto

Siga estos pasos para crear una lista de áreas o ubicaciones que se pueden utilizar en el diseñador de defectos.

1. Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Áreas del defecto**.
2. Seleccione **Nuevo** para crear un registro.
3. En el campo **Área del defecto**, especifique un nombre para el área del defecto.
4. En el campo **Descripción**, escriba una descripción.
5. Seleccione **Guardar**.

## <a name="create-fault-types"></a>Crear tipos de defecto

Siga estos pasos para crear una lista de los tipos de defecto que se pueden utilizar en el diseñador de defectos.

1. Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Tipos de defecto**.
2. Seleccione **Nuevo** para crear un registro.
3. En el campo **Tipo de defecto**, especifique un nombre para el tipo de defecto.
4. En el campo **Descripción**, escriba una descripción.
5. Seleccione **Guardar**.

## <a name="set-up-the-fault-designer"></a>Configurar el diseñador de defectos

En el diseñador de defectos, configure los datos del defecto en tipos de activo.

1. Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Diseñador de defectos**.
2. En el panel izquierdo, seleccione el tipo de activo para el que configurar un registro de defecto.
3. En la ficha desplegable **Síntoma del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Síntoma del defecto**, seleccione un síntoma del defecto.
4. En la ficha desplegable **Área del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Área del defecto**, seleccione un área del defecto.
5. En la ficha desplegable **Tipo del defecto**, seleccione **Agregar línea** y, a continuación, en el campo **Tipo del defecto**, seleccione un tipo del defecto.
6. Para crear rápidamente combinaciones de todos los síntomas, áreas y tipos del defecto existentes para el tipo activo seleccionado, seleccione **Crear combinaciones de defectos**. Esta función resulta útil si ha añadido muchos síntomas, áreas y tipos de defecto. Es más fácil eliminar líneas para cualquier combinación que no sea relevante para el tipo de activo que crear nuevas líneas manualmente.

    > [!NOTE]
    > Para copiar la configuración de los síntomas, las áreas y los tipos de defecto a partir de un tipo de activo para el tipo de activo seleccionado, seleccione **Copiar desde el tipo de activo**.

7. Seleccione **Guardar** para guardar los cambios.

![Figura 1](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Crear causas de defecto

Siga estos pasos para crear una lista de causas de defecto conocidas que se pueden agregar a una orden de trabajo o a una solicitud de mantenimiento.

1. Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Causas de defecto**.
2. Seleccione **Nuevo** para crear un registro.
3. En el campo **Causa de defecto**, especifique un nombre para la causa de defecto.
4. En el campo **Descripción**, escriba una descripción.
5. Seleccione **Guardar**.

## <a name="create-fault-remedies"></a>Permite soluciones a defectos

Siga estos pasos para crear una lista de sugerencias de soluciones y reparaciones que se pueden agregar a una orden de trabajo o a una solicitud de mantenimiento.

1. Seleccione **Administración de activos** \> **Configuración** \> **Defecto** \> **Soluciones a defectos**.
2. Seleccione **Nuevo** para crear un registro.
3. En el campo **Soluciones a defectos**, especifique un nombre para la solución de defectos.
4. En el campo **Descripción**, escriba una descripción.
5. Seleccione **Guardar**.

> [!NOTE]
> Puede cambiar los nombres de los síntomas, áreas, tipos y causas de los defectos, así como de las soluciones según sea necesario. Los cambios en el nombre se reflejan automáticamente en los registros relacionados del defecto.
