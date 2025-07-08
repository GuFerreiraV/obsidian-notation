- **Uma das maneiras de inverter uma cadeia de caracteres (string) em C# é usando o método *Reverse()*.** Porém, não é a única maneira de fazer a inversão de um string.
- Supondo que temos uma cadeia de caracteres como essa abaixo: 
	```csharp
		string s = "100*b/y";
```
- Caso usássemos o método Reverse() para inverter essa string, o resultado seria este:
```csharp
	return string.Join(" ", s.Split(' ').Select(word => new string(word.Reverse().ToArray())));
	// output: y/b*001
```
- Não é o resultado esperado, já que ocorre uma inversão na ordem dos elementos mas também muda a integridade de cada elemento, e isso não é bom em alguns casos (100 virou 001 após a inversão).
---
- Para que ocorra a inversão de forma correta, mantendo a integridade dos elementos, usaremos a tokenização. 
- ==Tokenizar== significa quebrar a string em "==pedaços==" (chamados tokens), que podem ser números, operadores ou variáveis. 
- Com a abordagem a seguir, garantimos que os valores permaneçam intactos enquanto a ordem de seus elementos é invertida.
```csharp

	public static string ReverseExpression(string eq)
	{
	// padrão de regex para encontrar os valores
	string pattern = @"(\d+)|([a-zA-Z])|([*/+-])";

	// Encontra todas as correspondências no eq original
	MatchCollection matches = Regex.Matches(eq, pattern);
	
	// Lista para armaneza os tokens
	List<string> tokens = new List<string>();

	// Adiciona cada token à lista
	foreach(Match match in matches)
	{
		tokens.Add(match.Value);
	}
	
	// Inverte a ordem dos tokens na lista
	tokens.Reverse();
	
	// volta em uma string
	return string.Join("",tokens);
	}
	
```
