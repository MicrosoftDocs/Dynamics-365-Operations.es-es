---
title: Mensajes electrónicos
description: Este artículo proporciona información general y de configuración del correo electrónico en Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 01/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 4e765c6d56e0ab6d209c27a70fd4b7e52273c103
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069892"
---
# <a name="electronic-messaging"></a>Mensajes electrónicos

[!include [banner](../includes/banner.md)]

Este artículo proporciona información general e información de configuración para la funcionalidad de **mensajes electrónicos** (EM).

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

## <a name="security-privileges"></a>Privilegios de seguridad

Los siguientes privilegios de seguridad están disponibles para mensajes electrónicos.

| Privilegio de seguridad           | Nivel de acceso | Asociación |
|------------------------------|--------------|-------------|
| Mantener mensajes electrónicos | Este privilegio brinda acceso completo a la funcionalidad EM. Si tiene este privilegio, puede configurar la mensajería electrónica y ejecutar todo el procesamiento. | Este privilegio está incluido en el deber de seguridad **Mantener las transacciones de impuestos sobre las ventas**. Ese deber, a su vez, está incluido en el rol de seguridad **Contador**. |
| Visualizar mensajes electrónicos     | Este privilegio brinda acceso de solo lectura a la funcionalidad EM. Si tiene este privilegio, puede ver la configuración de mensajería electrónica y los mensajes. Sin embargo, no puede configurar ni ejecutar nada. | Este privilegio está incluido en el deber de seguridad **Consultar el estado de transacciones de impuestos**. Ese deber, a su vez, está incluido los siguientes roles de seguridad:<ul><li>Administrador de cobros</li><li>Funcionario de clientes</li><li>Administrador de clientes</li><li>Contable de impuestos</li><li>Contable</li><li>Administrador contable</li><li>Supervisor contable</li><li>Director de ventas</li><li>Funcionario de proveedores</li></ul> |
| Operar mensajes electrónicos  | Este privilegio da acceso solo a las páginas **Mensajes electronicos** y **Elementos de mensaje electrónico**. Si tiene este privilegio, puede ejecutar todo el procesamiento que se llama desde esas páginas. | Este privilegio está incluido en el deber de seguridad **Operar mensajes electrónicos**. Ese deber, a su vez, está incluido en el rol de seguridad **Operador de mensajes electrónicos**. |

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Funciones normativas específicas del país compatibles con la funcionalidad EM

La siguiente tabla proporciona información sobre algunas características normativas específicas de cada país que son compatibles con la funcionalidad EM.

| País     | Nombre de característica | Función de grabación de demostración |
|-------------|--------------|------------------------|
| España       | [Suministro inmediato de información del IVA, SII](../localizations/emea-esp-sii.md) | |
| Hungría     | [Sistema de facturación en línea](../localizations/emea-hun-online-invoicing.md) | |
| Reino Unido | [Crear impuestos digitales (MTD) - Envío de la declaración de IVA](../localizations/emea-gbr-mtd-vat-integration.md) | [Finanzas y operaciones: Impuesto digital del Reino Unido: declaración de IVA en Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
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
| Noruega      | [Devolución de IVA con envío directo a Altinn](../localizations/emea-nor-vat-return.md) | [Nueva devolución de IVA con envío directo a Altinn en Dynamics 365 Finance](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/new-vat-return-with-direct-submission-to-altinn-in-dynamics-365-finance-december-1-2021) |
| Francia      | [Informe declarativo de VAT (Francia)](../localizations/emea-fra-VAT-declaration-preview-France.md) | |
| Austria     | [Declaración de IVA (Austria)](../localizations/emea-aut-vat-declaration-austria.md) | |
| Alemania     | [Declaración de IVA (Alemania)](../localizations/emea-deu-vat-declaration-germany.md) | |
| Países Bajos | [Declaración de IVA para Países Bajos](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Suecia      | [Declaración de IVA (Suecia)](../localizations/emea-swe-VAT-declaration-Sweden.md) | |
| Suiza | [Declaración de IVA (Suiza)](../localizations/emea-che-vat-declaration-switzerland.md) | |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]


