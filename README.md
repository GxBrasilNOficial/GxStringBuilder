# Genexus StringBuilder
External Object Genexus para utilização do System.Text.StringBuilder (.Net/NetCore) e (java.lang.StringBuilder)

## Instalação
Importar o arquivo StringBuilder.xpz_ na KB.
    Menu Knowledge Manager -> Import -> selecionar o arquivo _.xpz_

## Utilização
1) Declarar uma variável com _Data Type_ _StringBuilder_
2) Utilizar os métodos de incremento disponíveis: AppendString(&string), AppendDouble(&num18_6), AppendLine(&string), AppendInt(&num8), AppendLong(&num18)
3) Capturar o texto gerado com o método: ToString()

## Exemplo prático
```Genexus
// Procedure - Source
// ...

// Foreach / for / etc...
For &i = 0 to 999999
	// Adiciona texto sem adicionar nova linha.
	&Stringbuilder.AppendString("adiciona texto")
	&Stringbuilder.AppendString("adiciona texto2")
	// vai gerar uma string: "adiciona textoadiciona texto2"
	
	// Adiciona texto com o nweline() no final
	&Stringbuilder.AppendLine("adiciona texto")
	// Ou &Stringbuilder.AppendString("adiciona texto"+newline())

	&Stringbuilder.AppendLine("adiciona texto2")
	// Ou &Stringbuilder.AppendString("adiciona texto2"+newline())

	/* // Vai gerar a string:
		"adiciona texto
		adiciona texto2"
	*/
EndFor

// Define o caminho onde vai gerar o arquivo
&File.Source = !'C:\www\myapp\temp\meutxt.txt'

// Se o arquivo existir...
If &File.Exists()
    // Deletar
	&File.Delete()
EndIf

// Escrever no txt todo o conteúdo incrementado em &Stringbuilder
&File.WriteAllText(&Stringbuilder.ToString())

//...
```
[-- Ref. StringBuilder --](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder#StringAndSB)

## Meta
Gilmar J. A. Goulart – [@gilmargoulart](https://github.com/gilmargoulart)