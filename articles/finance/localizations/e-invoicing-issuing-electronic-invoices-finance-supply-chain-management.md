---
title: Emitir facturas electrónicas en Finance y Supply Chain Management
description: Este tema explica cómo emitir facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management a través del complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 187f5a20d088b4fcd7af2a6576357a69c2efc2c6
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104434"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Emitir facturas electrónicas en Finance y Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema explica cómo emitir facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management a través del complemento de facturación electrónica.


## <a name="feature-activation"></a>Activación de características

Para comenzar a emitir facturas electrónicas a través del complemento de facturación electrónica, es necesario activar la referencia de la característica en Finance y Supply Chain Management.

Cada referencia de característica corresponde a una característica de facturación electrónica específica que cumple con los requisitos de facturación electrónica de un país o región.

La siguiente tabla muestra la lista de referencias de características que admite el complemento de facturación electrónica.

| Referencia de la característica | Nombre                                              | País/región |
|-------------------|---------------------------------------------------|----------------|
| BR-00053          | NF-e federal: factura electrónica brasileña       | Brasil         |
| BR-00095          | Facturas electrónicas brasileñas NFS-e               | Brasil         |
| DK-00001          | Facturación electrónica al sector público (OIOUBL): DK    | Dinamarca        |
| EG-00008          | Facturación electrónica para Egipto                             | Egipto          |
| ES-00025          | Factura electrónica al sector público           | España          |
| EUR-00023         | Facturación electrónica en la Unión Europea al sector público (OIOUBL)       | Europa         |
| ITA-00036         | IT: facturación electrónica al sector público (FatturaPA) | Italia          |
| MX-00010          | Facturación electrónica de CFDI                                  | México         |
| MX-00016          | CFDI para facturación electrónica: proceso de cancelación           | México         |

En los casos en los que existe una característica de facturación electrónica heredada, compatible con el alcance de las localizaciones del país, la activación de la referencia de la característica permite la emisión de facturas electrónicas a través del complemento de facturación electrónica y desactiva la característica anterior.

## <a name="submit-electronic-documents"></a>Enviar documentos electrónicos

El proceso de envío de documentos electrónicos representa el único punto de comunicación entre Finance y Supply Chain Management y el complemento de facturación electrónica. Durante cada evento de envío, la comunicación fluye en ambas direcciones:

- **Desde Finance y Supply Chain Management al complemento de facturación electrónica**: Finance y Supply Chain Management envía las facturas resumidas al complemento de facturación electrónica. Según sea necesario, también envían el contenido de las variables que se configuraron como parte de las características de facturación electrónica.
- **Desde el complemento de facturación electrónica hasta Finance y Supply Chain Management**: dependiendo de la característica de facturación electrónica, Finance y Supply Chain Management reciben actualizaciones del complemento de facturación electrónica sobre los resultados de procesamiento de las facturas que se enviaron anteriormente. También envían el contenido de las variables que se configuraron como parte de las características de facturación electrónica.

Para enviar documentos electrónicos al complemento de facturación electrónica, en Finance y Supply Chain Management, vaya a **Administración de la organización &gt; Periódico &gt; Documentos electrónicos &gt; Enviar documentos electrónicos**.

El punto de partida es una factura contabilizada. Esta factura puede provenir de diferentes orígenes, como pedidos de ventas, facturas de proyectos o facturas de servicios.

El proceso de envío se puede ejecutar manualmente o en segundo plano.

- **Ejecución manual**: para la ejecución manual, debe utilizar la opción **Filtrar** para definir el rango de documentos que se deben enviar. En la página **Filtros**, puede configurar su propia consulta para seleccionar las facturas registradas que deben enviarse. Una vez realizada la selección, debe iniciar manualmente la ejecución del procesamiento y esperar a que termine de ejecutarse. Cuando se completa el procesamiento, un mensaje en el Centro de actividades muestra la cantidad de documentos electrónicos que se han enviado correctamente.
- **Ejecución en segundo plano**: la ejecución en segundo plano se ejecuta sin necesidad de iniciar sesión ni de mantener abierto el cuadro de diálogo de envío. Puede programar el proceso para que se ejecute y definir la frecuencia de ejecución.

## <a name="view-the-submission-logs"></a>Ver los registros de envío

En Finance y Supply Chain Management, puede utilizar los registros de envío para ver los resultados del procesamiento del envío al complemento de facturación electrónica. Vaya a **Administración de la organización &gt; Periódico &gt; Documentos electrónicos &gt; Envío de documentos electrónicos** y luego, en el campo **Tipo de Documento**, seleccione un valor para filtrar el tipo de facturas que muestran los registros.

Hay tres posibles estados de envío:

- **Programado**: el complemento de facturación electrónica recibió el envío de Finance y Supply Chain Management, y el procesamiento de la característica de facturación electrónica está en curso.
- **Terminado**: el complemento de facturación electrónica procesó correctamente la característica de facturación electrónica tal como estaba configurado para ejecutarla.
- **Errores**: el complemento de facturación electrónica encontró un error o lo detuvo una excepción durante el procesamiento de la característica de facturación electrónica.

> [!IMPORTANT]
> El estado de envío se refiere al estado del procesamiento que realiza el complemento de facturación electrónica en la característica de facturación electrónica. No se refiere al estado final de la propia factura electrónica.
>
> Por ejemplo, si una factura electrónica debe enviarse a un servicio web externo para su aprobación, el estado de envío podría ser **Completado**, pero el estado de la factura electrónica podría ser **Rechazado**. En este caso, el complemento de facturación electrónica fue capaz de procesar correctamente la característica de facturación electrónica tal y como estaba configurada para ejecutarla. Sin embargo, la factura electrónica se rechazó porque no cumplía con los criterios que el servicio web estableció para la aprobación de facturas.

Los registros de envío incluyen las siguientes características adicionales:

- **Detalles de envío**: ver los detalles del envío principal. La visualización muestra el registro de ejecución completo de las acciones que se configuran en la característica de facturación electrónica. También permite a los usuarios descargar los archivos que se crean durante el procesamiento. En escenarios donde la factura debe aprobarla un servicio web externo, permite a los usuarios ver el estado de la factura.
- **Envíos relacionados**: ver los detalles de los envíos de elementos secundarios.
- **Cancelar envíos**: esta característica habilita un proceso de envío especial en escenarios donde la factura electrónica debe aprobarla un servicio web externo. Instruye al complemento de facturación electrónica para enviar al servicio web un mensaje específico que tiene como objetivo cancelar el estado de una factura electrónica aprobada en la base de datos del servicio web.
- **Volver a enviar el documento**: reenviar un documento electrónico que ya se envió al complemento de facturación electrónica. Se crea un registro completamente nuevo en la página **Detalles de envío**.
- **Enviar envío relacionado**
