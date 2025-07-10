- A pilha é uma das estruturas de dados e trabalha com o formato LIFO (Last In First Out). Isso quer dizer que, o primeiro elemento a ser inserido na pilha, normalmente é o último que sai dela, e, o último que é inserido, é o primeiro a sair.
- Exemplo, uma pilha de livros:  
	![[Pasted image 20250710114549.png]]
- Sendo assim, a pilha permite acesso a apenas um item de dados, o último que foi inserido. Para remover o penúltimo, é necessário remover o último.
- Pilha é considerada uma estrutura de dados simples, sendo fácil de implementar.

## Implementação
```java
	public class Main
{
    public Object[] stack;
	public int posStack;
    
    public Main()
    {
        this.posStack = -1;
        this.stack = new Object[10];    
    }
    
    public boolean EmptyStack()
    {
        if(this.posStack == -1) return true;        
        return false;
    }
    
    public int Length() {
        if(this.EmptyStack()) 
        {
            return 0;
        }
        return this.posStack + 1;
    } 
    
    public void empilhar(Object value)
    {
        if (this.posStack < this.stack.length - 1) 
	        this.stack[++posStack] = value; 
    }

    public Object desempilhar()
    {
        if(EmptyStack()) 
        { 
            return null;
        } 
        return this.stack[this.posStack --];
    } 
    
	public static void main(String[] args) {
	    
	    Main s = new Main();
	    s.empilhar("Portuguesa");
	    s.empilhar("Frango com catupiry ");
        s.empilhar("Calabresa ");
        s.empilhar("Quatro queijos ");
        s.empilhar(10);
                while (s.EmptyStack() == false) {
            System.out.println(s.desempilhar());
        }   
	}
}

```

---
## Observações
- No Java, já existe uma classe que faz a implementação de uma pilha, chama-se **Stack**
- *java.util.Stack*
```java
	import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<String> minhaPilha = new Stack<>();

        minhaPilha.push("Primeiro");
        minhaPilha.push("Segundo");
        minhaPilha.push("Terceiro");

        System.out.println("Pilha: " + minhaPilha); 

        String topo = minhaPilha.peek();
        System.out.println("Elemento no topo: " + topo); /

        String removido = minhaPilha.pop();
        
        System.out.println("Elemento removido: " + removido); 
        System.out.println("Pilha após pop: " + minhaPilha); 

        System.out.println("A pilha está vazia? " + minhaPilha.empty()); 
    }
}
```