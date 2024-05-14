# Fundamentos do Node.js 🚀

Bem-vindo ao repositório do curso de Fundamentos do Node.js da Rocketseat! Este repositório contém os conceitos básicos e exemplos práticos abordados durante o curso, incluindo:

- Streams
- Fundamentos HTTP
  - Request
  - Response
  - Headers
  - Status Code
  - Params

## Instalação

Para executar os exemplos deste repositório, siga os passos abaixo:

1. Certifique-se de ter o Node.js instalado. Você pode baixá-lo [aqui](https://nodejs.org/).
2. Clone este repositório e instale as dependências:

```bash
git clone https://github.com/HenriqueTechPro/fundamentos_nodejs.git
cd fundamentos_nodejs
npm run dev

Exemplos de Código
Exemplo de Servidor HTTP Simples

import http from 'node:http';
import { Transform } from 'node:stream';

class InverseNumberStream extends Transform {
  _transform(chunk, encoding, callback) {
    const transformed = Number(chunk.toString()) * -1;
    console.log(transformed);
    callback(null, Buffer.from(String(transformed)));
  }
}

const server = http.createServer(async (req, res) => {
  const buffers = [];

  for await (const chunk of req) {
    buffers.push(chunk);
  }

  const fullStreamContent = Buffer.concat(buffers).toString();
  console.log(fullStreamContent);

  res.end(fullStreamContent);
});

server.listen(3334, () => {
  console.log('Servidor rodando na porta 3334');
});


Recursos Adicionais
Documentação Oficial do Node.js
Rocketseat


Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests.

Licença
Este projeto está licenciado sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.


