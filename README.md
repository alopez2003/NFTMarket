# Programación de tokens no fungibles (estándares ERC-720 y ERC-1155) por Alberto López Gutiérrez

Continuando con el Sprint 3, nos adentramos a la programación de NFT's y un Marketplace para la compra/venta de dichos activos, como los temas anteriores, se me ha hecho sumamente interesante el tema, muchas gracias por el aprendizaje compartido!!!

Si se quiere consultar el Sprint 1, anexo la [liga](https://github.com/alopez2003/solidity1) al mismo, así como la [liga](https://github.com/alopez2003/exchytoken/tree/main) del Sprint 2.

NOTA: Desde que inicié este master, no ha existido un grupo, siempre hemos entregado mis compañeros y yo el trabajo de forma individual, me parece que sólo ha habido un grupo. En mi caso continuaré con la entrega individual. Muchas gracias!!

## Sprint 3

En este sprint vamos a trabajar con una cuenta diferente, desde que la cuenta que ocupabamos de MetaMask quedó con una actividad pendiente, al parecer las comisiones que está pidiendo son excesivas, por lo que ocuparemos entonces otra cuenta, vamos a trabajar con la cuenta con la address: 0xC65fA7Ce4FF244727739a81FC4d9805d978e34Df

Vamos a ocupar los contratos proporcionados por Open Zeppelin de [ERC721.sol](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.8.1/contracts/token/ERC721/ERC721.sol) y [ERC1155.sol](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.8.1/contracts/token/ERC1155/ERC1155.sol) respectivamente.

Debido a que queremos interactuar con el contrato, y es necesario verificarlo desde un inicio, conforme al Sprint anterior vimos que tuvimos desafios interesantes con el Hardhat, en específico con el flattener, aún cuando teníamos el archivo "flattened", cuando verificabamos no podía ser identificado una parte del código, no coincidía con la verificación. En este Sprint vamos a ocupar para el despliegue del contrato Remix, con el fin de poder verificar los contratos desde un inicio.

### ERC-720

