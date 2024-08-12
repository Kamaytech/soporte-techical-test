# soporte-techical-test


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
