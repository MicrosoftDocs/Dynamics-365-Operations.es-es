---
title: Conseguir candidatos usando grupos de talentos
description: Este tema explica cómo crear y configurar grupos de talentos en Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-22-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: d2d680aa54e4610959c12bc1feef11ba8f30b0ca
ms.sourcegitcommit: 40be0096af50e74d9946e382d3bbd2683bed1fc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2019
ms.locfileid: "1711303"
---
# <a name="source-candidates-by-using-talent-pools"></a>Conseguir candidatos usando grupos de talentos

[!include[banner](../includes/banner.md)]


Los reclutadores y los administradores de contratación pueden organizar a los candidatos mediante la funcionalidad de grupos de talentos en Attract. Las grupos de talentos pueden ayudarle a realizar el seguimiento de todos los candidatos y a involucrarlos para trabajos en su empresa.

## <a name="create-and-share-a-talent-pool"></a>Crear y compartir un grupo de talentos

Cualquier usuario que tenga el rol de reclutador, administrador de contratación, o administrador de Attract puede crear grupos de talentos. El propietario de un grupo de talentos también puede compartir dicho conjunto con otros usuarios de modo que grupos de usuarios, especialmente reclutadores, puedan estudiar un conjunto compartido de candidatos.

Los contribuidores a un grupo de talentos pueden ver la lista de candidatos en dicho grupo. También pueden agregar a candidatos al grupo o eliminar candidatos de él.

Ejecute los pasos siguientes para crear y compartir un grupo de talentos.

1. En la página principal de Attract, en el panel de navegación izquierdo, seleccione **Grupos de talentos**.

    La pestaña **Mis grupos de talentos** muestra todos los grupos de talentos a los que tiene acceso, con detalles acerca de cada uno. Los detalles incluyen el propietario del grupo y el número de candidatos que contiene.

1. En la parte superior derecha de la página, seleccione **Nuevo** para abrir el cuadro de diálogo **Crear grupo de talentos**.
1. Escriba un nombre único para el grupo de talentos.
1. Para agregar personas como colaboradores del grupo, encuentre sus nombres mediante el selector de personas y, a continuación, agréguelos a la lista. Puede compartir un grupo de talentos solo con usuario que tienen la función de reclutador, administrador de contratación, o administrador de Attract.
1. Seleccione **Agregar** para crear el grupo de talentos.
     > [!NOTE]
     > Como alternativa, puede agregar contribuidores a un grupo de talentos tras haberlo creado. También puede gestionar el acceso a un grupo de talentos. Por ejemplo, puede revocar el acceso de un usuario al grupo de talentos.
     > - Para agregar contribuidores a un grupo de talentso existente que posee, en la pestaña **Mis grupos de talentos**, en la parte superior derecha de la tarjeta del grupo de talentos, seleccione los puntos suspensivos (**…**) y a continuación seleccione **Editar**. Encuentre a las personas mediante el selector de personas, y agréguelas a la lista. 
     > - Para revocar el acceso de un usuario al grupo de talentos, en la parte superior derecha de la tarjeta de grupo de talentos, seleccione los puntos suspensivos (**…**) y luego seleccione **Editar**. En la pestaña **Administrar el acceso**, seleccione el botón de papelera que está junto al usuario.

6. Seleccione **Actualizar** para completar y guardar la operación.

> [!NOTE]
> Para crear más de un grupo de talentos, la organización debe tener el complemento de contratación completa.

## <a name="add-and-remove-candidates"></a>Agregar y quitar candidatos

El propietario y los contribuidores al grupo de talentos pueden agregar candidatos al grupo de talentos, ver los candidatos que contiene y eliminar los candidatos del grupo.

1. En la pestaña **Mis grupos de talentos**, seleccione un grupo de talentos para abrirlo.

    Se mostrará una lista de los candidatos que forman parte del grupo de talentos.

