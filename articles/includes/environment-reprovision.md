Al copiar una base de datos entre entornos, deberá ejecutar la herramienta de reaprovisionamiento de entornos antes de que la base de datos que se copió sea completamente funcional, con el fin de asegurarse de que todos los componentes de Retail se actualizaron.

> [!IMPORTANT]
> Es recomendable ejecutar este procedimiento tanto si usa los componentes Retail como si no, ya que la función Retail se incluye en todos los entornos. 

Antes de continuar, debe asegurarse de cumplir los siguientes requisitos previos:
1. Si se está actualizando a la versión de julio de 2017 (también conocida como 7.2) 7.2.11792.56024, aplique las siguientes revisiones de la aplicación X++ en el entorno de destino antes de ejecutar la actualización de datos en ese entorno. Estos impedirán que se produzcan varios errores durante la actualización de datos:

    - KB 4036156 - actualización menor de versión de Retail - "la secuencia numérica de variante no está establecida". Este paquete de revisiones también incluye KB 4035399 y KB 4035751. Tenga en cuenta que para usar este paquete debe tener como mínimo la Platform Update 9. Si no está seguro, instale los últimos binarios.
    
2. Si está actualizando desde Microsoft Dynamics AX 2012, instale las correcciones siguientes de la aplicación X++ en el entorno de destino antes de ejecutar la actualización de datos:
    - KB 4033183 - La actualización no minorista de Dynamics AX 2012 R2 o Dynamics AX 2012 R3 Pre-CU8 falla con Objeto no encontrado para dbo.RETAILTILLLAYOUTZONE.
    - KB 4040692 - La actualización de Dynamics AX 2012 R3 a Microsoft Dynamics 365 for Operations 7.2 falla por el índice duplicado RetailSalesLine en SalesLineIdx.
    - KB 4035490 - Degradación de rendimiento con la actualización del script GeneralJournalAccountEntry MainAccount.


Siga estos pasos para ejecutar la herramienta de reaprovisionamiento del entorno.

1. En la biblioteca del activo compartido, seleccione **Paquete implementable del software**.
2. Descargue la herramienta de reaprovisionamiento del entorno.
3. En la biblioteca del activo para su proyecto, seleccione **Paquete implementable del software**.
4. Seleccionar **Nuevo** para crear un paquete nuevo.
5. Especifique un nombre y descripción para el paquete. Puede usar **Herramienta de reaprovisionamiento de entorno** como el nombre del paquete.
6. Cargue el paquete que ha descargado antes.
7. En la página **Detalles del entorno** para su entorno de destino, seleccione **Mantener** > **Aplicar las actualizaciones**.
8. Seleccione la herramienta de reaprovisionamiento del entorno que cargó antes y a continuación seleccione **Aplicar** para aplicar el paquete.
9. Supervisar el progreso del paquete de implementación. 

Para más información acerca de cómo aplicar un paquete implementable, consulte [Aplicar un paquete implementable](../deployment/create-apply-deployable-package.md). Para más información acerca de cómo aplicar manualmente un paquete implementable, consulte [Instalar un paquete implementable](../deployment/install-deployable-package.md).
