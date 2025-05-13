# Sistemas de Alto Throughput: Problemática

Definição: Alto Throughput (ou vazão, em português) é a quantidade de trabalho ou dados processados por unidade de tempo. Número de mensagens que o sistema consegue processar, transmitir ou armazenar por segundo

## Link para entrega:

[Link da Entrega](https://forms.gle/rK8semRtpqKrabLn6)

## Propostas

### Sistema Estilo iFood
Um sistema de entrega de alimentos como o iFood precisa lidar com um alto volume de requisições simultâneas de múltiplas frentes:
- **Pedidos**: Validação em tempo real de itens, preços, disponibilidade e promoções.
- **Restaurantes**: Recebimento e atualização de status de pedidos, além de gerenciamento de cardápios.
- **Entregadores**: Alocação dinâmica de pedidos, localização em tempo real e roteamento otimizado.
- **Outros**: Notificações push, suporte ao cliente e relatórios analíticos.

**Desafio**: Gerenciar milhares de mensagens por segundo com baixa latência, alta resiliência e integração consistente entre frentes.

### Sistema Estilo Mercado Livre
Um marketplace como o Mercado Livre enfrenta requisições intensas em diversas camadas:
- **Pedidos**: Processamento de compras, validação de pagamentos e integração com gateways financeiros.
- **Estoque**: Atualização em tempo real da disponibilidade de produtos, sincronizada entre vendedores.
- **Entregadores**: Rastreamento de envios, alocação de transportadoras e cálculo de prazos.
- **Outros**: Recomendações personalizadas, busca por produtos e avaliações.

**Desafio**: Escalar para milhões de usuários simultâneos, garantindo consistência de dados e suporte a picos sazonais.

### Sistema Estilo Alura
Uma plataforma de ensino online como a Alura gerencia interações dinâmicas:
- **Alunos**: Acessos a cursos, acompanhamento de progresso, participação em fóruns e emissão de certificados.
- **Cursos**: Atualização de conteúdos, trilhas de aprendizado e avaliações.
- **Notificações**: Envio de lembretes, progresso e novidades, em tempo real ou agendado.
- **Outros**: Relatórios de engajamento e integração com sistemas de pagamento.

**Desafio**: Suportar alta vazão para streaming de vídeos, personalização em escala e consistência no progresso do aluno.

## Características

- **Alto Throughput**: Necessidade de processar milhares de mensagens por segundo em sistemas com múltiplos usuários e frentes.
- **DLQ (Dead Letter Queue)**: Gerenciar mensagens que falham no processamento para reprocessamento ou análise.
- **Arquitetura Recomendada**: Escolher a arquitetura ideal para cada caso, considerando escalabilidade e manutenção.
- **Discussão em Sala**: Análise colaborativa para alinhar soluções aos requisitos.

## Pontos de Discussão

- Qual ferramenta de mensageria é mais adequada e por quê?
- Qual arquitetura deve ser utilizada (Monolito, Microserviços, SOA ou Event-Driven)?
- Qual a melhor abordagem para banco de dados (SQL, NoSQL, CQRS, Event Sourcing)?
- Como SQS e SNS podem ser aplicados na solução?
- Quais são as desvantagens e riscos das escolhas acima?
