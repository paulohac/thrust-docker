# Docker - ThrustJS

Este repositório contém as receitas Docker para a plataforma ThurstJS.

## Tags

* lastest Última versão do Thrust na última versão do Java suportada.
* oracle-8 Última versão do Thrust no último update do Java OpenJDK 8 com .
* openjdk-8 Última versão do Thrust no último update do Java Oracle 8.

## Build

```bash
cd openjdk-8 # ou cd oracle-8
docker build -t thrust .
```

## Uso

```bash
docker run --rm -it -v $(pwd):/app thrust nomearquivo.js
```

## Exemplo

### Comandos:
```bash
mkdir exemplo
cd exemplo
echo "print('Ola Mundo!')" > main.js
docker run --rm -it -v $(pwd):/app thrust main.js
```
### Saída:
```bash
Ola Mundo!
```