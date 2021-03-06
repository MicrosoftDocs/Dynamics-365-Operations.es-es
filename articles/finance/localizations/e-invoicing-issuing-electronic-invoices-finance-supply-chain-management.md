---
title: Emitir facturas electrónicas en Finance y Supply Chain Management
description: Este tema explica cómo emitir facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management mediante facturación electrónica.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8d6ef59b64a96e13bdc2e5ddf299ef7ab98e105c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840085"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Emitir facturas electrónicas en Finance y Supply Chain Management

[!include [banner](../includes/banner.md)]

Este tema explica cómo emitir facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management mediante facturación electrónica.


## <a name="feature-activation"></a>Activación de características

Para emitir facturas electrónicas mediante facturación electrónica, debe activar la característica en Finance y Supply Chain Management.

Cada característica corresponde a una característica de facturación electrónica específica que cumple con los requisitos de facturación electrónica de un país o región.

La siguiente tabla muestra la lista de características que puede admitir la facturación electrónica.

| Nombre                                              | País/región |
|---------------------------------------------------|----------------|
|Factura electrónica para Austria                        |Austria         |
|Factura electrónica para Bélgica                         |Bélgica         |
|NF-e federal: factura electrónica brasileña       |Brasil          |
|NFS-e: factura electrónica de servicios para Brasil (ciudad)|Brasil          |
|Factura electrónica para Dinamarca                          |Dinamarca         |
|Factura electrónica para Egipto                        |Egipto           |
|Factura electrónica para Estonia                        |Estonia         |
|Factura electrónica para Finlandia                         |Finlandia         |
|Factura electrónica para Francia                          |Francia          |
|Factura electrónica para Alemania                          |Alemania         |
|PEPPOL: factura electrónica global                 |Global          |
|Factura electrónica para Italia                         |Italia           |
|CFDI: factura electrónica para México                  |México          |
|Factura electrónica para Holanda                           |Países Bajos     |
|Factura electrónica para Noruega                       |Noruega          |
|Factura electrónica para España                         |España           |

En los casos en los que exista una característica de facturación electrónica heredada, compatible con el ámbito de las localizaciones de país o región, la activación de una de estas características desactiva la característica heredada y permite la emisión de facturas electrónicas a través de la facturación electrónica.

> [!IMPORTANT]
> Una vez habilitada la función de integración del complemento de facturación electrónica, la nueva experiencia de facturación electrónica se desactiva de forma predeterminada. Puede utilizar el concepto de característica para habilitar de forma selectiva nuevas experiencias para las entidades jurídicas que utilizan la funcionalidad específica del país o región. La opción **Global** controla la nueva experiencia para los condados o regiones restantes que no se enumeran específicamente en la tabla.

## <a name="submit-electronic-documents"></a>Enviar documentos electrónicos

El proceso de envío de documentos electrónicos representa el único punto de comunicación entre Finance y Supply Chain Management con la facturación electrónica. Durante cada evento de envío, la comunicación fluye en ambas direcciones:

- **Desde Finance y Supply Chain Management a la facturación electrónica**: Finance y Supply Chain Management envían las facturas resumidas a la facturación electrónica. Según sea necesario, también envían el contenido de las variables que se configuraron como parte de las características de facturación electrónica.
- **Desde la facturación electrónica hasta Finance y Supply Chain Management**: dependiendo de la característica de facturación electrónica, Finance y Supply Chain Management reciben actualizaciones desde la facturación electrónica sobre los resultados de procesamiento de las facturas que se enviaron anteriormente. También envían el contenido de las variables que se configuraron como parte de las características de facturación electrónica.

Para enviar documentos electrónicos a la facturación electrónica, en Finance y Supply Chain Management, vaya a **Administración de la organización &gt; Periódico &gt; Documentos electrónicos &gt; Enviar documentos electrónicos**.

El punto de partida es una factura contabilizada. Esta factura puede provenir de diferentes orígenes, como pedidos de ventas, facturas de proyectos o facturas de servicios.

El proceso de envío se puede ejecutar manualmente o en segundo plano.

- **Ejecución manual**: para la ejecución manual, debe utilizar la opción **Filtrar** para definir el rango de documentos que se deben enviar. En la página **Filtros**, puede configurar su propia consulta para seleccionar las facturas registradas que deben enviarse. Una vez realizada la selección, debe iniciar manualmente la ejecución del procesamiento y esperar a que termine de ejecutarse. Cuando se completa el procesamiento, un mensaje en el Centro de actividades muestra la cantidad de documentos electrónicos que se han enviado correctamente.
- **Ejecución en segundo plano**: la ejecución en segundo plano se ejecuta sin necesidad de iniciar sesión ni de mantener abierto el cuadro de diálogo de envío. Puede programar el proceso para que se ejecute y definir la frecuencia de ejecución.

## <a name="view-the-submission-logs"></a>Ver los registros de envío

En Finance y Supply Chain Management, puede utilizar los registros de envío para ver los resultados del procesamiento del envío a la facturación electrónica. Vaya a **Administración de la organización &gt; Periódico &gt; Documentos electrónicos &gt; Envío de documentos electrónicos** y luego, en el campo **Tipo de Documento**, seleccione un valor para filtrar el tipo de facturas que muestran los registros.

Hay tres posibles estados de envío:

- **Programado**: la facturación electrónica recibió el envío de Finance y Supply Chain Management, y el procesamiento de la característica de facturación electrónica está en curso.
- **Terminado**: la facturación electrónica procesó correctamente la característica de facturación electrónica tal como estaba configurada para ejecutarla.
- **Errores**: la facturación electrónica encontró un error o la detuvo una excepción durante el procesamiento de la característica de facturación electrónica.

> [!IMPORTANT]
> El estado de envío se refiere al estado del procesamiento que realiza la facturación electrónica en la característica de facturación electrónica. No se refiere al estado final de la propia factura electrónica.
>
> Por ejemplo, si una factura electrónica debe enviarse a un servicio web externo para su aprobación, el estado de envío podría ser **Completado**, pero el estado de la factura electrónica podría ser **Rechazado**. En este caso, la facturación electrónica resultó capaz de procesar correctamente la característica de facturación electrónica tal y como estaba configurada para ejecutarla. Sin embargo, la factura electrónica se rechazó porque no cumplía con los criterios que el servicio web estableció para la aprobación de facturas.

Los registros de envío incluyen las siguientes características adicionales:

- **Detalles de envío**: ver los detalles del envío principal. La visualización muestra el registro de ejecución completo de las acciones que se configuran en la característica de facturación electrónica. También permite a los usuarios descargar los archivos que se crean durante el procesamiento. En escenarios donde la factura debe aprobarla un servicio web externo, permite a los usuarios ver el estado de la factura.
- **Envíos relacionados**: ver los detalles de los envíos de elementos secundarios.
- **Cancelar envíos**: esta característica habilita un proceso de envío especial en escenarios donde la factura electrónica debe aprobarla un servicio web externo. Instruye a la facturación electrónica para enviar al servicio web un mensaje específico que tiene como objetivo cancelar el estado de una factura electrónica aprobada en la base de datos del servicio web.
- **Volver a enviar el documento**: reenviar un documento electrónico que ya se envió a la facturación electrónica. Se crea un nuevo registro en la página **Detalles de envío**.
- **Enviar envío relacionado**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
