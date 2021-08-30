---
title: Mensajes electrónicos
description: Este tema proporciona información general y de configuración del correo electrónico en Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 06/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 191abc37b7c349aaf3c9e871fe2f1885eec9fc896271d6fac27e5caa0b0fe3b0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768348"
---
# <a name="electronic-messaging"></a>Mensajería electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona información general e información de configuración para la funcionalidad de **mensajes electrónicos** (EM).

Recientemente, los gobiernos y las autoridades legislativas de varios países y regiones en todo el mundo han implementado los requisitos de informe para las empresas que se registran en dichos países o regiones. El objetivo de los requisitos es habilitar que los datos que se obtienen de dichas empresas estén en formato electrónico, directamente desde sistemas donde se han contabilizado, almacenado, y procesado.

La funcionalidad EM en Microsoft Dynamics 365 Finance admite varios procesos de interoperación electrónica entre Finance y los sistemas que los gobiernos y las autoridades legislativas proporcionan para informar, enviar y recibir información oficial.

La funcionalidad de EM se integra con el módulo **Informes electrónicos** (ER). Puede configurar los formatos de ER para los mensajes electrónicos. Para obtener más información, consulte [Informes electrónicos (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Conceptos básicos para la funcionalidad EM

La funcionalidad de EM se basa en las siguientes entidades:

- **Mensaje electronico** - Un informe o declaración que se debe informar o transmitir internamente, como un informe que se envía a una oficina de impuestos.
- **Elementos del mensaje electrónico** Registros que se deben incluir en el mensaje que se notifica.
- **Procesamiento de mensaje electrónico**: una cadena de acciones que se debe ejecutar para obtener los datos necesarios, generar informes, almacenar datos en Azure Blob Storage, transmitir informes fuera del sistema, recibir respuestas que se encuentran fuera del sistema, y actualizar la base de datos, según la información que se recibe. Las acciones en la cadena pueden ser vinculadas o desvinculadas.

La ilustración siguiente muestra el flujo de datos de EM.

![Flujo de datos de mensajes electrónicos.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Escenarios compatibles con la funcionalidad EM

La funcionalidad de EM admite los escenarios siguientes:

- Crear manualmente los mensajes y generar los informes basados en formatos de ER asociados de exportación de distintos tipos. Estos tipos incluyen Microsoft Excel, XML, notación de objetos JavaScript (JSON), PDF, texto y Microsoft Word.
- Crear automáticamente y procesar mensajes que se basan en la información que se solicitó y se recibió de una autoridad usando un formato ER de importación asociado.
- Recopilar y procesar información de un origen de datos como elementos de mensaje. Origen de datos es una tabla Finance.
- Almacenar la información adicional, y evaluar los diversos valores llamando a clases ejecutables específicamente definidas en relación con mensajes o elementos de mensajes.
- Agregar información obtenida en elementos de mensaje, dividir dicha información por mensaje, y generar informes que se encuentran en formatos de ER asociados de exportación.
- Transmitir los informes que se generan a un servicio Web mediante la información de seguridad que se almacena en Azure Key Vault.
- Recibir una respuesta de un servicio Web, interpretar la respuesta, y actualizar los datos de Finance según sea adecuado.
- Almacenar y revisar todos los informes generados.
- Almacenar y revisar toda la información de registro relacionada con las acciones que se ejecutan para un mensaje o un elemento de mensaje.
- Controlar el procesamiento a través de distintos estados de mensaje y estados de elementos de mensaje.

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Funciones normativas específicas del país compatibles con la funcionalidad EM

La siguiente tabla proporciona información sobre algunas características normativas específicas de cada país que son compatibles con la funcionalidad EM.

| País     | Nombre de característica | Función de grabación de demostración |
|-------------|--------------|------------------------|
| España       | [Suministro inmediato de información del IVA, SII](../localizations/emea-esp-sii.md) | |
| Hungría     | [Sistema de facturación en línea](../localizations/emea-hun-online-invoicing.md) | |
| Reino Unido | [Crear impuestos digitales (MTD) - Envío de la declaración de IVA](../localizations/emea-gbr-mtd-vat-integration.md) | [Finance and Operations: Impuesto digital del Reino Unido: declaración de IVA en Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Lituania   | [Informes de i.SAF](../localizations/emea-ltu-isaf.md) | |
| Polonia      | [Declaración de IVA con registros (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Finance: Registros de auditoría de IVA SAF/JPK](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Países Bajos | [Declaración de IVA para Países Bajos](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| República Checa | [Declaración de IVA](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brasil      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Rusia      | [Declaración de IVA](../localizations/rus-vat-declaration.md) | |
| Rusia      | [Informes de contabilidad en formato electrónico](../localizations/rus-accounting-reporting.md) | |
| Rusia      | [Declaración de impuestos de ganancias](../localizations/rus-profit-tax-declaration.md) | |
| Rusia      | [Declaración de impuestos evaluada](../localizations/rus-assessed-tax-declaration.md) | |
| Rusia      | [Declaración de impuestos de transporte](../localizations/rus-transport-tax-declaration.md) | |
| Rusia      | [Declaración de impuestos de terreno](../localizations/rus-land-tax-declaration.md) | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

