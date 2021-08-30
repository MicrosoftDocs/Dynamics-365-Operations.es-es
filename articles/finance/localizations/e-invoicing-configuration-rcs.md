---
title: Configurar la facturación electrónica en Regulatory Configuration Services (RCS)
description: Este tema explica cómo configurar la facturación electrónica en Dynamics 365 Regulatory Configuration Services (RCS).
author: gionoder
ms.date: 07/29/2021
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
ms.openlocfilehash: 98ba40da7b365e46e1c624ba70c7dc048144e2c7137e8fd8eb5abe348028ce35
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757983"
---
# <a name="configure-electronic-invoicing-in-regulatory-configuration-services-rcs"></a>Configurar la facturación electrónica en Regulatory Configuration Services (RCS)

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre las capacidades de configuración de la facturación electrónica en Dynamics 365 Regulatory Configuration Services (RCS).

Es a través de las capacidades de configuración como la facturación electrónica le ayuda a cumplir con los requisitos comerciales y normativos de las facturas electrónicas, sin tener que programar. Y en los escenarios donde las facturas electrónicas deben aprobarse electrónicamente mediante servicios web, las capacidades de configuración también le ayudan a cumplir con los requisitos para intercambiar mensajes con servicios web, sin necesidad de codificación.

## <a name="electronic-reporting"></a>Informes electrónicos

Informes electrónicos (ER) admite la facturación electrónica.

La asignación y los formatos del modelo de datos son componentes configurables que se crean y mantienen a través de ER y se utilizan en la facturación electrónica. El diseñador de formatos de ER es la herramienta para crear y mantener formatos de archivo. Se utiliza para configurar las características de facturación electrónica.

