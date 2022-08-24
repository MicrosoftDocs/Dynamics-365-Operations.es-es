---
title: Informe de retención de impuestos para Indonesia
description: Este artículo explica cómo configurar y generar el informe de retención de impuestos para Indonesia.
author: AdamTrukawka
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.search.scope: ''
ms.openlocfilehash: 732db563532ebc46c7b9fc69c2aaa128640084f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282447"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Informe de retención de impuestos para Indonesia (ID-00005)

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar y generar el archivo de retención de impuestos PPH que las entidades legales en Indonesia utilizan para informar transacciones de retención en la aplicación e-Bupot.

La autoridad fiscal de Indonesia (DGT) determina que los empresarios sujetos a impuestos (PKP) que están registrados en KPP Pratama como retenedores / recaudadores de impuestos del impuesto sobre la renta (PPh) Artículo 23 y / o artículo 26 deben informar electrónicamente los Artículos 23 y 26 de la declaración del impuesto sobre la renta mediante el uso de la aplicación e-Bupot. 

- **Artículo 23** - El informe incluye todas las transacciones de retención de proveedores donde el código de país / región de la dirección principal es el código de Indonesia.
- **Artículo 26** - El informe incluye todas las transacciones de retención de proveedores donde el código de país / región de la dirección principal no es el código de Indonesia.

## <a name="prerequisites"></a>Requisitos previos

- La dirección principal de la entidad jurídica debe estar en Indonesia.
- La función **Retención de impuestos global** debe estar habilitada en el espacio de trabajo **Gestión de características**. Para obtener más información acerca de cómo habilitar características, consulte [Visión general de la Administración de características.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="download-electronic-reporting-configurations"></a>Descargar configuraciones de informes electrónicos

La generación de un archivo de importación se basa en configuraciones de informes electrónicos (ER). Para obtener más información sobre las capacidades y los conceptos de los informes configurables, consulte [Informes electrónicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para entornos de producción y pruebas de aceptación del usuario (UAT), siga las instrucciones de [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Para generar el archivo de importación, cargue las siguientes configuraciones desde el repositorio:

- **Modelo de declaración de impuestos.versión.93.xml** o posterior
- **Asignación de modelo de declaración de impuestos.versión.93.153.xml** o posterior
- **Importación del esquema WHT PPh.versión.93.14** o una versión posterior

## <a name="set-up-general-ledger-parameters"></a>Configurar los parámetros de Contabilidad general

1. Vaya a **Impuestos** \> **Configuración** \> **Parámetros de contabilidad general**.
2. En la pestaña **Retención de impuestos**, en el campo **Asignación de formato de declaración WHT**, seleccione **Importación del esquema WHT PPh (ID)**. 
3. Vaya a **Impuesto** \> **Configuración** \> **Retención de impuestos** \> **Tipos de ingresos de retención de impuestos** para configurar el tipo de ingreso de retención de impuestos **Kode Bukti Potong** y luego asigne los códigos a los grupos de retención de impuestos de artículos relacionados. Los códigos son necesarios para generar el archivo de integración mediante la aplicación e-Bupot. 

## <a name="generate-the-withholding-import-file"></a>Genere el archivo de importación de retenciones

El proceso de preparación y generación del archivo e-Bupot para un período específico se basa en las transacciones de retención de impuestos que se contabilizaron durante el trabajo de liquidación o contabilización de pago de impuestos.

Para generar el archivo, siga estos pasos.

1. Vaya a **Impuesto** \> **Declaraciones** \> **Retención de impuestos** \> **Archivo de importación PPH e-bupot 23 y 26**.
2. Seleccione la fecha de inicio y finalización para el informe y luego seleccione el período de liquidación.
3. Escriba la fecha de la transacción y luego seleccione **Aceptar**.
4. Seleccione el idioma. Todos los informes están traducidos al inglés de EE. UU. (**en-us**) e indonesio (**id**).
5. Seleccione el tipo de negocio y luego introduzca los números de cheque y documento. 
6. Compruebe si el administrador ha firmado el informe. Esta información se notifica en el archivo. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
