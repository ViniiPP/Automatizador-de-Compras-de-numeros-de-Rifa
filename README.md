## 🎟️ Raffle Number Auto Clicker

Script em JavaScript para automatizar a seleção de números disponíveis em sistemas de rifa baseados em HTML/DOM, executado diretamente pelo console do navegador.

---

## 🚀 O que este script faz

- Seleciona automaticamente números disponíveis
- Ignora números já pagos (`paid`)
- Ignora números reservados (`reserved`)
- Simula cliques reais de mouse
- Faz scroll automático até cada número
- Não depende de bibliotecas externas

---

## 📌 Código

```js
const buttons = document.querySelectorAll(
  '#raffle-numbers button.raffle-number-btn:not(.paid):not(.reserved)'
);

console.log('Botões disponíveis:', buttons.length);

buttons.forEach((btn, i) => {
  setTimeout(() => {
    btn.scrollIntoView({ block: 'center' });

    btn.dispatchEvent(new MouseEvent('mousedown', { bubbles: true }));
    btn.dispatchEvent(new MouseEvent('mouseup', { bubbles: true }));
    btn.dispatchEvent(new MouseEvent('click', { bubbles: true }));
  }, i * 10);
});