1. Para agregar candidatos al grupo de talentos, seleccione **+ Nuevo** en la parte superior derecha para abrir el cuadro de diálogo **Agregar candidato** y, a continuación, uno de los siguientes.

    - Para agregar un candidato interno, puede buscar la persona por su dirección de correo electrónico. Tras completar una búsqueda con éxito, la dirección de correo electrónico del candidato, el nombre, y el apellido se rellenan. Si tiene el currículum del candidato o algún documento relacionado con él, puede cargarlo en este punto. A continuación seleccione **Agregar** para agregar el candidato al grupo de talentos.
    - Para agregar un candidato externo, especifique manualmente su dirección de correo electrónico, nombre y, apellido. Si tiene el currículum del candidato o algún documento relacionado, puede cargarlo en este punto. A continuación seleccione **Agregar** para agregar el candidato al grupo de talentos.
    - Para agregar varios candidatos, seleccione la pestaña **De Excel**. A continuación puede descargar la plantilla de Microsoft Excel adecuada, especificar los detalles de los candidatos, guardar la hoja de cálculo de Excel, y cargarla a la aplicación.

        Si se encuentran errores en la hoja de cálculo, recibirá mensajes sobre ellos. Puede corregir los errores e intentar volver a cargar la hoja de cálculo. Cuando no se encuentren más de errores, seleccione **Agregar** para cargar la hoja de cálculo. La hoja de cálculo se procesa en segundo plano y se le notificará cuando se hayan agregado todos los candidatos al grupo de talentos.

1. Para quitar un candidato existente del grupo de talentos, en la columna **Acción** seleccione el botón de papelera para dicho candidato.

## <a name="search-and-view-candidate-profiles"></a>Buscar y ver perfiles del candidato

> [!NOTE] 
> Esta característica está actualmente en vista previa. Si desea probarlo, debe [activarlo en la configuración de administrador de Attract](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature). 

Las reservas de talentos le permiten ver el perfil de un candidato, la información de LinkedIn, documentos relacionados y el historial de la aplicación. Puede buscar la base de datos completa de todos los candidatos agregados a cualquier reserva de talentos, incluidos candidatos cerrados y activos.

>[!NOTE]
> Al agregar nuevos candidatos, las nuevas adiciones pueden tardar hasta 15 minutos en ser indexadas para la búsqueda.

Con la experiencia mejorada de la búsqueda, puede buscar en todos los documentos de candidato y filtrar por los medallistas de plata, los orígenes, las aptitudes, la formación, etc. En versiones anteriores, se tenía que especificar la entidad que se quiere buscar. Attract ahora puede buscar todos los campos relacionados con el candidato y alinear los resultados.

1. Para iniciar una búsqueda nueva en la base de datos del candidato, escriba el texto que desea buscar en el cuadro de búsqueda en la pestaña **Reservas de talentos**. 

Puede escribir cualquier el nombre del candidato o cualquier atributo que esté buscando. Para separar atributos, use un espacio.

Puede limitar los resultados cambiando su consulta de búsqueda o con los filtros inteligentes en el lado izquierdo de la página.

Los resultados de la búsqueda muestran resaltados los atributos que coincidan con la consulta de búsqueda. Permite seleccionar cualquier candidato interesado en ver su perfil.

### <a name="syntax-highlights"></a>Resaltes de la sintaxis 

| Operador | Uso                                                      | Ejemplo              |
|----------|------------------------------------------------------------|----------------------|
| \*       | Permite buscar las subcadenas; se puede utilizar para devolver todos los registros | Entrada: Mi\* <br></br> Resultado: todos los registros con campos que empiecen por "Mi", por ejemplo, Microsoft los sistemas micro, las empresas de Midtown, o Middleton <br></br>Entrada: \* <br></br> Resultado: todos los registros en la base de datos |
| “”       | Búsquedas de una coincidencia exacta                                | Entrada: “Microsoft” <br></br> Resultado: todos los registros que contengan “Microsoft”                    |

>[!WARNING]
> No desactive la búsqueda de relevancia para su instancia de Common Data Service. Esto deshabilitará la experiencia de búsqueda en Attract.

