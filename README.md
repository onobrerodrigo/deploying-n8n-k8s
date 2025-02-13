## Provisionamento do N8N em Kubernetes

### Descrição

Este repositório contém os manifestos necessários para provisionar a aplicação N8N em um ambiente Kubernetes para desenvolvimento, mas que pode ser facilmente adapatado para um ambiente de produção. O N8N é uma ferramenta de integração e automação de workflows que permite conectar diversos serviços diferentes e automatizar tarefas de forma visual e intuitiva.

### Pré-requisitos

- Kubernetes cluster configurado e rodando.
- Acesso ao kubectl configurado para o cluster.
- Secret e ConfigMap já definidos para as configurações de ambiente e banco de dados.
- Um PersistentVolume disponível para o StatefulSet do PostgreSQL, caso deseje persistência de dados.

### Observações

- Certifique-se de que todos os Secrets e ConfigMaps estão corretamente criados no namespace n8n antes de aplicar o StatefulSet e o Deployment.
- Ajuste o storageClassName e as configurações de resources conforme a política de armazenamento e os recursos disponíveis no seu cluster Kubernetes.
- As senhas e chaves no Secret estão codificadas em Base64. Decodifique-as antes de usar e codifique novamente se necessário.
- Para atualizar a aplicação, simplesmente aplique novamente os manifestos com kubectl apply ou ajuste a imagem no Deployment para uma nova versão do N8N.

## Contribuição

Se você encontrar bugs ou tiver melhorias para sugerir, sinta-se à vontade para abrir uma issue ou enviar um pull request. Certifique-se de que todas as alterações mantenham as melhores práticas de segurança e operação em Kubernetes.

Esse README.md fornece uma visão geral e instruções básicas para a implantação do N8N em um cluster Kubernetes. Lembre-se de que, dependendo da sua infraestrutura e requisitos específicos, podem ser necessários ajustes adicionais, como a configuração de serviços para expor o N8N fora do cluster, configuração de persistência de dados para o N8N, e ajustes de segurança.