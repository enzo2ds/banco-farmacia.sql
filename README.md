# banco-farmacia.sql
CREATE TABLE Farmacia 
(
    idFarmacia INT PRIMARY KEY, -- Adicionado para identificar a farmácia
    tel_farmacia VARCHAR(15),
    nome_farmacia VARCHAR(100),
    endereco_farmacia VARCHAR(255),
    cnpj_farmacia VARCHAR(20) UNIQUE -- CNPJ deve ser único
);

CREATE TABLE Produto 
(
    cod_produto INT PRIMARY KEY,
    valor_produto DECIMAL(10, 2),
    qtd_farmacia INT,
    idFarmacia INT,
    FOREIGN KEY (idFarmacia) REFERENCES Farmacia (idFarmacia)
);

CREATE TABLE Farmaceutico 
(
    rg_farmaceutico VARCHAR(20) PRIMARY KEY, -- RG geralmente é alfanumérico
    nome_farmaceutico VARCHAR(100),
    idFarmacia INT,
    FOREIGN KEY (idFarmacia) REFERENCES Farmacia (idFarmacia)
);
