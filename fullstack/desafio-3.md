<div>
    <h1>Desafio 2: Gerenciador de Estoque</h1>
    <h2>Objetivo</h2>
    <p>Desenvolver um sistema de controle de estoque para pequenos comércios usando <code>ArrayList</code>.</p>
        <h2>Exemplo de estoque</h2>
    <pre>
ArrayList&lt;Produto&gt; estoque = new ArrayList&lt;&gt;() {{
    add(new Produto(1, "Caneta", 10));
    add(new Produto(2, "Caderno", 5));
    add(new Produto(3, "Borracha", 3));
}};</pre>
    <h2>Requisitos Obrigatórios</h2>
    <h3>Entrada de Dados</h3>
    <ul>
        <li>
            <strong>Atualizar Estoque (Compras)</strong>
            <ul>
                <li>Ler via <code>Scanner</code>:
                    <ul>
                        <li>ID do produto vendido</li>
                        <li>Quantidade comprada</li>
                    </ul>
                </li>
                <li>Permitir múltiplas atualizações até o usuário digitar "sair"</li>
            </ul>
        </li>
    </ul>
    <h3>Processamento</h3>
    <ul>
        <li>
            <strong>Lógica de Atualização</strong>
            <ul>
                <li>Subtrair quantidade vendida do estoque</li>
                <li>Validar:
                    <ul>
                        <li>Produto existe no estoque</li>
                        <li>Quantidade vendida ≤ estoque disponível</li>
                    </ul>
                </li>
            </ul>
        </li>
        <li>
            <strong>Monitoramento de Estoque</strong>
            <ul>
                <li>Verificar estoque após cada operação</li>
                <li>Gerar alerta imediato se quantidade indisponível </li>
            </ul>
        </li>
    </ul>
 <h3>Saída de Dados</h3>
    <ul>
        <li>
            <strong>Listagem de Produtos</strong>
            <ul>
                <li>Exibir tabela formatada ao iniciar a aplicação:
                    <pre>
| ID | Produto   | Quantidade |
|----|-----------|------------|
| 1  | Caneta    | 12         |
| 2  | Caderno   | 3          |
                    </pre>
                </li>
            </ul>
        </li>
        <li>
            <strong>Alertas</strong>
            <ul>
                <li>Mensagem destacada quando quantidade estiver inválida:
                    <pre>[ALERTA] Quantidade não disponível de "Caderno". Temos 3 unidades!</pre>
                </li>
            </ul>
        </li>
    </ul>
    <h2>Exemplo de Fluxo</h2>
     <pre>
[Estoque]
| ID | Produto   | Quantidade |
|----|-----------|------------|
| 1  | Caneta    | 12         |
| 2  | Caderno   | 3          |
<br />
[Comprar Produtos]
ID do produto (ou 'sair'): 1
Quantidade: 2
ID do produto (ou 'sair'): 2
Quantidade: 1
Nome do produto (ou 'sair'): sair
<br />
Compra realizada com sucesso!
| Produto   | Quantidade |
|-----------|------------|
| Caneta    | 2          |
| Caderno   | 1          |
    </pre>
    <h2>Checklist de Validação</h2>
    <ul>
        <li>ArrayList armazena objetos Produto corretamente</li>
        <li>Atualizações refletem no estoque imediatamente</li>
        <li>Alertas de estoque</li>
    </ul>
</div>
