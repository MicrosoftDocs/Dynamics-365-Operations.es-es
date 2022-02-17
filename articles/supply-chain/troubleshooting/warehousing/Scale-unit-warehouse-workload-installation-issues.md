---
title: Se producen problemas de procesamiento después de instalar una carga de trabajo de almacén de unidades de escala
description: Este tema describe los problemas que pueden ocurrir poco después de instalar una carga de trabajo de almacén de unidades de báscula y brinda consejos para solucionarlos.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071653"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>Se producen problemas de procesamiento después de instalar una carga de trabajo de almacén de unidades de escala

Este tema describe los problemas que pueden ocurrir poco después de instalar una carga de trabajo de almacén de unidades de báscula y brinda consejos para solucionarlos.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>Problema 1: error después de que se libera una carga de un banco de trabajo de planificación de carga

### <a name="symptoms-of-issue-1"></a>Síntomas del problema 1

Cuando suelta una carga desde la página **Banco de trabajo de planificación de carga** o **Banco de trabajo de planificación de carga saliente**, recibe un mensaje de error que tiene el siguiente formato:

> Se produjo una excepción al registrar la carga %1. No se pudo liberar la carga.
> 
> ACTUALIZAR CONJUNTO DE TABLA DE ENVÍO...
> 
> No se puede editar un registro en Envíos (WHSShipmentTable). Id. del envío: ...

Aquí hay un ejemplo real que incluye datos de muestra:

> Se produjo una excepción al registrar la carga USMF-000033. No se pudo liberar la carga.
Sesión 5133 (administrador)
>
> ACTUALIZAR WHSSHIPMENTTABLE SET ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? DONDE ((RECID=?) Y (RECVERSION=?))  
> [Microsoft][Controlador ODBC 17 para SQL Server][SQL Server]La unidad de escala @@ intentó actualizar los registros propiedad de la unidad de escala @A.  
> Servidor de objetos de Azure:
>
> No se puede editar un registro en Envíos (WHSShipmentTable). Id. del envío: USMF-000031, USMF-000033. La base de datos SQL ha emitido un error.

### <a name="cause-of-issue-1"></a>Causa del problema 1

Este problema puede ocurrir si existe la siguiente combinación de condiciones al instalar la carga de trabajo del almacén de unidades de báscula:

- El sistema incluye una carga no liberada donde varias líneas están asociadas con diferentes pedidos y algunas líneas de carga no están asociadas con un envío.
- El sistema está configurado para utilizar la consolidación de envíos.

En una implementación de topología híbrida distribuida, cada registro de carga y envío se marca como propiedad de una unidad de escala o concentrador específico. Cuando suelta una carga de la página **Banco de trabajo de planificación de carga**, el sistema cambia la propiedad asignada. Sin embargo, debido a las condiciones enumeradas anteriormente, es posible que el sistema no pueda resolver la propiedad de los datos. Por lo tanto, no logra liberar la carga al almacén.

### <a name="resolution-of-issue-1"></a>Resolución del problema 1

Divida la carga en dos cargas más pequeñas antes de enviarla al almacén.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>Problema 2: error mientras se procesa una ola en una unidad de escala

### <a name="symptoms-of-issue-2"></a>Síntomas del problema 2

Cuando está procesando una ola en una unidad de escala, recibe un mensaje de error que tiene el siguiente formato:

> No puede modificar la línea de carga con RecId = %1, id. de carga = %2 ya que todavía es propiedad del centro de la empresa. Asegúrese de que la carga de salida correspondiente se haya liberado a una unidad de báscula y, por lo tanto, se hayan creado líneas de pedido de almacén.

Aquí hay un ejemplo real que incluye datos de muestra:

> Registro de información para el trabajo Ejecutar onda USMF-000000012 (9223377668365210)  
> Registro de información para la tarea Ejecutar onda USMF-000000012 (9223377668370462)  
> No puede modificar la línea de carga con RecId = 68719478242, id. de carga = USMF-000034 ya que todavía es propiedad del centro de la empresa. Asegúrese de que la carga de salida correspondiente se haya liberado a una unidad de báscula y, por lo tanto, se hayan creado líneas de pedido de almacén.

### <a name="cause-of-issue-2"></a>Causa del problema 2

En una implementación de topología híbrida distribuida, la propiedad de los datos de carga y envío se asignan a una marca unidad de escala o concentrador específico. Como parte del procesamiento de ondas, se espera que la propiedad de los datos se asigne a una unidad de escala.

Cuando instala una carga de trabajo de almacén de unidades de escala, si un envío abierto está asociado con una carga y una oleada, el sistema no puede controlar la propiedad de los datos. Por lo tanto, el procesamiento de ondas falla en la unidad de escala.

### <a name="resolution-of-issue-2"></a>Resolución del problema 2

Liberar la carga al almacén del centro.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>Solucionar problemas al ver la propiedad y el destino de un registro

En una implementación de topología híbrida distribuida, muchos tipos de registros se marcan como propiedad de una unidad de escala o concentrador específico. Después de cambiar a una topología híbrida distribuida y/o configurar una nueva carga de trabajo de almacén de unidades de escala, el sistema asigna la propiedad a cada registro relevante. Este proceso a veces puede producir errores o resultados inesperados. Por lo tanto, la información sobre la propiedad de un registro y el destino de la transferencia pueden ayudarlo a solucionar problemas que ocurren después de realizar ese tipo de cambios.

Siga estos pasos para ver la propiedad y el destino de la transferencia de un registro.

1. Abra el registro relevante.
1. En el Panel de acciones, en la ficha **Opciones**, en el grupo **Info del registro**, seleccione **Mostrar todos los campos**.
1. La página que aparece muestra todos los valores de todos los campos que están disponibles para el registro seleccionado. Revise los siguientes campos:

    - **SYSSCALEUNITID** – Este campo muestra el propietario actual del registro.
    - **SYSTARGETSCALEUNITID** – Este campo muestra el ID de unidad de báscula del concentrador o unidad de báscula al que se transferirá el registro cuando el propietario actual haya terminado de trabajar con él. El valor de este campo lo utilizan los trabajos por lotes que gestionan este tipo de proceso. Aunque este campo no está directamente relacionado con la propiedad, la propiedad puede cambiar cuando se transfiere el registro. En algunos cassos, este campo estará en blanco.
