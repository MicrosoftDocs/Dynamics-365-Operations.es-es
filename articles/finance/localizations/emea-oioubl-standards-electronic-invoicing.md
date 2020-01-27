---
title: Estándares compatibles para la facturación electrónica en Europa
description: Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.
author: mrolecki
manager: AnnBe
ms.date: 07/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2fb188498705dcbad841645ced43e6a1715cbbd0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915166"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a>Estándares compatibles para la facturación electrónica en Europa

[!include [banner](../includes/banner.md)]

Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa. 

La implementación y la adopción de la facturación electrónica a escala de la Unión Europea está regulada por la [Directiva del Consejo 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), que afecta a todos los estados miembros de la UE. Las empresas que desean beneficiarse de la facturación electrónica deben enviar las facturas de pedido de ventas, facturas de servicios, facturas de proyecto, notas de abono de pedidos de ventas, y notas de crédito de la factura de proyecto como archivos .xml al gobierno u otras partes comerciales que ordenen el uso de la facturación electrónica. Estos archivos .xml deben cumplir determinados estándares. Los requisitos específicos de país y la implementación pueden ser diferentes en los estados miembros de la UE, pero suelen usar Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) en diferentes versiones con personalizaciones junto con [PEPPOL](https://www.peppol.eu) especificaciones y puntos de acceso para la validación y el transporte. La ventaja principal del UBL es que los documentos empresariales se pueden estandarizar para distintos fines. Dado que el UBL es una norma flexible e internacional que admite muchos requisitos empresariales, estos documentos empresariales se pueden intercambiar a través de las fronteras nacionales.

## <a name="what-electronic-invoice-formats-are-currently-available-in-dynamics-365-finance"></a>¿Qué formatos de factura electrónica se encuentran disponibles en Dynamics 365 Finance?

Los formatos específicos de país siguientes de facturas electrónicas están disponibles:

-   OIOUBL v.2.02 para Dinamarca
-   EHF v.3.0 para Noruega
-   PEPPOL BIS v. 2 para Austria, Francia, y Bélgica
-   UBL-OHNL 1.9 para los Países Bajos
-   FacturaE v.3.2.1 para España
-   FatturaPA v.1.2 para Italia
-   xRechnung v.1.2 para Alemania
-   Abrir PEPPOL BIS Billing v.3.0 para la Unión Europea

La facturación electrónica se basa en [Informes electrónicos (ER)](../../dev-itpro/analytics/general-electronic-reporting.md). Un modelo de datos **Modelo de factura de cliente** y varias configuraciones de formato específicos de país/región se han creado para Austria (AT), Dinamarca (DK), Italia (IT), Noruega (NO), España (ES), Francia (FR), Bélgica (BE), Países Bajos (NL), Alemania (DE) y la Unión Europa (EU).

-   Factura de ventas de OIOUBL - para AT, DK, y NO
-   Nota de abono de OIOUBL - para AT, DK, y NO
-   Factura de proyecto de OIOUBL - para AT, DK, y NO
-   Nota de abono de proyecto OIOUBL - para AT, DK, y NO
-   Factura de ventas de UBL para FR
-   Nota de abono de ventas de UBL para FR
-   Factura del proyecto de UBL para FR
-   Nota de abono de proyecto de UBL para FR
-   Factura de ventas de UBL para BE
-   Nota de abono de ventas de UBL para BE
-   Factura de proyecto de UBL para BE
-   Nota de abono de proyecto de UBL para BE
-   Factura de ventas de UBL para NL
-   Nota de abono de ventas de UBL para NL
-   Factura de proyecto de UBL para NL
-   Nota de abono de proyecto de UBL para NL 
-   Factura de ventas (ES)
-   Factura de ventas (IT)
-   Factura de proyecto (ES)
-   Factura de proyecto (IT)
-   Factura de ventas DE
-   Factura de proyecto DE
-   Factura de ventas de Peppol - para la UE
-   Nota de crédito de ventas de Peppol - para la UE
-   Factura de proyecto de Peppol - para la UE
-   Nota de crédito de proyecto de Peppol - para la UE

Las facturas electrónicas y las notas de abono que genera incluyen la información requerida, como el número EAN (número europeo de artículo), la persona de contacto, el número de la cuenta de dimensión y la información de la dirección del cliente. Se aplican reglas de validación cuando se generan facturas, de modo que puede verificar que se haya especificado la información correcta. El conjunto de información necesaria puede ser diferente de un país a otro. Como los requisitos, al igual que los formatos y los países admitidos, están sujetos a cambios, debe ir siempre a la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS) y ver la lista más actualizada de archivos disponibles que tienen un tipo de activo de **configuración de GER**.

## <a name="additional-information"></a>Información adicional
Para obtener más información acerca de cómo configurar facturas electrónicas, puede reproducir las siguientes [Guías de la tarea](../../fin-and-ops/get-started/help-overview.md#task-guides) en el panel de la Ayuda:

 - Configurar la facturación electrónica OIOUBL
 - Importar configuraciones de facturación electrónica OIOUBL
 - Configurar cuentas de cliente para la facturación electrónica OIOUBL

> [!NOTE] 
> Aunque estas guías de la tarea fueron creadas para el formato de factura *OIOUBL* específicamente danés, son aplicables en otros países compatibles con desviaciones de menor importancia.
