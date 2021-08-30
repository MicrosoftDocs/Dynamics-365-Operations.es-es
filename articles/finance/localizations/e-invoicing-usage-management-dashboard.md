---
title: Panel de administración de uso
description: Este tema explica cómo usar el panel de administración de uso para monitorear el uso del servicio de Facturación Electrónica y seguir cumpliendo con las regulaciones.
author: gionoder
ms.date: 06/02/2021
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
ms.openlocfilehash: 35b50c8cb5c6ef72f466a4fb10c7af0e53afc3db5d1ef9e2b23d6049e24a70c3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776483"
---
# <a name="usage-management-dashboard"></a>Panel de administración de uso

[!include [banner](../includes/banner.md)]

El panel de **Gestión de uso** le ayuda a monitorear el uso del servicio de Facturación Electrónica y, por lo tanto, ayuda a su organización a seguir cumpliendo con las regulaciones según su uso mensual. El cumplimiento se determina calculando el volumen de envío y comparándolo con el volumen adquirido de envíos para identificar cualquier incoherencia entre el volumen adquirido y el volumen usado.

El panel incluye los siguientes indicadores:

- Un indicador de costes que puede usar para monitorear el consumo con fines de cumplimiento de licencias:

    - Utilización mensual (exportación)

- Tres indicadores operativos que puede utilizar para realizar un seguimiento del uso del servicio de Facturación electrónica con fines de gestión:

    - Uso por característica
    - Uso por entorno
    - Utilización mensual (importación)

## <a name="measurement-scope"></a>Ámbito de medidas

- Unidad de medida: 

    El panel de **Gestión de uso** cuenta la presentación de documentos comerciales y facturas electrónicas importadas.

- Organización: 

    El recuento se resume por el id. del inquilino de su organización, independientemente del número de instancias de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management, o el número de entidades jurídicas donde está habilitado el servicio de Facturación electrónica.


## <a name="indicator-usage-per-month-export"></a>Indicador: Uso por mes (exportación)

Este indicador proporciona detalles sobre las facturas electrónicas que su organización emite durante un período definido.

### <a name="scope"></a>Ámbito
- La cantidad de documentos comerciales que se envían desde Finance and Supply Chain Management al servicio de Facturación electrónica, independientemente del número de líneas que contengan esos documentos comerciales.
- La cantidad de documentos comerciales enviados que el servicio de Facturación electrónica procesa con éxito. Un documento se considera procesado correctamente cuando se completa el flujo de acciones que se definen en la configuración de funciones.

> [!NOTE]
> Cuando se envía una factura electrónica a un servicio web externo, el recuento es independiente de los resultados del procesamiento del servicio web (aceptado, rechazado o error de validación del esquema). Si el servicio web recibió y respondió a la solicitud del servicio de Facturación Electrónica, el envío se considera un recuento válido.

- **Excepción:** Los documentos comerciales no se cuentan si se vuelven a enviar desde Finance and Supply Chain Management al servicio de Facturación electrónica, como en los escenarios en los que se requiere un nuevo envío del mismo documento comercial para cambiar el estado de la factura electrónica. Por ejemplo, la emisión de una factura electrónica brasileña (documento fiscal) se cuenta como válida, pero la solicitud de cancelación no se cuenta.


### <a name="calculation"></a>Cálculo

El cálculo del saldo se calcula de la siguiente manera:

Saldo = Gratis + Comprado - Usado

Donde:

- Gratis:
  
    Un volumen gratuito de documentos comerciales que el cliente puede enviar por mes. Incluye un paquete de 100 documentos comerciales que se pueden enviar al servicio de Facturación Electrónica. El volumen libre no es acumulativo y el saldo restante no se transfiere al siguiente período.
  
- Comprado:
  
    Un paquete de 1000 documentos comerciales que se pueden enviar al servicio de Facturación Electrónica. Este paquete debe adquirirse para su organización mensualmente. El volumen comprado no es acumulativo y el saldo restante no se transfiere al siguiente período.
  
- Utilizado: 

    El recuento de envíos de documentos comerciales al servicio de Facturación Electrónica según criterios definidos.
   
> [!IMPORTANT]
> Si su organización planea exceder el volumen mensual de 100 envíos gratuitos, compre el volumen máximo para asegurarse de cumplir con la política de licencias de Microsoft para el servicio de facturación electrónica.
>
> Actualmente, el volumen comprado debe ingresarse manualmente, de acuerdo con la fecha de adquisición, como paquetes múltiples de 1000 envíos.

## <a name="indicator-usage-by-feature"></a>Indicador: uso por función

Este indicador muestra el uso de funciones de facturación electrónica para la emisión de facturas electrónicas durante un período definido.

- Cálculo:
  
    Usado = El recuento de cuántas veces se usó cada función de facturación electrónica durante el envío de documentos comerciales al servicio de facturación electrónica.

## <a name="indicator-usage-by-environment"></a>Indicador: uso por entorno

Este indicador muestra el uso de entornos de servicio de facturación electrónica durante un período definido.

- Cálculo:
    
    Usado = El recuento de cuántas veces se usó cada entorno de servicio de facturación electrónica durante el envío de documentos comerciales al servicio de facturación electrónica.

## <a name="indicator-usage-per-month-import"></a>Indicador: Uso por mes (importación)

Este indicador muestra el volumen de importación de facturas electrónicas por el servicio de Facturación Electrónica a Finance and Supply Chain Management durante un período definido.

- Ámbito:

    Facturas electrónicas que se importan a Finance and Supply Chain Management, independientemente del número de líneas que contengan esas facturas electrónicas.

- Cálculo:

    Recibido = El recuento de facturas electrónicas importadas en Finance and Supply Chain Management.

## <a name="functions"></a>Funciones
### <a name="purchase"></a>Compra

En la pestaña **Uso por mes (exportación)**, seleccione **Compra** para registrar manualmente la cantidad de envíos adquiridos.

Para una fecha determinada, seleccione **Nuevo** e ingrese el número de **Paquetes** adquiridos en esa fecha.

La **Cantidad** se calcula del modo siguiente:

Cantidad = Paquetes * 1000

La **Cantidad** calculada se refleja en **Comprado** desde el indicador **Uso por mes (exportación)**.

### <a name="update"></a>Actualización

En el panel de acciones, seleccione **Actualizar** para actualizar el cálculo y actualizar los datos que se muestran en la página y en el gráfico.

### <a name="reset-history-data"></a>Restablecer datos de historial

En el panel de acciones, seleccione **Restablecer los datos del historial** para actualizar la base de datos desde donde se calculan los indicadores.




> [!NOTE]
> El panel de **Gestión de uso** no muestra importes monetarios. En cambio, muestra solo el volumen de envíos contados y documentos importados.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
