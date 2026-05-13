> [!IMPORTANT]
> Esta es una prueba técnica real que realicé para el proceso de selección de IAMBI S.A.S para el cargo de Ingeniero de Soporte y QA.

> [!TIP]
> Las respuestas mostradas fueron las que utilicé durante la prueba y funcionaron correctamente según los resultados esperados.

# Prueba Conocimientos Soporte - IAMBI S.A.S

Gracias por hacer parte de este proceso de selección.

Esta prueba nos permitirá evaluar tus conocimientos para el cargo de Ingeniero de Soporte y QA. Por favor responde basado en tu experiencia y conocimientos técnicos.

Mucha suerte y esperamos que pronto seas parte de nuestro equipo.
> [!NOTE]
> Existen muchas maneras válidas de resolver varios de estos ejercicios. Lo importante no es copiar exactamente el mismo query o respuesta, sino llegar a la misma lógica, resultado o conclusión técnica.

---

# Información del Candidato

- Correo electrónico:
- Nombre completo:

---

# Base de Datos
<img width="860" height="483" alt="image" src="https://github.com/user-attachments/assets/88e4bbd6-0dab-4df0-9d4f-d613dab2be2a" />

---

# 1. Query Total Productos Ordenados

Escribe el query para obtener el número total de productos que han sido ordenados.
> [!TIP]
> Recomiendo intentar resolver primero cada ejercicio por tu cuenta antes de desplegar las respuestas ocultas.

<details>
<summary>Ver respuesta</summary>

```sql
SELECT SUM(Quantity) AS total_productos
FROM Orders;
```

</details>

---

# 2. Reporte Compras de Televisores

## Resultado esperado

<img width="427" height="118" alt="image" src="https://github.com/user-attachments/assets/64e8d5c6-9cd8-4069-9259-dc4a09cf8b32" />

---

Realice una consulta que permita generar el anterior reporte de compras de televisores.

<details>
<summary>Ver respuesta</summary>

```sql
SELECT
    p.Name AS Producto,
    c.Name AS Cliente,
    o.Quantity AS Cantidad,
    o.Total AS Total
FROM Orders o
INNER JOIN Client c
    ON o.ClientId = c.ClientId
INNER JOIN Product p
    ON o.ProductId = p.ProductId
WHERE p.Name = 'Televisor';
```

</details>

---

# 3. Reporte Total de Ventas por Producto

## Resultado esperado

<img width="428" height="131" alt="image" src="https://github.com/user-attachments/assets/03755092-82d9-4535-b615-5c46cce4ed58" />

---

Escribe el query para obtener el reporte total de ventas por producto.

<details>
<summary>Ver respuesta</summary>

```sql
SELECT
    p.Name AS Producto,
    p.Reference AS Referencia,
    SUM(o.Quantity) AS Cantidad,
    SUM(o.Total) AS Total
FROM Orders o
INNER JOIN Product p
    ON o.ProductId = p.ProductId
GROUP BY p.Name, p.Reference;
```

</details>

---
> [!WARNING]
> Algunas consultas SQL pueden optimizarse aún más dependiendo del motor de base de datos, volumen de información o reglas de negocio utilizadas en un entorno real.

# 4. Clientes con Compras Superiores a 10 Millones

## Resultado esperado

<img width="339" height="100" alt="image" src="https://github.com/user-attachments/assets/0d9fb32d-2d97-418f-a500-208fc87c5566" />

---

Escribe el query para obtener el reporte anterior con la lista de clientes que hayan comprado más de 10 millones.

<details>
<summary>Ver respuesta</summary>

```sql
SELECT
    c.Name AS Nombre,
    c.LastName AS Apellido,
    SUM(o.Total) AS Total
FROM Orders o
INNER JOIN Client c
    ON o.ClientId = c.ClientId
GROUP BY c.Name, c.LastName
HAVING SUM(o.Total) > 10000000;
```

</details>

---

# 5. SQL

¿Cuál es la diferencia entre las instrucciones:

- `DROP TABLE`
- `TRUNCATE TABLE`
- `DELETE FROM TABLE`

Explique brevemente.

<details>
<summary>Ver respuesta</summary>

| Comando | Función |
|---|---|
| DROP TABLE | Elimina completamente la tabla y su estructura |
| TRUNCATE TABLE | Elimina todos los registros rápidamente |
| DELETE FROM | Elimina registros específicos o todos usando condiciones |

