---
title: Definir los derechos de acceso de un controlador de objeto de coste
description: "Este tema proporciona información sobre los derechos de acceso para los controladores de objeto de coste."
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 44ef687dcc5c7f515494894b3784bf5eceb99eed
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="access-rights-of-a-cost-object-controller"></a>Derechos de acceso de un controlador de objeto de coste

[!include[banner](../includes/banner.md)]

El área de trabajo **Control de costes** es un punto central donde los administradores pueden ver el rendimiento de los objetos de coste. Este espacio de trabajo permite a los administradores consumir datos de contabilidad de costes aunque no sean contables de costes. Por razones de seguridad, los administradores deben poder ver únicamente los datos de la contabilidad de costes relacionados con los objetos de coste específicos de los que sean responsables.

Existen cuatro roles únicos en contabilidad de costes.

| Nombre de rol               | Licencia      |
|-------------------------|--------------|
| Administrador de contabilidad de costes | Actividad     |
| Contable de costes         | Operations   |
| Contable de costes   | Operations   |
| Controlador de objeto de coste  | Miembros del equipo |

Este tema explica cómo asignar el rol **Controlador de objeto de coste** a un administrador.

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

|                                   | Usuarios            | Intervalos de miembros de dimensión   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| **Nodos**                         | **Id. de usuario**      | **Desde miembro de dimensión** | **Hasta miembro de dimensión** |
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
    - Visualizaciones de datos de Power BI que se insertan en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (cliente)

> [!IMPORTANT]
> - Antes de que la jerarquía de listas de acceso pueda afectar a los datos de Power BI, se deben emparejar la jerarquía de listas de acceso y la seguridad en Power BI. Para obtener más información, consulte [Configurar la seguridad del paquete del contenido de contabilidad de costes](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Este tema muestra los requisitos previos que deben estar presentes antes de poder usar el espacio de trabajo **Control de costes**.

Consulte también

- [Espacio de trabajo de control de costes](cost-control-workspace.md)
- [Jerarquía de dimensiones](dimension-hierarchy.md)
- [Configurar la seguridad del paquete contenido de contabilidad de costes](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
