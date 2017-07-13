---
title: "Configuración de la funcionaidad de inicio de sesión extendido para Cloud POS y MPOS"
description: "En este tema se abordan las opciones de configuración de inicio de sesión extendido para PDV en la nube y Retail Modern POS (MPOS)."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 0b7e5ed451497aea1c2ce798af2b717705538d47
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017



---

# Configuración de la funcionaidad de inicio de sesión extendido para Cloud POS y MPOS
<a id="set-up-extended-logon-functionality-for-cloud-pos-and-mpos" class="xliff"></a>

[!include[banner](includes/banner.md)]


En este tema se abordan las opciones de configuración de inicio de sesión extendido para PDV en la nube y Retail Modern POS (MPOS).

Configuración del inicio de sesión extendido
<a id="setting-up-extended-logon" class="xliff"></a>
=========================

Puede encontrar la configuración de las máscaras de código de barras en **Retail** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Perfiles del PDV** &gt; **Perfiles de funcionalidad**. La ficha desplegable **Funciones** incluye las siguientes opciones que están relacionadas con el inicio de sesión extendido.

### Inicio de sesión de código de barras de personal
<a id="staff-bar-code-logon" class="xliff"></a>

Cuando la opción **Inicio de sesión de código de barras del personal** se activa, los trabajadores que tienen un inicio de sesión extendido asignado a sus credenciales del punto de venta (PDV) pueden iniciar sesión mediante un código de barras.

### El inicio de sesión de código de barras de personal requiere contraseña
<a id="staff-bar-code-logon-requires-password" class="xliff"></a>

Cuando se activa la opción **El inicio de sesión de código de barras del personal necesita contraseña**, el inicio de sesión de código de barras del personal selecciona únicamente el trabajador al que se la asignado el inicio de sesión extendido que se presenta. Los trabajadores aún tienen que especificar su contraseña cuando se activa esta opción.

### Inicio de sesión de tarjeta de personal
<a id="staff-card-logon" class="xliff"></a>

Cuando la opción **Inicio de sesión de tarjeta del personal**, los trabajadores que tienen un inicio de sesión extendido asignado a sus credenciales del PDV pueden iniciar sesión mediante una barra magnética.

### El inicio de sesión de tarjeta de personal requiere contraseña
<a id="staff-card-logon-requires-password" class="xliff"></a>

Cuando se activa la opción **El inicio de sesión de tarjeta del personal necesita contraseña**, el inicio de sesión de tarjeta del personal selecciona únicamente el trabajador al que se la asignado el inicio de sesión extendido que se presenta. Los trabajadores aún tienen que especificar su contraseña cuando se activa esta opción.

Asignación de un inicio de sesión extendido
<a id="assigning-an-extended-logon" class="xliff"></a>
===========================

De forma predeterminada, solo los directores pueden asignar el inicio de sesión extendido a los trabajadores. Para asignar el inicio de sesión extendido, vaya a **Inicio de sesión extendido** en PDV. A continuación, busque un trabajador introduciendo su id. de operador en el campo de búsqueda. Seleccione el trabajador y, a continuación, haga clic en la pestaña **Asignar**. En la siguiente página, pase o o escanee el inicio de sesión que desee asignar al trabajador. Si se lee correctamente, el botón **Aceptar** estará disponible. Haga clic en **Aceptar** para guardar el inicio de sesión extendido para dicho trabajador.

Eliminación de un inicio de sesión extendido
<a id="deleting-an-extended-logon" class="xliff"></a>
==========================

Para eliminar el inicio de sesión extendido que se asigna a un trabajador, busque el trabajador mediante la operación **Inicio de sesión extendido**. Seleccione el trabajador y, a continuación, haga clic en **Anular asignación**. Se eliminarán todas las credenciales de inicio de sesión extendidas asociadas con dicho trabajador.

Extensión de inicio de sesión extendido
<a id="extending-extended-logon" class="xliff"></a>
========================

El servicio del inicio de sesión puede ser extendido para admitir dispositivos de inicio de sesión extendidos adicionales, como escáneres de la palma. Para obtener más información, consulte la documentación de extensibilidad del PDV.

Uso del inicio de sesión extendido
<a id="using-extended-logon" class="xliff"></a>
====================

Cuando se configura el inicio de sesión extendido, y se le ha asignado a un trabajador un código de barras o una cinta magnética, el trabajador sólo tiene que pasar o escanear su tarjeta mientras se abre la página de inicio de sesión del PDV. Si una contraseña también es necesaria para que el inicio de sesión pueda continuar, se le pedirá al trabajador que especifique su contraseña.




