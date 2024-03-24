# Programación de tokens no fungibles (estándares ERC-721 y ERC-1155) por Alberto López Gutiérrez

Continuando con el Sprint 3, nos adentramos a la programación de NFT's y un Marketplace para la compra/venta de dichos activos, como los temas anteriores, se me ha hecho sumamente interesante el tema, muchas gracias por el aprendizaje compartido!!!

Si se quiere consultar el Sprint 1, anexo la [liga](https://github.com/alopez2003/solidity1) al mismo, así como la [liga](https://github.com/alopez2003/exchytoken/tree/main) del Sprint 2.

NOTA: Desde que inicié este master, no ha existido un grupo, siempre hemos entregado mis compañeros y yo el trabajo de forma individual, me parece que sólo ha habido un grupo. En mi caso continuaré con la entrega individual. Muchas gracias!!

## Sprint 3

En este sprint vamos a trabajar con una cuenta diferente, desde que la cuenta que ocupabamos de MetaMask quedó con una actividad pendiente, al parecer las comisiones que está pidiendo son excesivas, por lo que ocuparemos entonces otra cuenta, vamos a trabajar con la cuenta con la address: 0xC65fA7Ce4FF244727739a81FC4d9805d978e34Df

Debido a que queremos interactuar con el contrato, y es necesario verificarlo desde un inicio, conforme al Sprint anterior vimos que tuvimos desafios interesantes con el Hardhat, en específico con el flattener, aún cuando teníamos el archivo "flattened", cuando verificabamos no podía ser identificado una parte del código, no coincidía con la verificación. En este Sprint vamos a ocupar para el despliegue del contrato Remix, con el fin de poder verificar los contratos desde un inicio.

A pesar de trabajar sobre Remix, vamos a cargar los contratos de la misma carpeta donde estabamos trabajando Hardhat para mantener un orden 

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/7582159e-c15b-43f8-be03-b4633161faa3)


### MyNFT.sol - ERC721

Este archivo está hecho con el fin de poder mintear nuevos NFT's, se puede encontrar en el directorio raíz de este GitHub

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/b53aa4cc-3b3a-4117-8141-781a76984042)

Confirmamos que esto será desplegado en la cartera de MetaMask con la address seleccionada

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/72d98597-ce44-408f-b502-6beabe805461)

Desplegamos el contrato y nos pide confirmación en MetaMask

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/189fe0db-25e0-44d4-bf6a-d61ef13e6dea)

Podemos ver que ya fue desplegado el contrato

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/454e27a5-1c91-422b-8477-fe189b4c16d7)

Podemos ver que ya fue desplegado el contrato hace pocos  minutos

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/3f7f5c2b-03a6-4e92-be19-8a4252aeb178)

Se encuentra con las siguientes direcciones:

Transacción: https://testnet.bscscan.com/tx/0x332c8acc3a1c11dd084096993fbdea8ce7fb293818a60a4d6ae3a4e04fac3725
Address: https://testnet.bscscan.com/address/0x0cbbaccaee14cb19a5f396410f354a536c054be9

Vamos a verificar el contrato puesto que se ve en Bytecode:

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/eac1f9cb-849b-4fe6-9705-fe726068ed84)

En Remix, a partir de determinadas versiones, el Flatten se encuentra en el menú de archivos en vez del plugin asociado, por lo que damos click con el botón derecho al archivo MyNFT.sol y elegimos Flatten para poder unificar todas las librerias con el contrato en un solo archivo

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/ff29dccc-2d5a-4fd8-8c4c-ea4c74baf5c6)

Y obtenemos un archivo MyNFT_flattened.sol con todo el código unificado

Vamos hacia la parte de verificación y llenamos los campos que se piden

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/8df354eb-9242-4210-ac11-88ebc21cb1fa)

Anexamos el código Flattened y Verificamos

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/6086d53b-ad02-4961-8af5-d5aa7ca06e4b)

Y listo, ya tenemos confirmación de que fue generado el Bytecode

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/0f1ebf95-5645-4f55-96ca-aacea58feee8)

Y vemos que ya podemos interactuar con las funciones de lectura y escritura del contrato

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/9c8b1f01-6c47-44b6-aa52-20cd1a5dae9d)

