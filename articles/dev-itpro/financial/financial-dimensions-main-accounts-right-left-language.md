---
title: Las dimensiones financieras y cuentas principales en un idioma de derecha a izquierda
description: "Este tema describe algunas de las decisiones de implementación que debe tener en cuenta cuando use un idioma de derecha a izquierda y debe configurar las dimensiones financieras y las cuentas principales."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b8ceee7486cae9ec0ff7dfedc35909e2f01d0616
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="financial-dimensions-and-main-accounts-in-a-right-to-left-language"></a><span data-ttu-id="9b32c-103">Las dimensiones financieras y cuentas principales en un idioma de derecha a izquierda</span><span class="sxs-lookup"><span data-stu-id="9b32c-103">Financial dimensions and main accounts in a right-to-left language</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9b32c-104">Este tema describe algunas de las decisiones de implementación que debe tener en cuenta cuando use un idioma de derecha a izquierda y debe configurar las dimensiones financieras y las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="9b32c-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="9b32c-105">Las dimensiones financieras y las cuentas principales son componentes clave de la fase de planificación para una implementación.</span><span class="sxs-lookup"><span data-stu-id="9b32c-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="9b32c-106">Después de crear las dimensiones financieras y cuentas principales en el sistema, se usan en las páginas de **Configuración de estructuras contables**, de **Estructuras de reglas avanzadas**, y de **Configuración de dimensión financiera para las aplicaciones de integración**.</span><span class="sxs-lookup"><span data-stu-id="9b32c-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="9b32c-107">El orden que se define en dichas páginas se utiliza en el sistema para la entrada y el consumo de datos.</span><span class="sxs-lookup"><span data-stu-id="9b32c-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="9b32c-108">En algunas partes del sistema, las dimensiones financieras y las cuentas principales aparecen en campos diferentes.</span><span class="sxs-lookup"><span data-stu-id="9b32c-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="9b32c-109">Sin embargo, en otros lugares, como los diarios, las dimensiones financieras y las cuentas principales aparecen como una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="9b32c-109">However, in other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="9b32c-110">Prácticas recomendadas para configurar dimensiones financieras y cuentas principales en un sistema de derecha a izquierda</span><span class="sxs-lookup"><span data-stu-id="9b32c-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

-   <span data-ttu-id="9b32c-111">Al seleccionar el delimitador para los planes contables, seleccione una de las opciones de delimitador doble: guión doble (--), barra doble (||), dos puntos (..) o doble subrayado (\_\_).</span><span class="sxs-lookup"><span data-stu-id="9b32c-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (--), double bar (||) or double period (..), or double underscore (\_\_).</span></span>
-   <span data-ttu-id="9b32c-112">Al crear los valores de la dimensión financiera y de la cuenta principal, utilice solo números y caracteres de idioma de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="9b32c-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
-   <span data-ttu-id="9b32c-113">Evite el uso del delimitador del plan contable seleccionado en los valores de la dimensión financiera y de la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="9b32c-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="9b32c-114">Siguiendo estas prácticas recomendadas, ayuda a garantizar la representación coherente del orden definido por el usuario en el sistema.</span><span class="sxs-lookup"><span data-stu-id="9b32c-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>




