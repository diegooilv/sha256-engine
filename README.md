# SHA-256 From Scratch

Este repositório tem como objetivo implementar o algoritmo **SHA-256** do zero, utilizando apenas JavaScript, sem depender do módulo `crypto` ou de bibliotecas externas.

A proposta não é apenas chegar ao resultado final, mas entender como cada etapa do algoritmo funciona internamente. Todo o projeto será desenvolvido em pequenas etapas, começando pelos conceitos mais básicos até a implementação completa.

## Objetivos

* Entender o funcionamento de uma função hash.
* Aprender como o SHA-256 é estruturado.
* Implementar cada parte do algoritmo manualmente.
* Desenvolver uma implementação legível e bem documentada.
* Comparar o resultado com a implementação oficial do Node.js.

---

# Etapas

## Módulo 1 — Fundamentos

### 1. O que é uma função hash?

Entender o conceito de hash, suas propriedades e as diferenças entre hash, criptografia e encoding.

### 2. Como o computador representa texto?

Descobrir como uma string é convertida em bytes utilizando UTF-8.

### 3. Bits e bytes

Revisão sobre representação binária, bytes e como os computadores armazenam informações.

### 4. Binário e hexadecimal

Aprender a converter números entre decimal, binário e hexadecimal.

### 5. Operações bit a bit

Estudar AND, OR, XOR e NOT, que aparecem constantemente no SHA-256.

### 6. Shift e rotação de bits

Entender deslocamentos (`<<`, `>>`, `>>>`) e rotações de bits.

### 7. Inteiros de 32 bits no JavaScript

Aprender como o JavaScript lida com operações de 32 bits e por que usamos `>>> 0`.

### 8. Aritmética módulo 2³²

Entender overflow e por que ele faz parte do algoritmo.

### 9. Visão geral do SHA-256

Conhecer todas as etapas do algoritmo antes de começar a implementá-las.

### 10. Estrutura do projeto

Organizar os arquivos e preparar a base da implementação.

---

## Módulo 2 — Preparando a mensagem

### 11. Convertendo texto em bytes

Transformar a entrada em uma sequência de bytes.

### 12. Padding — Parte 1

Adicionar o primeiro bit (`1`) após a mensagem.

### 13. Padding — Parte 2

Completar a mensagem com zeros até atingir o tamanho esperado.

### 14. Acrescentando o tamanho original

Adicionar os últimos 64 bits contendo o comprimento da mensagem.

### 15. Dividindo em blocos

Separar a mensagem em blocos de 512 bits.

### 16. Criando as primeiras 16 words

Converter cada bloco em 16 palavras de 32 bits.

### 17. Revisão da preparação da mensagem

Verificar se toda a estrutura está correta antes da compressão.

---

## Módulo 3 — Message Schedule

### 18. O que é o Message Schedule?

Entender por que o SHA-256 trabalha com 64 words.

### 19. Implementando σ0 e σ1

Criar as funções responsáveis pela expansão da mensagem.

### 20. Expandindo para 64 words

Gerar todas as words utilizadas durante as rodadas.

### 21. Validando o Message Schedule

Comparar os resultados com exemplos conhecidos.

---

## Módulo 4 — Constantes e estado inicial

### 22. Os valores iniciais (H0...H7)

Entender de onde surgem os oito valores iniciais do algoritmo.

### 23. As constantes K

Conhecer a origem das 64 constantes utilizadas nas rodadas.

### 24. Registradores

Preparar as variáveis `a` até `h` que serão atualizadas durante a compressão.

---

## Módulo 5 — Funções do algoritmo

### 25. Função Ch

Implementar a função *Choose*.

### 26. Função Maj

Implementar a função *Majority*.

### 27. Funções Σ0 e Σ1

Implementar as funções utilizadas na compressão.

### 28. Revisão das funções

Reunir todas as funções antes de iniciar as rodadas.

---

## Módulo 6 — Compressão

### 29. Entendendo uma rodada

Estudar o funcionamento de uma única rodada da compressão.

### 30. Calculando T1

Implementar o primeiro cálculo da rodada.

### 31. Calculando T2

Implementar o segundo cálculo da rodada.

### 32. Atualizando os registradores

Atualizar corretamente os valores de `a` até `h`.

### 33. Executando as 64 rodadas

Aplicar o processo completo de compressão.

### 34. Atualizando o estado do hash

Somar o resultado da compressão ao estado atual.

---

## Módulo 7 — Finalização

### 35. Processando múltiplos blocos

Adaptar a implementação para mensagens maiores que 512 bits.

### 36. Gerando o hash final

Obter os oito valores finais do algoritmo.

### 37. Convertendo para hexadecimal

Produzir a saída no formato hexadecimal.

### 38. Validando a implementação

Comparar os resultados com a implementação oficial do Node.js.

---

## Módulo 8 — Extras

### 39. Testes

Criar casos de teste para diferentes entradas.

### 40. Refatoração

Melhorar organização, legibilidade e reutilização do código.

### 41. Especificação oficial

Relacionar a implementação com a documentação do NIST.

### 42. Próximos passos

Explorar conceitos relacionados, como HMAC, SHA-224, Merkle Trees, Proof of Work e algoritmos para armazenamento de senhas.

---

## Resultado esperado
 
Ao final deste projeto, a ideia é ter uma implementação completa do SHA-256 escrita do zero, entendendo cada operação realizada pelo algoritmo, desde a conversão da mensagem até a geração do hash final.