Lo primero que hacemos es conectarlo a nuestra cartera de MetaMask y veamos algunas funciones de lectura como el balance (balanceOf) con la dirección de mi address 0xC65fA7Ce4FF244727739a81FC4d9805d978e34Df y vemos que el balance es 0

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/e65ccebd-d119-41ef-b3ab-3bf07fdfe196)

#### mint - awardItem

Ahora lo que hacemos, vamos a las funciones de escritura, en específico la de awardItem, donde vamos a mintear un nuevo NFT, le llamaremos NFTIEBSALG1 hacia mi address 0xC65fA7Ce4FF244727739a81FC4d9805d978e34Df y le damos click en el botón de Write

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/8186d73c-ca09-4cee-bfa3-9106849896f0)

Nos pide confirmación en MetaMask

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/e2be1c8e-9a5b-4372-925a-a18a4cfd429f)

Y vemos la transacción ejecutada hace poco tiempo

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/9952e5d8-e585-429f-acd8-de7a7b9f7cb7)

https://testnet.bscscan.com/tx/0x1b448512ffc116404425e93d5dc4c923744b52e7dedbf786286882bfce2e4cd7

Vemos que se ha creado el Token 0

Si ahora vamos a la parte de lectura, y consultamos el balanceOf con la dirección 0xC65fA7Ce4FF244727739a81FC4d9805d978e34Df podemos ver tenemos la cantidad de 1, así como podemos ver que en el ownerOf del tokenId 0 pone la dirección de mi address, y también si hacemos la consulta de tokenURI con el tokenId 0 vemos que se llama NFTIEBSALG1

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/9836b00b-db2e-4812-981a-961dbaa4b224)


Hasta ahora no he podido compilar el contrato NFTMarketplace.sol, seguire intentando para poder continuar.

Primero se subió la versión de NFTMarketplace.sol, mismo que se encontrará en este repositorio, se hicieron los cambios pertinentes sobre el archivo NFTMarketplace (1).sol, también anexado en este repositorio, sin embargo en la compilación lo que marca es que, al momento de ser una función que llama a Ownable, necesita parámetros de entrada, aún cuando podemos poner la dirección del Smart Contract del NFT creado, no deja avanzar en la compilación.

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/fcbc991b-d4cb-4bf4-b2e3-7f2aa4a6cd68)

Preguntando a ChatGPT, lo que nos recomienda es poner en el constructor la dirección del dueño original, mismo que puede ser _NFT_address

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/63086564-19d2-49b2-9a68-11b59e26e81e)

Sin embargo, al ponerlo, establece el siguiente warning en el código de gas infinito:

![Screenshot from 2024-03-24 00-13-14](https://github.com/alopez2003/NFTMarket/assets/67942268/19f767a1-310e-4cd7-a8dd-e024a89db3ce)

Pegamos la dirección del smart contract donde tenemos nuestro NFT y damos click en Deploy

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/e036227c-5e83-4f76-ae00-80395a25d60a)

Nos sale el mismo warning una vez desplegado de "Gas estimation failed"

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/6749bdbe-372e-4eea-8fc3-876709cdabde)

Cancelamos esa operación

**Update:** actualizamos el Ownable(_NFT_Address) por Ownable(msg.sender), tenemos el mismo error, vamos a probar aún así a ejecutar no haciendo caso al warning

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/b3d77ff9-417a-420d-b917-f8d7aa06f781)

Nos pide confirmación MetaMask

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/48de9daf-0dfd-4f10-861c-9b0fb59ea42a)

Aparece desplegado

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/da104ca0-aba3-4dc5-bd12-222da43d146d)

Podemos ver que fue desplegado hace unos momentos

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/ccde40e7-4248-4b49-9594-2fb2dd37fd66)

URL de transacción y de contrato

Transacción: https://testnet.bscscan.com/tx/0x936a344208e2367352c36338e0dcfd4bc86b843d37e3954fcd702bd6665d7e34
Contrato: https://testnet.bscscan.com/address/0x404a07518541d7f7b7c3ef9a0b82f550866a14e4

Ahora vamos a verificarlo ya que lo tenemos en bytecode

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/53867adb-3c84-4d8d-9ba3-954aac7aedc1)

Lo que hacemos es hacer Flatten al codigo (por cierto, lo pueden encontrar esta actualización con el archivo NFTMarketplace(2).sol)

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/abe3e895-ae98-4f71-b2d7-e2a673ae330d)

