# Gerador de CPF Válido em Python (sem funções)

Este projeto foi criado para praticar lógica de programação em Python, gerando números de CPF válidos seguindo o algoritmo oficial dos dígitos verificadores.

### 📚 Base de estudo

Curso: *Curso de Python 3 do básico ao avançado - com projetos reais*  
Instrutores: *Luiz Otávio Miranda* e *Tales Calogi Malaquias* 
Plataforma: *Udemy*
Adaptei o projeto com minhas próprias palavras e estrutura para praticar o que aprendi.
---

## Como funciona

1. Gera 9 dígitos aleatórios.
2. Calcula o primeiro dígito verificador usando regra matemática do CPF.
3. Calcula o segundo dígito verificador com base nos 9 dígitos + primeiro dígito.
4. Imprime o CPF completo válido.

---

## Código principal

```python
import random

nove_digitos = ''
for i in range(9):
    nove_digitos += str(random.randint(0, 9))

contador_regressivo_1 = 10
resultado_digito_1 = 0 
for digito in nove_digitos:
    resultado_digito_1 += int(digito) * contador_regressivo_1
    contador_regressivo_1 -= 1
digito_1 = (resultado_digito_1 * 10) % 11
digito_1 = digito_1 if digito_1 <= 9 else 0

dez_digitos = nove_digitos + str(digito_1)
contador_regressivo_2 = 11
resultado_digito_2 = 0 
for digito in dez_digitos:
    resultado_digito_2 += int(digito) * contador_regressivo_2
    contador_regressivo_2 -= 1
digito_2 = (resultado_digito_2 * 10) % 11
digito_2 = digito_2 if digito_2 <= 9 else 0

cpf_gerado_pelo_calculo = f'{nove_digitos}{digito_1}{digito_2}'
print(cpf_gerado_pelo_calculo)



