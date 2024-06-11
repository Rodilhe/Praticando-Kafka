# Praticando-Kafka


Para o funcionamento do projeto é necessário a instalação do Apache kafka.

## Download do Apache Kafka
Baixe a última versão do Apache Kafka do site oficial. Escolha a versão binária Scala 2.12 ou 2.13.
Extraia o conteúdo do arquivo baixado para um diretório de sua escolha (por exemplo, C:\kafka).
### Passo 1: Configuração do Apache Zookeeper
O Apache Kafka vem com o Apache Zookeeper incluído. Você precisará configurá-lo antes de iniciar.

Abra um terminal (Prompt de Comando ou PowerShell).
Navegue até o diretório do Kafka (por exemplo, cd C:\kafka\kafka_2.13-2.8.0).
Inicie o Zookeeper usando o script de inicialização:
sh
Copiar código
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
### Passo 2: Configuração e Início do Apache Kafka
Em um novo terminal, navegue até o diretório do Kafka (por exemplo, cd C:\kafka\kafka_2.13-2.8.0).
Inicie o Kafka usando o script de inicialização:
sh
Copiar código
.\bin\windows\kafka-server-start.bat .\config\server.properties
### Passo 3: Testando a instalação
Agora que tanto o Zookeeper quanto o Kafka estão em execução, você pode testar a instalação criando um tópico, enviando e consumindo mensagens.

Criar um tópico:

No terminal Kafka, crie um novo tópico chamado "test":
sh
Copiar código
.\bin\windows\kafka-topics.bat --create --topic test --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
Produzir mensagens:

No terminal Kafka, inicie um produtor para enviar mensagens ao tópico "test":
sh
Copiar código
.\bin\windows\kafka-console-producer.bat --topic test --bootstrap-server localhost:9092
Escreva algumas mensagens no terminal e pressione Enter após cada uma.
Consumir mensagens:

Em outro terminal Kafka, inicie um consumidor para ler mensagens do tópico "test":
sh
Copiar código
.\bin\windows\kafka-console-consumer.bat --topic test --bootstrap-server localhost:9092 --from-beginning
Você deverá ver as mensagens que foram enviadas pelo produtor.

## Testando nossa aplicação

### Basta rodar os projetos Consumer e Producer Kafka e chamar o endpoint do Producer, observe o terminal do Consumer e verá o resultado do tópico produzido.
