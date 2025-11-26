# Minha Padaria — Entrega da Atividade
---

Este README responde às questões da atividade e descreve as melhorias aplicadas no site `Minha Padaria.html`, evidências de implementação e instruções para publicação.

Sumário
- Objetivo
- 1) Affordance — o que foi aplicado e como melhora a navegação
- 2) Heurísticas de Nielsen aplicadas (A–D)
- 3) Análise semiótica e Signo Visual (recursos utilizados)
- 4) Publicação do site (instruções)
- Entregáveis e Evidências

---

OBJETIVO
O objetivo desta entrega é refatorar a interface do site "Minha Padaria" com foco em affordance e usabilidade, aplicar heurísticas de Nielsen para melhorar a experiência do usuário, criar um signo visual representativo e publicar a versão modificada.

1 — Affordance (3,0 pontos)
Definição breve: Affordance significa que elementos visuais devem sugerir sua função (por exemplo, botões parecem clicáveis, campos de entrada parecem editáveis), reduzindo a necessidade de instruções explícitas.

1.1 — Melhorias aplicadas no site `Minha Padaria.html` (uso de affordance)
- Navegação visível e legível: o menu principal (links para `#doces`, `#salgados`, `#encomendas`, `#contato`) está no header e usa texto claro. Isso permite que o usuário entenda imediatamente onde navegar.
- Botões com aparência de botão: classes `.btn` e `.cart-btn` têm cor de fundo, borda arredondada e mudança visual no hover/focus — aparência física que indica clique.
- Campo de busca com placeholder: o input de busca possui placeholder descritivo "Buscar pães, doces ou salgados", comunicando seu propósito sem instruções.
- Formulário de adicionar ao carrinho: cada produto apresenta um `input type="number"` (quantidade) e um botão "Adicionar ao carrinho" posicionado ao lado — proximidade e layout deixam clara a ação.
- Feedback imediato: ao adicionar um item, o contador `#cart-count` é atualizado e um toast exibe mensagem confirmando a ação; isso comunica resultado da interação.
- Ícones e rótulos combinados: o carrinho mostra um ícone (🧺) e um contador — ícone + número tornam a função óbvia.

Como essas alterações melhoram a navegação
- Reduzem a carga cognitiva: o usuário reconhece controles pela aparência e posição.
- Diminuem necessidade de instruções: a funcionalidade é sugerida visualmente.
- Aumentam confiança: feedback claro (toast e contador) confirma ações.

2 — Heurísticas de Nielsen (3,0 pontos)
Aplicadas no site conforme solicitado.

2.1.A — Visibilidade do status do sistema
- Implementação: um bloco `.status` no header exibe `#status-text` ("Aberto agora" / "Fechado no momento") e um ponto colorido `.status-dot` (verde/vermelho). O texto e a cor atualizam com base no horário do usuário (JS simples).
- Evidência: abra `Minha Padaria.html` e observe o status no canto superior esquerdo do header.
- Acessibilidade: o container usa `aria-live="polite"` para notificar tecnologias assistivas sobre mudanças sutis.

2.1.B — Consistência e padrões
- Implementação: padronização de cores (cor primária `#d2691e`), estilo de botões (`.btn`, `.cart-btn`), estrutura de cards (`.card-food`) para produtos, e comportamento de links (hover/focus) consistente.
- Evidência: todos os botões de ação possuem aparência similar e os cards repetem o mesmo layout para cada item.

2.1.C — Prevenção de erros
- Implementação: campos de quantidade usam `min="1"` e há validação no JavaScript que impede valores inválidos (exibe toast informando o erro e ajusta para 1).
- Evidência: tente inserir 0, negativo ou texto no campo de quantidade — o sistema força `1` e mostra mensagem.

2.1.D — Correspondência entre o sistema e o mundo real
- Implementação: linguagem direta do domínio ("Adicionar ao carrinho", "Encomendas", nomes dos alimentos), imagens reais de produtos e o signo visual que remete a pão/trigo.
- Evidência: termos e ícones usados correspondem ao vocabulário do usuário de uma padaria; elementos visuais (imagens) reforçam o conteúdo.

