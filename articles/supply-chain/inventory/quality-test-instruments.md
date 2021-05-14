---
title: Instrumentos de prueba de gestión de calidad
description: Este tema describe cómo crear instrumentos de prueba, de modo que se puedan usar para pruebas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc09021f89a9064a3140a726fca74e3eceab13da
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956820"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="b95e7-103">Instrumentos de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="b95e7-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b95e7-104">Este tema describe cómo crear instrumentos de prueba, de modo que se puedan usar para pruebas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b95e7-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b95e7-105">Use la página **Instrumentos de prueba** para definir y ver detalles sobre los dispositivos que se utilizan para realizar pruebas en pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="b95e7-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="b95e7-106">Los instrumentos de prueba son opcionales.</span><span class="sxs-lookup"><span data-stu-id="b95e7-106">Test instruments are optional.</span></span> <span data-ttu-id="b95e7-107">Sin embargo, pueden ayudar a los trabajadores de calidad a saber qué dispositivo o herramienta deben usar para realizar una prueba específica.</span><span class="sxs-lookup"><span data-stu-id="b95e7-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="b95e7-108">Ejemplo de instrumento de prueba</span><span class="sxs-lookup"><span data-stu-id="b95e7-108">Test instrument example</span></span>

<span data-ttu-id="b95e7-109">Está realizando varias pruebas en componentes eléctricos.</span><span class="sxs-lookup"><span data-stu-id="b95e7-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="b95e7-110">Algunas pruebas son para la salida de tensión de los componentes, una prueba es para su temperatura y una prueba es para su peso.</span><span class="sxs-lookup"><span data-stu-id="b95e7-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="b95e7-111">Se utilizan diferentes herramientas, dispositivos o equipos para realizar cada prueba.</span><span class="sxs-lookup"><span data-stu-id="b95e7-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="b95e7-112">Por ejemplo, se usa un medidor de tensión para medir la tensión, se usa un termómetro para medir la temperatura y se usa una balanza para medir el peso.</span><span class="sxs-lookup"><span data-stu-id="b95e7-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="b95e7-113">Puede configurar cada uno de estos dispositivos como un instrumento de prueba e indicar la unidad de medida en la que se deben registrar los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="b95e7-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="b95e7-114">Por ejemplo, los resultados del medidor de tensión se registran en voltios, los resultados del termómetro se registran en grados Fahrenheit o grados Celsius y los resultados de la báscula se registran en libras o kilogramos.</span><span class="sxs-lookup"><span data-stu-id="b95e7-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="b95e7-115">Crear un instrumento de prueba</span><span class="sxs-lookup"><span data-stu-id="b95e7-115">Create a test instrument</span></span>

1. <span data-ttu-id="b95e7-116">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Instrumentos de prueba**.</span><span class="sxs-lookup"><span data-stu-id="b95e7-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="b95e7-117">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="b95e7-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b95e7-118">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="b95e7-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b95e7-119">**Instrumento de prueba**: introduzca un id. o nombre único para el instrumento de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b95e7-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="b95e7-120">**Descripción**: escriba una descripción detallada del instrumento de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b95e7-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="b95e7-121">**Unidad**: seleccione la unidad en la que el instrumento mide los resultados.</span><span class="sxs-lookup"><span data-stu-id="b95e7-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="b95e7-122">El campo **Precisión** se configura automáticamente, según la unidad que seleccione.</span><span class="sxs-lookup"><span data-stu-id="b95e7-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="b95e7-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b95e7-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b95e7-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b95e7-124">Additional resources</span></span>

- [<span data-ttu-id="b95e7-125">Pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="b95e7-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="b95e7-126">Grupos de pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="b95e7-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
