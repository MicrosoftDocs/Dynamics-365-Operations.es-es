---
title: Derechos de acceso para controladores de objeto de coste
description: Este artículo proporciona información sobre los derechos de acceso para los controladores de objeto de coste.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c40be758c5e5d1d1fb025630ed8321ae46251892
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903200"
---
# <a name="access-rights-for-cost-object-controllers"></a>Derechos de acceso para controladores de objeto de coste

[!include [banner](../includes/banner.md)]

El área de trabajo **Control de costes** es un punto central donde los administradores pueden ver el rendimiento de los objetos de coste. Este espacio de trabajo permite a los administradores consumir datos de contabilidad de costes aunque no sean contables de costes. Por razones de seguridad, los administradores deben poder ver únicamente los datos de la contabilidad de costes relacionados con los objetos de coste específicos de los que sean responsables.

Existen cuatro roles únicos en contabilidad de costes.

| Nombre de rol               | Licencia      |
|-------------------------|--------------|
| Administrador de contabilidad de costes | Actividad     |
| Contable de costes         | Operations   |
| Contable de costes   | Operations   |
| Controlador de objeto de coste  | Miembros del equipo |

Este artículo explica cómo asignar el rol **Controlador de objeto de coste** a un administrador.

Cuando el rol **Controlador de objeto de coste** se asigna a un administrador, este puede realizar las siguientes tareas:

- Acceder al espacio de trabajo **Control de costes** (en el cliente).

    - Explorar y tener acceso de vista a las páginas que admiten exploración.

- Acceder al espacio de trabajo **Control de costes** (en el la aplicación móvil).

> [!NOTE]
> El rol **Controlador de objeto de coste** no controla a qué objetos de coste puede el usuario acceder y ver sus datos. La seguridad de filas se proporciona mediante jerarquías de dimensión y la jerarquía de listas de acceso.

## <a name="grant-access-rights"></a>Conceder derechos de acceso
El siguiente ejemplo muestra cómo puede ser el aspecto de las jerarquías de dimensión.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión    | Nombre de tipo de jerarquía de dimensión      | Jerarquía de listas de acceso |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organización             | Centros de coste | Jerarquía de clasificación de dimensiones | **Sí**               |

Puede usar el FastTab **Usuarios** en el diseñador de jerarquías para insertar uno o más Id. de usuarios en cada nodo.

|             Nodos                 | Usuarios            | Desde miembro de dimensión     |   Hasta miembro de dimensión   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| Organización                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Administrador                 | Abril            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanzas   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RR. HH.        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Producción            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Empaquetado | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Ensamblado  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> Los contables de coste debe asignarse al nivel superior de la jerarquía, de modo que puedan ver todas las entradas de contabilidad de costes.

Antes de que se puedan aplicar la jerarquía de listas de acceso y sus configuraciones de seguridad, debe establecer la opción **Habilitar acceso de visualización para los miembros de dimensión de objeto de coste** en **Sí** en la pestaña **General** de la página **Parámetros de la contabilidad de costes** (**Contabilidad de costes** > **Configuración** > **Parámetros**).

Los valores para la jerarquía de listas de acceso se utilizan para controlar los datos que se muestran en siguientes áreas:

- Espacio de trabajo **Control de costes** (en el cliente):

    - Datos en las páginas para las que se usan para la obtención de detalles

- Espacio de trabajo **Control de costes** (en el la aplicación móvil):

    - Saldos en tarjetas

- Microsoft Power BI:

    - Datos que se muestran en las visualizaciones de Power BI
    - Visualización de los datos de Power BI que se insertarán en el cliente de Dynamics 365 Finance

> [!IMPORTANT]
> - Antes de que la jerarquía de listas de acceso pueda afectar a los datos de Power BI, se deben emparejar la jerarquía de listas de acceso y la seguridad en Power BI. Para obtener más información, consulte [Configurar la seguridad del paquete del contenido de contabilidad de costes](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Este artículo muestra los requisitos previos que deben estar presentes antes de poder usar el espacio de trabajo **Control de costes**.

Recursos adicionales

- [Espacio de trabajo de control de costes](cost-control-workspace.md)
- [Jerarquía de dimensiones](dimension-hierarchy.md)
- [Configurar la seguridad del paquete contenido de contabilidad de costes](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
