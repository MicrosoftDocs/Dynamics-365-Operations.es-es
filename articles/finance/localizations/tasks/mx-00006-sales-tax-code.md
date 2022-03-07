---
title: MX-00006 Configuración de un código de impuesto sobre las ventas
description: Los documentos financieros jurídicos, como declaraciones de impuestos o facturas electrónicas enviadas a las autoridades fiscales en México, deben contener distintos tipos de identificadores de registro de impuestos u otra información relacionada.
author: sndray
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxVatReportCategory_MX, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ee0b20ad2eeeaea7dd72dc458ded96299ca9aa4956c79ce838b7560c2baa8a8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738410"
---
# <a name="mx-00006-set-up-sales-tax-code"></a>MX-00006 Configuración de un código de impuesto sobre las ventas

[!include [banner](../../includes/banner.md)]

Los documentos financieros jurídicos, como declaraciones de impuestos o facturas electrónicas enviadas a las autoridades fiscales en México, deben contener distintos tipos de identificadores de registro de impuestos u otra información relacionada. Esta guía detalla de los pasos necesarios para completar la información sobre identificadores de registro en entidades jurídicas mexicanas.

1. Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.
2. Haga clic en Nuevo.
    * Si ha creado previamente su entidad jurídica para México, edite una entidad jurídica existente en lugar de crear una nueva.  
3. En el campo Nombre, escriba un valor.
4. En el campo Empresa, escriba un valor.
5. En el campo País o Región, seleccione el código de país o región.
6. Haga clic en Aceptar
7. Expanda o contraiga la sección Números de registro.
8. En el campo Tipo de empresa, seleccione una opción.
9. En el campo Número de RFC, escriba el número de RFC de 12 caracteres de la entidad jurídica.
    * El número de Registro Federal del Contribuyentes (RFC) es el número de identificación fiscal asignado por las autoridades fiscales a una persona o una corporación. El sistema valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.  
10. En el campo Número de CURP, escriba el número de CURP de 18 caracteres de la entidad jurídica.
    * El número de identificación de tarjeta fiscal único (CURP), que es el número de identificación fiscal asignado por las autoridades fiscales a una persona. El sistema valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.  Este campo es obligatorio cuando el campo RFC está vacío.  
11. En el campo Inscripción estatal, escriba un valor.
12. En el campo Representante legal, escriba un valor.
13. En el campo RFC de representante legal, escriba el número de RFC de 12 caracteres del representante de la entidad jurídica.
    * El sistema valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.  
14. En el campo CURP de representante legal, escriba el número de CURP de 12 caracteres del representante de la entidad jurídica.
    * El sistema valida los identificadores de registro de impuestos según el formato especificado por las autoridades fiscales de México.  
15. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]