---
title: Automatización del proceso de cobros
description: Este tema describe el proceso de configuración de estrategias de procesos de cobro que identifican automáticamente las facturas de los clientes que requieren un recordatorio por correo electrónico, una actividad de cobro (como una llamada telefónica) o una carta de cobro que se enviará al cliente.
author: panolte
manager: AnnBe
ms.date: 08/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: a63058904df72a7fda5a67ed1e6a846eed393ce0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969710"
---
# <a name="collections-process-automation"></a>Automatización del proceso de cobros

[!include [banner](../includes/banner.md)]

Este tema describe el proceso de configuración de estrategias de procesos de cobro que identifican automáticamente las facturas de los clientes que requieren un recordatorio por correo electrónico, una actividad de cobro (como una llamada telefónica) o una carta de cobro que se enviará al cliente. 

Las organizaciones dedican una cantidad significativa de tiempo a investigar informes de saldos antiguos, cuentas de clientes y facturas abiertas para determinar qué clientes deben ser contactados sobre una factura abierta o un saldo de cuenta. Esta investigación le quita tiempo al agente de cobros que dedica a comunicarse con los clientes para cobrar saldos deudores o resolver disputas de facturas. La automatización del proceso de cobros le permite configurar un enfoque basado en estrategias para su proceso de cobros. Esto le ayuda a aplicar las actividades de cobros de manera consistente al proporcionar recordatorios personalizados por correo electrónico o un proceso programado para enviar cartas de cobro. 

## <a name="collections-process-setup"></a>Configuración del proceso de cobros
Puede usar la página **Configuración del proceso de cobros** (**Crédito y cobros > Configuración > Configuración del proceso de cobros**) para crear un proceso de cobros automatizado que programará actividades, enviará mensajes de correo electrónico y creará y publicará cartas de cobro de clientes. Los pasos del proceso se basan en la factura abierta principal o más antigua. Cada paso utiliza esta factura para determinar qué comunicación o actividad debe realizarse con un cliente específico.  

### <a name="process-hierarchy"></a>Jerarquía de procesos
Cada grupo de clientes solo se puede asignar a una jerarquía de procesos. El rango de jerarquía de este paso identifica qué proceso tendrá prioridad si un cliente está incluido en más de un grupo que tiene asignada una jerarquía de procesos. El identificador del grupo determina qué clientes se asignarán al proceso. 

Los días tranquilos se utilizan para garantizar que el proceso automatizado no contacte con un cliente con demasiada frecuencia.  Por ejemplo, si los días tranquilos se establecen en dos, el proceso automatizado no se pondrá en contacto con un cliente durante al menos dos días, incluso si la factura principal original se ha liquidado en su totalidad. 

Para excluir a los clientes de la automatización del proceso si el saldo de la cuenta o el saldo de la factura es menor que un valor definido, establezca el campo **Excluir del proceso** en **Sí** y especifique el valor del importe.

## <a name="process-details"></a>Detalles del proceso
**Descripción** se utiliza para identificar el propósito o el nombre del paso en la jerarquía.

**Tipo de acción** define si el paso creará una actividad, enviará un correo electrónico o creará una carta de cobro.

**Documento comercial** define la plantilla utilizada para crear el tipo de acción.  Puede ser una plantilla de actividad, una plantilla de correo electrónico o una carta de cobro por cliente. 

Los tipos de acción se pueden crear antes o después de la fecha de vencimiento de la factura, según la configuración que se muestra en la columna **Días en relación con la fecha de vencimiento de la factura**.

Cuando selecciona un tipo de acción de correo electrónico, el destinatario se utilizará para definir si se trata de un contacto de cliente, grupo de ventas o agente de cobros. El valor en el campo **Contacto de propósito comercial** determinará qué contacto de la cuenta de ese cliente recibirá la comunicación.

## <a name="business-document-details"></a>Detalles de documentos empresariales
Los detalles del documento empresarial variarán según el tipo de acción que se seleccione en los detalles del proceso.  Cuando el tipo de acción es una actividad, se mostrarán los detalles de la plantilla de actividad.  Estos detalles incluyen el nombre de la plantilla de la actividad, el tipo de actividad que se creará, el propósito de la actividad, el número de días programados para completar la actividad y los detalles de la actividad.  Esta actividad luego se vinculará a la factura principal que informa al destinatario de la acción que se necesita para completar la actividad.

Si el tipo de acción es un correo electrónico en los detalles del proceso, esta sección contendrá dos fichas desplegables.  La primera se utiliza para definir el identificador de la plantilla, la descripción del correo electrónico, el idioma predeterminado, el nombre de usuario que se asignará a los mensajes de correo electrónico que se envían automáticamente y la dirección de correo electrónico de los remitentes asociados. La segunda permitirá que el cuerpo del correo electrónico se cree después de que los valores en los campos **Idioma** y **Tema** se guarden seleccionando **Editar**.  Esto abrirá una ventana que permite cargar contenido HTML. También puede escribir el mensaje que se creó manualmente en el cuadro inferior izquierdo de la ventana.  

> [!Note]
> Se puede guardar un correo electrónico de Outlook con el cuerpo deseado de la comunicación en formato HTML. Esto luego se puede cargar para implementar la plantilla. <br> <br> Si se selecciona el tipo de acción de carta de cobro, no habrá una sección de detalles del documento comercial en el formulario de configuración.


## <a name="fasttab-reference"></a>Referencia a la ficha desplegable
Las siguientes tablas enumeran las páginas y los campos desde los que se puede acceder a las fichas desplegables, junto con una descripción de la información en esa pestaña. 

