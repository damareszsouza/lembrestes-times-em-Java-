# lembrestes-times-em-Java-


Para criar lembretes em Java, você pode usar a classe `Timer` e a classe `TimerTask`. A classe `Timer` permite agendar tarefas para serem executadas em um momento específico no futuro. A classe `TimerTask` é uma classe abstrata que representa uma tarefa a ser executada pelo `Timer`.

Aqui está um exemplo simples de como criar um lembrete em Java:

```java
import java.util.Timer;
import java.util.TimerTask;

public class Lembrete extends TimerTask {
    private String mensagem;

    public Lembrete(String mensagem) {
        this.mensagem = mensagem;
    }

    public void run() {
        System.out.println(mensagem);
    }

    public static void main(String[] args) {
        // Cria um novo Timer
        Timer timer = new Timer();

        // Define a mensagem do lembrete
        String mensagem = "Reunião com o Dr. Silva";

        // Define a data e hora do lembrete
        long delay = 1000 * 60 * 60 * 24; // 24 horas
        long agora = System.currentTimeMillis();
        long dataHoraLembrete = agora + delay;

        // Agenda o lembrete para a data e hora especificadas
        timer.schedule(new Lembrete(mensagem), new Date(dataHoraLembrete));
    }
}
```

Neste exemplo, estamos criando uma classe chamada `Lembrete` que estende a classe `TimerTask`. Estamos definindo um construtor para a classe que recebe uma mensagem como parâmetro. Em seguida, estamos implementando o método `run`, que exibe a mensagem do lembrete.

Em seguida, estamos criando um novo objeto `Timer`. Estamos definindo a mensagem do lembrete como uma string e definindo a data e hora do lembrete usando o método `System.currentTimeMillis()` e adicionando um intervalo de tempo especificado em milissegundos.

Finalmente, estamos agendando o lembrete para a data e hora especificadas usando o método `schedule` do objeto `Timer`.

