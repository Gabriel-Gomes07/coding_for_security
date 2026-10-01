1 - Não, porém se usar a flag "-v", sim.
A diferença é que ao usar a flag "-v" estamos mandando destruir o conteiner e os volumes também, mas sem a flag apenas o conteiner é destruido.

2 - Pois o nome do host tem que ser o mesmo que o  nome do serviço. Caso trocasse para "localhost" ele não encontraria o banco.

3 - O healthcheck com "condition: service_healthy" exige que o conteiner esteja em um estado saudável (que o banco esteja pronta e funcionando).
Como por exemplo, uma empresa tenta executar o docker sem ao menos verificar se o banco está está pronto para aceitar conexões, e acaba dando erro por conta que o banco ainda está iniciando.

4 - Para que o docker não precise instalar novamente as dependências, deixando o processo de build extremamente lento. 

5.1 - O "COPY" literalmente copia arquivos e o "ADD" faz o que o "COPY" faz, mas também consegue baixar arquivos da internet e extrair arquivos compactados.

5.2 - Pois usar a versão padrão traria uma série de ferramentas, utilitários de rede e bibliotecas desnecessários para se utilizar dentro de uma API. E juntamente com isso, aumentaria as brechas de segurança por ter uma maior "superfície de ataque".

5.3 - Serve para listar arquivos e pastas que não devem ser copiadas para dentro da imagem Docker.
