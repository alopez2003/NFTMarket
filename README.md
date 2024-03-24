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






















