# Scroll Blur Wrapper

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

Um componente React com TypeScript leve e de alto desempenho que aplica um efeito de *motion blur* (desfoque de movimento) dinâmico aos elementos filhos, baseando-se na velocidade de rolagem do usuário.

Totalmente executado no lado do cliente (Client Side), otimizado para GPU e acessível.

<p align="center">
  <br />
  <b>Demo:</b> <a href="https://freddydanilo.com">Freddy Danilo</a>
  <br />
</p>

## ✨ Funcionalidades

- **Alta Performance:** Otimizado para usar aceleração de hardware (GPU) e evitar re-renderizações desnecessárias.
- **Frame Rate Independent:** O efeito visual é consistente em monitores de 60Hz, 120Hz ou 144Hz+.
- **Acessível:** Respeita automaticamente a preferência do sistema `prefers-reduced-motion`, desativando o efeito para usuários sensíveis a movimento.
- **Visual Correto:** Utiliza `sRGB` para cores fiéis e corrige artefatos nas bordas do desfoque.
- **Zero Dependências:** Não requer bibliotecas de animação pesadas.

## 💻 Como usar

Copie o componente para o seu projeto e importe-o onde desejar:

### Uso Básico

```tsx
import { ScrollBlurWrapper } from "./components/scroll-blur-wrapper";

export default function Exemplo() {
  return (
    <ScrollBlurWrapper>
      <div className="conteudo">
        <h1>Meu Conteúdo com Blur</h1>
        {/* ... restante do conteúdo ... */}
      </div>
    </ScrollBlurWrapper>
  );
}
```
### Uso com Container de Scroll Personalizado
Se o scroll não for na janela (window), mas sim em uma div interna:

```tsx
import { useRef } from "react";
import { ScrollBlurWrapper } from "./components/scroll-blur-wrapper";

export default function ExemploContainer() {
  const containerRef = useRef<HTMLDivElement>(null);

  return (
    <div ref={containerRef} style={{ overflowY: "auto", height: "100vh" }}>
      <ScrollBlurWrapper scrollContainer={containerRef}>
         {/* Conteúdo aqui */}
      </ScrollBlurWrapper>
    </div>
  );
}
```

## Props

| Propriedade | Tipo | Padrão | Descrição |
| :--- | :--- | :--- | :--- |
| `children` | `ReactNode` | **Obrigatório** | Elementos a serem envolvidos pelo efeito. |
| `className` | `string` | `undefined` | Classes CSS (compatível com Tailwind). |
| `style` | `CSSProperties` | `undefined` | Estilos inline adicionais. |
| `minVelocity` | `number` | `5` | Velocidade mínima de scroll para iniciar o desfoque. |
| `maxBlur` | `number` | `10` | Limite máximo visual do desfoque (em px). |
| `strength` | `number` | `0.2` | Multiplicador de intensidade do efeito. |
| `blurDirection` | `"vertical" \| "horizontal"` | `"vertical"` | Orientação do desfoque. |
| `scrollContainer` | `RefObject<HTMLElement>` | `undefined` | Referência para um container de scroll (caso não seja a janela). |

## ❤️ Apoie este projeto
Se este componente te ajudou, considere fazer uma doação ou deixar uma estrela!

[![Donate](https://img.shields.io/badge/Donate-PayPal-blue.svg?style=flat-square&logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=RA8KH3JFCKXCS)

### ⭐ Deixe uma estrela no repositório
Uma simples estrela ajuda muito o projeto a crescer e alcançar mais desenvolvedores.

Desenvolvido por: Freddy Danilo
