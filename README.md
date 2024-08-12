# soporte-techical-test
### **Instrucciones Generales**

1. El aspirante debe crear una base de datos postgres local y recrear las tabla impuesto,cliente,producto,cpedidos,dpedidos para lo cual se adjunta sentencia SQL(Creacion de tablas).
2. El aspirante debe poblar las tablas creadas con el SQL adjunto(Poblar Tablas)

### **Creacion de tablas**
  ```sql
CREATE TABLE impuesto (
    imp_id SERIAL PRIMARY KEY,
    imp_nombre CHARACTER VARYING,
    imp_porcentaje CHARACTER VARYING,
    imp_activo boolean
);


CREATE TABLE cliente (
    cli_id SERIAL PRIMARY KEY,
    cli_nombre CHARACTER VARYING,
    cli_apellido CHARACTER VARYING,
    cli_activo boolean
);


CREATE TABLE producto (
    pro_id SERIAL PRIMARY KEY,
    pro_descripcion CHARACTER VARYING,
    pro_precio NUMERIC(10, 2),
    pro_activo boolean
);


CREATE TABLE cpedidos (
    cpe_id SERIAL PRIMARY KEY,
    cli_id INT REFERENCES cliente(cli_id),
    cpe_fecha DATE,
    imp_id INT REFERENCES impuesto (imp_id),
    cpe_subtotal NUMERIC(10, 2),
    cpe_impuesto NUMERIC(10, 2),
    cpe_total NUMERIC(10, 2)
);


CREATE TABLE dpedidos (
    dpe_id SERIAL PRIMARY KEY,
    cpe_id INT REFERENCES cpedidos(cpe_id),
    pro_id INT REFERENCES producto(pro_id),
    dpe_cantidad NUMERIC(10, 2)	,
    dpe_precio NUMERIC(10, 2),
    dpe_total NUMERIC(10, 2)		
);

```

