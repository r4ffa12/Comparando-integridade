# Comparando-integridade

Clique no botão superior esquerdo “Aplicativos” --> “Acessórios” --> “Editor de Texto” para abrir o Mousepad e insira o seguinte texto:

Copy
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam eget ligula eu lectus lobortis condimentum. Aliquam nonummy auctor massa. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla at risus. Quisque purus magna, auctor et, sagittis ac, posuere eu, lectus. Nam mattis, felis ut adipiscing.
Salve o texto na pasta “Arquivo --> Salvar como --> Documentos” com o nome “Texto.txt”. Feche o Mousepad.

Abra o Terminal e execute o seguinte comando (com senha “rnpesr”) para ser super usuário:

Copy
┌──(kali㉿kali)-[~]
└─$ sudo -i
[sudo] senha para aluno:
Volte ao Terminal e navegue até a pasta “Documentos” e veja que o arquivo “Texto.txt” está presente com o seguinte comando:

Copy
┌──(root㉿kali)-[~]
└─# cd /home/aluno/Documentos/
                                                                             
┌──(root㉿kali)-[/home/kali/Documentos]
└─# ls
Texto.txt
Copie o arquivo “Texto.txt” no arquivo “Texto_copia.txt” na mesma pasta e veja que realmente foi copiado:

Copy
┌──(root㉿kali)-[/home/aluno/Documentos]
└─# cp Texto.txt Texto_copia.txt
                                                                             
┌──(root㉿kali)-[/home aluno/Documentos]
└─# ls
Texto_copia.txt  Texto.txt
Verifique se há diferença entre os arquivos:

Copy
┌──(root㉿kali)-[/home/kali/Documentos]
└─# diff Texto.txt Texto_copia.txt
Veja que o comando mostrado acima não tem retorno, ou seja, não há diferença entre os arquivos.

Abra o arquivo “Texto_copia.txt”:

Copy
┌──(root㉿kali)-[/home kali/Documentos]
└─# nano Texto_copia.txt
Modifique a primeira letra “L” por “P”:

Copy
Porem ipsum dolor sit amet, consectetur adipiscing elit. Etiam eget ligula eu lectus lobortis condimentum. Aliquam nonummy auctor massa. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla at risus. Quisque purus magna, auctor et, sagittis ac, posuere eu, lectus. Nam mattis, felis ut adipiscing.
Salve o arquivo modificado com “Ctrl+X”, “S” e “Enter”

Agora, verificaremos a diferença entre os arquivos:

Copy
┌──(root㉿kali)-[/home/kali/Documentos]
└─# diff Texto.txt Texto_copia.txt
1c1
< Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam eget ligula eu lectus lobortis condimentum. Aliquam nonummy auctor massa. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla at risus. Quisque purus magna, auctor et, sagittis ac, posuere eu, lectus. Nam mattis, felis ut adipiscing.
\ Nenhum caractere de nova linha no final do arquivo
---
> Porem ipsum dolor sit amet, consectetur adipiscing elit. Etiam eget ligula eu lectus lobortis condimentum. Aliquam nonummy auctor massa. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla at risus. Quisque purus magna, auctor et, sagittis ac, posuere eu, lectus. Nam mattis, felis ut adipiscing.
A saída do comando mostrado acima é:

1c1: Indica que a diferença começa na linha 1 do arquivo original (Texto.txt).

<: Indica a linha no arquivo original (Texto.txt). Neste caso, a linha original começa com "Lorem ipsum dolor sit amet..."

---: Divide a linha original da linha modificada.

>: Indica a linha no arquivo modificado (Texto_copia.txt). Neste caso, a linha modificada começa com "Porem ipsum dolor sit amet..."

Portanto, a diferença encontrada está na primeira linha do arquivo, onde a palavra "Lorem" foi substituída por "Porem".
