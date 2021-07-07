# Kafka Connect

## O que é o Kafka Connect?

“Kafka Connect é um componente gratuito e open-source do Apache Kafka que trabalha como um hub de dados centralizado para integrações simples entre banco de dados, key-value stores, search indexes e file systems.”

##Dinâmica

Apache Kafa <=> Kafka Connect [Connetor, Connector, ...] => MySql, Mongo, Salesforce

Vai pegar dados do banco de dados enviar para o kafka (Data Sources)

JDBC, Elasticsearch, Aws Lambda (Sinks)

Não importa de onde vem os dados os conectores fazem o trabalho todo.

## Standalone Workers

Worker, responsável por executar as tarefas.

## Distributed Works

Trabalha em um cluster com diversos Works, pode ser separado em grupos.

## Converters

As tasks utilizam os “converters” para mudar o formato dos dados tanto para leitura ou escrita no Kafka
- Avro
- Protobuf
- JsonSchema
- Json
- String
- ByteArray

## DLQ - Dead Letter Queue

Quando há um registro inválido, independente da razão, o erro pode ser tratado nas configurações do conector através da propriedade “errors.tolerange”. Esse tipo de configuração pode ser realizado apenas para conectores do tipo “Sink”.

none: Faz a tarefa falhar imediatamente
all: Erros são ignorados e o processo continua normalmente
errors.deadletterqueue.topic.name = <nome-do-topico>

### Conectores: https://www.confluent.io/