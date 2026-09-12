# OBJETIVO

Guia de referência sobre pacotes NPM.

---

## Instalar pacotes
  
```shell
npm install -g <pacote>
```

>[!Important]
> **Parâmetro Global**: Se colocar -g em qualquer comando, a opção vira global

## Listar pacotes

```Shell
npm ls -g --depth=0 --parseable
```

## Remover pacotes

```Shell
npm uninstall -g <pacote>
```

### Descobrir quantas instalações existem
```Shell
where.exe node
where.exe npm

Get-Command node -All | Select-Object Source
Get-Command npm -All | Select-Object Source

node -v
npm -v
npm config get prefix
```
