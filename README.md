# Kubernetes-KEDA-RabbitMQ-DotNet6_ContagemAcessos
Objetos para Deployment de um Worker Service (contagem de acessos) no Kubernetes utilizando KEDA, Helm, RabbitMQ e .NET 6

Worker Service para consumo de **mensagens vinculadas a uma fila do RabbitMQ** (imagem **renatogroffe/workercontagem-rabbitmq-dotnet6**) - é justamente esta aplicação que será escalada via **KEDA**:

**https://github.com/renatogroffe/DotNet6-WorkerService-RabbitMQ-SqlServer_ContagemAcessos**

Projeto que serviu de base para o **envio de mensagens a uma fila do RabbitMQ** (imagem **renatogroffe/apicontagem-rabbitmq-dotnet6**):

**https://github.com/renatogroffe/ASPNETCore6-REST_API-RabbitMQ_ContagemAcessos**

No arquivo **keda-instalacao&sdot;sh** estão as instruções para instalação do KEDA **(Kubernetes Event-driven Autoscaling)** em um **cluster Kubernetes**.

Para os testes de carga que escalam a aplicação utilizei o pacote npm [**loadtest**](https://www.npmjs.com/package/loadtest). O exemplo a seguir procederá com o envio de **20 mil requisições**, simulando **100 usuários concorrentes**:

**loadtest -c 100 -n 20000 -k** ***ENDPOINT***
