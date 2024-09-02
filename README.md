# Est-gio---Target-Sistemas

### 1) Observe o trecho de código abaixo: int INDICE = 13, SOMA = 0, K = 0;
Enquanto K < INDICE faça { K = K + 1; SOMA = SOMA + K; }
Imprimir(SOMA);
Ao final do processamento, qual será o valor da variável SOMA?

### 2) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

IMPORTANTE: Esse número pode ser informado através de qualquer entrada de sua preferência ou pode ser previamente definido no código;

### 3) Dado um vetor que guarda o valor de faturamento diário de uma distribuidora, faça um programa, na linguagem que desejar, que calcule e retorne:
• O menor valor de faturamento ocorrido em um dia do mês;
• O maior valor de faturamento ocorrido em um dia do mês;
• Número de dias no mês em que o valor de faturamento diário foi superior à média mensal.

IMPORTANTE:
a) Usar o json ou xml disponível como fonte dos dados do faturamento mensal;
b) Podem existir dias sem faturamento, como nos finais de semana e feriados. Estes dias devem ser ignorados no cálculo da média;

### 4) Dado o valor de faturamento mensal de uma distribuidora, detalhado por estado:
• SP – R$67.836,43
• RJ – R$36.678,66
• MG – R$29.229,88
• ES – R$27.165,48
• Outros – R$19.849,53

Escreva um programa na linguagem que desejar onde calcule o percentual de representação que cada estado teve dentro do valor total mensal da distribuidora.  

### 5) Escreva um programa que inverta os caracteres de um string.

IMPORTANTE:
a) Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;
b) Evite usar funções prontas, como, por exemplo, reverse;

## 1) Cálculo da Variável `SOMA`

Dado o trecho de código:

```python
INDICE = 13
SOMA = 0
K = 0

while K < INDICE:
    K = K + 1
    SOMA = SOMA + K

print(SOMA)
````
## 2) Verificação de Número na Sequência de Fibonacci

Dado o trecho de código:

```python
def fibonacci_number(n):
    a, b = 0, 1
    
    while a <= n:
        if a == n:
            return f"O número {n} pertence à sequência de Fibonacci."
        a, b = b, a + b

    return f"O número {n} não pertence à sequência de Fibonacci."

# Exemplo 
numero = 21  # Você pode alterar esse valor para testar com outros números
resultado = fibonacci_number(numero)
print(resultado)

```

## 3) Análise de Faturamento Diário

Dado o trecho de código:

```python
import json

def calcular_faturamento(file_path):
    with open(file_path, 'r') as file:
        data = json.load(file)
    
    faturamento = data["faturamento"]

      # Remover dias sem faturamento (0.0)
    faturamento = [valor for valor in faturamento if valor > 0]

    menor_valor = min(faturamento)
    maior_valor = max(faturamento)
    media_mensal = sum(faturamento) / len(faturamento)

    dias_acima_media = len([valor for valor in faturamento if valor > media_mensal])

    return menor_valor, maior_valor, dias_acima_media

#Exemplo 
arquivo_faturamento = "faturamento.json"  # Caminho para o arquivo JSON
menor, maior, dias_acima = calcular_faturamento(arquivo_faturamento)
print(f"Menor valor: {menor}")
print(f"Maior valor: {maior}")
print(f"Dias acima da média: {dias_acima}")
```

## 4) Percentual de Representação do Faturamento por Estado

Dado o trecho de código:

```python
faturamento_estados = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

total_faturamento = sum(faturamento_estados.values())

percentuais = {estado: (valor / total_faturamento) * 100 for estado, valor in faturamento_estados.items()}

for estado, percentual in percentuais.items():
    print(f"{estado}: {percentual:.2f}%")
```

## 5) Inverter os Caracteres de uma String

Dado o trecho de código:

```python
def inverter_string(texto):
    texto_invertido = ""
    for char in texto:
        texto_invertido = char + texto_invertido
    return texto_invertido

# Exemplo
texto = "OpenAI"
texto_invertido = inverter_string(texto)
print(f"Texto original: {texto}")
print(f"Texto invertido: {texto_invertido}")

```