3 — Análise semiótica e SIGNO VISUAL (3,0 pontos)

3.1 — Signo Visual criado para representar o site "Minha Padaria"
- Descrição do signo: logotipo simples composto por um ícone circular que lembra um pão/trigo e o nome da marca escrito ao lado. As cores escolhidas são:
	- `#fff6ea`: tom claro associado à massa/pão fresco;
	- `#d2691e`: marrom/laranja que remete ao forno e à crosta do pão.
- Recursos usados:
	- Ícone (símbolo): formas vetoriais (SVG) estilizadas para lembrar um pão arredondado e elementos estilizados que lembram trigo.
	- Índice (forma): círculo como índice para representar integralidade e alimento (círculos evocam comida, pães redondos etc.).
	- Texto: o nome "Minha Padaria" próximo ao ícone para reforçar leitura e reconhecimento.
- Justificativa semiótica:
	- O signo combina forma (círculo), cor (tons quentes) e ícone (pão/trigo) para produzir um significado imediato: associação com padaria e alimentos frescos. É legível em tamanhos pequenos (favicon) e grande (header).

4 — Publicação do site (1,0 ponto)

Instruções para publicar via GitHub Pages (passos resumidos):
1. No diretório do projeto (`c:\Users\Aluno\Documents\Site\Site`), inicialize git e commit os arquivos:

```powershell
cd "c:\Users\Aluno\Documents\Site\Site"
git init
git add .
git commit -m "Entrega Minha Padaria - versão final"
```
2. Crie repositório no GitHub e adicione o remote (substitua `<USER>` e `<REPO>`):

```powershell
git remote add origin https://github.com/<USER>/<REPO>.git
git push -u origin main
```
3. No GitHub: *Settings > Pages* escolha o branch `main` e a pasta `/ (root)`. Aguarde alguns minutos; a URL ficará disponível no formato `https://<USER>.github.io/<REPO>/`.

Alternativas: Netlify ou Vercel também publicam sem necessidade de configurar GitHub Pages manualmente (siga os guias de cada serviço).

---

Entregáveis
- Código do projeto: todos os arquivos em `c:\Users\Aluno\Documents\Site\Site` (ex.: `Minha Padaria.html`, `styles.css`, `img1.jpg`, `padaria02.png`).
- URL do site: após publicar, cole aqui a URL fornecida pelo serviço (GitHub Pages, Netlify, etc.).
- Evidências (resumo): descrição das funcionalidades e local onde estão implementadas.

Evidências detalhadas — onde encontrar as funcionalidades solicitadas
- Affordance:
	- Campo de busca: `Minha Padaria.html` — elemento `<input id="search-input">` (placeholder explicativo).
	- Botões: classe `.btn` e `.cart-btn` (arquivo `styles.css`) com estilo distinto.
	- Ação de adicionar ao carrinho: formulários com classe `.add-form` e script que atualiza `#cart-count`.
- Heurísticas de Nielsen:
	- Status do sistema: elemento `.status` com `#status-text` no header; JS que atualiza com horário.
	- Consistência: classes reutilizáveis (`.card-food`, `.btn`) no HTML e estilos em `styles.css`.
	- Prevenção de erros: inputs com `min="1"` e validação JS nas submissões das forms.
	- Correspondência com o mundo real: nomes de produtos, imagens e texto descritivo próximos ao vocabulário do usuário.
- Signo visual: SVG no header (procure a tag `<svg class="logo">` em `Minha Padaria.html`).

Observações finais e próximos passos
- Caso queira, eu posso: 
	- Publicar o projeto no GitHub Pages (preciso do nome do repositório e confirmação para executar os comandos locais);
	- Gerar um PDF com estas evidências formatadas;
	- Ajustar responsividade (por exemplo, empilhar a imagem `img1.jpg` acima do texto em telas pequenas).

---