y nos aparece un archivo NFTMarketplace_flattened.sol

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/c03e74a4-8025-4a3c-af96-79c1bac7da84)

Ese mismo archivo lo llevaremos a la verificación del contrato:

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/8aecd9cc-f1a2-425e-a4a6-2366d447fcf4)

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/f4b1bc5c-24b1-4a28-89bc-2d446051dd35)


Y listo, podemos ver que ya fue aceptada la verificación

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/77d4672d-e0fb-4eb0-a5ba-28c6bdcc30d3)

URL del código verificado

https://testnet.bscscan.com/address/0x404a07518541d7f7b7c3ef9a0b82f550866a14e4#code

Podemos ver que ya accedemos a las funciones del contrato tanto de lectura como de escritura

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/9a288e73-259d-4b75-8017-57e775bb6c32)

**Venta de NFT**

#### approve

Para poder poner en venta el NFT creado, lo primero que tenemos que hacer es aprobar la dirección del Smart Contract de MarketPlace, con address 0x404A07518541d7F7B7c3Ef9a0b82F550866a14e4 en el Smart Contract de MyNFT, donde creamos el NFT.

Establecemos la dirección y el ID del Token, que es el 0 en el campo approve y damos click en Write

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/bd91401d-920c-495d-a2fe-720b0f270cd6)

Pide confirmación MetaMask

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/c3526c59-824b-42b7-a138-cf3fd572cd7e)

Y podemos ver que la transacción se ha creado hace poco

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/f40d9eba-b330-4039-80c8-620a237c137c)


URL de la transacción

https://testnet.bscscan.com/tx/0x2491d9ada36b90e9e6afba5d685715d0824e01f684fe361a2d874903618eec66


#### Venta - listitem - transfer

Ahora lo que hacemos, una vez aprobado el Smart Contract, vamos a poner en Venta ese NFT

Accedemos en el Smart Contract de NFTMarketplace a la función de escritura listItem y establecemos el ID del NFT, que es el 0, y el precio, que vamos a colocarlo en "1000000" Gwei y damos click en Write

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/b739ca27-7691-4182-867b-8159d5f7bb07)

Pide confirmación en MetaMask

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/66924e35-9b5b-4740-bb98-b1787bbfcdcc)

Y vemos la transacción que ha sido ejecutada hace unos pocos segundos

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/89e28357-853e-4b80-b475-f030d81923e1)

URL de la transacción:

https://testnet.bscscan.com/tx/0x320534d8014b8bdc1bcd3202c3e7c03a88f49856b8d357947dbf435791288285

Podemos ver en los detalles de la transacción que fue ejecutada la función listItem y que fue transferida de mi address a la address del contrato

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/49697a8b-e35e-4144-aafa-acc265bb8279)

#### compra - transferFrom

Ahora vamos a comprar ese NFT desde otra cuenta, con address 0x80392D2071c4E1aBBDdD3DBf8eaCa4431081b787

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/23ead12e-77aa-45e4-8b9f-f79d31d12878)

Accedemos a las funciones de escritura del Smart Contract de NFTMarketplace, pero ahora con la función buyItem

Primero convertimos 1000000 Gwei en BNB, nos da la cantidad de 0.000000000001

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/fb02e558-d49e-42b3-b3d9-4e3f2bee094a)

Establecemos el monto, que es "0.000000000001" y el itemID que es el 0 y damos click en Write

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/b6bec068-00a3-4255-b10c-0eb7a1dae9fc)

Pide confirmación MetaMask

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/b7db6290-9263-4917-938f-1cbdcb85ca6d)

y vemos la transacción que fue ejecutada hace unos pocos segundos

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/dcc3ca75-bc4e-4207-9dd5-a8e9d4e8e380)

URL de la transacción

https://testnet.bscscan.com/tx/0x06a006bf25985b45baaa0b61ac3c868986882f73a2e9c473a03865c53d76d258

Vemos detalles super importantes como que el contrato de Marketplace me mando el NFT al Account 2, pero que la transferencia fue realizada a mi address original (Account 3), 

![image](https://github.com/alopez2003/NFTMarket/assets/67942268/9a08c614-3886-4312-90b6-396998c796dd)












































