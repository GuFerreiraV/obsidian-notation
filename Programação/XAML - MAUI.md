### ContentPage
- É uma tag que exibe apenas uma única exibição (view). Essa única visualização é um layout, como Grid ou StackLayout.
- ContentPage pode ser modelado com um modelo de controle.
![[pages.png]]
```csharp
	<ContentPage 
		xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="MyMauiApp.MyPage" 
             Title="MyPage" // Título da page no app
             BackgroundColor="White"> // Cor de fundo da page
             
		// Filho de um ContentPage -> Layout
		<StackLayout>
		    <Label Text="Welcome to .NET MAUI!"
	            VerticalOptions="Center"
	            HorizontalOptions="Center" />
	    </StackLayout>
	</ContentPage>
```








### ToolbarItem
- É um conceito fundamental na UI de apps, utilizado para exibir ações ou botões na barra de ferramentas de uma página. 
- É um botão que é exibido no app, então, quando à um evento `Clicked` e o mesmo é acionado, ele funciona semelhante a um botão normal.

- Principais propriedades:
	- **Text:** define o texto exibido no botão.
	- **IconImageSource:** Define o ícone a ser exibido no botão.
	- **Clicked**: Evento que é disparado quando o `ToolbarItem` é pressionado.
- Uso no XAML
	- O `ToolbarItem` é declarado dentro da tag `<ContentPage.ToolbarItems>`
		- Exemplo: 
		```csharp
	<ContentPage.ToolbarItems>
		<ToolbarItem Text="Salva Item" Clicked="ToolbarItem_Clicked" />
    </ContentPage.ToolbarItems>
    ```

### VerticalStackLayout
- É um controle de layout projetado para organizar elementos de interface do usuário.
- Sua finalidade principal é organizar suas exibições filhas em uma pilha unidimensional vertical.
- É uma tag alternativa mais eficiente ao `StackLayout` para empilhamento vertical e é comumente usado para organizar uma subseção da interface do usuário em uma page.

- Propriedades principais:
	- **Spacing:** Indica a quantidade de espaço entre cada exibição filha. O valor padrão dessa propriedade é 0.
	- **Padding**: Cria espaço interno em torno do conteúdo de um elemento, separando-o da borda do próprio elemento.
	```csharp
<VerticalStackLayout Spacing="10" Padding="10">
    <Label Text="Descrição do produto: "/>
	      <Entry x:Name="txt_descricao"/>
    <Label Text="Qtde: " />
	     <Entry x:Name="txt_quantidade" Keyboard="Numeric"/>
    <Label Text="Preço: "/>
	    <Entry x:Name="txt_preco" Keyboard="Numeric"/>
</VerticalStackLayout>
```
![[Pasted image 20250718170419.png]]

### Frame
> Frame está obsoleto a partir do .NET 9
- O **Frame** é um ==controle de UI== que serve principalmente para encapsular uma exibição ou um layout com uma borda que pode ser configurada com cores, sombras e entre outras opções.
- Ele atua como um invólucro visual, permitindo agrupar e estilizar partes da sua interface de usuário. Como se fosse uma ==moldura para fotos==.
```csharp
<Frame BorderColor="Gray" // cor da borda
       CornerRadius="5" // Propriedade que arredonda as bordas
       Padding="8"
       >
    <StackLayout>
        <Label Text="Card"
               FontAttributes="Bold" // deixa em negrito
               FontSize="14"/>
        <BoxView HeightRequest="2" 
                 BackgroundColor="Gray" 
                 HorizontalOptions="Fill"/> // esse BoxView cria uma linha separadora
        <Label Text="Isso é um teste "/>
    </StackLayout>
</Frame>
```
![[Pasted image 20250723131825.png]]
### ListView

