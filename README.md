# Advinhe

Um jogo web interativo desenvolvido em React para adivinhar palavras do contexto de programação, letra por letra. O jogador dispõe de um número limitado de tentativas e recebe dicas para auxiliar na adivinhação.

## Visão Geral

Advinhe é uma aplicação de jogo de palavras que desafia o usuário a descobrir termos técnicos da programação através da adivinhação de letras. A cada letra correta, ela é revelada na palavra. O jogo termina quando o jogador consegue adivinhar toda a palavra ou esgota suas tentativas.

## Funcionalidades

### Mecânica de Jogo

- Seleção aleatória de palavras de uma base de termos de programação
- Exibição de dicas contextualizadas para cada palavra
- Sistema de tentativas limitadas (número de letras + 5 tentativas adicionais)
- Validação de letras duplicadas
- Feedback visual imediato para letras corretas e incorretas

### Interface do Usuário

- **Header**: Exibe o logo, contador de tentativas e botão de reinício
- **Dica**: Apresenta informações que ajudam na adivinhação da palavra
- **Palavra**: Mostra as letras descobertas e espaços em branco para letras não reveladas
- **Campo de Palpite**: Input para o usuário digitar uma letra por vez
- **Registro de Letras**: Exibe todas as letras utilizadas, diferenciando acertos e erros

### Controles

- Digitação de uma letra no campo de palpite
- Clique no botão "Confirmar" para validar a letra
- Clique no ícone de reinício para começar um novo jogo (com confirmação)

### Validações

- Aceita apenas uma letra por vez
- Detecta e rejeita letras já utilizadas
- Impede envio de campos vazios
- Diferencia maiúsculas e minúsculas (padronização interna)

## Base de Palavras

O jogo inclui cinco desafios pré-configurados:

1. **CSS** - Linguagem de estilos
2. **React** - Biblioteca para criar interfaces Web
3. **HTML** - Linguagem de marcação
4. **Javascript** - Uma das linguagens de programação mais utilizadas no mundo
5. **Typescript** - Para adicionar tipagem no Javascript

## Estrutura do Projeto

```
advinhe/
├── src/
│   ├── components/
│   │   ├── header/          # Cabeçalho com logo e controles
│   │   ├── letter/          # Componente individual de letra
│   │   ├── Button/          # Botão reutilizável
│   │   ├── Input/           # Campo de entrada reutilizável
│   │   ├── LettersUsed/     # Registro de letras utilizadas
│   │   └── tip/             # Exibição de dicas
│   ├── utils/
│   │   └── words.ts         # Base de palavras e tipos
│   ├── App.tsx              # Componente principal da aplicação
│   ├── main.tsx             # Ponto de entrada do React
│   ├── app.module.css       # Estilos do componente principal
│   └── global.css           # Estilos globais
├── public/                  # Ativos públicos (logo, ícones)
├── index.html               # Documento HTML
├── package.json             # Dependências e scripts
├── tsconfig.json            # Configuração TypeScript
└── vite.config.ts           # Configuração Vite
```

## Tecnologias

- **React** ^19.2.6 - Biblioteca para construção de interfaces
- **TypeScript** ~6.0.2 - Tipagem estática para JavaScript
- **Vite** ^8.0.12 - Build tool e dev server
- **CSS Modules** - Estilos com escopo de componente

## Instalação

### Pré-requisitos

- Node.js 16.0 ou superior
- npm ou yarn

### Passos

1. Clone o repositório:
```bash
git clone https://github.com/pedroveiga-l/advinhe.git
```

2. Instale as dependências:
```bash
npm install
```

3. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

4. Abra o navegador e acesse `http://localhost:5173`

## Scripts Disponíveis

- `npm run dev` - Inicia o servidor de desenvolvimento
- `npm run build` - Compila TypeScript e otimiza para produção

## Fluxo de Jogo

1. A aplicação inicia com uma palavra aleatória
2. O jogador recebe uma dica sobre a palavra
3. O jogador digita uma letra e clica em "Confirmar"
4. Sistema valida e processa a letra:
   - Se correta: letra é revelada e adicionada ao registro de acertos
   - Se incorreta: letra é adicionada ao registro de erros
   - Se duplicada: exibe aviso
5. O jogo termina quando:
   - Jogador acerta todas as letras: mensagem de vitória
   - Jogador esgota as tentativas: mensagem de derrota
6. Ao finalizar, um novo jogo é iniciado automaticamente

## Lógica de Pontuação

- O score incrementa em 1 ponto a cada letra correta identificada
- Quando a pontuação atinge o número de letras na palavra, o jogador vence
- Limite de tentativas: comprimento da palavra + 5 tentativas adicionais

## Estilo e Design

- Interface limpa e moderna
- Paleta de cores: branco, cinza claro e laranja (#e8891c)
- Fontes: Noto Sans, Inter e Inter Tight
- Responsividade adequada para a área principal (556px de largura)
- Transições suaves para melhor experiência do usuário

## Componentes Reutilizáveis

### Letter
Exibe uma letra individual com opções de tamanho e cor.

Propriedades:
- `value`: Letra a exibir
- `size`: "default" | "small"
- `color`: "default" | "correct" | "wrong"

### Button
Botão estilizado reutilizável.

Propriedades:
- `title`: Texto do botão
- Herda propriedades nativas de `<button>`

### Input
Campo de entrada estilizado e reutilizável.

Propriedades:
- Herda todas as propriedades nativas de `<input>`

## Estados da Aplicação

A aplicação gerencia os seguintes estados:

- `score`: Pontuação atual (acertos)
- `letter`: Letra sendo digitada
- `lettersUsed`: Array de letras utilizadas com indicativo de acerto/erro
- `challenge`: Objeto com palavra atual e dica

## Configurações Personalizáveis

Para adicionar novas palavras ao jogo, edite o arquivo `src/utils/words.ts`:

```typescript
export const WORDS: Challenge[] = [
  { id: 1, word: "PALAVRA", tip: "Descrição da palavra" },
  // ... mais palavras
]
```

## Melhorias Futuras

Possíveis extensões para o projeto:

- Sistema de níveis de dificuldade
- Ranking de pontuações (localStorage)
- Mais palavras na base de dados
- Modo multiplayer
- Suporte a idiomas
- Temas customizáveis
- Estatísticas do jogador

## Licença

Este projeto é parte dos estudos da Rocketseat Full Stack.

## Autor

Desenvolvido como projeto de aprendizado em React e TypeScript.
