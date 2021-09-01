---
title: Habilitar la gestión de la calidad y las disconformidades
description: Este tema proporciona una descripción general del proceso para instalar y configurar características de administración de calidad y disconformidad en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b202d76e4b5bc0dfe9f0572274b3453abca58a435b70e96874155f867114a2aa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717349"
---
# <a name="enable-quality-and-nonconformance-management"></a>Habilitar la gestión de la calidad y las disconformidades

[!include [banner](../includes/banner.md)]

Este tema proporciona una descripción general del proceso para instalar y configurar características de administración de calidad y disconformidad en Microsoft Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>Habilitar la gestión de la calidad y las disconformidades

Siga estos pasos para habilitar la gestión de calidad en su sistema.

1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de la gestión de inventario y almacenes**.
1. En la pestaña **Gestión de calidad**, establezca la opción **Utilizar la gestión de la calidad** en *Sí*.
1. Use el campo **Índice por hora** para especificar una tasa de mano de obra por hora en la divisa local. El índice por hora se usa para calcular los costes de operaciones relacionadas con un caso de disconformidad. El índice por hora y los costes calculados proporcionan información de referencia para un caso de disconformidad. No interactúan con otra función.
1. Seleccione **Configuración de informes**.
1. Agregue nuevas líneas para los distintos tipos de informes y seleccione el tipo de documento que se utilizará para cada informe.
1. Cierre la página.
1. Cierre la página.

## <a name="quality-management-configuration-process"></a>Procesar la configuración de administración de calidad

Antes de que pueda comenzar a utilizar las funciones de gestión de calidad y generar pedidos de calidad, debe configurar el sistema y los requisitos previos. A continuación, se muestra una lista de los pasos necesarios para configurar la gestión de calidad.

1. [Habilitar la gestión de la calidad y las disconformidades](#enable-qm).
1. Opcional: [Configurar instrumentos de prueba](quality-test-instruments.md).
1. [Configurar pruebas](quality-tests.md).
1. [Configurar las variables de prueba y los resultados](quality-test-variables.md).
1. [Configurar grupos de prueba](quality-test-groups.md).
1. Opcional: [Configurar grupos de calidad y vincular a productos](quality-groups.md).
1. Opcional: [Configurar asociaciones de calidad](quality-associations.md).

Una vez completada la configuración, puede comenzar a crear y procesar pedidos de calidad. Para obtener más información sobre cómo crear y trabajar con pedidos de calidad, vea [Pedidos de calidad](quality-orders.md).

## <a name="nonconformance-management-configuration-process"></a>Procesar la configuración de administración de disconformidades

Antes de que pueda comenzar a utilizar las funciones de disonformidad y generar pedidos de disconfomidad, debe configurar el sistema y los requisitos previos. A continuación, se muestra una lista de los pasos necesarios para configurar la gestión de disconformidades.

1. [Habilitar la gestión de la calidad y las disconformidades](#enable-qm).
1. [Confiurar los trabajadores responsables de aprobar disconformidades](quality-responsible-workers.md).
1. [Configurar tipos de problemas](quality-problem-types.md).
1. [Configurar zonas de cuarentena](quality-quarantine-zones.md).
1. [Configurar tipos de diagnóstico](quality-diagnostic-types.md).
1. [Configurar operaciones](quality-operations.md).
1. Opcional: [Configurar cargos de calidad](quality-charges.md).

Una vez completada la configuración, puede comenzar a crear y procesar disconformidades. Para obtener más información sobre cómo crear y trabajar con disconformidades, consulte [Crear y procesar disconformidades](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
