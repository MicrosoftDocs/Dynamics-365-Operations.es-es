---
title: "Gestión de turnos y caja registradora"
description: "En este artículo se explica cómo configurar y utilizar los dos tipos de turnos de punto de venta (PDV) comerciales: independiente y compartido. Se pueden utilizar turnos compartidos por varios usuarios en varios lugares, mientras que los turnos independientes se pueden utilizar solo por un trabajador cada vez."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b8e12f3f4c2f8f5a596c8994f2a4571d8a907062
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="shift-and-cash-drawer-management"></a>Gestión de turnos y caja registradora

[!include[banner](includes/banner.md)]


En este artículo se explica cómo configurar y utilizar los dos tipos de turnos de punto de venta (PDV) comerciales: independiente y compartido. Se pueden utilizar turnos compartidos por varios usuarios en varios lugares, mientras que los turnos independientes se pueden utilizar solo por un trabajador cada vez.

Hay dos tipos de turnos de puntos de venta (PDV) comerciales: independientes y compartidos. Los turnos independientes solo pueden utilizarse por un trabajador cada vez. Los turnos compartidos se pueden utilizar por varios usuarios en varios lugares. Por tanto, crean de manera efectivamente un turno único para varios trabajadores de un almacén.

## <a name="standalone-shifts"></a>Turnos independientes
Los turnos independientes se utilizan en un escenario de PDV fijo tradicional, donde el efectivo se concilia de manera independiente para cada registro de PDV. Por ejemplo, en un entorno de supermercado, normalmente hay varios registrados de PDV fijos y se asigna un cajero a cada uno de ellos. En este caso, cada registro probablemente utiliza un turno independiente y el cajero es responsable de la caja registradora o del efectivo físico de ese registro. Un turno independiente abarca toda la actividad de ese registro durante el turno de trabajo del cajero. En las actividades se puede incluir el importe inicial que se deposita en la caja registradora, todas las eliminaciones y adiciones de operaciones de efectivo como ingresos bancarios y entrada flotante, y la declaración por forma de pago al final del turno.

### <a name="set-up-a-stand-alone-shift"></a>Configurar un turno independiente

Se designa un turno independiente en el nivel de caja registradora. Este procedimiento explica cómo configurar un turno independiente en un registro de PDV.

1.  Haga clic en **Retail** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de hardware**.
2.  Seleccione el perfil de hardware que se utilizará para el turno independiente.
3.  En la ficha desplegable **Cajón**, confirme que la opción **Caja registradora de turno compartido** está establecida en **No**.
4.  Haga clic en **Guardar**.
5.  Haga clic en **Venta minorista** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Registros**.
6.  Seleccione el registro que requiere un turno independiente y, a continuación, haga clic en **Editar**.
7.  En el campo **Perfil de hardware**, seleccione el perfil de hardware que seleccionó en el paso 2.
8.  Haga clic en **Guardar**.
9.  Haga clic en **Venta minorista** &gt; **TI de venta minorista** &gt; **Programación de distribución**.
10. Seleccione la programación de distribución **1090** y, a continuación, haga clic en **Ejecutar ahora** para sincronizar los cambios en el PDV.

### <a name="use-a-stand-alone-shift"></a>Usar un turno independiente

1.  Inicie sesión en el PDV.
2.  Si no hay ningún turno abierto, seleccione **Abrir un turno nuevo**.
3.  Vaya a la operación **Declarar importe inicial** y especifique el importe de efectivo que se agrega a la caja registradora para empezar el día de trabajo.
4.  Realice algunas transacciones.
5.  Al final del día, seleccione **Declarar forma de pago** para declarar el importe de efectivo que se mantiene en la caja registradora.
6.  Especifique el importe de efectivo y, a continuación, haga clic en **Guardar** para guardar la declaración por forma de pago.
7.  Seleccione **Cerrar turno** para cerrar el turno.