Para obtener más información, consulte [Visión general de los informes electrónicos (ER)](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Características de facturación electrónica

Las características de facturación electrónica se encargan de generar facturas electrónicas a través de la facturación electrónica. Encapsulan las reglas de configuración y las utilizan para procesar los datos que Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management envían a la facturación electrónica y a las facturas electrónicas.

Las características también admiten escenarios en los que se requiere el cumplimiento de las especificaciones de formato de archivo y la salida es un archivo electrónico independiente. En la mayoría de los casos, la autoridad fiscal publica las especificaciones del formato de archivo.

Finalmente, las características admiten el intercambio de mensajes con servicios web externos alojados por la autoridad tributaria o por alguna parte acreditada, y solicitudes de autorización o sello de aprobación en la factura electrónica.

## <a name="availability-of-electronic-invoicing-features"></a>Disponibilidad de características de facturación electrónica

La disponibilidad de las características de facturación electrónica depende del país o región. Aunque algunas características están generalmente disponibles, otras están en versión preliminar.

### <a name="generally-available-features"></a>Funciones generalmente disponibles

La siguiente tabla muestra las características de facturación electrónica que se encuentran actualmente generalmente disponibles.

| País/región | Nombre de característica                         | Documento empresarial |
|----------------|--------------------------------------|-------------------|
| Austria        | Facturas electrónicas para Austria (AT)    | Facturas de ventas y facturas de proyectos |
| Bélgica        | Factura electrónica para Bélgica (BE)      | Facturas de ventas y facturas de proyectos |
| Brasil         | NF-e brasileño (BR)                  | Modelo de documento fiscal 55, cartas de corrección, cancelaciones y descartes |
| Brasil         | NFS-e brasileño ABRASF Curitiba (BR) | Documentos fiscales de servicios |
| Brasil         | Importación brasileña de NF-e desde correo electrónico (BR) | Modelo de documento fiscal 55 |
| Dinamarca        | Factura electrónica para Dinamarca (DK)       | Facturas de ventas y facturas de proyectos |
| Egipto          | Factura electrónica egipcia (EG)     | Facturas de ventas y facturas de proyectos |
| Estonia        | Factura electrónica para Estonia (EE)     | Facturas de ventas y facturas de proyectos |
| Finlandia        | Factura electrónica para Finlandia (FI)      | Facturas de ventas y facturas de proyectos |
| Francia         | Factura electrónica para Francia (FR)       | Facturas de ventas y facturas de proyectos |
| Alemania        | Factura electrónica para Alemania (DE)       | Facturas de ventas y facturas de proyectos |
| Italia          | FatturaPA (IT)                       | Facturas de ventas y facturas de proyectos |
| Países Bajos    | Factura electrónica para Países Bajos (NL)        | Facturas de ventas y facturas de proyectos |
| Noruega         | Factura electrónica para Noruega (NO)    | Facturas de ventas y facturas de proyectos |
| España          | Factura electrónica para España (ES)      | Facturas de ventas y facturas de proyectos |
| Europa         | Factura electrónica PEPPOL            | Facturas de ventas PEPPOL y facturas de proyectos |
| Europa         | Factura de proveedor PEPPOL                | Facturas de proveedor de importación PEPPOL |

### <a name="preview-features"></a>Características de vista previa

La siguiente tabla muestra las características de facturación electrónica que se encuentran actualmente en versión preliminar.

| País/región | Nombre de característica                         | Documento empresarial |
|----------------|--------------------------------------|-------------------|
| México         | CFDI mexicano (MX)                    | Facturas de venta, albaranes, transferencias de inventario, complementos de pago y cancelaciones |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Componentes configurables de las características de facturación electrónica

Las características de facturación electrónica constan de los siguientes grupos de componentes configurables:

- **Formatos**: los formatos permiten configurar qué debe generar la facturación electrónica cuando un documento electrónico se convierte en factura electrónica. Los formatos incluyen la configuración del formato para la factura electrónica y para los archivos y mensajes que se utilizan para enviar solicitudes y recibir respuestas cuando se requiere comunicación con un servicio web externo.
- **Acciones**: las acciones le permiten configurar cómo la facturación electrónica genera la transformación de un documento electrónico que Finance and Supply Chain Management envió en una factura electrónica.
- **Reglas de aplicabilidad**: las reglas de aplicabilidad le permiten configurar el contexto que la facturación electrónica debe considerar para procesar una característica de facturación electrónica.
- **Variables**: las variables permiten configurar el soporte para la construcción de la lógica de configuración. Las variables pueden funcionar como entrada de valores para realizar una acción específica. Alternativamente, pueden funcionar como un intercambio de valores entre Finance y Supply Chain Management y la facturación electrónica.
- **Asignación de modelos de documentos electrónicos**: la asignación del modelo de documento electrónico le permite configurar la asignación del modelo ER. La asignación del modelo define la asignación de datos de la factura abstracta que se integra en la facturación electrónica cuando se envían los documentos electrónicos.
- **Modelo de contexto de factura**: el modelo de contexto de factura le permite configurar el modelo de contexto de factura de ER y definir el contexto de una característica de facturación electrónica.
- **Tipos de respuesta**: los tipos de respuesta le permiten configurar qué debe actualizar la facturación electrónica en Finance y Supply Chain Management como resultado del procesamiento de la factura electrónica.

### <a name="formats"></a>Formatos

Las siguientes listas muestran las configuraciones de formato ER que están disponibles para las características de facturación electrónica.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Facturas electrónicas austriacas (AT): facturas de ventas y proyectos para Austria

- Factura de ventas OIOUBL
- Factura de proyecto OIOUBL
- Nota de crédito de ventas OIOUBL
- Nota de crédito de proyecto OIOUBL

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Factura electrónica belga (AT): facturas de ventas y proyectos para Bélgica

- Factura de ventas UBL BE
- Factura de proyecto UBL BE
- Nota de crédito de proyecto UBL BE
- Nota de crédito de ventas UBL BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>NF-e brasileño (BR): NF-e Federal (Brasil)

- Enviar formato de exportación NFe (BR)
- Formato de exportación de carta de corrección NF-e (BR)
- Cancelar formato de exportación NFe (BR)
- Descartar formato de exportación NFe (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>NFS-e brasileño (BR): NFS-e ABRASF Ciudad de Curitiba

- NFS-e ABRASF Curitiba (BR)
- Consulta NFS-e ABRASF Curitiba (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Factura electrónica danesa (DK): facturas de ventas y proyectos para Dinamarca

- Factura de ventas OIOUBL
- Factura de proyecto OIOUBL
- Nota de crédito de ventas OIOUBL
- Nota de crédito de proyecto OIOUBL

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Factura electrónica neerlandesa (NL): facturas de ventas y proyectos para Países Bajos

- Factura de ventas UBL NL
- Factura de proyecto UBL NL
- Nota de crédito de proyecto UBL NL
- Nota de crédito de ventas UBL NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Factura electrónica egipcia (EG): facturas de ventas y proyectos para Egipto

- Factura de venta (EG) (facturación)
- Factura de proyecto (EG) (facturación)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Factura electrónica estonia (EE): facturas de ventas y proyectos para Estonia

- Factura de ventas (EE)
- Factura de proyecto (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Factura electrónica finlandesa (FI): facturas de ventas y proyectos para Finlandia

- Factura de ventas (FI)
- Factura del proyecto (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Factura electrónica francesa (FR): facturas de ventas y proyectos para Francia

- Factura de ventas UBL FR
- Factura de proyecto UBL FR
- Nota de abono de proyecto UBL FR
- Nota de crédito de ventas UBL FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Factura electrónica alemana (DE): facturas de ventas y proyectos para Alemania

- Factura de ventas (DE)
- Factura de proyecto (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Factura electrónica italiana (IT): facturas de ventas y proyectos para Italia

- Factura de ventas (IT)
- Factura de proyecto (IT)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>CFDI mexicano (MX): CFDI para México

- formato de factura CFDI (MX)
- Albarán CFDI (MX)
- Transferencias de inventario CFDI (MX)
- Formato de pago CFDI (MX)
- Formato de cancelación factura CFDI (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Factura electrónica noruega (NO): facturas de ventas y proyectos para Noruega

- Factura de ventas OIOUBL
- Factura de proyecto OIOUBL
- Nota de crédito de ventas OIOUBL
- Nota de crédito de proyecto OIOUBL

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>Factura electrónica PEPPOL: facturas de ventas y proyectos PEPPOL

- Factura de ventas PEPPOL
- Factura de proyecto PEPPOL
- Nota de crédito de ventas PEPPOL
- Nota de crédito de proyecto PEPPOL

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Factura electrónica española (ES): facturas de ventas y proyectos para España

- Factura de ventas (ES)
- Factura de proyecto (ES)

Además de las configuraciones de formato ER que están disponibles para usar con el servicio de Facturación Electrónica, también puede crear sus propias configuraciones de formato ER. Sin embargo, las configuraciones de formato que se crean para usar con las funciones de Facturación electrónica no admiten la referencia directa a las tablas de Finance o Supply Chain Management ni a ninguno de los metadatos correspondientes. Solo se admiten referencias a la asignación del modelo ER.

### <a name="actions"></a>Acciones 

La siguiente tabla enumera las acciones disponibles y si están actualmente disponibles de forma generalizada o aún en vista previa.

| Acción                                        | Descripción                                                                  | Disponibilidad         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Documento de transformación                            | Ejecute el formato de informes electrónicos para transformar el documento.                   | Disponibilidad general  |
| Firmar documento xml                             | Firme documentos xml con firma digital.                                   | Disponibilidad general  |
| Firmar documento json para la autoridad fiscal egipcia | Firme documentos json con firma digital para la autoridad fiscal egipcia.       | Disponibilidad general  |
| Integrar con el servicio ETA egipcio           | Comuníquese con la autoridad fiscal egipcia.                                     | Disponibilidad general  |
| Llamar al servicio SEFAZ brasileño                  | Intégrese con el servicio SEFAZ brasileño para el envío de documentos fiscales.       | Disponibilidad general  |
| Llamar al servicio PAC mexicano                      | Intégrese con el servicio PAC mexicano para el envío de CFDI.                      | En vista previa           |
| Respuesta de proceso                              | Analice la respuesta recibida desde la llamada del servicio web.                     | Disponibilidad general  |
| Usar MS Power Automate                         | Integrar con flujo incorporado en Microsoft Power Automate.                       | En vista previa           |

### <a name="applicability-rules"></a>Reglas de aplicabilidad

Las reglas de aplicabilidad son cláusulas configurables que se definen en el nivel de la función de facturación electrónica. Las reglas están configuradas para proporcionar un contexto para la ejecución de funciones de facturación electrónica a través del conjunto de capacidades de facturación electrónica.

Cuando un documento comercial de Finance o Supply Chain Management se envía a la facturación electrónica, el documento comercial no incluye una referencia explícita que permita al conjunto de capacidades de facturación electrónica llamar a una función de facturación electrónica en particular para procesar el envío.

No obstante, cuando se configura adecuadamente, el documento comercial contiene los elementos necesarios que permiten que la facturación electrónica resuelva qué función de facturación electrónica se debe seleccionar y luego generar la factura electrónica.

Las reglas de aplicabilidad permiten que el conjunto de capacidades de facturación electrónica encuentre las características exactas de facturación electrónica que se deben utilizar para procesar el envío. Esto se hace haciendo coincidir el contenido del documento comercial enviado con las cláusulas de las reglas de aplicabilidad.

Por ejemplo, dos funciones de facturación electrónica con reglas de aplicabilidad relacionadas se implementan en el conjunto de capacidades de facturación electrónica.

| Característica de facturación electrónica | Reglas de aplicabilidad        |
|------------------------------|--------------------------- |
| C                            | <p>País = BR</p><p>y</p><p>Entidad jurídica = BRMF</p>  |
| mil millones                            | <p>País = MX</p><p>y</p><p>Entidad jurídica = MXMF</p>  |

Si un documento comercial de Finance o Supply Chain Management se envía al conjunto de capacidades de Facturación electrónica, el documento comercial contiene los siguientes atributos rellenados como:

- País = BR
- Entidad jurídica = BRMF

El conjunto de capacidades de facturación electrónica seleccionará la función de facturación electrónica **A** para procesar el envío y generar la factura electrónica.

Del mismo modo, si el documento comercial contiene:

- País = MX
- Entidad jurídica = MXMF

Función de facturación electrónica **B** se selecciona para generar la factura electrónica.

La configuración de las reglas de aplicabilidad no puede ser ambigua. Esto significa que dos o más funciones de facturación electrónica no pueden tener las mismas cláusulas; de lo contrario, no se realizará ninguna selección. Si hay una duplicación de las funciones de facturación electrónica, para evitar la ambigüedad, utilice cláusulas adicionales para permitir que el conjunto de capacidades de facturación electrónica distinga entre las dos funciones de facturación electrónica.

Por ejemplo, considere la función de facturación electrónica **C**. Esta función es una copia de la función de facturación electrónica **A**.

| Característica de facturación electrónica | Reglas de aplicabilidad        |
|------------------------------|--------------------------- |
| C                            | <p>País = BR</p><p>y</p><p>Entidad jurídica = BRMF</p>  |
| C                            | <p>País = BR</p><p>y</p><p>Entidad jurídica = BRMF</p>  |

En este ejemplo, la característica **C** está delante de un envío de documento comercial que contiene lo siguiente:

- País = BR
- Entidad jurídica = BRMF

La capacidad de facturación electrónica no puede distinguir qué función de facturación electrónica se debe utilizar para procesar el envío porque los envíos contienen exactamente las mismas cláusulas.

Para crear una distinción entre las dos características a través de las reglas de aplicabilidad, se debe agregar una nueva cláusula a una de las características para permitir que el conjunto de capacidades de facturación electrónica seleccione la característica de facturación electrónica adecuada.

| Característica de facturación electrónica | Reglas de aplicabilidad        |
|------------------------------|--------------------------- |
| C                            | <p>País = BR</p><p>y</p><p>Entidad jurídica = BRMF</p>  |
| C                            | <p>País = BR</p><p>y</p><p>Entidad jurídica = BRMF</p><p>y</p><p>Modelo=55</p>  |

Para apoyar la creación de cláusulas más complejas, están disponibles los siguientes recursos:

Operadores lógicos:
- Y
- O

Tipos de operadores:
- Equal
- Not equal
- Greater than
- Less than
- Posterior o igual a
- Anterior o igual a
- Contains
- Empieza por

Tipos de datos:
- Cadena
- Número
- Booleano
- Fecha
- UUID

Capacidad para agrupar y desagrupar cláusulas.
El ejemplo tiene el aspecto siguiente.

| Característica de facturación electrónica | Reglas de aplicabilidad        |
|------------------------------|--------------------------- |
| C                            | <p>País = BR</p><p>y</p><p>( Entidad jurídica = BRMF</p><p>o</p><p>Modelo=55)</p>  |


## <a name="configuration-providers"></a>Proveedores de configuración

Los proveedores de configuración proporcionan las características de facturación electrónica y sus componentes ER, como la asignación de modelo, la configuración del formato y el modelo de contexto. Publican las características de facturación electrónica y los componentes de ER en el repositorio global asociado. Desde allí, otras organizaciones pueden descargarlos.

Antes de configurar las características de facturación electrónica a través de RCS, debe configurar su propia organización como proveedor de configuración en el módulo **Informes electrónicos**. Para obtener más información sobre cómo establecer un proveedor de configuración en **Activo**, consulte [Crear proveedores de configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>Ver las características de facturación electrónica en el repositorio global

Para explorar las características de facturación electrónica que están disponibles en el repositorio global para un proveedor de configuración específico, sincronice la instancia RCS de su organización. Una vez completada la sincronización, se actualiza la lista de características de facturación electrónica disponibles.

## <a name="importing-electronic-invoicing-features"></a>Importación de características de facturación electrónica

Antes de utilizar o configurar las características de facturación electrónica, debe importarlas a la instancia RCS de su organización. La operación de importación crea una copia local de las características y copia todos los artefactos ER que utilizan las características (por ejemplo, configuraciones de formato y configuraciones de modelos) en la instancia RCS de su organización.

Puede importar las características de facturación electrónica desde cualquier proveedor de configuración.

## <a name="creating-electronic-invoicing-features"></a>Creación de características de facturación electrónica

Puede crear una característica de facturación electrónica desde cero o derivarla de una característica adicional de facturación electrónica.

Al crear una característica de facturación electrónica desde cero, debe agregar manualmente los componentes de ER (por ejemplo, configuraciones de versión de característica y otras configuraciones, como la configuración de la versión de característica y la configuración de la aplicación). Cuando crea una característica derivándola de otra característica, la nueva característica hereda todas las configuraciones de la original. 

## <a name="electronic-invoicing-feature-version"></a>Versión de característica de facturación electrónica

Las características de facturación electrónica tienen versiones. Cuando se crea una nueva versión, el número de versión se incrementa automáticamente. Se puede definir una fecha de "vigencia desde" para la nueva versión.

Las versiones de la característica de facturación electrónica siguen un ciclo de vida que tiene hasta tres estados:

- **Borrador**: si una versión de característica se encuentra en este estado, puede editar sus atributos de configuración y cualquiera de sus artefactos (por ejemplo, configuraciones de formato de archivo).
- **Completar**: si una versión de característica se encuentra en este estado, se ha publicado en el repositorio global asociado a su organización. Ya no puede editar la versión de la característica ni ninguno de los componentes de ER.
- **Publicado**: si una versión de la característica se encuentra en este estado, se ha publicado en la facturación electrónica. Ya no puede editar la versión de la característica ni ninguno de los componentes de ER.

### <a name="feature-configurations"></a>Configuraciones de características

Las configuraciones de características contienen todas las configuraciones de formato ER que utilizan las características de facturación electrónica. Todos los archivos electrónicos que utilizan una característica de facturación electrónica durante el procesamiento provienen de las configuraciones de formato que se han agregado a las configuraciones de características de esa característica.

Desde las configuraciones de características, puede acceder al diseñador de formato ER, que es la herramienta ER que se utiliza para crear configuraciones de formato.

### <a name="feature-setup"></a>Configuración de características

Las configuraciones de características se utilizan en combinación con configuraciones de características. Cada configuración de características encapsula un conjunto de acciones, reglas de aplicabilidad y variables que proporcionan el comportamiento esperado para que una característica de facturación electrónica pueda cumplir con un requisito específico de la factura electrónica.

### <a name="application-setup"></a>Configuración de aplicación

La configuración de la aplicación debe estar asociada con una aplicación conectada creada previamente.

A través de la configuración de la aplicación, puede configurar la parte de una característica de facturación electrónica que debe realizarse en Finance y Supply Chain Management. Al menos tres componentes configurables son obligatorios, independientemente de la característica de facturación electrónica:

- **Nombre de la tabla**: la entidad de Finance y Supply Chain Management que mantiene las facturas registradas y en la que se basa la característica de facturación electrónica.
- **Contexto**: el nombre del modelo de contexto de factura que se configuró a través de ER.
- **Asignación de documento empresarial**: el nombre del modelo de asignación de factura que se configuró a través de ER.

> [!IMPORTANT]
> La configuración que se introduce en la configuración de la aplicación se puede ver en Finance y Supply Chain Management. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**. En la pestaña **Documento electrónico**, seleccione **Implementar** y luego seleccione la opción **Aplicación conectada**.

### <a name="deploying-feature-versions"></a>Implementar versiones de características

En RCS, use el comando **Implementar** para publicar como destino una versión de característica de facturación electrónica. Seleccione **Implementar** y luego seleccione una de las siguientes opciones para definir el destino de la implementación: 

- **Entorno de servicio**: cuando el objetivo de la implementación es el entorno del servicio, la versión de la característica de facturación electrónica se publica en el entorno del servicio. La facturación electrónica está lista para recibir y procesar documentos electrónicos enviados por Finance y Supply Chain Management.
- **Aplicación conectada**: cuando el destino de la implementación es la aplicación conectada, la configuración proporcionada por la instalación de la aplicación se escribe en la instancia de Finance y Supply Chain Management que estaba asociada anteriormente.

Solo las versiones de la característica de facturación electrónica que tienen un estado de **Completado** se pueden implementar en un entorno de servicio o en una aplicación conectada.

### <a name="removing-feature-versions"></a>Eliminación de versiones de características

En RCS, use el comando **Anular implementación** para eliminar una versión específica de la característica de facturación electrónica de un entorno de servicio de la facturación electrónica.

> [!IMPORTANT]
> El comando **Anular implementación** solo funciona en entornos de servicio. No elimina las versiones de la característica de facturación electrónica de las aplicaciones conectadas.

### <a name="rebasing-electronic-invoicing-features"></a>Nueva base de características de facturación electrónica

Cuando una característica de facturación electrónica se deriva de otra, el comando **Nueva base** actualiza la característica derivada con los cambios que se han introducido en la característica original.

## <a name="additional-resources"></a>Recursos adicionales

- [Emitir facturas electrónicas en Finance y Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
