# Ativfidade-01---Pilhas-e-Fila

Editor de Texto:
A melhor opção aqui é usar uma pilha. Quando você aperta "Desfazer" (Ctrl+Z), quer voltar nas ações na ordem que fez, e a pilha faz isso de boa. A última coisa que você fez é a primeira a sair


Exames no Hospital:
Aqui também rola uma pilha. Os exames ficam lá registrados e você precisa imprimir do último pro primeiro, a pilha resolve essa, porque é só puxar do topo. Quanto a como armazenar, se tiver uma ideia de quantos exames vão rolar, usa um array porque é rápido. Mas se não sabe, a lista encadeada é mais flexível e se adapta melhor.


Controle de Tarefas:
fila pra tarefas normais e pilha pra aquelas que são prioridades. As tarefas que chegam vão na fila na ordem que aparecem, mas as prioridades pulam pra pilha e saem primeiro. Assim, você garante que o que é mais urgente sai antes.

Classe Pilha:
package c1;
public class Pilha {
    private final int[] elementos;
    private int topo;
    private final int capacidade;

    public Pilha(int capacidade){
        this.capacidade = capacidade;
        this.elementos = new
        int [capacidade];
        this.topo = -1;
    }
    public void push(int valor){
        if (topo == capacidade - 1) {
            System.out.println("A pilha está cheia! Não é possível adicionar o valor" + valor);
        }else {
            elementos[++topo] = valor;
        }
    }
    public int pop() {
        if (isEmpty()) {
            System.out.println("A pilha está vazia! Não é possível remover");
            return -1;
        }
        return elementos[topo--];
    }
    public int peek() {
        if (isEmpty()) {
            System.out.println("Pilha vazia!");
            return -1;
        }
        return elementos[topo];
    }
    public boolean isEmpty() {
        return topo == -1;
    }
 public static void main(String[] args) {
    Pilha pilha = new Pilha(5);
    pilha.push(10);
    pilha.push(20);
    pilha.push(30);

    System.out.println("Elemento no topo:" + pilha.peek());

    System.out.println("Removendo elementos da pilha:");
    while (!pilha.isEmpty()) {
        System.out.println("Removido:" + pilha.pop());
    }
 }
    
}

Classe FIla:
package c1;


    public class Fila {
    private final int[] dados;
    private int inicio;
    private int fim;
    private int tamanho;
    private final int capacidade;

    public Fila(int capacidade) {
        this.capacidade = capacidade;
        this.dados = new int[capacidade];
        this.inicio = 0;
        this.fim = -1;
        this.tamanho = 0;
    }

    public void enqueue(int valor) {
        if (tamanho == capacidade) {
            System.out.println("A fila está cheia!");
        } else {
            fim = (fim + 1) % capacidade;
            dados[fim] = valor;
            tamanho++;
        }
    }

    public int dequeue() {
        if (isEmpty()) {
            System.out.println("A fila está vazia!");
            return -1;
        } else {
            int valor = dados[inicio];
            inicio = (inicio + 1) % capacidade;
            tamanho--;
            return valor;
        }
    }

    public int peek() {
        if (isEmpty()) {
            System.out.println("A fila está vazia!");
            return -1;
        } else {
            return dados[inicio];
        }
    }

    public boolean isEmpty() {
        return tamanho == 0;
    }

    public static void main(String[] args) {
        Fila fila = new Fila(5);
        fila.enqueue(10);
        fila.enqueue(20);
        fila.enqueue(30);
        System.out.println("Primeiro da fila: " + fila.peek());
        System.out.println("Removendo os elementos:");
        while (!fila.isEmpty()) {
            System.out.println(fila.dequeue());
        }
    }
}



