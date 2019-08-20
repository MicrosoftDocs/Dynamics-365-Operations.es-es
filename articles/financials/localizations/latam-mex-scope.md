---
title: Ámbito de localización mexicana
description: Este tema describe la estrategia y el ámbito relativos a impuestos, finanzas, y leyes y normativas de contabilidad en México que se han implementado como parte de Microsoft Dynamics AX o de Microsoft Dynamics 365 for Finance and Operations.
author: sndray
manager: AnnBe
ms.date: 04/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b5c339fed4532cf4afa8bf8309a174c62b8fef9
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849355"
---
# <a name="scope-of-the-mexican-localization"></a>Ámbito de la localización mexicana

[!include[banner](../includes/banner.md)]

Microsoft dedica normalmente recursos considerables a ampliar la funcionalidad de proceso empresarial de las aplicaciones de Microsoft Dynamics desarrollando características y funciones que abordan requisitos normativos específicos sobre impuestos, contabilidad o finanzas en países o regiones donde Microsoft pone Microsoft Dynamics a disposición de todos.

Microsoft Dynamics AX y Microsoft Dynamics 365 for Finance and Operations ayudan a organizaciones a dirigir sus operaciones empresariales y también a gestionar sus obligaciones de cumplir con las leyes, las normas y las prácticas empresariales específicas y habituales del país o región para gestionar las actividades diarias. Este software incluye características y funciones que están diseñados para abordar las leyes o las normativas de informes normativos, financieros, contables o de impuestos que normalmente afectan a los negocios en México.

Sin embargo, Microsoft Dynamics AX y Finance and Operations no abordan todos los requisitos legislativos, normativos o comerciales de México, ya que las leyes y normativas varían por la forma en que afectan a organizaciones. Por ejemplo, las características normativas que Microsoft suele crear y poner a disposición del público “listas para usar” para Microsoft Dynamics AX y Finance and Operations en México no suelen incluir funciones que admiten lo siguiente, salvo lo indicado específicamente en este tema:

- Normas nacionales
- Payroll
- Regulaciones específicas del sector
- Regulaciones verticales 
- Requisitos de estado, ciudad, o municipales

