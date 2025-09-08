
# Projeto AWS: Integração de Serviços S3, EC2, Lambda Function e EBS

## Serviços Utilizados

### Amazon S3 (Simple Storage Service)
O Amazon S3 é um serviço de armazenamento de objetos que oferece escalabilidade, disponibilidade de dados e segurança. É ideal para armazenar arquivos, backups, imagens, vídeos e dados estáticos.

### Amazon EC2 (Elastic Compute Cloud)
O Amazon EC2 fornece capacidade de computação escalável na nuvem. Permite executar servidores virtuais (instâncias) com diferentes configurações de hardware e software.

### AWS Lambda
O AWS Lambda permite executar código em resposta a eventos sem provisionar ou gerenciar servidores. É ideal para tarefas automatizadas, processamento de dados e integração entre serviços.

### Amazon EBS (Elastic Block Store)
O Amazon EBS fornece volumes de armazenamento em bloco para uso com instâncias EC2. É utilizado para armazenar dados persistentes como bancos de dados e arquivos de sistema.

## Caso de Uso: Processamento de Imagens

### Cenário
Uma empresa precisa de uma solução automatizada para processar imagens enviadas por usuários. As imagens devem ser armazenadas, processadas e os resultados disponibilizados de forma eficiente.

### Arquitetura Proposta
1. **Armazenamento Inicial**: O usuário envia uma imagem que é armazenada em um bucket do Amazon S3.
2. **Disparo de Evento**: O upload da imagem no S3 dispara um evento que aciona uma função Lambda.
3. **Processamento**: A função Lambda inicia uma instância EC2 que possui um script de processamento de imagem.
4. **Armazenamento de Resultados**: A instância EC2 utiliza um volume EBS para armazenar temporariamente os dados processados.
5. **Finalização**: Os resultados são enviados de volta para o S3 e a instância EC2 é finalizada.

### Benefícios
- Escalabilidade automática com Lambda e EC2.
- Armazenamento seguro e durável com S3.
- Persistência de dados com EBS.
- Baixo custo operacional com uso sob demanda.

