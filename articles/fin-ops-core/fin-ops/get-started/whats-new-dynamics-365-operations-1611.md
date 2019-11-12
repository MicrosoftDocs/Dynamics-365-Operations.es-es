---
title: Novedades y cambios en Dynamics 365 for Operations versión 1611 (noviembre de 2016)
description: Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Operations versión 1611.
author: sericks007
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4b0397b7120769969c4c7aae16dd2a2b3ec97371
ms.sourcegitcommit: 4d6ec2b1a9674712e1efb8c46b919d554f21a2b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "2627597"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016"></a>Novedades y cambios en Dynamics 365 for Operations versión 1611 (noviembre de 2016)

[!include [banner](../includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Operations versión 1611.

## <a name="cost-accounting"></a>Contabilidad de costes

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definir las dimensiones del elemento de coste e importar miembros de la dimensión del elemento de coste.</td>
<td>Los elementos de coste se utilizan en Contabilidad de costes para clasificar costes y documentar el flujo de costes. Los elementos de costes principales se importan mediante un conector de datos de Microsoft Dynamics 365 for Operations para obtener cuentas principales directamente desde Operaciones o mediante un conector genérico de datos, donde obtiene las cuentas principales a través de Microsoft Excel desde cualquier otro tipo de sistema de origen. Una vez las cuentas principales se hayan importado en la Contabilidad de costes, se usan como miembros de dimensión de elemento de coste. Los elementos de costes secundarios son definidos por el usuario y se usan en asignaciones para documentar el flujo de costes.</td>
</tr>
<tr>
<td>Elaborar dimensiones de elemento de coste.</td>
<td>Si las cuentas principales a través de las entidades jurídicas no se pueden compartir debido a requisitos estatutarios de contabilidad, puede asignarlas después de importarlas en la Contabilidad de costes para obtener una vista holística de la organización.</td>
</tr>
<tr>
<td>Definir las dimensiones del objeto de coste e importar miembros de la dimensión del objeto de coste.</td>
<td>Los objetos de coste son cualquier tipo de objeto a los que se designan los costes. Los objetos típicos de coste incluyen productos, proyectos, recursos, departamentos, centros de coste, y regiones geográficas. Puede usar un conector de datos de Microsoft Dynamics 365 for Operations para obtener dimensiones financieras y valores desde Operaciones o utilizar un conector genérico de datos, donde puede obtener dimensiones y valores mediante Excel desde cualquier otro tipo de sistema de origen. Por ejemplo, si usa la dimensión financiera del Centro de costes como dimensión del objeto, todos los centros de costes que se importen son los miembros de la dimensión para el objeto de coste.</td>
</tr>
<tr>
<td>Definir o importar dimensiones estadísticas.</td>
<td>Los miembros de dimensión estadística se calculan en unidades no monetarias, como horas de maquinaria, número de empleados y espacio. Se usan en los extractos o como base para las asignaciones y distribuciones.</td>
</tr>
<tr>
<td>Crear plantillas de proveedor de medidas estadísticas.</td>
<td>Una plantilla de proveedor de cálculo estadístico se usa para transformar los datos de Dynamics 365 for Operations en medidas estadísticas. La plantilla se asocia con un miembro de dimensión estadístico determinado. Las plantillas se filtran previamente de modo que sólo se muestren las tablas que están asociadas a dimensiones financieras.</td>
</tr>
<tr>
<td>Crear libros mayores de contabilidad de costes.</td>
<td>Un libro mayor de la contabilidad de costes es un libro mayor agnóstico que utiliza su propio calendario y divisa. Desempeña un papel importante en el procesamiento de todas las transacciones de coste. Por ejemplo, un libro mayor de la contabilidad de costes clasifica los costes en función de sus propios elementos de coste y agrega los costes en función de sus propias dimensiones del objeto. Puede crear tantos libros mayores de contabilidad de costes como sea necesario para hacer el informe de gestión desde diferentes perspectivas.</td>
</tr>
<tr>
<td>Crear unidades de control de costes.</td>
<td>Las unidades de control de costes constituyen la estructura de coste y definen el flujo de coste en un libro mayor de la contabilidad de costes. Deben estar asociadas a dimensiones de objeto de coste para representar las dimensiones de objeto de coste en el libro mayor.</td>
</tr>
<tr>
<td>Procesar entradas de contabilidad general.</td>
<td>Para medir el rendimiento real, debe tener datos. Los datos se importan mediante los conectores que define para el libro mayor de la contabilidad de costes. Al procesar las entradas de contabilidad general, los datos se importan gradualmente.</td>
</tr>
<tr>
<td>Procesar entradas presupuestarias.</td>
<td>Para medir el rendimiento presupuestado, debe tener datos. Los datos se importan mediante los conectores que define para el libro mayor de la contabilidad de costes. Al procesar las entradas presupuestarias, los datos se importan gradualmente.</td>
</tr>
<tr>
<td>Crear e implementar las directivas de comportamiento del coste.</td>
<td>Use una directiva de comportamiento del coste para clasificar costes como fijos, variables o semivariables. Una directiva se basa en una regla y tiene fecha efectiva. De forma predeterminada, todos los costes se marcan como sin clasificar hasta que se aplica una directiva de comportamiento de coste y se calculan los efectos de dicha regla. Después del cálculo, se clasifican los costes.</td>
</tr>
<tr>
<td>Costes de seguimiento.</td>
<td>Para ayudarle a comprender el impacto de las directivas de costes, la Contabilidad de costes le permite realizar un seguimiento de los costes a los valores de origen y a las reglas aplicadas donde se originan. Esta función proporciona rastreabilidad completa sobre cuándo se producen los costes, qué tipos de costes se han producido, y qué reglas de comportamiento del coste se han aplicado.</td>
</tr>
<tr>
<td>Definir las jerarquías de dimensión.</td>
<td>Puede crear jerarquías de dimensión para la categorización o con fines de clasificación. Por ejemplo, puede definir una jerarquía de categorización que se basa en una dimensión de elemento de coste y sus miembros. Opcionalmente, puede definir una jerarquía de clasificación que se basa en una dimensión de objeto de coste y sus miembros. Las estructuras del informe se usan en las siguientes situaciones:
<ul>
<li>Defina asignaciones, índices de costes y reglas de acumulación de costes.</li>
<li>Puede visualizar extractos mediante el área de trabajo.</li>
<li>Defina el acceso para ver los datos agregados.</li>
<li>Ver los datos en Excel.</li>
</ul></td>
</tr>
<tr>
<td>Cree los extractos que se pueden ver en el área de trabajo.</td>
<td>Use el área de trabajo para obtener una visión general rápida de los costes reales y los presupuestados, así como las desviaciones. Puede filtrar los datos por período o nivel de coste. El área de trabajo se ha diseñado para los administradores responsables del control de costes. Cumple con las reglas de acceso que se definen para las jerarquías de dimensión.</td>
</tr>
<tr>
<td>Crear informes mediante Excel.
<blockquote>[!NOTE] Debe ejecutar Microsoft Excel 2016.</blockquote>
</td>
<td>Puede exportar los datos de la Contabilidad de costes directamente a Excel a través de entidades de datos y usar Microsoft PivotTable para crear informes.</td>
</tr>
</tbody>
</table>

## <a name="expense-management"></a>Gestión de gastos

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Reasignar transacciones de tarjeta de crédito de empleados despedidos. | A veces, cuando se despide a un empleado, se deshabilita su cuenta de Active Directory Domain Services (AD DS) cuando se importan las transacciones de tarjeta de crédito activo que deben registrarse como gastos. Anteriormente, no se podía asignar un delegado para la entrada de gastos o adjuntar las transacciones de tarjeta de crédito a un informe de gastos. Ahora puede usar la página **Transacciones de tarjeta de crédito** para reasignar el empleado por cualquier transacción de tarjeta de crédito cuyo empleado ha sido despedido. Tras reasignar la transacción de tarjeta de crédito, dicha transacción se puede seleccionar para un informe de gastos y pagar mediante el proceso habitual para el reembolso del informe de gastos. |
| Cambiar la información de la tarjeta de crédito de gastos para empleados pendientes y anteriores. | Puede modificar la información de la tarjeta de crédito de la Gestión de gastos para los trabajadores que están pendientes y los trabajadores anteriores. Anteriormente, se podía cambiar la información de la tarjeta de crédito de gastos solo si el trabajador era un empleado activo. |
| Copiar un informe de gastos. | Ahora puede copiar un gasto existente al crear un nuevo gasto en el mismo informe de gastos. Puede copiar un informe de gastos y todos los gastos no asociados de la tarjeta de crédito a un nuevo informe de gastos. Debe realizar cualquier itemización requerida y adjuntar los recibos necesarios, en función de las directivas y categorías de gastos definidas. Puede agregar transacciones de tarjeta de crédito al informe de gastos seleccionando agregar gastos no conciliados. |
| Edición de gastos en bloque. | Algunas transacciones de tarjeta de crédito no se pueden asignar a una categoría de gastos, o es posible que se asignen incorrectamente cuando se importan. En este caso, los empleados deben cambiar manualmente la categoría de gastos asociada. Al gestionar los gasto no conciliados, puede editar en bloque la categoría de gastos para los gastos seleccionados. Además, cuando se gestionan los gastos seleccionados para un informe de gastos específico, puede editar en bloque el proyecto y la información adicional. |
| Cambiar el tipo de cambio para las transacciones de tarjetas de crédito | El tipo de cambio real que se utiliza para una transacción de tarjeta de crédito podría diferir del tipo de cambio que se han configurado en el sistema. Anteriormente, los empleados no podrían cambiar el tipo de cambio para una transacción de tarjeta de crédito que se importaba en la Gestión de gastos. Ahora puede establecer el parámetro en la página **Parámetros de gestión de gastos** para permitir que se cambie el tipo de cambio para las transacciones de tarjeta de crédito. |
| Configuración de autenticación anticorrupción para gastos. | Algunos empleados de una organización pueden tener negocios con funcionarios del gobierno, y algunos gastos que aparecen como parte de dicho negocio se pueden percibir como sobornos. En Gestión de gastos, ahora puede configurar una autenticación anticorrupción que se muestra para las categorías de gastos seleccionadas, como comidas y regalos. Los empleados deben seleccionar si los gastos que se configuran para la autenticación anticorrupción cumplen con los criterios definidos por las directivas de la organización. |
| Evite la entrada manual de gastos para categorías de gastos específicas. | Una categoría de gastos se puede configurar para representar una transacción de tarjeta de crédito para la que no se puede cambiar la categoría. Un ejemplo es una cuota por el pago atrasado de la tarjeta de crédito. Ahora puede configurar una categoría de gastos que permita que se puedan crear gastos únicamente a través de la importación. Esta característica impide que los empleados creen manualmente un gasto para la categoría. Tampoco permite que la categoría se cambie para las transacciones que se han importado y que usan esta categoría. |
| Adjuntar un recibo a los gastos varios. | Un recibo que se carga a la Gestión de gastos se puede relacionar con gastos varios. Anteriormente, un recibo relacionado con gastos varios tenía que cargarse una vez para cada gasto. Ahora puede adjuntar un recibo a un gasto que ya se ha cargado y adjuntado a otro gasto en el mismo informe de gastos. Además, si se carga un recibo a la cabecera del informe de gastos, puede seleccionar una o varias líneas donde adjuntar la factura. |
| Crear gastos de fechas futuras. | Al copiar un informe de gastos, por ejemplo, la fecha de transacción para un gasto puede tener una fecha futura. Las versiones anteriores no permiten gastos con fechas futuras. Ahora puede crear y guardar los gastos con fecha futura. Sin embargo, no se pueden enviar los gastos con fecha futura. |
| Configurar impuestos de gastos para un estado/provincia. | En determinados países/regiones, los gastos en que se incurre en distintos estados/provincias podrían estar sujetos a diferentes índices de impuestos de ventas. Ahora puede establecer las configuraciones de impuestos de gastos a nivel de estado/provincia, no sólo a nivel de país/región. Si deja el campo **Estado/provincia** en blanco en la página **Configuración de impuestos**, el grupo de impuestos de ventas se aplica a todos los estados/provincias para el país/región especificado. |
| Configuración de los tipos de tarjetas de crédito de gasto. | Anteriormente, no había una página donde poder crear nuevos tipos de tarjeta de crédito, como Visa, MasterCard o Amex, que se pueden usar con la Gestión de gastos. Ahora puede crear tipos de tarjeta de crédito para utilizar con la Gestión de gastos. La página se encuentra en la zona **Configuración** en la sección **Cálculos y códigos**. |
| Defina un flujo de trabajo de aprobación de varios niveles para los informes de gastos. | Un flujo de trabajo nuevo para los informes de gastos admite un proceso de aprobación de varios niveles. Los empleados especifican los aprobadores provisionales y los aprobadores finales al crear el informe de gastos. A continuación, el flujo de trabajo distribuye primero el informe de gastos a los aprobadores provisionales. Una vez el informe de gastos se aprueba a ese nivel, el flujo de trabajo lo distribuye a los aprobadores finales para la aprobación final. |
| Crear y mantener los gastos que no se adjuntan a un informe de gastos. | El usuario podrá crear gastos y mantenerlos (por ejemplo, adjuntando o detallando los recibos, o asignando invitados) sin tener que crear un informe de gastos primero. Se pueden seleccionar y añadir uno o más gastos a un nuevo informe de gastos, de forma que se puedan enviar para su aprobación. Una nueva página para mantener los gastos está disponible en **Gestión de gastos** &gt; **Mis gastos** &gt; **Gastos**. |

## <a name="financial-management"></a>Administración financiera

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Hacer seguimiento de las evaluaciones del activo fijo mediante un único concepto de "libro".</td>
<td>Anteriormente, se utilizaban dos tipos diferentes de evaluación para seguir los valores de activos fijos: modelos de valor y libros de amortización. En la versión actual, estos dos conceptos se han combinado en un solo concepto de evaluación que se denomina libros. Los libros tienen todas las funciones de modelos de valor y de libros de amortización. Por ejemplo, se puede desactivar el registro en la contabilidad general. Los libros que se registran en la contabilidad general normalmente se utilizan para informes financieros de empresas. Los libros que no se registran en la contabilidad general se pueden usar para fines de informes tributarios.</td>
</tr>
<tr>
<td>Realizar el cierre anual de la Contabilidad general para varias entidades jurídicas.</td>
<td>Para acelerar el proceso de cierre de fin de año, ahora puede ejecutar el cierre de fin de año para varias entidades jurídicas desde una página de cierre anual compartida. Los grupos de personas jurídicas pueden definir, junto con los valores que se deben conservar de un año a otro. También se han creado otras mejoras de usabilidad para el proceso de cierre de fin de año.</td>
</tr>
<tr>
<td>Aprovechar las mejoras de la revalorización de divisa extranjera de la Contabilidad general.</td>
<td>Se han creado las siguientes mejoras para el proceso de Contabilidad general para la revalorización de divisa extranjera:
<ul>
<li>Se ha añadido un tipo de cambio a la cuenta principal. Ahora se utiliza este tipo de cambio para determinar el tipo de cambio durante la revalorización de la divisa. Si no se define ningún tipo de cambio, el proceso continúa usando el tipo de cambio definido en el libro mayor.</li>
<li>Ahora es más fácil seleccionar un intervalo de cuentas principales y de divisas para ejecutar el proceso de revalorización.</li>
<li>La revalorización se puede ejecutar para varias entidades jurídicas.</li>
<li>Ahora el sistema mantiene un historial de cada proceso de revalorización realizado, como hace para los procesos de revalorización de las Cuentas de clientes (AR) y las Cuentas de proveedores (AP).</li>
<li>Si ejecuta el proceso, ahora puede obtener una vista previa de los resultados de revalorización. La vista previa muestra los resultados de todas las entidades jurídicas para las que se ejecutó el proceso. A continuación, desde la vista previa puede registrar todas las entidades jurídicas o un subconjunto de ellas. También puede exportar los resultados de la vista previa a Excel.</li>
</ul></td>
</tr>
<tr>
<td>Ver transacciones para capas de registro adicionales.</td>
<td>En la página de la lista <strong>Saldo de comprobación</strong> y el informe <strong>Extracto de dimensión</strong>, ahora puede seleccionar las capas de registro adicionales que se han añadido a la Contabilidad general. Cuando selecciona las capas de registro adicionales, los ajustes para las capas de registro están comprendidas en los saldos de la página de lista o en el informe.</td>
</tr>
<tr>
<td>Adjuntar la documentación práctica a la plantilla de cierre del período financiero.</td>
<td>Anteriormente, podía adjuntar documentación después de completar una tarea. Por ejemplo, podía adjuntar un informe que se había generado. Ahora también puede adjuntar un documento práctico a la plantilla. Dicho documento práctico se copiará a cada tarea en la programación financiera del período, de modo que el propietario de la tarea puede ver las instrucciones acerca de cómo completar la tarea.</td>
</tr>
<tr>
<td>Definir la configuración de la contabilidad de empresas vinculadas desde una página compartida.</td>
<td>La página de <strong>Configuración de la contabilidad de empresas vinculadas</strong> ahora es compartida, de modo que una organización puede definir todos los pares de entidades jurídicas que pueden tramitar entre sí. Además, puede especificar una transacción en la entidad jurídica de origen pero no desde la entidad jurídica de destino. Si una entidad jurídica puede iniciar una transacción de empresas vinculadas, se deben definir los pares recíprocos. Por lo tanto, la entidad jurídica de destino también se configura como entidad jurídica de origen.</td>
</tr>
<tr>
<td>Enviar los documentos de justificación para los planes presupuestarios.</td>
<td>Puede crear una plantilla de justificación como documentación adicional para cualquier importe presupuestario solicitado. Los usuarios pueden completar los detalles de la plantilla y adjuntar la plantilla al plan presupuestario, para que se pueda usar durante el proceso de aprobación.</td>
</tr>
<tr>
<td>Habilitar las reglas avanzadas para las entradas de registro presupuestario.</td>
<td>Si las reglas avanzadas se configuran en la Contabilidad general, dichas reglas se pueden usar para las nuevas entradas y transferencias en el registro presupuestario.</td>
</tr>
<tr>
<td>Aprovechar la visibilidad mejorada de la actividad de facturación de pago anticipado.</td>
<td>Una nueva página de lista de <strong>Abrir pagos anticipados</strong> proporciona una captura del estado de la actividad de facturación de pago anticipado. La página proporciona información al departamento de cuentas de proveedores acerca de los pedidos de compra con valores restantes de pago anticipado que se deben facturar, valores facturados que se deben pagar y valores de factura pagados que se deben aplicar a las facturas estándar. Además, las mejoras de la aplicación automática de facturas de pago anticipado pagadas a las facturas estándar ayudan a los empleados de facturación a realizar las entradas de datos de forma más eficaz.</td>
</tr>
<tr>
<td>Usar el espacio de trabajo <strong>Facturación de colaboración de proveedor</strong>.</td>
<td>Un nuevo espacio de trabajo de <strong>Facturación</strong> en el área de <strong>Colaboración de proveedor</strong> permite a los proveedores externos acceder de forma segura a la información de su facturación. Por ejemplo, los proveedores pueden ver si se ha pagado una factura y enviar su propia factura. Este cambio promueve una comunicación más eficaz y oportuna con los proveedores externos. Por lo tanto, los empleados de facturación tienen menos interrupciones.</td>
</tr>
<tr>
<td>Cambiar entidades jurídicas durante la entrada de la factura.</td>
<td>Las mejoras permiten a los empleados de facturación que deben especificar facturas para varias entidades jurídicas, cambiar rápidamente la entidad jurídica de las páginas de facturación. Esta característica ahorra tiempo a los empleados de facturación, ya que no tienen que cerrar sesión en la entidad jurídica actual e iniciar sesión en una entidad jurídica diferente. La página <strong>Diario de facturas global</strong> y <strong>Facturas de proveedor</strong> permiten a los usuarios cambiar la entidad jurídica durante la entrada de datos.</td>
</tr>
<tr>
<td>Ayuda para los archivos electrónicos del Programa de registro combinado federal/estatal de la Agencia tributaria (IRS) 1099</td>
<td>Si la tecla de configuración <strong>EE. UU.</strong> está habilitada, el proceso de registro electrónico 1099 proporciona funciones adicionales que cumplen con las normas de la Agencia tributaria (IRS) para el Programa de registro combinado federal/estatal. La Agencia tributaria (IRS) ha adoptado este programa para poder enviar de forma electrónica información de vuelta a los estados participantes.</td>
</tr>
<tr>
<td>Mejoras de las soluciones</td>
<td>Las mejoras ayudan a los empleados de pago a llegar a acuerdos de forma más eficaz, ya que pueden permitir que varios pagos sin registrar se liquiden en la misma factura.</td>
</tr>
<tr>
<td>Vista de multisociedad</td>
<td>Los empleados de pagos centralizados podrán ver facturas vencidas para todas las empresas. Los espacios de trabajo <strong>Pagos de proveedor</strong> y <strong>Pagos de cliente</strong> proporcionan una mayor visibilidad y control sobre las facturas vencidas ofreciendo una forma de ver y filtrar entre empresas que forman parte de una jerarquía organizativa centralizada de pagos.</td>
</tr>
<tr>
<td>Usar el espacio de trabajo <strong>Gestión bancaria</strong>.</td>
<td>Un espacio de trabajo nuevo de <strong>Gestión bancaria</strong> ayuda a realizar un seguimiento de las cuentas bancarias y los saldos para las entidades jurídicas. Los saldos actuales y pendientes están disponibles inmediatamente para todas las cuentas, y puede volver atrás desde los saldos a los documentos detallados de transacción. También puede ver los datos del saldo histórico para cada cuenta bancaria, o un resumen para todas las cuentas bancarias de la empresa, en vistas a corto plazo y a largo plazo. Puede obtener una idea mejor de la conciliación de cuenta bancaria porque la fecha de la última conciliación se notifica para cada cuenta bancaria, y porque también hay un indicador para reconciliaciones que están en curso.</td>
</tr>
<tr>
<td>Importar extractos bancarios electrónicos para todas las entidades jurídicas en un solo paso.</td>
<td>Ahora puede importar extractos bancarios electrónicos para todas las entidades jurídicas en un solo paso. Los archivos de extractos bancarios pueden contener instrucciones de muchas cuentas bancarias y entidades jurídicas, y los archivos zip pueden contener varios archivos de extractos bancarios. Usando un único proceso de importación, puede iniciar la conciliación para todas las cuentas bancarias notificadas en todas las entidades jurídicas. Esta característica ayuda a ahorrar tiempo, ya que no es necesario cambiar entre empresas y varias importaciones del extracto. También puede ejecutar automáticamente reglas coincidentes con todos los extractos importados en cada empresa.</td>
</tr>
<tr>
<td>Seguimiento de evaluación</td>
<td>Un único activo fijo puede tener varias evaluaciones para distintos estándares de contabilidad y opcionalmente puede registrar las transacciones asociadas a la contabilidad general. Anteriormente, estas evaluaciones se seguían mediante los modelos de valor o los libros de amortización. Ahora puede seguir estas evaluaciones, que ahora se conocen como libros, mediante un conjunto común de diarios, preguntas e informes. La experiencia unificada simplifica la implementación y reduce el número de interfaces que los procesos periódicos necesitan.</td>
</tr>
<tr>
<td>Aprovechar las mejoras de las ejecuciones de la depreciación entre empresas.</td>
<td>Ahora puede comenzar una ejecución de depreciación de los activos en todas las entidades jurídicas desde la misma página. También puede registrar automáticamente los diarios después de crearlos. Puede enviar la creación y el registro de los diarios al procesamiento por lotes, de modo que la depreciación se ejecute en segundo plano. Estas mejoras reducen las deficiencias, ya que no es necesario iniciar ejecuciones individuales de depreciación de forma independiente para cada empresa. La mejora también permite una gestión centralizada mejor de los activos fijos.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gestión del capital humano

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Crear un diario de rendimiento.</td>
<td>Antes de completar la revisión, normalmente se recopila información sobre las actividades o los eventos que contribuyeron al éxito como empleado durante el período de revisión. Puede añadir una entrada a su diario de rendimiento para documentar dichas actividades y eventos. También puede conectar las actividades y eventos a un objetivo o una evaluación de rendimiento para proporcionar más información al revisor.</td>
</tr>
<tr>
<td>Crear objetivos más detallados.</td>
<td>Tiene más control sobre el contenido de los objetivos que configura. Puede crear las medidas para los objetivos, vincular entradas del diario de rendimiento a las medidas, y adjuntar y ver documentos. Puede almacenar objetivos como plantillas y reutilizarlas para una configuración rápida.</td>
</tr>
<tr>
<td>Crear evaluaciones de rendimiento más detalladas.</td>
<td>Las evaluaciones del rendimiento, que se conocen formalmente como discusiones, ahora son lo suficiente flexibles para admitir los comentarios continuaos y revisiones más formales. Puede extraer objetivos activos y publicar comentarios sobre ellos, y añadir secciones de sus competencias para revisar. Se proporcionan secciones adicionales donde puede añadir o ver medidas, entradas del diario de rendimiento, datos adjuntos y fines de conexión relacionados con la revisión.</td>
</tr>
<tr>
<td>Asociar jerarquías de puestos adicionales con flujos de trabajo.</td>
<td>Puede asociar un flujo de trabajo a una jerarquía de puestos. También puede modificar los pasos de flujo de trabajo para optimizar el proceso de aprobación de modo que se ajuste a sus requisitos empresariales. Por lo tanto, puede definir una estructura de aprobación eficaz que se ajuste a las distintas relaciones jerárquicas que usa la organización.</td>
</tr>
<tr>
<td>Soporte del flujo de trabajo para especificar números de identificación personal (PINs) en Employee Self-Service.</td>
<td>La capacidad del flujo de trabajo para los recursos humanos (HR) se ha ampliado y ahora incluye soporte para los PIN. Los empleados pueden agregar y editar el PIN para mejorar la eficacia. No obstante, los empleados de RR. HH. pueden revisar esta información para comprobar su precisión y exhaustividad antes de añadirla al registro del empleado.</td>
</tr>
<tr>
<td>Crear plantillas de objetivos y usarlas para añadir nuevos objetivos.</td>
<td>Puede crear plantillas de objetivos para objetivos que comparten muchos empleados de la empresa. Los empleados pueden añadir sus propios objetivos desde una plantilla, los administradores pueden añadir objetivos del equipo, y los miembros del equipo de RR. HH. pueden añadir objetivos para empleados por toda la empresa.</td>
</tr>
<tr>
<td>Crear grupos de objetivos y usarlos para añadir nuevos objetivos.</td>
<td>Puede añadir plantillas de objetivos a un grupo, y usar el grupo para crear uno o más objetivos para un empleado, un equipo, un puesto, un departamento o la empresa.</td>
</tr>
<tr>
<td>Obtener más control sobre el proceso de revisión.</td>
<td>Puede usar un flujo de trabajo para controlar el proceso de revisión. Puede crear plantillas de revisión y utilizarlas para crear revisiones. También puede añadir calificaciones a una revisión.</td>
</tr>
<tr>
<td>Use los períodos de revisión para definir el intervalo de tiempo para la revisión.</td>
<td>Puede definir un período de tiempo para una evaluación de rendimiento y las fechas de inicio y fin de la revisión se especificarán automáticamente. Sin embargo, puede cambiar las fechas predeterminadas según sea necesario.</td>
</tr>
<tr>
<td>Acceso a cinco nuevos paquetes de contenido de Power BI para Recursos humanos</td>
<td>Los nuevos paquetes de contenido permiten a las organizaciones de recursos humanos y a los administradores de Recursos humanos analizar lo siguiente:
<p>Métricas de recursos</p>
<ul>
<li>Desgloses demográficos por edad, género y estado civil</li>
<li>Comparar los índices de abandono cada año y ver una una lista de motivos que los empleados han dado para abandonar la organización.</li>
<li>Permite ver una lista de vacantes, así como una comparación de las vacantes y los puestos cerrados</li>
</ul>
<p>Compensaciones y prestaciones</p>
<ul>
<li>Comparar a los empleados pagados por horas y a sueldo</li>
<li>Ver el número de empleados inscritos en beneficios disponibles</li>
<li>Permite ver los empleados por tipo de empleo</li>
</ul>
<p>Contratación</p>
<ul>
<li>Analizar los candidatos en función del número de candidatos, de dónde proceden, y los puestos a los que se presentan</li>
</ul>
<p>Aprendizaje en la organización</p>
<ul>
<li>Inscripción en el curso por ubicación</li>
<li>Asistencia al curso según el estado</li>
<li>Lista de empleados registrados para los cursos</li>
</ul>
<p>Competencias y desarrollo del empleado</p>
<ul>
<li>Lista de conocimientos de los empleados</li>
<li>Desglose de tipos de aptitudes por miembro del equipo</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="localizations"></a>Localizaciones

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Las localizaciones están disponibles para 18 países adicionales:
<ul>
<li>Austria</li>
<li>Bélgica</li>
<li>Brasil</li>
<li>China</li>
<li>República Checa</li>
<li>Estonia</li>
<li>Finlandia</li>
<li>Hungría</li>
<li>Italia</li>
<li>Letonia</li>
<li>Lituania</li>
<li>Noruega</li>
<li>Polonia</li>
<li>Arabia Saudí</li>
<li>España</li>
<li>Suecia</li>
<li>Suiza</li>
<li>Tailandia</li>
</ul>
<p>Los países siguientes también requieren la ubicación del minorista. La ubicación del minorista para estos países no se ha completado y se planifica solo para H1 CY2017:</p>
<ul>
<li>Brasil</li>
<li>República Checa</li>
<li>Estonia</li>
<li>Hungría</li>
<li>Letonia</li>
<li>Lituania</li>
<li>Malasia</li>
<li>Polonia</li>
<li>Suecia</li>
</ul>
</td>
<td>Dynamics 365 for Operations está disponible en 18 países adicionales. Como parte de nuestro esfuerzo para hacer la ubicación más fácil y más configurable, las funciones reguladoras de informes electrónicos se han convertido en configuraciones de Informes electrónicos (ER), y algunos informes reguladores de Microsoft SQL Server Reporting Services (SSRS) han sido transformados a configuraciones de ER que usan plantillas de Excel. Dichas funciones se mencionan específicamente más adelante en esta tabla.</td>
</tr>
<tr>
<td>Japón: agrupar activos fijos cuando se imprime el formulario 26 y sus tablas anexadas.</td>
<td>El formulario 26 se debe enviar a cada ciudad en la que opera la empresa. Para ahorrarle esfuerzo al imprimir el formulario 26, los activos fijos se puede agrupar automáticamente y ordenar por ubicación.</td>
</tr>
<tr>
<td>Japón: consultar los importes de la depreciación acelerada y adicional en el perfil.</td>
<td>El perfil puede proporcionar una estimación precisa de los importes de la depreciación acelerada y adicional.</td>
</tr>
<tr>
<td>Japón: permite calcular progresivamente la retención de impuestos.</td>
<td>El gobierno japonés requiere el cálculo de la retención de impuestos progresivamente, en función del importe de pago.</td>
</tr>
<tr>
<td>Japón: importar el archivo del código postal de edificios grandes específicos de la empresa.</td>
<td>El archivo del código postal que la autoridad ofrece para grandes edificios específicos de la empresa se pueden importar al sistema. A continuación, la dirección se puede derivar de los códigos postales.</td>
</tr>
<tr>
<td>Japón: configurar un período inactivo para los activos fijos.</td>
<td>Los períodos inactivos permiten al usuario pausar la amortización de activos fijos durante un período específico. Esta función es requerida por la regulación.</td>
</tr>
<tr>
<td>Europa: configurar un número de registro del impuesto sobre el valor añadido (IVA) para la dirección de una parte mediante el marco del identificador del registro.</td>
<td>Puede configurar un número de registro de IVA para la dirección de una parte mediante el marco del identificador de registro y una nueva categoría de registro de <strong>Identificador de IVA</strong>.</td>
</tr>
<tr>
<td>Finlandia: configurar un número de cliente de aduanas para la dirección de una parte mediante el marco del identificador del registro.</td>
<td>Puede configurar un número de cliente de aduanas para la dirección de una parte mediante el marco del identificador de registro y una nueva categoría de registro del <strong>Identificador de cliente de aduanas</strong>.</td>
</tr>
<tr>
<td>Francia: permite imprimir las facturas de cliente en un diseño específico para Francia.</td>
<td>La copia impresa de la factura de cliente se ajusta para cumplir con los requisitos específicos de Francia.</td>
</tr>
<tr>
<td>Francia: permite aplicar la numeración cronológica de documentos por período fiscal.</td>
<td>Para cumplir con los requisitos específicos de Francia para la numeración de facturas de cliente, puede configurar las secuencias numéricas para las facturas de cliente por período fiscal.</td>
</tr>
<tr>
<td>Ubicación de Austria : configuraciones de ER</td>
<td>
<ul>
<li>Formato XML de la lista de ventas de la UE para Austria</li>
<li>Formato de Intrastat para Austria</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Austria</li>
<li>Formato de pago de domiciliación bancaria ISO20022 para Austria</li>
<li>Formato EDIFACT-PAYMUL austriaco</li>
<li>Declaración de IVA para Austria</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Bélgica: configuraciones de ER</td>
<td>
<ul>
<li>Formato BLWI para Bélgica</li>
<li>Formato XML de la lista de ventas de la UE para Bélgica</li>
<li>Informe de activos fijos para Bélgica</li>
<li>Formato Intervat para Bélgica</li>
<li>Formato Intrastat para Bélgica</li>
<li>Informe de movimientos de facturación para Bélgica</li>
<li>Formato de exportación de la transacción contable para Bélgica</li>
<li>Formato de pago de proveedor SWIFT para Bélgica</li>
<li>Formato de importación de extracto bancario CODA para Bélgica</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Bélgica</li>
<li>Formato de pago de domiciliación bancaria ISO20022 para Bélgica</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Brasil: configuraciones de ER</td>
<td>
<ul>
<li>GIA SP para Brasil</li>
<li>GIA-ST para Brasil</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de la República Checa: configuraciones de ER</td>
<td>
<ul>
<li>Formato XML para la lista de ventas de la UE para la República Checa</li>
<li>Formato de Intrastat para la República Checa</li>
<li>Declaración de IVA para la República Checa</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de China: configuraciones de ER</td>
<td>
<ul>
<li>Formato del informe de antigüedad de cliente para China</li>
<li>Formato del informe de análisis del importe debido del cliente para China</li>
<li>Formato del informe de vencimiento de proveedores para China</li>
<li>Formato del informe de análisis del importe debido del proveedor para China</li>
<li>Análisis de antigüedad del formato de pago de clientes para China</li>
<li>Formato del informe de saldos de cliente para China</li>
<li>Formato del informe de saldos de cuenta contable para China</li>
<li>Formato del informe de saldos de proveedores para China</li>
<li>Archivo GBT para China</li>
<li>Formato del archivo Golden de exportación de impuestos</li>
<li>Formato del informe de desviación de consumo de la producción para China</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Estonia: configuraciones de ER</td>
<td>
<ul>
<li>Formato XML de la lista de ventas de la UE para Estonia</li>
<li>Formato de Intrastat para Estonia</li>
<li>Extracto de reclasificación de inventario para Estonia</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Estonia</li>
<li>Informe de aviso de los saldos de proveedor del cliente para Estonia</li>
<li>Declaración de IVA para Estonia</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Finlandia: configuraciones de ER</td>
<td>
<ul>
<li>Formato TXT de la lista de ventas de la UE para Finlandia</li>
<li>Formato de Intrastat para Finlandia</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Finlandia</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Hungría: configuraciones de ER</td>
<td>
<ul>
<li>Formato XML de la lista de ventas de la UE para Hungría</li>
<li>Formato de Intrastat para Hungría</li>
<li>Formato simplificado Intrastat para Hungría</li>
<li>Formato de exportación de factura enumerada para Hungría</li>
<li>Declaración de IVA para Hungría</li>
<li>Declaración de IVA desglosado para Hungría</li>
<li>Extracto de inventario para Hungría</li>
<li>Formato de pago MultiCash para Hungría</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Italia: configuraciones de ER</td>
<td>
<ul>
<li>Formato de Intrastat para Italia</li>
<li>Formato de factura de proyecto para Italia</li>
<li>Formato de factura de ventas para Italia</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Italia</li>
<li>Formato de pago de domiciliación bancaria ISO20022 para Italia</li>
<li>Formato de remesa de recaudación RIBA para Italia</li>
<li>Informe de transacciones tributarias nacionales para Italia</li>
<li>Informe de lista negra para Italia</li>
<li>Informe del Modello770 para Italia</li>
<li>Informe anual de comunicaciones de impuestos para Italia</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Letonia: configuraciones de ER</td>
<td>
<ul>
<li>Informe de uso de recibos en efectivo (LV)</li>
<li>Formato XML de la lista de ventas de la UE para Letonia</li>
<li>Formato XML de correcciones de la lista de la UE para Letonia</li>
<li>Formato Intrastat (A) para Letonia</li>
<li>Formato Intrastat (B) para Letonia</li>
<li>Lista de recuento de inventario para Letonia</li>
<li>Extracto de recuento de inventario para Letonia</li>
<li>Movimiento de inventario para Letonia</li>
<li>Nota de entrega de transferencia interna para Letonia</li>
<li>Documento de reclasificación de inventario para Letonia</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Letonia</li>
<li>Declaración de IVA para Letonia</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Lituania: configuraciones de ER</td>
<td>
<ul>
<li>Formato XML de la lista de ventas de la UE para Lituania</li>
<li>Formato Intrastat para Lituania</li>
<li>Extracto de inventario para Lituania</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Lituania</li>
<li>Informe de interconciliación de proveedor de cliente para Lituania</li>
<li>Declaración de IVA para Lituania</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Noruega: configuraciones de ER</td>
<td>
<ul>
<li>Formato de la carta de cobro para Noruega</li>
<li>Formato de pago AutoGiro para Noruega</li>
<li>Formato de pago de un cliente AvtaleGiro para Noruega</li>
<li>Formato de pago de un cliente eFaktura para Noruega</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Noruega</li>
<li>Formato de pago NETS para Noruega</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Polonia: configuraciones de ER</td>
<td>
<ul>
<li>Formato Intrastat para Polonia</li>
<li>Documentos del almacén para Polonia</li>
<li>Documento de reclasificación de inventario para Polonia</li>
<li>Formato de pago MultiCash para Polonia</li>
<li>Formato de pago exterior MultiCash para Polonia</li>
<li>Informe de confirmación de los saldos de proveedor del cliente para Polonia</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Arabia Saudí: configuraciones de ER</td>
<td>Formato de asignación de gastos varios de Bank LC para Arabia Saudí</td>
</tr>
<tr>
<td>Ubicación de España: configuraciones de ER</td>
<td>
<ul>
<li>Formato TXT de la lista de ventas de la UE para España</li>
<li>Formato Intrastat para España</li>
<li>Formato de factura de proyecto para España</li>
<li>Formato de factura de ventas para España</li>
<li>Formato de pago de transferencia de crédito ISO20022 para España</li>
<li>Formato de pago de domiciliación bancaria ISO20022 para España</li>
<li>Formato de libro de registro de IVA español</li>
<li>Formato de resumen de libro de registro de IVA español</li>
<li>Exportar a ASCII el Modelo 347 para España</li>
<li>Informe del Modelo 347 para España</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Suecia: configuraciones de ER</td>
<td>
<ul>
<li>Formato Intrastat para Suecia</li>
<li>Formato de pago del cliente Autogiro de Bankgirot para Suecia</li>
<li>Formato de los pagos de proveedor Bankgirot para Suecia</li>
<li>Formato de pago de proveedor SWIFT para Suecia</li>
<li>Formato de exportación SIE para Suecia</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Suecia</li>
</ul>
</td>
</tr>
<tr>
<td>Ubicación de Suiza: configuraciones de ER</td>
<td>
<ul>
<li>Formato de pago de DebitDirect para Suiza</li>
<li>Formato de pago de domiciliación bancaria LSV para Suiza</li>
<li>Formato de pago de transferencia de crédito ISO20022 para Suiza</li>
<li>Formato de pago de domiciliación bancaria ISO20022 para Suiza</li>
<li>Formato de importación de extracto bancario ESR para Suiza</li>
</ul>
</td>
</tr>
<tr>
<td>Alemania: pagos de proveedor de exportación en formato de DTAZV</td>
<td>Alemania requiere DTAZV con especificación de formato extranjero, lo que representa un mensaje de transferencia de crédito (pago de proveedor) de acuerdo con la especificación para los pagos fronterizos de Alemania a una cuenta bancaria extranjera o a un banco nacional en una divisa extranjera.</td>
</tr>
</tbody>
</table>

### <a name="electronic-reporting"></a>Informes electrónicos

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Configurar los informes de ER para insertar datos, en varios formatos, desde el almacenamiento de la Gestión documental a los mensajes electrónicos que se generan. | Los informes de ER pueden introducir datos en mensajes electrónicos que se generan desde el almacenamiento de Gestión documental. Por lo tanto, los datos adjuntos de un documento empresarial se pueden agregar a los mensajes electrónico que se generan para dicho documento, de acuerdo con los requisitos legales. Actualmente, estos archivos adjuntos se pueden agregar en formato MIME a un mensaje XML que se genera. Como alternativa, los archivos adjuntos se pueden agregar en formato Base64 a un mensaje binario que se genera. |
| Configurar los informes de ER para generar documentos electrónicos en Excel, Microsoft Word o formato PDF. | Una configuración permite a informes de ER generar documentos electrónicos en tres formatos diferentes: Hoja de cálculo Open XML (Excel), Word y formato de datos de Formularios XML (XFDF) (PDF). Los usuarios pueden seleccionar un formato añadiendo una plantilla de formato a un informe de ER como Excel, Word o un documento PDF. |
| Configurar los informes de ER para insertar datos en encabezados y pies de página de documentos electrónicos que se generan en formato de hoja de cálculo OpenXML, y para controlar los saltos de página. | Los informes del ER pueden especificar datos empresariales en encabezados y pies de página, y controlar dónde aparecen los saltos de página. Por lo tanto, los informes pueden dar soporte a las secciones estáticas de la parte superior e inferior para las páginas de los documentos electrónicos que se generan. También pueden admitir la paginación específica de aquellos documentos, para que cumplan con los requisitos legales. |
| Configurar el destino de los informes de ER para que los resultados se envíen por correo electrónico y para poder utilizar los datos empresariales y la lógica de ER (expresiones) para especificar, en el tiempo de ejecución, la dirección de correo electrónico que se usará. | Anteriormente, cuando configuraba un destino de ER, la dirección de correo electrónico del destinatario podía definirse en el tiempo de diseño. Ahora puede configurar una expresión en el formato de ER. Esta expresión se puede seleccionar en un destino como origen de la dirección de correo electrónico para cada configuración del formato y cada componente de salida (carpeta o archivo) por separado. Por lo tanto, cuando un informe de ER está ejecutando, cada archivo generado se puede enviar a otro destinatario, y la dirección de correo electrónico se puede definir en función de la lógica y de los datos empresariales de ER. |
| Configurar el destino de los informes de ER para que el resultado se pueda enviar a la carpeta de Microsoft SharePoint como un nuevo archivo o una nueva versión de archivo existente, y para poder utilizar los datos empresariales en el marco de Power BI de Microsoft como un conjunto de datos o un informe. | Cuando configura informes de ER, ahora puede preparar fácilmente (sin codificar) los datos empresariales solicitados para que se puedan usar por el marco de Power BI. Al ejecutar dichos informes de ER, puede proporcionar el marco de Power BI con los datos empresariales y/o los informes de Excel correspondientes que ya están disponibles. Si programa la ejecución del informe en el modo periódico, puede establecer la transmisión de datos empresariales programada desde Dynamics 365 for Operations a Power BI para mantener la programación de actualización de informes basados en Power BI. |
| Configurar los informes de ER para utilizar la parte del documento electrónico que ya se ha generado como origen de datos para generar el resto de dicho documento. | Puede configurar los informes de ER que crean el resultado en formato de texto para realizar el recuento de las líneas del documento. Esta información se puede utilizar en otras partes del documento para crear líneas que incluyan los detalles de resumen. La información de resumen (los totales y los números) se puede calcular e imprimir en los documentos electrónicos generados, sin necesidad de más transformaciones de los datos. Por lo tanto, esta función mejora el rendimiento de la ejecución de informes y ayuda a mantener el mantenimiento futuro del formato de ER configurado más fácil. |
| Configurar los informes de ER para especificar la extensión del nombre de archivo para los documentos electrónicos que se generan en formato de texto. | Puede configurar informes de ER para crear el resultado en formato de texto, para que se pueda guardar como archivo con una extensión específica. Además de la extensión .txt predeterminada, puede configurar extensiones como .csv y .prn, de acuerdo con la especificación de formato. |
| Crear nuevos informes de ER que se basan en una versión específica de un modelo de ER. | Anteriormente, cuando se creaba un nuevo formato de ER, solo la versión más reciente del modelo seleccionado de ER se podía utilizar como ubicación de origen de datos del formato. Ahora puede seleccionar cualquier versión disponible del modelo de ER seleccionado. Esta función permite mantener los informes de ER para el año actual y diseñar una nueva versión del modelo de ER para el siguiente año en paralelo. |
| Buscar los orígenes de datos y los formatos/modelos por el texto o el objeto seleccionado con solo un clic. Resolver de forma proactiva los conflictos de base y solucionar los conflictos entre las configuraciones. Configurar los informes de ER para crear los mensajes múltiples de validación para errores que se detectan hasta que se detiene la ejecución de informes. | Varias mejoras de la experiencia del usuario (UX) en el marco de trabajo de ER ayudan a los usuarios a trabajar de forma más eficiente y sencilla. |
| Mostrar el espacio de trabajo de **ER** en los informes de Power BI. | Los usuarios pueden configurar la página **Área de trabajo de ER** para que incluya los nuevos elementos de menú y elementos en directo que ejecutan los informes basados en Power BI. |

## <a name="payroll"></a>Nómina

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configurar los registros de sueldo y procesar las nóminas mediante la función equivalente a la funcionalidad del módulo <strong>Salario</strong> de Microsoft Dynamics AX 2012 R3.</td>
<td>Ahora puede configurar y procesar la nómina de EE. UU. mediante un conjunto de funciones equivalente al conjunto de funciones de AX 2012 R3.
<ul>
<li>Puede configurar ciclos y períodos de pago, ciclos de trabajo y períodos de trabajo, códigos de ganancias y grupos de códigos de ganancias, horarios, tipos de ausencias y planes de incremento de prestaciones.</li>
<li>También puede configurar las deducciones obligatorias para prestaciones e impuestos, y registrar la información de nómina para los puestos y trabajadores para fines de informes y análisis.</li>
<li>También puede configurar y gestionar las deducciones para embargos y recaudación de impuestos, y para cualquier cuota administrativa asociada.</li>
</ul>
</td>
</tr>
<tr>
<td>Supervisar y procesar el proceso del período de pago mediante el nuevo espacio de trabajo <strong>Gestión de nóminas </strong>.</td>
<td>Ahora puede supervisar fácilmente el procesamiento de su nómina. De un vistazo, los administradores de nóminas pueden ver los extractos de ganancias y pagos que requieren su atención, para que el pago se realice completamente y de forma precisa. El espacio de trabajo <strong>Gestión de nóminas </strong>permite a los usuarios supervisar y ejecutar los procesos enteramente desde un espacio de trabajo único.</td>
</tr>
<tr>
<td>Generar archivos de pago positivos para los cheques de la nómina.</td>
<td>Existe una nueva extensión para el Cobro y pago en positivo de la gestión bancaria para los pagos de nómina. La separación de los elementos del menú se ha añadido en el proceso principal para habilitar la configuración aislada específica para las nóminas. La función es idéntica a la característica positiva principal de pago que se lanzó en la versión 7.0.1 de la aplicación de Microsoft Dynamics AX (mayo de 2016). Debido a esta extensión, los datos de nómina se aíslan completamente del resto de las transacciones positivas de pago. Este aislamiento ayuda a garantizar que solo los usuarios de nóminas pueden tener acceso y ver los datos relacionados con las nóminas.</td>
</tr>
<tr>
<td>Importar líneas de extracto de las ganancias desde un origen externo mediante la nueva entidad de datos de la Línea de extracto de ganancias.</td>
<td>Una nueva entidad de datos importante habilita la integración con los sistemas de cálculo externos de tiempo y ganancias. La entidad de datos importa las líneas de extracto de ganancias y realiza la misma lógica predeterminada que el usuario especificó directamente en el extracto de ganancias. Después de la importación, las líneas se asocian automáticamente al documento correspondiente del extracto de ganancias. Si no existe un documento correspondiente al extracto de ganancias, se crea un documento automáticamente.</td>
</tr>
</tbody>
</table>

## <a name="planning-and-scheduling"></a>Planificación y programación

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Establezca la configuración de pedido predeterminada para ventas y compras, en función de las dimensiones de producto activo en el producto principal. Por lo tanto, puede definir la configuración predeterminada de pedido para la referencia de almacén (SKU) o una SKU parcial. | Puede especificar la configuración predeterminada del pedido que se aplica a una dimensión de producto o una combinación de dimensiones de producto.<p>**Ejemplo**</p><p>Se vende un producto que se denomina camiseta Polo. Este producto está disponible en dos colores: verde y azul. También está disponible en dos tallas: pequeña y mediana. El Color y la Talla son dimensiones de producto activo para la camiseta Polo. Puede bloquear las compras de todas las camisetas verdes Polo, independientemente de su talla.</p> |

## <a name="product-master-data"></a>Datos del producto principal

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configurar todos los valores predeterminados de pedido y la configuración específica de pedido al mismo tiempo, a partir de una página.</td>
<td>Esta fución proporciona una visión general mejor de los valores del artículo.</td>
</tr>
<tr>
<td>Crear una nomenclatura de los números de variante del producto.</td>
<td>Puede incluir artículos como las dimensiones de productos, atributos y caracteres en los números de variantes del producto. Al crear un pedido de ventas o un pedido de compra, puede buscar rápidamente la variante del producto específica.</td>
</tr>
<tr>
<td>Permite buscar los productos y variantes del producto en ventas y escenarios de compra.</td>
<td>Al crear una línea de ventas o línea de compra, puede buscar los productos mediante dimensiones de producto y cualquier número de producto excepto los Números de artículo comerciales globales (GTIN) y los códigos de barras. Esta búsqueda es una búsqueda de texto completo que sustituirá la búsqueda de “Empieza por” que se usa en la lista de búsqueda de ventas y compras. Esta función permite encontrar grupos de productos que tienen propiedades similares o un producto que tiene características únicas. Para activar esta función, seleccione el parámetro <strong>Habilitar consulta para búsqueda de producto</strong> en la página <strong>Parámetros de búsuqeda</strong>.</td>
</tr>
<tr>
<td>Especifique la variante del producto directamente al crear ventas o la transacción de compra. Opcionalmente, puede seleccionar una lista de combinaciones de dimensiones válidas.</td>
<td>Esta función es una mejora de la productividad.
<p><strong>Ejemplo</strong></p>
<p>Se vende un producto que se denomina camiseta Polo. Este producto está disponible en dos colores: verde y azul. También está disponible en dos tallas: pequeña y mediana. El Color y la Talla son dimensiones de producto activo para la camiseta Polo. Cuando se especifica una línea de ventas para la camiseta Polo que tiene el color verde y la talla pequeña, no es necesario introducir datos en los campos <strong>Número de artículo</strong>, <strong>Color</strong> y <strong>Talla</strong>. Puede crear la línea siguiendo uno de estos pasos:</p>
<ul>
<li>En el campo <strong>Número de artículo</strong>, especifique el número de la variante del producto, el valor de un color o la talla. En la búsqueda, encuentre la variante específico que desea vender, y cree la línea de ventas.</li>
<li>En el campo <strong>Número de artículo</strong>, introduzca el número de artículo. Vaya a cualquier campo de dimensión de producto. En la búsqueda de <strong>Dimensión del producto</strong>, verá todas las combinaciones de dimensiones emitidas que se aplican a la camiseta Polo. En un paso, puede seleccionar la variante del producto que desea vender.</li>
</ul>
</td>
</tr>
<tr>
<td>Especifique si los números de producto aparecen en las páginas transaccionales.</td>
<td>Las páginas transaccionales, como pedidos de ventas y pedidos de compra, solo muestran los campos de <strong>Número de artículo</strong> y <strong>Nombre de producto</strong>. Para ver el campo <strong>Número de producto</strong>, seleccione el parámetro <strong>Mostrar números de producto en los formularios</strong> debajo de <strong>Parámetros de gestión de la información de producto</strong>.</td>
</tr>
</tbody>
</table>

## <a name="project-management-and-accounting"></a>Gestión de proyectos y contabilidad

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Use la última selección al registrar propuestas de factura en un lote. | Los contables de proyecto pueden configurar un trabajo por lotes para recoger automáticamente las propuestas de factura para registrar, si dichas ofertas cumplen los criterios que se especifican en el trabajo por lotes. Esta función mejora la automatización del registro de la factura, ya que el trabajo por lotes se puede ejecutar continuamente y recoge automáticamente las propuestas para el registro. |
| Crear analítica en el escritorio de Power BI. | El contenido de Business Intelligence (BI) para los datos relacionados con el proyecto y los recursos se puede crear fácilmente en el escritorio de Power BI. |
| Use los pagos por adelantado de pedido de compra e inclúyalos correctamente en el proceso de estimación del proyecto. | Para los pedidos de compra del proyecto, los anticipos deben procesarse antes de que se pueda emitir a los proveedores algún pago. Dichas facturas de anticipo aparecen ahora en el proceso de estimación/reconocimiento de proyecto para proyectos de tipo **Precio fijo**. |
| Obtener acceso y gestionar las estimaciones de costes e ingresos, y los requisitos del artículo, directamente desde una tarea de estructura de descomposición de trabajo (WBS). | Puede gestionar las estimaciones de coste, de ingresos y los requisitos del artículo para una tarea WBS específica en el cuadro de diálogo de detalles para dicha tarea en la vista de planificación de WBS. |
| Seleccionar una fuente de financiación en los diarios de cuotas. | Si el contrato para un proyecto contiene varias fuentes de financiación, puede seleccionar una fuente de financiación específica cuando se registran las cuotas. Si no selecciona una fuente de financiación concreta, se usan las reglas de financiación que se especifican en el contrato para asignar la cuota. |
| Abrir informes de proyecto en Excel. | Las nuevas entidades de datos de las actualizaciones presupuetarias y del libro mayor permiten abrir los datos del informe de proyecto en Excel y crear analíticas mediante las funciones de Excel. |
| Usar solo una tecla de configuración para habilitar la función de Gestión de proyectos y contabilidad (PMA). | Las claves de configuración relacionadas con el proyecto han sido sustituidas por una clave de configuración de proyecto que activa la función de PMA. |

## <a name="retail-and-commerce"></a>Retail y Commerce

### <a name="advanced-warehouse-management-in-a-retail-store"></a>Gestión avanzada de almacén en una tienda al por menor

Los distribuidores pueden usar la solución de Gestión avanzada de almacenes (WHS) en sus tiendas y realizar las actualizaciones necesarias a las funciones actuales de punto de venta (POS). Los procesos de la solución manual deberían funcionar en una tienda igual que en cualquier otro almacén. Todos los procesos de inventario de tienda al por menor actuales y cualquier proceso de PDV que crea o actualiza transacciones de inventario, se actualizan para utilizar los requisitos específicos de los almacenes habilitados para WHS.

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Use el PDV para buscar el inventario disponible en las tiendas habilitadas para WHS. | Cuando busca inventario, el proceso debería funcionar igual que antes. La búsqueda debería mostrar las cantidades disponibles a nivel de almacén, y no debería tener en cuenta el estado de la Ubicación, de Inventario, o de Dimensiones del número de matrícula. |
| Use el PDV para procesar el recibo de un producto para un pedido de transferencia en un almacén habilitado para WHS. | Puede recibir pedidos de transferencia en los PDV para artículos y tiendas habilitadas para WHS. El usuario debería poder seleccionar las ubicaciones donde recibir y poder introducir los identificadores de matrícula para rellenar automáticamente las líneas que recibe. |
| Use el PDV para procesar el recibo de un producto para un pedido de compra en un almacén habilitado para WHS. | Puede recibir pedidos de compra en el PDV para artículos y tiendas habilitadas para WHS. El usuario debería poder seleccionar las ubicaciones donde recibir y poder introducir los identificadores de matrícula para rellenar automáticamente las líneas que recibe. |
| Use el PDV para procesar un envío de productos desde una tienda habilitada para WHS. | Puede registrar las transferencias desde el PDV para artículos y tiendas habilitadas para WHS. El usuario debería poder seleccionar las ubicaciones desde las que enviar, el estado de inventario se debería generar automáticamente y las matrículas deberían omitirse. |

### <a name="enable-seamless-omni-channel-commerce"></a>Habilitar el comercio fluido para todos los canales

El comercio fluido de todos los canales se refiere a la gestión y el procesamiento de pedidos a través de tiendas físicas, escaparates en línea, centros de asistencia telefónica y experiencias de comercio móvil. En esta versión, se han hecho las siguientes inversiones en este área:

- Mejoras a la publicación para los escaparates de comercio electrónico
- Una aplicación móvil nueva destinada al consumidor que habilita el descubrimiento de productos, la gestión de la cuenta y las compras en línea.

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Consumidor: la versión actual de la aplicación destinada al consumidor habilita las siguientes funciones: búsqueda de producto, navegación por categorías, añadir al carrito y compra como invitado. Los distribuidores también pueden colocar su marca en la aplicación y enviarla luego a las tiendas de aplicaciones de Android e iOS. | Los distribuidores pueden crear fácilmente una aplicación destinada al consumidor que permite a los clientes navegar, buscar productos y enviarlos como invitado desde sus dispositivos móviles. |
| Listas de favoritos del cliente para escaparates de comercio electrónico | Los proveedores independientes de software (ISV) pueden usar el control de la lista de favoritos para permitir a los usuarios crear y gestionar varias listas en su escaparate en línea y ver/usar esas listas en el PDV. |
| Creación asincrónica del cliente mediante los escaparates de comercio electrónico | Los ISV podrán crear cuentas de cliente incluso cuando el Commerce Data Exchange: servicio en tiempo real no está disponible. |
| Publicar los productos del canal desde el Servidor del distribuidor a los escaparates de terceros. | El Servidor del distribuidor admite la autenticación de "servicio a servicio". Los ISV pueden aprovechar la publicación del producto del canal desde el Servidor del distribuidor a los escaparates de terceros. |

### <a name="extensibility"></a>Extensibilidad

- Los proyectos de tiempo de ejecución de comercio ahora están cerrados a Retail SDK
- Mejor despliegue y servicio a través de los paquetes de componentes de Microsoft y de los paquetes de ISV para PDV, Servidor del distribuidor, bases de datos, pagos y estaciones de hardware.

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| CRT/Servidor de distribuidor: los distribuidores o ISV pueden ampliar CRT mediante los vínculos de extensión. Los cambios del código en línea ya no se admiten. | Para habilitar la integración y la implementación continuas, los cambios del código en línea deberían evitarse por completo. Además, para admitir la respuesta fácil del hotfix sin ningún código de fusión e implantación para componentes de CRT. |

### <a name="personalized-product-recommendations"></a>Recomendaciones de productos personalizados

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Ver las recomendaciones personalizadas de productos en varios puntos de contacto en el punto de venta (PDV) para determinar el posible interés de un cliente sobre la base de su historial de compras, artículos en su lista de deseos, y artículos que otros clientes han comprado en línea y en tiendas físicas. | Para los minoristas con grandes catálogos, las recomendaciones personalizadas ayudan al cliente a descubrir los productos y a capacitar a los empleados de la tienda con una relación con clientes inteligente. Al mostrar productos orientados a los intereses y hábitos de compra de un cliente, las recomendaciones de productos pueden ayudar a aumentar las ventas minoristas y mejorar la retención de clientes. En Retail, las recomendaciones de producto son impulsadas por servicios cognitivos y el aprendizaje automático de Microsoft Azure. |

### <a name="pos-task-recorder"></a>Grabador de tareas de PDV

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Los distribuidores pueden usar el Grabador de tareas de PDV para generar material para la formación, diagramas de modelador del proceso empresarial (BPM) y generar el contenido de la Ayuda para mejorar la productividad y hacer un mejor análisis y diseño de las aplicaciones. | Para habilitar la integración y la implementación continuas, los cambios en línea deberían evitarse por completo. Además, para admitir la respuesta fácil del hotfix sin ningún código de fusión e implantación para componentes de CRT. |
| Ayuda en tiempo real en el PDV. | El cajero/administrador puede obtener ayuda en tiempo real del PDV en el proceso empresarial sin intercambiar el contexto. |

### <a name="store-system-providing-a-seamless-on-premises-store-experience"></a>Sistema de la tienda: proporcionar una experiencia fluida en las instalaciones de la tienda

El sistema de tiendas es una selección de la implementación de los distribuidores que ayuda a establecer un conjunto de operaciones de tienda, ya sea en las instalaciones de una tienda, en la nube pública de Microsoft o la nube privada propia del cliente. En esta versión, el ámbito es solo en almacén. Para mejorar los entornos que tienen conectividad de red lenta y no fiable, debemos proporcionar una opción para que los distribuidores implementen la base de datos del canal y el Servidor de distribuidor en la tienda. Entonces podrán seguir trabajando con sus escenarios de negocio principales incluso cuando no hay conectividad con la central (HQ). Según los distintos puntos de datos, que incluyen discusiones del equipo de ingeniería, resultados de encuestas a clientes y análisis de la competencia, hemos identificado el ámbito de la solución siguiente como ajuste ideal para nuestros clientes de destino:

- Un paquete de autoservicio está disponible para el sistema Tienda.
- La instalación predeterminada es una implementación de una casilla pero se permite la implementación personalizada.
- Se permite la fácil implementación/autoservicio.
- El Servidor de distribuidor y la base de datos del terminal se encuentran en el almacén, así como el servicio de cliente de Async.
- El Servidor del distribuidor en la tienda se comunica directamente con el Servidor de objetos de la aplicación (AOS) en la central (HQ) para el sistema Tienda.
- Soporte de situaciones de terminales cruzadas donde no hay conectividad con HQ.
- Retail Modern POS y el PDV en la nube siempre se comunican con Retail Server en la tienda.
- Soporte de Retail Modern POS y PDV en la nube donde no hay conectividad HQ.
- Soporte para Retail Modern POS: base de datos sin conexión específica (aislada de cada instancia de Retail Modern POS) donde no hay conectividad HQ.
- La autenticación se basa en el "servicio a servicio" solo para el sistema Tienda.
- Las llamadas del Servicio en tiempo real no se admiten si no existe ninguna conectividad a internet.
- La conectividad directa de la base de datos de Retail Modern POS a la base de datos del canal no se admite.
- Se permite la telemetría/monitorización

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Un distribuidor propietario descarga el instalador de autoservicio del sistema de Tienda de la página de la base de datos del canal en la central de Dynamics AX y descarga el archivo de configuración. | El distribuidor puede descargar sin problemas el paquete de autoservicio. |
| El distribuidor instala el sistema Tienda mediante el instalador de autoservicio. | El distribuidor puede instalar el sistema Tienda mediante el instalador de autoservicio. |
| El administrador de TI configura el sistema Tienda en Dynamics 365 for Operations (base de datos del canal, perfil del canal, tienda y paquete desplegable). | El administrador de IT puede configurar el sistema Tienda fácilmente y de forma eficaz. |
| El distribuidor opera el Retail Modern POS en la tienda física y puede realizar operaciones en tiempo real, como emitir tarjetas regalo, si hay conectividad. | El distribuidor puede realizar acciones en tiempo real desde el sistema Tienda cuando hay conectividad. |
| El distribuidor puede sincronizar los datos del sistema Tienda física a HQ siempre que haya conectividad. | El distribuidor puede sincronizar a y desde el sistema Tienda siempre que haya conectividad. |
| El distribuidor puede tener comunicación segura entre el sistema Tienda física y HQ. | El distribuidor puede comunicar de forma segura desde el sistema Tienda siempre que haya conectividad. |
| El administrador de IT y Microsoft Operations pueden supervisar y notificar el sistema Tienda física (los diagnósticos y los cambios de informes). | El administrador de IT y Microsoft Operations pueden supervisar de forma segura el sistema Tienda y solucionar los problemas eficientemente. |

### <a name="universal-windows-platform-app-for-retail-modern-pos"></a>Aplicación de plataforma de Windows universal para Retail Modern POS

Actualmente, Retail Modern POS solo está disponible como aplicación de Windows 8.1 para equipos de escritorio y tabletas, y como PDV en la nube para navegadores de escritorio o tabletas. En esta versión, el PDV moderno al por menor se convierte en una aplicación de la Plataforma Windows universal (UWP). Este cambio permitirá a Retail Modern POS ejecutarse en cualquier dispositivo de Windows 10 (escritorio, tableta o teléfono) e incluso cambiar entre las vistas de los dispositivos habilitados para Continuum.

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Habilitar la función de PDV importante para dispositivos pequeños. | La función de PDV al por menor está disponible para teléfonos y otros dispositivos pequeños que funcionan con Windows 10. |

## <a name="supply-chain-management"></a>Gestión de la cadena de abastecimiento

### <a name="consignment-inventory"></a>Inventario de entrega

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Como proveedor, puede almacenar las materias primas en el almacén del cliente. Como cliente, puede posponer la compra real hasta que las materias primas se necesitan para la producción. | Conservar un inventario de materias primas puede implicar grandes costes. Con la utilización del inventario de envío, un proveedor puede almacenar las materias primas en el almacén del cliente. De este modo, el cliente puede posponer la compra real hasta que las materias primas se necesitan para la producción. Las materias primas se piden y reciben mediante un pedido de reabastecimiento de envío. Dicho pedido de reabastecimiento registra las transacciones físicas pero no afecta a la contabilidad general. Para distinguir entre los artículos de inventario propiedad del cliente y los artículos de inventario propiedad del proveedor, puede usar la dimensión de inventario del Propietario. El cambio de propiedad para el inventario la gestiona un proceso del diario que controla la transferencia de propiedad para las materias primas del inventario propiedad del proveedor al inventario propiedad del cliente. Este proceso activa la creación de un pedido de compra y un recibo de producto.<blockquote>[!NOTE] Esta función se limita al envío de entrada de las materias primas para la producción. No se integra con la Gestión de almacenes (WHS) y la Gestión de transporte (TMS).</blockquote> |
| Como proveedor, recoge la información acerca del importe de inventario consignado que se transfiere al cliente. | Para facturar a un cliente, el proveedor requiere información acerca de las materias primas que se han adquirido desde el inventario de envío y la fecha de la compra. El proveedor también puede supervisar el inventario disponible en la ubicación del cliente mediante la interfaz de colaboración de proveedor. |
| Mover el inventario propiedad del proveedor mediante un diario de transferencia. | Para realizar un seguimiento de la posición física del inventario propiedad del proveedor, debería poder registrar la posición en el sistema. Mediante el uso de un diario de transferencia, puede registrar el movimiento físico del inventario, como el movimiento desde una ubicación en un almacén a otra en ese mismo almacén. |
| Ajustar el inventario propiedad del proveedor mediante un diario de recuento. | Es importante que se conserve el inventario del sistema disponible sincronizado con el inventario físico real. El inventario propiedad del proveedor se puede ajustar dentro y fuera mediante procesos de recuento como procesos de ajuste de cantidad y diarios de recuento. |
| Descubra más información acerca del soporte del envío en Dynamics 365 for Operations | Para obtener más información sobre el soporte para los procesos de envío, consulte [Envío](../../../supply-chain/inventory/consignment.md), [Configuración del envío](../../../supply-chain/inventory/set-up-consignment.md), [Crear un pedido de reabastecimiento de envío (Guía de tareas)](../../../supply-chain/inventory/tasks/create-consignment-replenishment-order.md), y [Cambiar la propiedad del inventario de envío en base a la demanda de la producción (Guía de tareas)](../../../supply-chain/inventory/tasks/change-ownership-consignment.md). |

### <a name="vendor-collaboration-previously-known-as-the-vendor-portal"></a>Colaboración del proveedor (conocido anteriormente como el Portal de proveedores)

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Permitir que los proveedores respondan a cada línea de pedido de compra y sugieran cambios. | En algunos casos, los proveedores desean aceptar las líneas de pedido de compra pero rechazar otras. Ahora los proveedores pueden gestionar individualmente las líneas de pedido de compra. Cada línea se puede rechazar, aceptar o aceptar con cambios. Por ejemplo, los proveedores pueden cambiar la fecha de entrega, dividir la entrega y la cantidad o sugerir un artículo alternativo. |
| Permitir que los proveedores gestionen la información de la persona de contacto. | Los proveedores pueden mantener la información de la persona de contacto para la empresa. Esta información incluye nombres, direcciones de correo electrónico y números de teléfono. El acceso a esta función se concede a través de una función de seguridad dedicada. |
| Compartir con los proveedores documentos relacionados con los pedidos de compra. | Si debe compartir un documento con un proveedor, como un documento acerca de los requisitos, es conveniente vincular el documento al pedido de compra correspondiente. El proveedor puede compartir notas y datos adjuntos con el cliente vinculando el documento a su respuesta al pedido de compra. La gestión documental es el marco de apoyo subyacente, y solo las notas y los datos adjuntos que se clasifican como “externos” se pueden compartir con los proveedores. |
| Aprovisionar nuevos usuarios de proveedor. | Si los proveedores utilizan la interfaz de colaboración del proveedor, tienen una forma fluida de solicitar nuevas cuentas de usuarios cuando los nuevos contactos necesitan tener acceso a la colaboración del proveedor. Los encargados de compras pueden enviar una solicitud para la cuenta de un usuario para una persona de contacto en la organización del proveedor. Una persona de contacto de proveedor que ya es un usuario de colaboración del proveedor también puede enviar este tipo de solicitud. Esta solicitud crea eventualmente un nuevo usuario en Dynamics 365 for Operations que tiene funciones de seguridad específicos del proveedor. También facilita una solicitud al portal Microsoft Azure B2B para aprovisionar el usuario con una nueva cuenta de usuario de Azure Active Directory (Azure AD). Los proveedores también pueden solicitar que las cuentas de usuario de proveedor específicas se desactiven, o que las funciones de seguridad se modifiquen. |
| Obtenga más información acerca de la colaboración del proveedor de Dynamics 365 for Operations. | Para obtener más información acerca de la colaboración del proveedor, consulte [Colaboración de proveedor con los proveedores externos](../../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md), [Colaboración de proveedor con los clientes](../../../supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations.md), [Gestionar usuarios de colaboración del proveedor](../../../supply-chain/procurement/manage-vendor-collaboration-users.md), [Configurar y mantener la colaboración del proveedor](../../../supply-chain/procurement/set-up-maintain-vendor-collaboration.md), y [Espacio de trabajo de facturación de la colaboración del proveedor](../../../finance/accounts-payable/vendor-portal-invoicing-workspace.md). |

### <a name="intercompany-order-processing"></a>Procesamiento de pedidos de empresa vinculada

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definir, directamente en las líneas de pedido de ventas, dónde debería originarse la demanda y cómo debería abastecerse.
<p><strong>Ejemplo</strong></p>
<p>Crear una línea de pedido de ventas y especificar la entrega directa como el tipo de entrega. Se añadirá el proveedor principal a la línea de pedido de ventas como punto de abastecimiento.</p>
</td>
<td>El flujo para aceptar el pedido ha mejorado significativamente. Ahora puede definir, directamente en las líneas de pedido de ventas, dónde debería originarse la demanda y cómo debería abastecerse. Ya no tiene que esperar hasta que todas las líneas se hayan añadido al pedido de ventas. Las nuevas opciones de las líneas de pedido de ventas le permiten especificar el tipo de entrega si especifica un proveedor. Cuando asocia un proveedor con las líneas de pedido de ventas, las cadenas del pedido se crean desde el proveedor para la entrega.
<ul>
<li>El proveedor puede ser un proveedor de empresas vinculadas que utiliza un pedido de compra y un pedido de ventas interno, o puede ser un proveedor externo que utiliza un pedido de compra externo.</li>
<li>El tipo de entrega puede ser <strong>Entrega directa</strong> o <strong>Existencias</strong>. El tipo de entrega de <strong>Existencias</strong> indica que el proveedor debe abastecer el inventario local antes de que se le envíe al cliente.</li>
</ul>
</td>
</tr>
<tr>
<td>Crear una promesa de pedido directamente desde las líneas de pedido de ventas.
<p><strong>Ejemplo</strong></p>
<p>Crear una línea de pedido de ventas que sea originaria de un proveedor de empresas vinculadas. Abandonar la línea. Las fechas de entrega se calculan en función de la disponibilidad de la empresa de abastecimiento.</p>
</td>
<td>Al crear líneas de pedido de ventas que usan la nueva información de abastecimiento, las fechas de entrega se calculan en función del control de la <strong>Fecha de entrega</strong>. Por ejemplo, si se selecciona un proveedor de empresas vinculadas, se calcula la disponibilidad en la empresa de abastecimiento. De esta manera, las cadenas de pedido se crean automáticamente junto con las líneas de pedido de ventas. Esta función permite garantizar que las fechas de entrega estén visibles en la empresa de abastecimiento, de modo que los perfiles disponibles para comprometerse (ATP) pueden gestionar la demanda anticipada directamente a medida que se crean los pedidos de ventas.</td>
</tr>
<tr>
<td>Revisar la disponibilidad de producto en todas las ubicaciones de abastecimiento, y seleccionar la mejor opción de abastecimiento.</td>
<td>La página <strong>Alternativas de entrega</strong> se ha rediseñado, y ahora proporciona información valiosa sobre todos los proveedores internos y externos aprobados. Esta información incluye las opciones de abastecimiento para las compras del proveedor. Cuando selecciona un modo de entrega, el sistema calcula las fechas de entrega posibles. Puede seleccionar sin problemas la mejor opción para el cliente y aplicar esta opción a cada línea de pedido de ventas.</td>
</tr>
</tbody>
</table>

### <a name="warehouse-enhancements-for-high-volume-distribution-centers"></a>Mejoras del almacén para los centros de distribución de grandes cantidades

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Crear el trabajo después de que las mercancías se hayan empaquetado en una estación de embalaje. | Esta función es útil cuando hay procesos adicionales después del trabajo manual de embalaje (como paletización, inspección de calidad, consolidación de envíos o cambios en los muelles de carga). El nuevo tipo de trabajo **Selección de contenedor empaquetado** permite mostrar estas tareas mediante el uso de líneas de trabajo independientes. Ahora puede mostrar las estaciones de empaquetado para generar trabajo después del empaquetado. Este trabajo se puede usar para organizar el movimiento de inventario empaquetado. |
| Contenedores de grupo en la estación de empaquetado. | Esta función permite agrupar varios paquetes en un contenedor o matrícula en la estación de empaquetado. Por ejemplo, un operador de comercio electrónico/venta al por mayor puede agrupar 100 paquetes individualmente empaquetados en un único contenedor (como un palé o una cesta). A continuación, este contenedor se puede mover, organizar o cargar a través de una sola instrucción de trabajo que un trabajador genera mediante el escaneo de un código de barras (matrícula) para el contenedor agrupado. Esta función minimiza las transacciones de trabajo para mover muchos contenedores empaquetados más pequeños. Para obtener más información, consulte [Crear un elemento de menú del dispositivo móvil para la consolidación del número de matrícula (Guía de tareas)](../../../supply-chain/warehousing/tasks/create-mobile-device-license-plate-consolidation.md). |
| Crear una directiva de lanzamiento para los contenedores empaquetados. | El trabajo desencadenado por el lanzamiento del contenedor se puede crear automáticamente o manualmente. Cuando es automático, el trabajo se genera en el cierre del contenedor mediante la directiva de la ubicación y el marco de la plantilla de trabajo. Cuando el lanzamiento es manual, el embalador puede decidir si el trabajo se debe generar para un único contenedor o para un grupo de contenedores. Esta función reduce el riesgo de que los contenedores cerrados se seleccionen y se muevan antes de que estén listos para moverse de la estación de empaquetado. También permite el lanzamiento agrupado de sistema no dirigido. |
| Reasignación de recogidas cortas | Se ha añadido el soporte para los procesos de recogida cortos, para ayudar a un socio que no puede recoger las mercancías y quiere cumplir con el pedido cuando el artículo que se requiere está disponible en otra ubicación. Se puede usar un proceso de reasignación automático que usa las mismas directivas de ubicación para recuperar las mercancías si está disponibles en otra ubicación. Como alternativa, cuando se usa la reasignación manual, el dispositivo móvil muestra una lista de ubicaciones junto con la cantidad disponible. El trabajador del almacén puede seleccionar de qué ubicación usar el inventario. Estos dos métodos se pueden establecer individualmente o combinados como un solo comando en el menú del trabajador del almacén. Cuando se usa la reasignación manual, el trabajador del almacén puede seleccionar la cantidad de recogida corta desde varias ubicaciones. Para obtener más información, consulte [Configuración de reasignación de artículo de recogida corta (Guía de tareas)](../../../supply-chain/warehousing/tasks/set-up-short-picking-item-reallocation.md). |
| Mover el inventario que tiene trabajo asociado. | Ahora puede mover el inventario que tiene trabajo asociado. Esta función puede ser útil si, por ejemplo, un trabajador desea liberar algo de espacio de entrada en el muelle y mover los palés registrados que están en espera de colocación a otra ubicación de entrada. El muelle se despeja y puede recibir una carga adicional de mercancías, y el inventario que se ha movido se actualiza con la nueva información de lugar. Esta función también se puede usar para liberar espacio en las ubicaciones de recogida moviendo el inventario que tiene trabajo asociado y creando espacio para el reabastecimiento. También puede usarla para mover cargas de una ubicación provisional a otra sin perder el trabajo de carga que se ha generado. De esta manera, la función puede ayudar a optimizar el tiempo necesario para cargar los camiones cuando llegan. Puede mover el inventario que se ha reservado para los pedidos de ventas, las emisiones del pedido de transferencia, los recibos de pedido de transferencia y los pedidos de compra. Se evita el movimiento si provoca que las líneas se dividan. Por ejemplo, si tiene una línea de trabajo de 100 piezas de un artículo, no podrá mover solo 30 piezas de dicho artículo a otra ubicación. |
| Combinar las matrículas que tienen trabajo asociado. | Puede combinar las matrículas que tienen trabajo de salida asociado a ellas. Por ejemplo, cuando se ha dividido una selección en varias piezas de trabajo, puede resultar útil permitir que las matrículas se combinen tras la entrega en la ubicación provisional. Las matrículas se pueden consolidar solo si estánn en la misma ubicación, son miembros de la misma carga y tienen la misma información de envío. |
| Trabajo de selección congelado asociado al reabastecimiento a nivel de línea. | Ahora puede congelar trabajo a nivel de línea en lugar de a nivel de encabezado, de manera que los trabajadores pueden cumplir con las líneas de selección que no están inmovilizadas por el reabastecimiento de la demanda. Por lo tanto, un mayorista que tiene pedidos de ventas de gran tamaño o un distribuidor que tiene pedidos de gran tamaño o pedidos de transferencia de reabastecimiento, pueden permitir que el trabajo de selección empiece en todas las líneas que no están sujetas al trabajo de reabastecimiento. El trabajo de selección y reabastecimiento se podrá completar en paralelo. Esta función se puede configurar para que pueda seleccionar si congelar a nivel de cabecera o a nivel de línea. También puede usar ambos métodos y crear una plantilla de trabajo para cada método. La configuración de encabezado/línea se establece en las plantillas de trabajo, pero puede cambiarla directamente en el trabajo generado. |
| Cancelar trabajo mediante el dispositivo móvil. | Ahora puede cancelar el trabajo mediante el dispositivo móvil, con o sin el reabastecimiento de la demanda. Anteriormente, tenía que usar el cliente rico. Para habilitar esta función, cree un elemento de menú del dispositivo móvil que tenga el modo establecido en **Indirecto** y el código de actividad en **Cancelar trabajo**. |

### <a name="warehouse-operation-enhancements"></a>Mejoras de la operación de almacén

| Lo que puede hacer | Por qué es importante |
|-----------------|-----------------------|
| Mostrar diferentes tipos de contenedor. | Puede usar distintos tipos de contenedor en el almacén para optimizar el almacenamiento y por otros motivos. La nueva entidad del Tipo de contenedor tiene las características físicas de los tipos de contenedor. Ahora puede asociar las matrículas con un tipo de contenedor específico y usar los límites de carga de la ubicación. Por ejemplo, puede utilizar esta función para controlar cuántos palés (u otros tipos de contenedor) permite en una ubicación específica. También se han añadido tipos de contenedor a los grupos de secuencia de la unidad para añadir tipos de contenedor predeterminados para el proceso de recepción. Los tipos de contenedor se pueden usar con directivas de entrada y salida de la ubicación. También se pueden usar en la vista de inventario disponible para ayudarle a determinar cuántos tipos de contenedor se guardan actualmente. Para obtener más información, consulte el artículo del blog [Uso de matrículas asociadas a un tipo de contenedor para impulsar los procesos de gestión de almacenes](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/). Aunque este artículo de blog describe una actualización de Microsoft Dynamics AX 2012, ahora se ha añadido el mismo soporte a Dynamics 365 for Operations. |
| Envíos inversos. | En un almacén, debe poder gestionar cambios de última hora. Por ejemplo, algunas mercancías pueden estar dañadas, por lo que no puede enviarlas. Como alternativa, un cliente puede hacer una solicitud de última hora para cancelar o cambiar un pedido. Ahora Dynamics 365 for Operations permite invertir un envío. Por lo tanto, puede cancelar un albarán de empaquetado para que pueda actualizarlo con las cantidades correctas posteriormente. De forma similar, en el flujo de entrada, puede cancelar los recibos de producto para que se pueda crear una versión actualizada. |
| Uso de palés con artículos mezclados. | Ahora puede recibir y registrar un palé "mixto". Un palé mixto consta de diferentes artículos que se agrupan sobre un palé para uno o varios pedidos de compra o líneas. Todos los registros se pueden resumir en una matrícula de destino. Este proceso se habilita a través del dispositivo móvil del almacén. Por ejemplo, cuando el palé de artículos mezclados llega al almacén, el empleado receptor identifica los artículos y las cantidades del palé antes de que el palé se mueva a las ubicaciones de lugar dedicadas. Dichas ubicaciones de colocación se identifican mediante plantillas de trabajo y directivas de ubicación. Si las ubicaciones de colocación se distribuyen sobre varios artículos que tienen ubicaciones fijas, esta función crea tantas líneas de trabajo como artículos diferentes en el palé mixto. Esta función realiza el registro y la colocación de los palés de artículos mezclados recibidos más rápido y de forma más flexible. Para obtener más información, consulte el artículo del blog [Recibir y registrar un palé con líneas de documentos de origen mixto mediante matrículas](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) y la información sobre el soporte del palé mixto del [aviso de la actualización acumulativa reciente](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Aunque este artículo de blog describe una actualización de AX 2012, ahora se ha añadido el mismo soporte a Dynamics 365 for Operations. |

### <a name="minor-feature-enhancements-in-supply-chain-management"></a>Mejoras de menor importancia de la Gestión de cadenas de suministro

<table>
<thead>
<tr>
<th>Lo que puede hacer</th>
<th>Por qué es importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Uso de entidades de datos nuevas para importar y exportar datos.</td>
<td>Puede importar y exportar datos mediante estas entidades de datos:
<ul>
<li>Factura de transporte</li>
<li>Añadir mediante el almacén y el estado de Inventario</li>
<li>Cambios de inventario</li>
<li>Presupuesto</li>
</ul>
</td>
</tr>
<tr>
<td>Use el control de Gantt mejorado para desarrollar situaciones interactivas de programación.</td>
<td>El control de Gantt mejorado permite desarrollar nuevas situaciones interactivas de programación y entregar API ampliadas que se pueden usar para personalizar el aspecto de actividades. A continuación se muestran algunos de los nuevos API:
<ul>
<li>Arrastrar y colocar verticalmente las actividades</li>
<li>Añadir/eliminar actividades</li>
<li>Previsualizar los períodos registrados en una barra de resumen</li>
<li>Cambiar el color y el estilo de los límites de la actividad</li>
<li>Cambiar el color, el estilo y el fondo del texto en la cuadrícula</li>
</ul>
</td>
</tr>
<tr>
<td>Mejor planificación de la gestión del material y los recursos.</td>
<td>Se han creado algunas mejoras a la planificación de material y de recursos:
<ul>
<li>El margen de emisión ahora se gestiona cuando un artículo está disponible.</li>
<li>Sobrescribe la fecha de entrega cuando firma pedidos planificados.</li>
<li>Conceder prioridad al cumplimiento de pedidos por encima de las existencias de seguridad.</li>
<li>Evitar la programación de los pedidos planificados en el pasado.</li>
</ul>
</td>
</tr>
<tr>
<td>Informar el consumo real de la producción y ver el estado del inventario.</td>
<td>Puede ver el consumo real de la producción. Además, una nueva casilla de verificación de <strong>Mostrar estado del inventario</strong> que se ha añadido en <strong>Movimiento</strong> en el artículo del menú de <strong>Creación de trabajo</strong> permite que pueda ver el estado del inventario.</td>
</tr>
<tr>
<td>Calcular el peso volumétrico, si los índices para el transportista de envío se basan en el peso volumétrico.</td>
<td>Se ha añadido un nuevo motor del índice de TMS que se basa en el peso volumétrico, de modo que pueda calcular el peso volumétrico.</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionales

[Novedades y cambios](whats-new-changed.md)