### <a name="process-hierarchy"></a>Jerarquía de procesos

|     Página                                                  |     Campo                         |     Descripción                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Configuración del proceso de cobros <br> Automatización de procesos       |                                   |     Cree y administre procesos de cobros basados en asignaciones de grupos de clientes.                                                                                                                             |
|     Configuración del proceso de cobros <br> Automatización de procesos       |     Jerarquía                     |     Define la prioridad de la automatización de procesos para asignar un cliente si pertenecen a varios grupos.                                                                                                   |
|     Configuración del proceso de cobros <br> Automatización de procesos       |     Id. de grupo                       |     Las consultas que definen un grupo de registros de clientes.                                                                                                                                                        |
|     Configuración del proceso de cobros <br> Automatización de procesos       |     Días tranquilos                    |     Limite la frecuencia con que un paso de proceso puede completarse. Por ejemplo, si se establecen dos días tranquilos, el siguiente paso del proceso no ocurrirá durante al menos dos días si cambia la factura principal.     |
|     Configuración del proceso de cobros <br> Automatización de procesos       |     Excluir del proceso        |     Seleccionando ya sea **Saldo antiguo del cliente menor que** o **Importe de la factura menor que** excluirá a un cliente de la automatización del proceso si no se cumplen los criterios del valor.                                   |

### <a name="process-details"></a>Detalles del proceso
|     Página                                                  |     Campo                                         |      Descripción                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Configuración del proceso de cobros <br> Automatización de procesos       |                                                   |     Defina los pasos emprendidos en función de la factura principal.                                                                                                |
|                                                           |     Descripción                                   |     Campo de texto libre utilizado para proporcionar un nombre y/o una descripción del paso.                                                                           |
|                                                           |     Tipo de acción                                   |     Actividad, correo electrónico o carta de cobro que se creará en el paso del proceso.                                                                     |
|                                                           |     Documento empresarial                           |     Define la actividad o plantilla de correo electrónico que se utiliza durante el paso del proceso.                                                                        |
|                                                           |     Cuándo                                          |     Define si el paso del proceso ocurrirá antes o después de la fecha de vencimiento de la factura principal junto con el campo **Días en relación con la fecha de vencimiento de la factura**.        |
|                                                           |     Días en relación con la fecha de vencimiento de la factura        |     Junto con el campo **Cuándo** identifica el tiempo del paso del proceso.                                                                          |
|                                                           |     Destinatario                                     |     Identifica si se enviará un correo electrónico a un cliente, grupo de ventas o contacto del agente de cobros.                                                   |
|                                                           |     Contacto para propósito comercial                    |     Determina qué dirección de correo electrónico del destinatario se utiliza en las comunicaciones por correo electrónico.                                                                                 |

### <a name="business-process-activity-template-details"></a>Detalles de la plantilla de actividad de proceso empresarial 
|     Página                                                  |     Campo                     |      Descripción                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Configuración del proceso de cobros <br> Automatización de procesos       |                               |     Sección del proceso de configuración que identifica los detalles de la plantilla de actividad.                                                                      |
|     Configuración del proceso de cobros <br> Automatización de procesos       |     Plantilla de actividades       |     Identifica el tipo, el propósito, la cantidad de días para completar y proporciona detalles sobre la actividad que se creará durante un paso del proceso de actividad.       |

### <a name="business-document-email-template-details"></a>Detalles de plantilla de correo electrónico de documento empresarial 
|     Página                                                  |     Campo     |      Descripción                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Configuración del proceso de cobros <br> Automatización de procesos       |               |     Identifica la descripción del correo electrónico, el idioma predeterminado, el nombre del remitente y la dirección de correo electrónico que se crearán durante un paso del proceso de correo electrónico.        |


### <a name="collections-history"></a>Historial de cobros 
|     Página                              |     Campo     |      Descripción                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Configuración del proceso de cobros       |               |     Ver el historial reciente de la jerarquía de procesos seleccionada.     |

### <a name="collection-process-assignment"></a>Asignación del proceso de cobros
|     Página                              |     Campo     |      Descripción                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Configuración del proceso de cobros       |               |     Vea los clientes asignados a un proceso de cobros.  
|     Asignación manual               |               |     Vea los clientes que se han asignado manualmente a un proceso o seleccione los clientes para asignarlos a un proceso. |
|     Vista previa de la asignación del proceso      |               |     Obtenga una vista previa de los clientes que se asignarán a una estrategia cuando se ejecute.   |
|     Obtener vista previa de asignación de clientes     |               |     Vea la estrategia que se le asigna a un cliente específico.    |
 
### <a name="parameters"></a>Parámetros
|     Página                                                                  |     Campo                                             |      Descripción                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Parámetros de clientes > Automatización del proceso de cobros     |     Porcentaje de clientes por tarea por lotes          |     Configuración para determinar el número de tareas por lotes por proceso de automatización.                                          |
|     Parámetros de clientes > Automatización del proceso de cobros     |     Registrar cartas de cobro automáticamente           |     Los tipos de acciones de cartas de cobro publicarán la carta durante la automatización.                                      |
|     Parámetros de clientes > Automatización del proceso de cobros     |     Crear actividades para la automatización                |     Cree y cierre actividades para tipos de acciones que no sean actividades para ver todos los pasos automatizados realizados en una cuenta.        |
|     Parámetros de clientes > Automatización del proceso de cobros     |     Días para mantener la automatización del proceso de cobros     |     Define el número de días que se almacena el historial de colecciones.                                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]