</details>

---

# 6. Análisis de Logs

Se tiene la siguiente situación:

Se está tratando de enviar un mensaje al WhatsApp de un usuario de la tienda “Tu Tendero”, sin embargo desde la tienda reportan que el usuario no responde.

Necesitan saber si:

- El mensaje sí está llegando
- Existe alguna falla en el sistema

---

## Log

```txt
2021-09-20 14:02:20.958|57304xxxxxxx| Succesfully got contact info {"contacts":[{"input":"+57304xxxxxxx","status":"invalid"}],"meta":{"api_status":"stable","version":"2.35.4"}}

2021-09-20 14:02:21.420|ERRO|5730xxxxxxx| id 1 got error, code is 400 and response is {"meta":{"api_status":"stable","version":"2.35.4"},"errors":[{"code":1013,"title":"User is not valid","details":"not a WhatsApp user"}]}!
```

---

Díganos por favor si el mensaje llega o no al usuario final.

- Si sí llega, indique con qué línea del log pudo corroborarlo.
- Si no llega, explique cuál es la causa.

<details>
<summary>Ver respuesta</summary>

El mensaje NO llega al usuario final.

### Evidencia encontrada

```txt
"status":"invalid"
```

y posteriormente:

```txt
"User is not valid"
```

además de:

```txt
"not a WhatsApp user"
```

### Causa

El número no está registrado en WhatsApp o no es válido para la API de WhatsApp Business.

</details>

---

# 7. Soporte Técnico

¿Sabes la diferencia entre un incidente y un requerimiento?

Explique brevemente.

<details>
<summary>Ver respuesta</summary>

## Incidente

Es una falla que afecta el funcionamiento normal de un sistema.

Ejemplos:

- Error al guardar
- Sistema caído
- Login dañado

---

## Requerimiento

Es una solicitud de acceso, servicio o funcionalidad.

Ejemplos:

- Crear usuario
- Instalar software
- Asignar permisos

</details>

---

# 8. Desarrollo PHP

Elaborar un reporte en PHP usando el framework de tu preferencia.

Adjunta tu solución junto con las instrucciones necesarias para poder visualizar el reporte.

<details>
<summary>Ver respuesta</summary>

Framework utilizado: Laravel

### Ruta

```php
Route::get('/reporte', [ReporteController::class, 'index']);
```

### Ejecución

```bash
composer install
php artisan serve
```

Abrir:

```txt
http://127.0.0.1:8000/reporte
```

</details>

---

# 9. Priorización de Tickets

Son las 9:00 AM, acabas de iniciar turno y tienes estos 3 tickets pendientes.

Solo puedes atender uno de inmediato.

¿Cuál eliges primero y por qué?

---

## Tickets

### 1.

El Director General no puede imprimir un documento urgente para una reunión.

### 2.

El sistema de ventas está lento para todos los cajeros de la tienda principal.

### 3.

Un usuario nuevo necesita sus accesos porque hoy es su primer día.

<details>
<summary>Ver respuesta</summary>

El ticket prioritario sería el problema del sistema de ventas lento.

### Razones

- Afecta múltiples usuarios
- Impacta directamente las ventas
- Genera filas y retrasos
- Puede causar pérdidas económicas

</details>

---

# 10. Atención y Resolución de Incidentes

Recibes un ticket de un usuario que solamente dice:

```txt
"El sistema no sirve, me sale error cuando guardo. ¡Urge arreglarlo!"
```

No hay capturas ni más detalles.

---

## Preguntas

### ¿Qué revisarías por tu cuenta antes de contactar al usuario?

### ¿Qué le responderías al usuario sin hacerlo enojar más?

<details>
<summary>Ver respuesta</summary>

### Validaciones iniciales

- Logs del sistema
- Logs de errores
- Estado de la base de datos
- Consultas lentas
- APIs
- Últimos despliegues
- Estado del servidor

---

### Respuesta al usuario

```txt
Hola, ya estoy revisando el inconveniente para solucionarlo lo antes posible. Estoy validando internamente el error que se presenta al guardar información. Si es posible, por favor envíame una captura o los pasos realizados antes del error para ayudarte más rápido.
```

</details>

---

# Empresa

IAMBI S.A.S

Equipo 