**Nota:** Hay otras operaciones disponibles durante el desplazamiento, en función de los procesos empresariales que están implementados. Las operaciones **Ingreso seguro**, **Ingreso bancario** y **Supresión de forma de pago** se pueden utilizar para quitar el dinero de la caja registradora durante el día o antes de cerrar el turno. Si hay poco dinero en la caja registradora, se puede utilizar la operación **Entrada flotante** para agregar efectivo a la caja registradora.

## <a name="shared-shifts"></a>Turnos compartidos
Se utiliza un turno compartido en un entorno donde varios cajeros comparten una caja registradora o varias cajas registradoras durante todo el día laborable. Normalmente, se utiliza un turno compartido en entornos de PDV móviles. En un entorno móvil, cada cajero no está asignado a una solo caja registradora ni es responsable de la misma. En su lugar, todos los cajeros deben poder presentar una venta y agregar efectivo a la caja registradora que se encuentre más cerca. En este escenario, las cajas registradoras que se comparten entre cajeros se incluyen en un turno compartido. Todas las cajas registradoras de un turno compartido se incluyen en el mismo turno para las actividades relacionadas con la administración de efectivo para ese turno. Por tanto, el importe inicial para el turno debe incluir la suma de todo el efectivo de todas las cajas registradoras que se incluyen en el turno compartido. Del mismo modo, la declaración por forma de pago será la suma de todo el efectivo de todas las cajas registradoras que se incluyen en el turno compartido. **Nota:** solo puede estar abierto un turno compartido cada vez en cada almacén. Los tunos compartidos e independientes se puede utilizar en el mismo almacén.

### <a name="set-up-a-shared-shift"></a>Configuración de un turno compartido

1.  Haga clic en **Retail** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de hardware**.
2.  Seleccione el perfil de hardware que se utilizará para el turno compartido.
3.  En la ficha desplegable **Cajón**, establezca la opción **Caja registradora de turno compartido** en **Sí**.
4.  Haga clic en **Guardar**.
5.  Haga clic en **Venta minorista** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Registros**.
6.  Seleccione el registro que requiere un turno compartido y, a continuación, haga clic en **Editar**.
7.  En el campo **Perfil de hardware**, seleccione el perfil de hardware que seleccionó en el paso 2.
8.  Haga clic en **Guardar**.
9.  Haga clic en **Venta minorista** &gt; **TI de venta minorista** &gt; **Programación de distribución**.
10. Seleccione la programación de distribución **1090** y, a continuación, haga clic en **Ejecutar ahora** para sincronizar los cambios en el PDV.

### <a name="use-a-shared-shift"></a>Usar un turno compartido

1.  Inicie sesión en el PDV.
2.  Si el PDV aún no está conectado a una estación de hardware, seleccione **Operación que no sea de categoría** y, a continuación, seleccione la operación **Seleccionar estación de hardware** para activar una estación de hardware para el turno compartido. Este paso solo es necesario la primera vez que se agrega un registro a un entorno de turno compartido.
3.  Cierre sesión del PDV y, a continuación, vuelva a iniciar sesión.
4.  Seleccione **Crear un turno nuevo**.
5.  Seleccione **Declarar importe inicial**.
6.  Escriba el importe inicial de todas las cajas registradoras del almacén que forman parte del turno compartido y, a continuación, haga clic en **Guardar**.
    -   Para agregar parte del importe inicial a cada caja registradora posterior, utilice la operación **Seleccionar estación de hardware** para activar la estación de hardware.
    -   Para agregar una caja registradora a un cajón de efectivo específico, utilice la operación **Abrir cajón**.
    -   Continúe hasta que todos los cajones de efectivo del turno compartido tengan su parte del importe inicial.

7.  Al final del día, abra cada caja registradora y extraiga el efectivo.
8.  Una vez haya extraído el efectivo de la última caja registradora, cuente todo el efectivo de todas las cajas registradoras.
9.  Utilice la operación **Declarar forma de pago** para declarar el importe total de efectivo de todas las cajas registradoras que se incluyen en el turno compartido.
10. Utilice la operación **Cerrar turno** para cerrar el turno compartido.





