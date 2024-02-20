  Este código Python é uma função chamada extrair_endereco que utiliza expressões regulares (regex) para extrair o nome da rua e o número do endereço de uma string.

  Aqui está uma explicação linha por linha do código:

1. import re: Importa o módulo re, que é usado para trabalhar com expressões regulares em Python.

2. def extrair_endereco(endereco): Define uma função chamada extrair_endereco que recebe uma string endereco como entrada.

3. padrao = r'(\D+)(\d+[\w\s]*)?$': Define uma expressão regular que procura pelo nome da rua e pelo número do endereço. 
   - (\D+): Captura um ou mais caracteres que não são dígitos (o nome da rua).
   - (\d+[\w\s]*)?: Captura um ou mais dígitos seguidos opcionalmente de outros caracteres alfanuméricos ou espaços (o número do endereço). O ? torna esta parte opcional.
   - $: Garante que a correspondência ocorra até o final da string.

4. resultado = re.match(padrao, endereco): Usa re.match() para procurar por correspondências entre o padrão e o endereço fornecido. re.match() tenta encontrar uma correspondência apenas no início da string.

5. if resultado:: Verifica se houve uma correspondência.

6. rua = resultado.group(1).strip(): Se houver uma correspondência, extrai o grupo 1 (o nome da rua) e remove espaços em branco extras com .strip().

7. numero = resultado.group(2).strip() if resultado.group(2) else '': Extrai o grupo 2 (o número do endereço) se ele existir, senão retorna uma string vazia. Também remove espaços em branco extras.

8. return rua, numero: Retorna o nome da rua e o número do endereço.

9. else: return None, None: Retorna None para ambos nome da rua e número se não houver correspondência.

  Depois da definição da função, há dois conjuntos de casos de teste:

- testes_simples: São endereços simples compostos apenas pelo nome da rua e o número.
- testes_complexos: São endereços mais complexos, que incluem números e nomes de rua em diferentes formatos.

  No final, os resultados dos testes são impressos para mostrar como a função extrair_endereco funciona com diferentes tipos de endereços.