### **Poblar Tablas**
```sql
INSERT INTO "public"."impuesto" ("imp_id", "imp_nombre", "imp_porcentaje", "imp_activo") VALUES (1, '15% VENTAS', '15', 't');
INSERT INTO "public"."impuesto" ("imp_id", "imp_nombre", "imp_porcentaje", "imp_activo") VALUES (2, '12% VENTAS', '12', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (1, 'CARLOS', 'LOPEZ', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (2, 'PEDRO', 'LITUMA', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (3, 'ANDY', 'ESPINEL', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (4, 'MANUEL', 'CARCHI', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (5, 'SAMUEL', 'PEREZ', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (6, 'LENIN', 'GOMEZ', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (7, 'ERICK', 'LOPEZ', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (8, 'BORIS', 'ALVEAR', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (9, 'CESAR', 'SARMIENTO', 't');
INSERT INTO "public"."cliente" ("cli_id", "cli_nombre", "cli_apellido", "cli_activo") VALUES (10, 'SANTIAGO', 'LITUMA', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (1, 'TECLADO MECANICO', '125.06', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (2, 'RATON INALAMBRICO', '91.85', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (3, 'MONITOR LED 24', '54.47', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (4, 'SSD 500GB', '219.14', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (5, 'MEMORIA RAM 16GB', '63.48', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (6, 'PROCESADOR INTEL I5', '469.75', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (7, 'PLACA BASE ATX', '311.61', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (8, 'FUENTE DE ALIMENTACION 650W', '139.27', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (9, 'CAJA PARA PC', '266.79', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (10, 'VENTILADOR PARA CPU', '102.87', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (11, 'DISCO DURO EXTERNO 1TB', '340.89', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (12, 'CAMARA WEB HD', '76.97', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (13, 'ALTAVOCES PARA PC', '294.05', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (14, 'MICROFONO USB', '411.11', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (15, 'IMPRESORA MULTIFUNCION', '286.39', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (16, 'ROUTER WIFI', '450.23', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (17, 'TARJETA GRAFICA GTX 1660', '276.78', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (18, 'TECLADO ERGONOMICO', '236.66', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (19, 'SILLA GAMING', '293.57', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (20, 'PANTALLA TACTIL 15', '322.30', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (21, 'HUB USB 30', '192.52', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (22, 'CARGADOR PORTATIL', '141.00', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (23, 'SOPORTE PARA MONITOR', '185.95', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (24, 'ALFOMBRILLA PARA RATON', '139.35', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (25, 'CABLE HDMI 20', '61.29', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (26, 'ADAPTADOR USBC', '380.58', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (27, 'PENDRIVE 64GB', '149.98', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (28, 'TARJETA DE SONIDO EXTERNA', '75.50', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (29, 'MOCHILA PARA LAPTOP', '58.35', 't');
INSERT INTO "public"."producto" ("pro_id", "pro_descripcion", "pro_precio", "pro_activo") VALUES (30, 'LECTOR DE TARJETAS SD', '130.48', 't');
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (1, 1, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (2, 1, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (3, 1, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (4, 1, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (5, 1, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (6, 1, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (7, 1, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (8, 1, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (9, 1, '2024-05-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (10, 1, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (11, 1, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (12, 1, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (13, 2, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (14, 2, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (15, 2, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (16, 2, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (17, 2, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (18, 2, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (19, 2, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (20, 3, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (21, 3, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (22, 3, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (23, 3, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (24, 3, '2024-04-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (25, 3, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (26, 3, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (27, 4, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (28, 4, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (29, 4, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (30, 4, '2024-02-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (31, 4, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (32, 4, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (33, 4, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (34, 5, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (35, 5, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (36, 5, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (37, 5, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (38, 5, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (39, 5, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (40, 5, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (41, 5, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (42, 5, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (43, 5, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (44, 6, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (45, 6, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (46, 6, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (47, 6, '2024-01-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (48, 6, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (49, 6, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (50, 6, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (51, 6, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (52, 6, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (53, 6, '2024-07-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (54, 8, '2024-08-01', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (55, 8, '2024-08-02', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (56, 8, '2024-08-05', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (57, 8, '2024-08-08', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (58, 8, '2024-08-07', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (59, 8, '2024-08-06', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (60, 8, '2024-08-06', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (61, 8, '2024-08-07', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (62, 8, '2024-08-07', 1, NULL, NULL, NULL);
INSERT INTO "public"."cpedidos" ("cpe_id", "cli_id", "cpe_fecha", "imp_id", "cpe_subtotal", "cpe_impuesto", "cpe_total") VALUES (63, 8, '2024-08-07', 1, NULL, NULL, NULL);
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (1, 1, 1, '1.00', '125.06', '125.06');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (2, 1, 2, '1.00', '91.85', '91.85');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (3, 1, 3, '1.00', '54.47', '54.47');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (4, 1, 4, '2.00', '219.14', '438.28');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (5, 1, 5, '3.00', '63.48', '190.44');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (6, 1, 6, '5.00', '469.75', '2348.75');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (7, 1, 7, '6.00', '311.61', '1869.66');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (8, 2, 12, '1.00', '76.97', '76.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (9, 2, 13, '1.00', '294.05', '294.05');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (10, 2, 14, '1.00', '411.11', '411.11');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (11, 2, 15, '2.00', '286.39', '572.78');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (12, 2, 16, '3.00', '450.23', '1350.69');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (13, 2, 17, '5.00', '276.78', '1383.90');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (14, 2, 18, '6.00', '236.66', '1419.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (15, 2, 19, '2.00', '293.57', '587.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (16, 2, 20, '2.00', '322.30', '644.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (17, 2, 21, '2.00', '192.52', '385.04');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (18, 3, 12, '1.00', '76.97', '76.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (19, 3, 13, '1.00', '294.05', '294.05');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (20, 3, 14, '1.00', '411.11', '411.11');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (21, 3, 15, '2.00', '286.39', '572.78');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (22, 4, 16, '3.00', '450.23', '1350.69');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (23, 4, 17, '5.00', '276.78', '1383.90');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (24, 4, 18, '6.00', '236.66', '1419.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (25, 4, 19, '2.00', '293.57', '587.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (26, 4, 20, '2.00', '322.30', '644.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (27, 4, 21, '2.00', '192.52', '385.04');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (28, 4, 1, '3.00', '125.06', '375.18');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (29, 4, 2, '4.00', '91.85', '367.40');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (30, 4, 3, '5.00', '54.47', '272.35');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (31, 5, 4, '6.00', '219.14', '1314.84');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (32, 5, 5, '7.00', '63.48', '444.36');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (33, 5, 6, '8.00', '469.75', '3758.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (34, 5, 7, '9.00', '311.61', '2804.49');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (35, 5, 8, '10.00', '139.27', '1392.70');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (36, 5, 9, '11.00', '266.79', '2934.69');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (37, 5, 10, '12.00', '102.87', '1234.44');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (38, 7, 11, '13.00', '340.89', '4431.57');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (39, 7, 12, '14.00', '76.97', '1077.58');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (40, 7, 13, '15.00', '294.05', '4410.75');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (41, 7, 14, '16.00', '411.11', '6577.76');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (42, 8, 15, '17.00', '286.39', '4868.63');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (43, 8, 16, '18.00', '450.23', '8104.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (44, 8, 17, '19.00', '276.78', '5258.82');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (45, 9, 18, '20.00', '236.66', '4733.20');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (46, 9, 19, '21.00', '293.57', '6164.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (47, 9, 20, '22.00', '322.30', '7090.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (48, 9, 21, '23.00', '192.52', '4427.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (49, 9, 22, '24.00', '141.00', '3384.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (50, 9, 23, '25.00', '185.95', '4648.75');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (51, 9, 24, '26.00', '139.35', '3623.10');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (52, 10, 25, '27.00', '61.29', '1654.83');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (53, 10, 26, '28.00', '380.58', '10656.24');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (54, 10, 27, '29.00', '149.98', '4349.42');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (55, 10, 28, '30.00', '75.50', '2265.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (56, 10, 29, '31.00', '58.35', '1808.85');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (57, 10, 30, '32.00', '130.48', '4175.36');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (58, 10, 25, '33.00', '61.29', '2022.57');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (59, 10, 26, '34.00', '380.58', '12939.72');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (60, 10, 27, '35.00', '149.98', '5249.30');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (61, 10, 28, '36.00', '75.50', '2718.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (62, 11, 29, '37.00', '58.35', '2158.95');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (63, 11, 30, '38.00', '130.48', '4958.24');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (64, 12, 12, '1.00', '76.97', '76.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (65, 12, 13, '1.00', '294.05', '294.05');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (66, 12, 14, '1.00', '411.11', '411.11');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (67, 13, 15, '2.00', '286.39', '572.78');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (68, 13, 16, '3.00', '450.23', '1350.69');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (69, 13, 17, '5.00', '276.78', '1383.90');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (70, 13, 18, '6.00', '236.66', '1419.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (71, 15, 19, '2.00', '293.57', '587.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (72, 15, 20, '2.00', '322.30', '644.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (73, 15, 21, '2.00', '192.52', '385.04');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (74, 14, 1, '3.00', '125.06', '375.18');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (75, 14, 2, '4.00', '91.85', '367.40');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (76, 14, 3, '5.00', '54.47', '272.35');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (77, 16, 4, '6.00', '219.14', '1314.84');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (78, 16, 5, '7.00', '63.48', '444.36');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (79, 16, 6, '8.00', '469.75', '3758.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (80, 16, 7, '9.00', '311.61', '2804.49');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (81, 16, 8, '10.00', '139.27', '1392.70');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (82, 16, 9, '11.00', '266.79', '2934.69');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (83, 16, 10, '12.00', '102.87', '1234.44');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (84, 16, 11, '13.00', '340.89', '4431.57');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (85, 16, 12, '14.00', '76.97', '1077.58');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (86, 16, 13, '15.00', '294.05', '4410.75');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (87, 17, 14, '16.00', '411.11', '6577.76');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (88, 17, 15, '17.00', '286.39', '4868.63');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (89, 17, 16, '18.00', '450.23', '8104.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (90, 17, 17, '19.00', '276.78', '5258.82');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (91, 18, 18, '20.00', '236.66', '4733.20');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (92, 18, 19, '21.00', '293.57', '6164.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (93, 18, 20, '22.00', '322.30', '7090.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (94, 19, 21, '23.00', '192.52', '4427.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (95, 20, 22, '24.00', '141.00', '3384.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (96, 20, 23, '25.00', '185.95', '4648.75');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (97, 20, 24, '26.00', '139.35', '3623.10');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (98, 21, 25, '27.00', '61.29', '1654.83');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (99, 21, 26, '28.00', '380.58', '10656.24');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (100, 21, 27, '29.00', '149.98', '4349.42');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (101, 22, 28, '30.00', '75.50', '2265.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (102, 22, 29, '31.00', '58.35', '1808.85');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (103, 23, 30, '32.00', '130.48', '4175.36');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (104, 24, 25, '33.00', '61.29', '2022.57');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (105, 24, 26, '34.00', '380.58', '12939.72');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (106, 25, 27, '35.00', '149.98', '5249.30');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (107, 26, 28, '36.00', '75.50', '2718.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (108, 26, 29, '37.00', '58.35', '2158.95');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (109, 26, 30, '38.00', '130.48', '4958.24');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (110, 27, 12, '1.00', '76.97', '76.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (111, 27, 13, '1.00', '294.05', '294.05');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (112, 28, 14, '1.00', '411.11', '411.11');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (113, 28, 15, '2.00', '286.39', '572.78');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (114, 29, 16, '3.00', '450.23', '1350.69');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (115, 29, 17, '5.00', '276.78', '1383.90');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (116, 30, 18, '6.00', '236.66', '1419.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (117, 30, 19, '2.00', '293.57', '587.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (118, 31, 20, '2.00', '322.30', '644.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (119, 32, 21, '2.00', '192.52', '385.04');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (120, 33, 1, '3.00', '125.06', '375.18');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (121, 34, 2, '4.00', '91.85', '367.40');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (122, 34, 3, '1.00', '54.47', '54.47');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (123, 35, 4, '1.00', '219.14', '219.14');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (124, 35, 5, '1.00', '63.48', '63.48');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (125, 36, 6, '2.00', '469.75', '939.50');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (126, 36, 7, '3.00', '311.61', '934.83');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (127, 37, 8, '5.00', '139.27', '696.35');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (128, 37, 9, '6.00', '266.79', '1600.74');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (129, 38, 10, '1.00', '102.87', '102.87');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (130, 38, 11, '1.00', '340.89', '340.89');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (131, 39, 12, '1.00', '76.97', '76.97');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (132, 39, 13, '2.00', '294.05', '588.10');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (133, 40, 14, '3.00', '411.11', '1233.33');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (134, 40, 15, '5.00', '286.39', '1431.95');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (135, 41, 16, '6.00', '450.23', '2701.38');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (136, 41, 17, '1.00', '276.78', '276.78');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (137, 42, 18, '1.00', '236.66', '236.66');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (138, 43, 19, '1.00', '293.57', '293.57');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (139, 44, 20, '2.00', '322.30', '644.60');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (140, 45, 21, '3.00', '192.52', '577.56');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (141, 46, 22, '5.00', '141.00', '705.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (142, 47, 23, '6.00', '185.95', '1115.70');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (143, 48, 24, '1.00', '139.35', '139.35');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (144, 49, 25, '1.00', '61.29', '61.29');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (145, 50, 26, '1.00', '380.58', '380.58');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (146, 51, 27, '2.00', '149.98', '299.96');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (147, 52, 28, '3.00', '75.50', '226.50');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (148, 53, 29, '5.00', '58.35', '291.75');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (149, 54, 30, '6.00', '130.48', '782.88');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (150, 55, 25, '1.00', '61.29', '61.29');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (151, 56, 26, '1.00', '380.58', '380.58');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (152, 57, 27, '1.00', '149.98', '149.98');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (153, 58, 28, '2.00', '75.50', '151.00');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (154, 59, 29, '3.00', '58.35', '175.05');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (155, 60, 30, '5.00', '130.48', '652.40');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (156, 61, 14, '6.00', '411.11', '2466.66');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (157, 62, 15, '5.00', '286.39', '1431.95');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (158, 62, 16, '6.00', '450.23', '2701.38');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (159, 63, 30, '7.00', '130.48', '913.36');
INSERT INTO "public"."dpedidos" ("dpe_id", "cpe_id", "pro_id", "dpe_cantidad", "dpe_precio", "dpe_total") VALUES (160, 63, 30, '8.00', '130.48', '1043.84');

```

