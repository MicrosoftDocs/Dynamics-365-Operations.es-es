---
title: "Configuración de la funcionaidad de inicio de sesión extendido para Cloud POS y MPOS"
description: "En este tema se abordan las opciones de configuración de inicio de sesión extendido para PDV en la nube y Retail Modern POS (MPOS)."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3e9ce03dfdc5dc027344186e0334b2ac2bc9341e
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a>Configuración de la funcionaidad de inicio de sesión extendido para Cloud POS y MPOS

[!INCLUDE [banner](includes/banner.md)]

En este tema se abordan las opciones de configuración de inicio de sesión extendido para PDV en la nube y Retail Modern POS (MPOS).

## <a name="setting-up-extended-logon"></a>Configuración del inicio de sesión extendido

Puede encontrar la configuración de las máscaras de código de barras en **Retail** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Perfiles del PDV** &gt; **Perfiles de funcionalidad**. La ficha desplegable **Funciones** incluye las siguientes opciones que están relacionadas con el inicio de sesión extendido.

### <a name="staff-bar-code-logon"></a>Inicio de sesión de código de barras de personal

Cuando la opción **Inicio de sesión de código de barras del personal** se activa, los trabajadores que tienen un inicio de sesión extendido asignado a sus credenciales del punto de venta (PDV) pueden iniciar sesión mediante un código de barras.

### <a name="staff-bar-code-logon-requires-password"></a>El inicio de sesión de código de barras de personal requiere contraseña

Cuando se activa la opción **El inicio de sesión de código de barras del personal necesita contraseña**, el inicio de sesión de código de barras del personal selecciona únicamente el trabajador al que se la asignado el inicio de sesión extendido que se presenta. Los trabajadores aún tienen que especificar su contraseña cuando se activa esta opción.

### <a name="staff-card-logon"></a>Inicio de sesión de tarjeta de personal

Cuando la opción **Inicio de sesión de tarjeta del personal**, los trabajadores que tienen un inicio de sesión extendido asignado a sus credenciales del PDV pueden iniciar sesión mediante una barra magnética.

### <a name="staff-card-logon-requires-password"></a>El inicio de sesión de tarjeta de personal requiere contraseña

Cuando se activa la opción **El inicio de sesión de tarjeta del personal necesita contraseña**, el inicio de sesión de tarjeta del personal selecciona únicamente el trabajador al que se la asignado el inicio de sesión extendido que se presenta. Los trabajadores aún tienen que especificar su contraseña cuando se activa esta opción.

## <a name="assigning-an-extended-logon"></a>Asignación de un inicio de sesión extendido

De forma predeterminada, solo los directores pueden asignar el inicio de sesión extendido a los trabajadores. Para asignar el inicio de sesión extendido, vaya a **Inicio de sesión extendido** en PDV. A continuación, busque un trabajador introduciendo su id. de operador en el campo de búsqueda. Seleccione el trabajador y, a continuación, haga clic en la pestaña **Asignar**. En la siguiente página, pase o o escanee el inicio de sesión que desee asignar al trabajador. Si se lee correctamente, el botón **Aceptar** estará disponible. Haga clic en **Aceptar** para guardar el inicio de sesión extendido para dicho trabajador.

## <a name="deleting-an-extended-logon"></a>Eliminación de un inicio de sesión extendido

Para eliminar el inicio de sesión extendido que se asigna a un trabajador, busque el trabajador mediante la operación **Inicio de sesión extendido**. Seleccione el trabajador y, a continuación, haga clic en **Anular asignación**. Se eliminarán todas las credenciales de inicio de sesión extendidas asociadas con dicho trabajador.

## <a name="extending-extended-logon"></a>Extensión de inicio de sesión extendido

El servicio del inicio de sesión puede ser extendido para admitir dispositivos de inicio de sesión extendidos adicionales, como escáneres de la palma. Para obtener más información, consulte la documentación de extensibilidad del PDV.

## <a name="using-extended-logon"></a>Uso del inicio de sesión extendido

Cuando se configura el inicio de sesión extendido, y se le ha asignado a un trabajador un código de barras o una cinta magnética, el trabajador sólo tiene que pasar o escanear su tarjeta mientras se abre la página de inicio de sesión del PDV. Si una contraseña también es necesaria para que el inicio de sesión pueda continuar, se le pedirá al trabajador que especifique su contraseña.




