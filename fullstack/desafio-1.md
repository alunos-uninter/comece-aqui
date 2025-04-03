<div>
  <h1>Desafio 1: Calculadora de Saúde Financeira - Requisitos Detalhados</h1>

  <h2>Objetivo</h2>
  <p>Desenvolver um programa Java que analise a saúde financeira mensal com base na renda e gastos do usuário.</p>

  <h2>Requisitos Obrigatórios</h2>
  <h3>1. Entrada de Dados</h3>
  <h4>a. Salário</h4>
  <ul>
    <li>Ler via Scanner o valor bruto mensal (ex: 4500.50)</li>
    <li>Aceitar apenas valores positivos</li>
  </ul>

  <h4>b. Despesas</h4>
  <ul>
    <li>Ler custos obrigatórios (ex: 1500 para aluguel, 500 para financiamentos)</li>
    <li>Ler gastos variáveis (ex: 150.75 para mercado, 30 para Netflix)</li>
    <li>Permitir múltiplas entradas até o usuário digitar "sair" para obrigatórios e variáveis</li>
    <li>Acumular valores digitados em uma variável</li>
    <li>Salvar total de cada despesa em uma variável</li>
    <li>Salvar total (somar total das despesas fixas e variáveis) em uma variável</li>
  </ul>

  <h3>2. Processamento</h3>
  <h4>a. Cálculo da Sobra</h4>
  <p>Fórmula:</p>
  <p><code>sobra = salário - despesas fixas - despesas variáveis</code></p>

  <h4>b. Classificação Financeira</h4>
  <p>Critérios:</p>
  <ul>
    <li><strong>Atenção:</strong> Sobra &lt; 20% do salário</li>
    <li><strong>Estável:</strong> 20% ≤ Sobra ≤ 35%</li>
    <li><strong>Saudável:</strong> Sobra &gt; 35%</li>
  </ul>

  <h4>c. Validações</h4>
  <ul>
    <li>Bloquear cálculo se:
      <ul>
        <li>Salário &lt; (despesas fixas + despesas variáveis)</li>
        <li>Valores negativos em qualquer entrada</li>
      </ul>
    </li>
  </ul>

  <h3>3. Saída de Dados</h3>
  <h4>a. Tabela de Resultados</h4>
  <p>Exibir em formato tabular:</p>
  <pre>
  | Salário | Despesas Fixas | Despesas Variáveis | Sobra   | Situação  |
  | R$ XXXX | R$ XXXX        | R$ XXXX            | R$ XXXX | Saudável |
  </pre>

  <h4>b. Formatação</h4>
  <ul>
    <li>Valores monetários com 2 casas decimais (ex: R$ 2350.00)</li>
  </ul>

  <h2>Exemplo de Fluxo</h2>
  <h3>terminal</h3>
  <pre>
  [Entradas]
  Salário: 6000
  Despesas fixas: 2500
  Despesas variáveis (digite 'sair' para finalizar):
  > 300
  > 450.50
  > 120
  > sair

[Saída]
| Salário | Despesas Fixas | Despesas Variáveis | Sobra | Situação |
| R$6000 | R$2500 | R$870.50 | R$2629.50 | 🚀 Saudável |

  </pre>

  <h2>Checklist de Validação</h2>
  <ul>
    <li>Calcula corretamente porcentagem da sobra</li>
    <li>Classifica todas 3 situações adequadamente</li>
    <li>Formata saída com tabela</li>
    <li>Loop funciona até comando "sair"</li>
  </ul>
</div>
