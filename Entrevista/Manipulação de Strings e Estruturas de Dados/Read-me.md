## 📌 Como inverter uma string em Python?
Inverter uma string em Python é muito simples! Aqui estão algumas formas de fazer isso. 🚀

####🔹 1. Usando Slicing ([::-1]) ✅ Mais rápido e Pythonico
A maneira mais eficiente e recomendada:

```
texto = "Python"
invertida = texto[::-1]
print(invertida)  # "nohtyP"
```

#### Como funciona?

* [::-1] cria uma cópia invertida da string.
________________________________________________________________________

## 🔹 2. Usando a Função reversed()
A função `reversed()` retorna um iterador, então precisamos juntar (`join`) os caracteres:
```
texto = "Python"
invertida = "".join(reversed(texto))
print(invertida)  # "nohtyP"
```

#### Por que usar `reversed()`?

* Pode ser útil em manipulações mais complexas.

* Torna a intenção mais explícita.

___________________________________________________________________________

## 🔹 4. Usando Recursão (Não recomendado para grandes textos)

```
from functools import reduce

texto = "Python"
invertida = reduce(lambda x, y: y + x, texto)
print(invertida)  # "nohtyP"
```
**Menos legível** que outras abordagens.
____________________________________________________________________________

## 🔹 Qual é a melhor forma?


| Método	|  Simplicidade	 |  Performance  |
|---------|----------------|---------------|
| **Slicing** [::-1]	| ✅ Muito simples	| 🚀 Muito rápido|
| **``reversed()** + `join()`	| ✅ Legível	| 🚀 Rápido |
| **Loop for**	| ❌ Verboso	| 🐢 Lento |
| **Recursão**	| ❌ Complexo	| ⚠️ Ineficiente |
| **reduce()**	| ❌ Pouco usado | ⚠️ Pouco eficiente |
 
#### Conclusão: [::-1] é a melhor opção! 🚀🔥






