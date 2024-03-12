# Gerenciamento de defeitos

Controle de qualidade: Planejamento, avalia melhorias do processo, obtenção de métricas e COMO controlar a qualidade.

Análise estática: avaliação da documentação do software e código-fonte (code review, ferramentas de automação de processos de verificação de código, análise de histórias e modelagens).
Análise dinâmica: relacionado a técnicas com o código em execução (testes automatizados e manuais).

Verificação X Validação

Verificação: garantir que o produto está sendo construído corretamente - código.
Validação: garantir que o produto está em conformidade com o que o usuário precisa. Cliente pode ser necessário nessa etapa.


## Rastreamento de defeitos

O rastreamento de defeitos é importante pois facilita a correção do processo ou do produto, reportando o status do produto e auxiliando no alinhamento de revisões pelo time de desenvolvimento.
Para que eu faça um bom rastreamento de defeitos, preciso entender bem o produto e entender os tipos de defeitos encontrados.

### O que é defeito/bug?

Genericamente significa qualquer anomalia encontrada no produto.

Definições:
    Erro: ação humana que produz um resultado incorreto.
    Defeito: imperfeição ou deficiência relacionada aos requerimentos e espeficicações do produto.
    Falha de sistema: evento no qual o sistema não executa uma função sob limites específicos.

É importante padronizar as definições na equipe!

Motivos para erros: pressão do tempo, falha humana, inexperiência, falta de comunicação, complexidades de código e arquitetura, condições de ambientes inesperadas...

## Ciclo de vida do bug

1 - New: defeito é identificado e cadastrado pela primeira vez;
2 - Assigned: defeito é atribuído para desenvolvedor avaliar;
3 - Open: desenvolvedor inicia análise e correção;
4 - Fixed: desenvolvedor finaliza correção;
5 - Pending Retest: estado de espera para o time de teste;
6 - Retest: estado de execução do reteste;
7 - Verified: defeito cirrigido;
8 - Reopen: defeito não-corrigido;
9 - Closed: corrigido + testado + aprovado;
10 - Duplicate: efeiito já encontrado anteriormente;
11 - Rejected: defeiton ão é novo;
12 - Deferred: será corrigido em versões futuras;
13 - Not a bug: não é de fato um erro depois de analisado.