Los detalles adicionales están disponibles en el [Manual de disponibilidad de localización](https://aka.ms/ax-availabilityguide).

Los socios de canal son un aspecto importante de nuestra estrategia global para entregar Microsoft Dynamics AX y Finance and Operations para ayudar a los clientes a cumplir con los requisitos para México. Aprovechándose de la naturaleza extensible de la arquitectura del desarrollo de Microsoft Dynamics AX y Finance and Operations, los socios de canal pueden abordar necesidades específicas del negocio de un cliente durante la implementación con cualquiera de los enfoques siguientes:

- Configuración de software (si está disponible)
- Personalizaciones o localizaciones creadas por socios (cuando sea necesario)

Aunque los socios de canal pudieran ofrecer soluciones que cumplan las normas legales específicas que son exclusivas de los municipios, las ciudades, los estados, u otras regiones de México, Microsoft no proporciona ninguna garantía (expresa, implícita, normativa u otras) de que las soluciones creadas por los socios cumplan con los requisitos aplicables localmente en negocios, impuestos, normas, leyes u otros requisitos.

Los socios de canal o clientes solo son responsables de las configuraciones, las personalizaciones, localizaciones, o traducciones que creen o implementen en nombre de los clientes, y también de las actualizaciones de estas soluciones. Son también los únicos responsables del soporte o cualquier otro servicio que se ofrezca a los clientes para estas soluciones. Debe ponerse en contacto con su socio de canal para obtener información acerca de las soluciones que el socio de canal crea para las versiones con licencia de Microsoft Dynamics AX o Finance and Operations.

Este tema describe la estrategia y el ámbito de los requisitos específicos que Microsoft ha implementado como parte del software de Microsoft Dynamics AX y Finance and Operations que puso a disposición comercial general en México.

## <a name="terminology-and-abbreviations"></a>Terminología y siglas
**Personalización** hace referencia a una de los siguientes puntos:

- Cualquier configuración, modificación o cambios que los socios o clientes realicen en el software de Microsoft Dynamics mismo o, si es aplicable, a la documentación del software para ajustarse a las necesidades de negocio específicas de un cliente. Entre los ejemplos figura agregar o cambiar el nombre de campos o tablas, crear informes personalizados, o integraciones con las soluciones de terceros.
- Cualquier software que se desarrolla para el software de Microsoft Dynamics.

**Localización** hace referencia a cualquier modificación en, adición a, o adaptación del software de Microsoft Dynamics para habilitar o para incluir funcionalidades o características específicas del software de manera que se ajuste a las normas legales aplicables (incl., sin ser exhaustivos, las versiones y las actualizaciones de software de Microsoft Dynamics, las herramientas de ayuda al usuario, y la documentación del usuario final). A continuación se muestran algunos ejemplos de las leyes o de las normas legales que pueden requerir la localización de software:

- El informe de impuestos local, como informes de impuestos, impuesto sobre el valor añadido (IVA) y bienes y servicios (GST)
- Seguimiento de facturas realizado por una autoridad gubernamental
- Cálculos de impuestos requeridos por el Gobierno
- Reglas de contabilidad locales
- Informes estatutarios y normativos locales

**Normas nacionales** hace referencia a los requisitos de software que se relacionan principalmente con las prácticas de Banca (como métodos de pago, formatos de pago, y extractos bancarios) y con menos frecuencia a los documentos comerciales (como documentos fiscales electrónicos). Las normas nacionales son requisitos locales que no son necesarios según la ley o la normativa, pero que se adoptan ampliamente dentro de una región geográfica y son críticos para la venta de las licencias para el software de gestión empresarial en esa región geográfica.

| Abreviatura | Descripción |
|--------------|-------------|
| CFD          | Facturas electrónicas por propios medios (autoenvío) – Comprobantes fiscales digitales |
| CFDI         | Facturas electrónicas por Internet – Comprobantes fiscales digitales por internet |
| DIOT         | Declaración de operaciones con terceros - Declaración informativa de operaciones con terceros |
| IEPS         | Impuesto especial sobre fabrica y servicios - Impuesto Especial sobre Producción y Servicios |
| ISR          | Impuesto sobre ingresos – Impuesto sobre la Renta |
| IVA          | Impuestos de IVA – Impuesto al Valor Agregado |
| PAC          | Proveedor de servicios de firma digital autorizados – Proveedores autorizados de certificación |
| SAT          | Servicio de administración fiscal – Servicio de Administración Tributaria |
| UUID         | Identificador único universal – Identificador universalmente único |

## <a name="mexican-localization-strategy"></a>Estrategia de localización mexicana

Normalmente la estrategia de Microsoft para abordar los requisitos de informes de impuestos, financieros, contables o estatutarios para México consiste en proporcionar localizaciones para Microsoft Dynamics AX y Finance and Operations que hacen lo siguiente:

- Implementan los requisitos fiscales federales que se detallan en la sección [Ámbito mexicano de localización](#mexican-localization-scope) más adelante en este tema.
- Entregan las nuevas características específicas normativas mediante configuraciones o mediante el desarrollo de una nueva funcionalidad que implementa los requisitos federales que se detallan en la sección [Ámbito mexicano de localización](#mexican-localization-scope), de acuerdo con la información especificada en este tema.
- Entregan nuevas características normativas específicas en el Service Pack más reciente disponible, o en un Service Pack nuevo, para las versiones admitidas de Microsoft Dynamics AX o Finance and Operations.
- Aplican los estándares nacionales y las características competitivas de la localización, mientras que Microsoft, a su discreción, determina si son necesarias o adecuadas en función de las necesidades de negocio de la región.
- No se centre en los requisitos de negocios, segmentos, verticales, regiones, o grandes empresas específicos, incluso cuando estos requisitos son requeridos por leyes, estatutos, o regulaciones en los niveles federal, estatal o de la ciudad.
- Excluyen los requisitos municipales, excepto los requisitos municipales que se detallan en la sección [Ámbito mexicano de localización](#mexican-localization-scope).

Existen leyes y requisitos específicos que se encuentran fuera de ámbito de Microsoft Dynamics AX y Finance and Operations. Estas leyes y requisitos se enumeran en la sección [Fuera de ámbito](#out-of-scope) más adelante en este tema.

Las localizaciones mexicanas que Microsoft desarrolla para Microsoft Dynamics AX y Finance and Operations se limitan a las características y la funcionalidad que se describen en este tema. Por lo tanto, Microsoft Dynamics AX y Finance and Operations deben ser analizados por clientes potenciales o por un profesional de impuestos (como un auditor fiscal y contable, una empresa especializada en derecho financiero o una empresa de consultoría de impuestos) que pueda realizar una evaluación para determinar si la funcionalidad es adecuada para atender las necesidades del negocio del cliente o si se requieren soluciones personalizadas.

## <a name="mexican-localization-scope"></a>Ámbito de localización mexicana
La interfaz de usuario y la ayuda en línea para Microsoft Dynamics AX y Finance and Operations se traducen a español mexicano. Es posible que la documentación adicional, como documentación y material para la formación, esté disponible solo en inglés y no esté disponible cuando el software se lance en general en México.

El ámbito de localización para la versión de Microsoft Dynamics AX y Finance and Operations que está disponible en México se limita al cálculo de impuestos, las transacciones contables, y la emisión y recepción de facturas en los escenarios siguientes: 

- Adquirir para pagar
- Presupuesto para efectivo
- Informes estatutarios y normativos

Para consultar una lista de las características específicas que Microsoft entrega y admite como parte de las localizaciones mexicanas para Microsoft Dynamics AX y Finance and Operations, consulte la sección [Características compatibles](#supported-features) más adelante en este documento. Puede encontrar los detalles acerca de cada característica en la ayuda de Microsoft Dynamics AX, en la ayuda en línea, y en el informe que se publican en la sección [Portal de localización de Microsoft Dynamics](https://mbs.microsoft.com/partnersource/deployment/resources/productreleases/gfmlocalizationportalmc.htm?printpage=false&sid=xdtafwuk1xh2l5jdjhhv0joy&stext=gfm%20localization%20portal).

## <a name="market-availability"></a>Disponibilidad de mercado
Microsoft tiene como objetivo entregar características normativas de una forma que dé suficiente tiempo para la instalación. En el caso de las actualizaciones de impuestos y normativas que contienen cambios necesarios para implementar los requisitos de informes de impuestos, contabilidad, financieros, o estatutarios que normalmente afectan a la mayoría de negocios en México, nuestro objetivo es lanzar las actualizaciones antes de la fecha de vigencia u otra fecha que indique la autoridad gubernamental aplicable, tanto a escala federal como estatal, tal como se identifica en la sección [Estrategia mexicana de localización](#mexican-localization-strategy), de modo que nuestros socios de canal tengan tiempo para actualizar sus soluciones del cliente. Internamente, denominamos a esta fecha la *fecha requerida por el mercado* (MRD).

Nos esforzamos por cumplir las MRD y fechas que exige la autoridad gubernamental aplicable. Sin embargo, los distintos factores pueden afectar a la entrega oportuna de las actualizaciones de impuestos y normativas. Estos factores son los siguientes:

- Cambios legislativos o normativos que el gobierno realiza sin suficiente aviso previo antes de la fecha de entrada en vigor de la ley
- Limitaciones de características, funcionalidad, infraestructura o arquitectura de las versiones de software afectadas que normalmente están disponibles en el mercado
- La complejidad y el alcance de la codificación, el reajuste, o la mejora del software que se requiere para implementar los requisitos de la legislación o las normas legales, o programar conflictos

Si no es posible cumplir para esas fechas, usamos los esfuerzos comercialmente razonables para desarrollar y lanzar actualizaciones de impuestos y normativas lo más rápidamente posible.

Las fechas que Microsoft publica tienen solo fines de planificación y están sujetas a cambios en cualquier momento sin previo aviso.

Microsoft no declara ni garantiza la puntualidad ni la integridad de ninguna actualización de impuestos o normativa que proporcione y en la medida de lo permitido en la ley aplicable, rechaza todas las garantías y condiciones implícitas, como garantías o condiciones implícitas de comercialización y adecuación para un fin concreto.

## <a name="supported-features"></a>Características compatibles
En la tabla siguiente se enumeran las características específicas que Microsoft entrega y admite como parte de las localizaciones mexicanas para Microsoft Dynamics AX y Finance and Operations.

<table>
<thead>
<tr>
<th>Área</th>
<th>Artículo</th>
<th>AX 2009</th>
<th>AX 2012 RTM-R2</th>
<th>AX 2012 R3</th>
<th>Finance and Operations</th>
</tr>
</thead>
<tbody>
<tr>
<td>Datos maestros</td>
<td>Identificadores de impuestos de la entidad jurídica:
<ul>
<li>RFC (identificador de impuestos mexicano – Registro Federal de Contribuyentes)</li>
<li>CURP (Código de registro de población único – Clave Única de Registro de Población)</li>
<li>Tipo de empresa</li>
<li>Inscripción estatal</li>
<li>Régimen de impuestos</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Identificadores fiscales de cliente
<ul>
<li>RFC</li>
<li>CURP</li>
<li>Tipo de empresa</li>
<li>Inscripción estatal</li>
</ul>
</td>
<td>Solo RFC</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Identificadores fiscales de proveedor
<ul>
<li>RFC</li>
<li>CURP</li>
<li>Tipo de empresa</li>
<li>Inscripción estatal</li>
</ul>
</td>
<td>Solo RFC</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Identificadores de impuestos del proveedor para la declaración DIOT:
<ul>
<li>Tipo de proveedor</li>
<li>Tipo de operación</li>
<li>ID de registro fiscal para extranjeros.</li>
<li>Código de país/región</li>
<li>Nacionalidad</li>
</ul>
</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Identificadores fiscales de banco
<ul>
<li>RFC</li>
</ul></td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Tipos de impuestos:
<ul>
<li>IVA</li>
<li>ISR</li>
<li>IEPS</li>
</ul>
</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>Impuestos<br>(Cálculo por funcionalidad básica)</td>
<td>Impuesto condicional y normal de IVA</td>
<td>Normal</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>IEPS</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>ISR normal</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>Comprar<br>(Recibir factura de bienes y servicios)</td>
<td>Entrar UUID de documento CFDI:
<ul>
<li>Factura de compra</li>
<li>Factura del proveedor</li>
<li>Registro de facturas</li>
<li>Diario general</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Especificar el número de serie y de factura:
<ul>
<li>Factura de compra</li>
<li>Factura del proveedor</li>
<li>Registro de facturas</li>
<li>Diario general</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Entrada de información relacionada para la declaración DIOT:
<ul>
<li>Factura de compra</li>
<li>Factura del proveedor</li>
<li>Registro de facturas</li>
<li>Diario general</li>
<li>Proyecto: gasto</li>
<li>Proyecto: cuota diario</li>
</ul>
</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>CFD</td>
<td>Soporte para el diseño CFD de 2.0</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño CFD de 2.2</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td></td>
<td>Mensajes/eventos de CFD:
<ul>
<li>Problema</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td></td>
<td>Versión CFD imprimible en formato PDF</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td></td>
<td>Visor XML de facturas emitidas de CFD</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td></td>
<td>Envío automático del documento de CFD por correo electrónico a clientes durante el proceso de registro</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td></td>
<td>Generación de un informe mensual</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>N.º</td>
</tr>
<tr>
<td>CFDI</td>
<td>Soporte para el diseño 3.0 de CFDI en facturas de cliente</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño 3.2 de CFDI en facturas de cliente</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño 3.3 de CFDI en facturas de cliente</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño 3.3 de CFDI en pagos de cliente con el complemento de sueldo 1.0</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño 3.3 de CFDI en pago anticipado de cliente:
<ul>
<li>Adelanto del pago CFDI</li>
<li>Factura y liquidación de CFDI</li>
<li>Invertir pago por adelantado de CFDI</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño 3.3 de CFDI en albaranes y pedidos de transferencias entre los sitios (TRASLADOS)</td>
<td>N.º</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño 3.3 de CFDI en facturas de cliente extranjero y el complemento extranjero 1.1</td>
<td>N.º</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Compatibilidad para el diseño global 3.3 de CFDI recibos de clientes (Retail)</td>
<td>N.º</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Soporte para el diseño de retención CFDI de 1.0</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Mensajes/eventos de CFDI:
<ul>
<li>Problema</li>
<li>Cancelar</li>
<li>Cancelación manual</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Versión imprimible de CFDI en formato PDF que incluya un código de barras bidimensional</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Visor XML de facturas emitidas de CFDI</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td></td>
<td>Envío automático de documentos de CFD por correo electrónico a clientes durante el proceso de registro</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>PAC</td>
<td>Microsoft solo proporciona un ejemplo de código para la integración de PAC con la autenticación del certificado del servidor Web.</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>DIOT</td>
<td>Generación de la declaración DIOT como archivo de texto</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>Ajuste por inflación</td>
<td>Generación y registro del proceso de ajuste de inflación</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>Declaración ISR</td>
<td>Generación del informe de declaración de ISR</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>Informes de IVA</td>
<td>Generación de informes de IVA:
<ul>
<li>Ventas</li>
<li>Compra</li>
</ul>
</td>
<td>N.º</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
<tr>
<td>Extracto electrónico de cuenta contable</td>
<td>Generación de archivos XML electrónicos de cuenta contable:
<ul>
<li>Plan contable</li>
<li>Saldo de comprobación</li>
<li>Asientos contables con documentos relacionados (folios)</li>
<li>Cuenta contable auxiliar</li>
</ul>
</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
<td>Sí</td>
</tr>
</tbody>
</table>

## <a name="out-of-scope"></a>Sin ámbito
Es posible que algunas capacidades de Microsoft Dynamics AX y Finance and Operations que normalmente están disponibles en otros países o regiones no estén disponibles en las localizaciones mexicanas de Microsoft Dynamics AX y Finance and Operations. Los siguientes elementos se encuentran fuera de ámbito o no se permiten en México.

### <a name="requirements"></a>Requisitos
Los siguientes requisitos específicos están fuera de ámbito en las localizaciones mexicanas de Microsoft Dynamics AX y Finance and Operations.

- Comercio exterior (entrante).
- Declaración de Impuesto Empresarial a Tasa Única (IETU).
- Integración de PAC para certificar el documento de factura de CFDI electrónico.

    Microsoft no admite la integración con todos los servicios Web PAC disponibles y autorizados. Las empresas deben personalizar las referencias de servicio para la solución seleccionada y configurar la autenticación del cliente (certificado) para generar la factura de CFDI (mensaje de XML). Microsoft ofrece la generación del mensaje XML y un ejemplo de código que muestra cómo integrarse con servicios Web de PAC. Este ejemplo de código se incluye en todas las versiones compatibles de CFDI, y lo ha desarrollado y probado usando la integración con los servicios Web de Interfactura PAC.

    La autenticación del cliente mediante un nombre de usuario y una contraseña no se admite actualmente.

- Generación de CFDI para los documentos de nómina.
- Los archivos XML electrónicos de las cuentas contables no incluyen la marca digital.
- Requisitos de estados/regiones distintos de los que se describen en la sección [Estrategia mexicana de localización](#mexican-localization-strategy) de este tema.
- Requisitos de agencias reguladoras o autarquías distintos del SAT.

### <a name="modules"></a>Módulos
Los siguientes módulos están fuera de ámbito en las localizaciones mexicanas de Microsoft Dynamics AX y Finance and Operations:

- Gestión presupuestaria
- Contabilidad de costes
- Viajes y gastos
- Cumplimiento y controles internos
- Recursos humanos
- Payroll
- Retail
- Centro de llamadas
- Administración de concesión de comercialización
- Administración de transporte
- Gestión de servicio
- Enterprise Portal para Microsoft Dynamics AX

### <a name="features-and-functionality"></a>Características y funcionalidades
Los siguientes características y funcionalidades están fuera de ámbito en las localizaciones mexicanas de Microsoft Dynamics AX y Finance and Operations:

- Flujo de efectivo
- Gestión de cobros
- Mejoras generales de servicio del diario
- Corrección de facturas de clientes
- Pago previo asociado con el pedido de compra
- Portal Web de facturación electrónica
- Facturas periódicas
- Archivado
- Sistema de administración de calidad
- Catálogos y categorización
- Adición de cifrado para el procesamiento de tarjetas de crédito en los servicios en línea para Microsoft Dynamics
- Portal de autoservicio para proveedores

### <a name="industries"></a>Sectores
- **En general:** El sector siguiente está fuera de ámbito en las localizaciones mexicanas de Microsoft Dynamics AX y Finance and Operations.

    - Sector público

- **Industrias minoristas:**

    - **Servicios comerciales**: Los servicios en línea siguientes están fuera de ámbito en los servicios comerciales de Microsoft Dynamics AX y Finance and Operations.

        - Sites Services para Microsoft Dynamics ERP
        - Servicios de comercio para Microsoft Dynamics ERP
        - Retail Server y POS modernos

    - **Minoristas**
    - **Características de impresora fiscal**

## <a name="references"></a>Referencias
El [Portal de localización de Microsoft Dynamics](https://mbs.microsoft.com/partnersource/deployment/resources/productreleases/gfmlocalizationportalmc.htm?printpage=false&sid=xdtafwuk1xh2l5jdjhhv0joy&stext=gfm%20localization%20portal) proporciona información sobre las características y documentos de localización que Microsoft ha liberado, así como sobre los que tiene previsto su lanzamiento.

## <a name="notes"></a>Notas
**Régimen especial (régimen especial)** hace referencia a cualquier tratamiento diferenciado, excepto la liberación de los impuestos, que la autoridad fiscal autoriza con respecto a los requisitos generales de la regla de impuestos (federal, estatal o municipal) y las obligaciones suplementarias, para simplificar el cumplimiento de las obligaciones fiscales del contribuyente en casos peculiares.
