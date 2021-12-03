1 - Escreva um script que use o comando tr para substituir todos os números em um arquivo por caracteres ‘X’.

    > 1.sh
      chmod +x 1.sh
      vim 1.sh

      #!/bin/bash

      a=$1

      cat ${a} | tr '0123456789' 'X'
  
  
2 - Escreva um script que use o comando tr para remover linhas vazias de um arquivo, isto é, linhas que possuem apenas o enter (\n).
  
      > 2.sh
        chmod +x 2.sh
        vim 2.sh

        #!/bin/bash

        a=$1

        cat ${a} | tr -s '\n'
    

3 - Escreva um script que leia um endereço IP, separe os 4 octetos, e imprima-os em formato binário. Ex.:

Digite um endereço IP: 8.8.4.4

Octeto #1: 8 em binário 00001000
Octeto #2: 8 em binário 00001000
Octeto #3: 4 em binário 00000100
Octeto #4: 4 em binário 00000100

      > 3.sh
        chmod +x 3.sh
        vim 3.sh

        #!/bin/bash

        read -p "Digite um endereço IP: " a

        num1=$(echo ${a} | cut -d '.' -f 1)
        num2=$(echo ${a} | cut -d '.' -f 2)
        num3=$(echo ${a} | cut -d '.' -f 3)
        num4=$(echo ${a} | cut -d '.' -f 4)

        b=$(bc <<< "obase=2;${num1}")
        c=$(bc <<< "obase=2;${num2}")
        d=$(bc <<< "obase=2;${num3}")
        e=$(bc <<< "obase=2;${num4}")

        echo "Octeto #1: ${num1} em binário: ${b}"
        echo "Octeto #2: ${num2} em binário: ${c}"
        echo "Octeto #3: ${num3} em binário: ${d}"
        echo "Octeto #4: ${num4} em binário: ${e}"



*** Todas as soluções daqui em diante devem usar o comando grep com expressões regulares.


4 - Escreva um script que, exiba uma frase criativa e especial e, baseado em opções passadas por argumentos de linha de comando:

a - Liste apenas os diretórios de uma pasta
b - Liste apenas os arquivos executáveis
c - Liste apenas os links simbólicos

Exemplo: lista.sh -a # lista apenas os diretórios

5 - Escreva um script que valide as seguintes regras para criação de uma senha: pelo menos 6 caracteres, uma letra maiúscula e um número. Validar significa receber uma senha e dizer se esta obedece ao padrão ou não (se possível a senha não deve ser exibida enquanto o usuário digita).



