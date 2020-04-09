---
title: Concepto de empresa en Common Data Service
description: En este tema se describe la integración de datos de empresa entre Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9a39cf5fa980d9a815ba675e410589dbd1279c83
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172909"
---
# <a name="company-concept-in-common-data-service"></a>Concepto de empresa en Common Data Service

[!include [banner](../../includes/banner.md)]


En Finance and Operations, el concepto *empresa* es una construcción legal y una construcción empresarial. También es un límite de seguridad y visibilidad para los datos. Los usuarios trabajan siempre en el contexto de una sola empresa y la mayoría de los datos se clasifican por empresa.

Common Data Service no tiene un concepto equivalente. El concepto más cercano es *unidad de negocio*, que es un límite principalmente de seguridad y de visibilidad para los datos de usuario. Este concepto no tiene las mismas implicaciones legales o empresariales que el concepto de empresa.

Dado que la unidad de negocio y la empresa no son conceptos equivalentes, no es posible forzar una asignación uno a uno (1: 1) entre ellos para el propósito de la integración de Common Data Service. Sin embargo, dado que los usuarios deben, de forma predeterminada, poder ver los mismos registros en la aplicación y Common Data Service, Microsoft ha introducido una nueva entidad en Common Data Service que se denomina cdm\_Company. Esta entidad es equivalente a la entidad de empresa en la aplicación. Para ayudar a garantizar que la visibilidad de registros es equivalente entre la aplicación y Common Data Service de forma inmediata, se recomienda la siguiente configuración para los datos en Common Data Service:

+ Para cada registro de empresa de Finance and Operations que se habilite para escritura dual, se creará un registro cdm\_Company asociado.
+ Cuando se crea un registro cdm\_Company y se habilita para escritura dual, se crea una unidad de negocio predeterminada con el mismo nombre. Aunque se crea automáticamente un equipo predeterminado para esa unidad de negocio, la unidad de negocio no se utiliza.
+ Se crea un equipo independiente del propietario con el mismo nombre. También está asociado con la unidad de negocio.
+ De forma predeterminada, el propietario de cualquier registro que se crea y se escribe de forma dual en Common Data Service se establece en el equipo "propietario de DW" vinculado a la unidad de negocio asociada.

En la siguiente ilustración se muestra un ejemplo de esta configuración de datos en Common Data Service.

![Configuración de datos en Common Data Service](media/dual-write-company-1.png)

Debido a esta configuración, cualquier registro relacionado con la empresa USMF será propiedad de un equipo que está vinculado a la unidad de negocio de USMF en Common Data Service. Por lo tanto, cualquier usuario que tenga acceso a esa unidad de negocio con un rol de seguridad que se establezca en la visibilidad de nivel de unidad de negocio podrá ver dichos registros. El siguiente ejemplo muestra cómo se pueden utilizar los equipos para proporcionar acceso correcto a dichos registros.

+ La función de “director de ventas” se asigna a los miembros del equipo de “ventas de USMF”.
+ Los usuarios con el rol “director de ventas” pueden tener acceso a cualquier registro de la cuenta que sea miembro de la misma unidad de negocio.
+ El equipo de “ventas de USMF" está vinculado a la unidad de negocio de USMF antes mencionada.
+ Por lo tanto, los miembros del equipo de “ventas de USMF” pueden ver cualquier cuenta que sea propiedad del usuario de "USMF DW", que habría llegado de la entidad de la empresa USMF en Finance and Operations.

![Cómo se pueden usar los equipos](media/dual-write-company-2.png)

Como muestra la ilustración anterior, esta asignación 1:1 entre la unidad de negocio, la empresa y el equipo es solo un punto de partida. En este ejemplo, una nueva unidad de negocio “Europa” se crea manualmente en Common Data Service como principal para DEMF y ESMF. Esta nueva unidad de negocio raíz no está relacionada con la escritura dual. Sin embargo, se puede usar para dar a los miembros del “equipo de ventas EUR” acceso a los datos de la cuenta en DEMF y ESMF estableciendo la visibilidad de los datos en **BU principal/secundaria** en el rol de seguridad asociado.

Un tema final a discutir es cómo la escritura dual determina a qué equipo propietario debe asignar los registros. Este comportamiento se controla mediante el campo **Default owning team** en el registro cdm\_Company. Cuando el registro cdm\_Company está habilitado para la escritura dual, un complemento crea automáticamente la unidad de negocio asociada y el equipo propietario (si no existe ya) y establece el campo **Default owning team** . El administrador puede cambiar este campo a un valor distinto. Sin embargo, el administrador no puede desactivar el campo cuando la entidad está habilitada para la escritura dual.

> [!div class="mx-imgBorder"]
![Campo del equipo propietario predeterminado](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Fragmentación y arranque de la empresa

La integración de Common Data Service aporta paridad a la empresa mediante un identificador de empresa para fragmentar los datos. Como muestra la siguiente ilustración, todas las entidades específicas de la empresa se extienden de modo que tengan una relación muchos a uno (N: 1) con la entidad cdm\_Company.

> [!div class="mx-imgBorder"]
![Relación N: 1 entre una entidad específica de la empresa y la entidad cdm_Company](media/dual-write-bootstrapping.png)

+ Para los registros, después de que se agregua y se guarda una empresa, el valor pasa a ser de solo lectura. Por lo tanto, los usuarios deben asegurarse de que se selecciona la empresa correcta.
+ Solo los registros con datos de la empresa son aptos para la escritura dual entre la aplicación y Common Data Service.
+ Para los datos existentes de Common Data Service, pronto habrá una experiencia de arranque dirigida por el administrador.
