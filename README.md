# Jogo do Número Secreto 🎯

Jogo de adivinhação em página única: o computador sorteia um número de **1 a 10** e o
jogador tenta acertar com dicas de "maior" ou "menor". A página fala as mensagens em
voz alta (Web Speech API) e não repete números até o ciclo completo.

Projeto de estudo de **JavaScript puro** (sem framework, sem build).

---

## Funcionalidades

- Sorteio aleatório entre 1 e 10
- Dica a cada tentativa: o número secreto é maior ou menor
- Contador de tentativas na mensagem de acerto
- **Voz** em português via `speechSynthesis` (com fallback silencioso)
- Botão "Novo jogo" liberado só após o acerto
- Controle de repetição: um número só volta a ser sorteado quando todos já saíram

---

## Stack

- HTML5
- CSS3
- JavaScript (ES6+)
- Web Speech API (`SpeechSynthesisUtterance`)

---

## Como rodar

Não precisa de instalação: abra o `index.html` no navegador.

```bash
# ou, com servidor local
npx serve .
```

---

## Estrutura

```
index.html   # marcação da tela
style.css    # estilos
app.js       # lógica do jogo
img/         # ilustração
```

---

## Decisões e aprendizados

- **Estado em variáveis globais** (`numeroSecreto`, `tentativas`, `listaDeNumerosSorteados`)
  — simples e suficiente para o tamanho do projeto; um próximo passo seria encapsular
  em um objeto ou módulo.
- **Recursão no sorteio** para evitar número repetido, com reset da lista quando todos
  já foram usados.
- **Voz com fallback:** se `speechSynthesis` não existir, o jogo continua funcionando
  apenas com texto no console.
- **Sem framework** de propósito: o objetivo era praticar DOM, eventos e funções.

---

## Limitações e próximos passos

- [ ] Separar estado e lógica da manipulação de DOM
- [ ] Validar entrada (hoje um campo vazio ou fora do intervalo não é tratado)
- [ ] Testes automatizados (a lógica é pura o suficiente para testar com Vitest)
- [ ] Opção de desligar a voz
- [ ] Aumentar o intervalo conforme a dificuldade

---

## Licença

MIT — veja [LICENSE](LICENSE).
