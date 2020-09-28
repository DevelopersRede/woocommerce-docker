# Rede Woocommerce

Esse é um ambiente Docker para desenvolvimento, onde você poderá testar o módulo Rede para WooCommerce.

## Construindo a imagem e rodando o container

```
./rede build
./rede start
```

Uma vez que a imagem já tiver sido construída, basta executar `./rede start`

## Entrada hosts

O servidor aceita requisições feitas para [dev.userede.com.br](http://dev.userede.com.br) e para [localhost](http://localhost). Caso queira usar
dev.userede.com.br, basta adicionar a seguinte entrada no seu /etc/hosts:

```
127.0.0.1  dev.userede.com.br
```