Todos los usuarios tienen una vista común de los perfiles del candidato. La pestaña **Perfil** muestra la información acerca de las aptitudes, experiencia profesional, y educación que el candidato ha proporcionado como parte de su solicitud usando el portal de proyectos profesionales.

- Puede ver los detalles del contacto para el candidato. También puede editar o actualizar la información según sea necesario mediante el botón **Detalles de edición**.

- Puede ver el historial completo de solicitudes del candidato. Puede ver todos los trabajos que ha solicitado el candidato en su organización y el estado de esas solicitudes. Si es parte de un equipo de contratación para un trabajo, puede seleccionar **Ver** para estudiar en detalle la solicitud.

- La pestaña **Documentos** muestra los documentos que el candidato ha agregado desde su perfil o durante las solicitudes del trabajo. Puede usar esta ficha o gestionar los curriculums vitae del candidato, las cartas de presentación, la cartera, y así sucesivamente. También puede usar esta ficha para agregar documentos.

    Para ver un documento, seleccione el nombre del documento en la lista de documentos. Puede ver los documentos Microsoft Word en la aplicación mediante Microsoft Office 365. También puede descargar los documentos en su equipo local mediante la opción **Descargar** para cada documento.

- La pestaña **LinkedIn** muestra la información de LinkedIn del candidato. Para usar esta ficha, debe conectar su cuenta de LinkedIn en la configuración del usuario, y su conexión de LinkedIn Recruiter del entorno debe establecerse. Para obtener más información, consulte [Abastecimiento con LinkedIn Recruiter](./attract-linked-in-recruiter.md).

> [!NOTE]
> Solo los candidatos pueden actualizar sus aptitudes, historial de aprendizaje y experiencia profesional.

## <a name="add-candidates-from-a-talent-pool-to-a-job"></a>Agregue los candidatos de un grupo de talentos a un trabajo

Desde los resultados de búsqueda o un grupo de talentos, puede insertar un candidato a cualquier trabajo activo para el que está contratando. Para insertar un candidato a un trabajo específico, siga estos pasos.

1. Encuentre el candidato usando la opción de la búsqueda y, a continuación, abra su perfil. Como alternativa, abra el grupo de talentos desde la ficha **Mis grupos de talentos**, busque el candidato en su grupo de talentos y, a continuación, abra su perfil.

1. En la página de perfil del candidato, seleccione **Agregar al trabajo** en la parte superior derecha. 
     
     Se muestra una lista de trabajos en relación a los cuales pertenece al equipo de contratación, como reclutador o jefe de contratación.

1. Seleccione el trabajo al que agregará el candidato y luego seleccione **Agregar**. También puede buscar el trabajo mediante el campo de búsqueda de la parte superior del cuadro de diálogo **Agregar candidato al trabajo**.

    Si la prospección se habilitó para el trabajo, se agrega el candidato a la fase **Cliente potencial**.

    Si la prospección no se habilitó para el trabajo, se agrega el candidato a la fase **Aplicar**. En función de la configuración de trabajo, el candidato también puede recibir un mensaje de correo electrónico donde se puede ver su solicitud.

## <a name="add-candidates-from-a-job-to-a-talent-pool"></a>Agregar candidatos de un trabajo a un grupo de talentos

Con frecuencia, hay varios buenos candidatos que no se seleccionan para un trabajo, pero no quiere perder su seguimiento. En este caso, puede que desee agregar los candidatos a un grupo de talentos de modo que pueda invitarlos para que presenten una solicitud para próximos trabajos.

1. Vaya al trabajo del que desea agregar un candidato.

1. Seleccione el candidato, y abra su solicitud.

1. En la página de solicitud, seleccione **Agregar a grupo de talentos**. Se muestra una lista de grupos de talentos a los que tiene acceso.

1. Seleccione o busque el grupo de talentos y, a continuación, seleccione **Agregar** para agregar el candidato a ese grupo de talentos.
