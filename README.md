use pizzas;

CREATE TABLE producto (
    clave INT PRIMARY KEY,
    nombre_producto VARCHAR(100) NOT NULL
);

CREATE TABLE cliente (
    telefono VARCHAR(15) PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    paterno VARCHAR(50) NOT NULL,
    materno VARCHAR(50) NOT NULL,
    colonia VARCHAR(100),
    cp VARCHAR(10),
    producto_id INT,
    FOREIGN KEY (producto_id) REFERENCES producto(clave)
);

CREATE TABLE kpi (
    area_id INT PRIMARY KEY,
    ventas DECIMAL(10, 2),
    tasas_recompra DECIMAL(10, 2)
);

CREATE TABLE personal (
    no_empleado INT PRIMARY KEY,
    area_id INT,
    FOREIGN KEY (area_id) REFERENCES kpi(area_id)
);
