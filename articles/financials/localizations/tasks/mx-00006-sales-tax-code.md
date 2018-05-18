--- 
title: "Configurar códigos de impuestos para México"
description: "Los documentos financieros jurídicos, como declaraciones de impuestos o facturas electrónicas enviadas a las autoridades fiscales en México, deben contener distintos tipos de identificadores de registro de impuestos u otra información relacionada."
author: sndray
manager: AnnBe
ms.date: 12/01/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1776aa62976916cdc3dc0c70ab8b59b234f9032f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-tax-codes-for-mexico"></a>Configurar códigos de impuestos para México

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los documentos financieros jurídicos, como declaraciones de impuestos o facturas electrónicas enviadas a las autoridades fiscales en México, deben contener distintos tipos de identificadores de registro de impuestos u otra información relacionada. Esta guía detalla todos los pasos necesarios para completar la información sobre identificadores de registro en entidades jurídicas mexicanas.

1. Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.
2. Haga clic en Nuevo.
    * Si ha creado previamente su entidad jurídica mexicana, podrá editar una entidad jurídica existente en lugar de crear una nueva.  
3. En el campo Nombre, escriba un valor.
4. En el campo Empresa, escriba un valor.
5. En el campo País o Región, seleccione el código de país o región.
6. Haga clic en Aceptar
7. Expanda o contraiga la sección Números de registro.
8. En el campo Tipo de empresa, seleccione una opción.
9. En el campo Número de RFC, escriba el número de RFC de 12 caracteres de la entidad jurídica.
    * El número de Registro Federal del Contribuyentes (RFC) es el número de identificación fiscal asignado por las autoridades fiscales a una persona o una corporación. Microsoft Dynamics AX valida los identificadores de impuestos según el formato especificado por las autoridades fiscales de México.  
10. En el campo Número de CURP, escriba el número de CURP de 18 caracteres de la entidad jurídica.
    * El número de identificación de tarjeta fiscal único (CURP), que es el número de identificación fiscal asignado por las autoridades fiscales a una persona.  Microsoft Dynamics AX valida los identificadores de impuestos según el formato especificado por las autoridades fiscales de México.  Este campo es obligatorio cuando el campo RFC está vacío.  
11. En el campo Inscripción estatal, escriba un valor.
12. En el campo Representante legal, escriba un valor.
13. En el campo RFC de representante legal, escriba el número de RFC de 12 caracteres del representante de la entidad jurídica.
    * Microsoft Dynamics AX valida los identificadores de impuestos según el formato especificado por las autoridades fiscales de México.  
14. En el campo CURP de representante legal, escriba el número de CURP de 12 caracteres del representante de la entidad jurídica.
    * Microsoft Dynamics AX valida los identificadores de impuestos según el formato especificado por las autoridades fiscales de México.  
15. Haga clic en Guardar.


