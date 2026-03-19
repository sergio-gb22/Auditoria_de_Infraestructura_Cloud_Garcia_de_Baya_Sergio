# Auditor-a_de_Infraestructura_Cloud_Garc-a_de_Baya_Sergio

### Misión 1: Mapeo de Seguridad
> **Objetivo:** Extraer todos los puertos de los servicios alojados específicamente en el centro de datos de París.

```xpath
/catalogo_cloud/centro_datos[@ubicacion='Paris']//servicio/@puerto /string()
```

### Misión 2: Auditoría de Mantenimiento
> **Objetivo:** Obtener la versión del sistema operativo del servidor de bases de datos identificado como 'srv-db-01'.

```xpath
/catalogo_cloud/centro_datos/servidor[@id='srv-db-01']/software/so/@version /string()
```

### Misión 3: Inventario de Alta Capacidad
> **Objetivo:** Listar todos los discos duros cuya capacidad sea igual o superior a 8 Terabytes.

```xpath
/catalogo_cloud/centro_datos//disco[@capacidad_tb >= 8] /string()
```

### Misión 4: Eficiencia Energética
> **Objetivo:** Identificar el primer servidor que se encuentre apagado para priorizar su revisión.

```xpath
/catalogo_cloud/centro_datos/servidor[@estado='apagado'][1] /string()
```

### Misión 5: Desafío del Auditor Senior
> **Objetivo:** Extraer la arquitectura de la CPU de aquellos servidores que cuentan con una GPU dedicada.

```xpath
/catalogo_cloud/centro_datos/servidor[hardware/gpu]/hardware/cpu/@arquitectura /string()
```
