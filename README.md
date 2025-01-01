# Projeto Distribuicao de Conteudo 
Esse repositório documenta a criação de um distribuidor de conteúdo utlizando de **ASG**, **ALB**, **CloudFront** e outros recursos da aws

#Descrição do projeto
- Utilização do Auto Scaling Group para que essa distribuição tenha Elasticidade, alta disponibilidade para que os usuarios tenham uma melhor experiência na usabilidade.
- Criei um Apliccation Load Balancer aonde ele será utilizado para distribuição de tráfego entre as instâncias que são criadas pelo ASG
- CloudFront, utilizado para melhorar a velocidade de entrega do conteúdo atráves do cache que pode ser habilitado
  
### Arquitetura do projeto 
![Diagrama.png](https://github.com/Jeff01875/Projeto-Distribuicao-Conteudo/blob/main/Diagrama.png)


#Passo a passo da implementação 

### 1. Criação do ASG

- Criei um Template de execução para que seja utilizado no ASG como modelo de inicialização das instâncias
- Criei um Auto Scaling Group aonde será executada 2 instâncias em Zonas de Disponibilidades distintas

![Criação Auto Scaling Group_ETAPA-6.png](https://github.com/Jeff01875/Projeto-Distribuicao-Conteudo/blob/a9e4ec4405fd50e54262c13525cdacd22a9bb44d/Cria%C3%A7%C3%A3o%20Auto%20Scaling%20Group_ETAPA-6.png)

### 2. Criação do ALB

- Criei um Target Group para agrupar as instâncias onde o conteúdo será consumido
- Associei o Application Load Balancer ao Target Group para que o tráfego seja distribuido

![Criação do Application Load Balancer_ETAPA-8.png](https://github.com/Jeff01875/Projeto-Distribuicao-Conteudo/blob/a9e4ec4405fd50e54262c13525cdacd22a9bb44d/Cria%C3%A7%C3%A3o%20do%20Application%20Load%20Balancer_ETAPA-8.png)

### 3. Criação do CloudFront

- Criei um Cloudfront para distribuir os usuario para o ALB aonde eles serão direcioandos para o conteúdo que irão acessar
- configurei o CloudFront para que ele armazene o cache do conteúdo em que os usuarios vão acessando, trazendo maior velocidade de acesso

![Criação do CloudFront_ETAPA-9.png](https://github.com/Jeff01875/Projeto-Distribuicao-Conteudo/blob/a9e4ec4405fd50e54262c13525cdacd22a9bb44d/Cria%C3%A7%C3%A3o%20do%20CloudFront_ETAPA-9.png)

### Benefícios da solução

- Alta Disponibilidade e elasticidade do conteúdo
- Distribuição do tráfego entre as instâncias, garantindo ao sobrecarga entre eles.
- Baixa Latência de acesso aos recursos.
