function exercicio1() {
    let numero;
    do {
        numero = Number(prompt("Digite um número positivo:"));
    } while (numero < 0);

    alert("Número válido: " + numero);
}

function exercicio2() {
    let soma = 0;
    let contador = 0;
    let nota;

    while (true) {
        nota = Number(prompt("Digite uma nota (negativo para sair):"));

        if (nota < 0) break;

        soma += nota;
        contador++;
    }

    if (contador > 0) {
        alert("Média: " + (soma / contador));
    } else {
        alert("Nenhuma nota válida foi inserida.");
    }
}

function exercicio3() {
    let total = 0;
    let valor;

    do {
        valor = Number(prompt("Digite o valor da compra (0 para finalizar):"));
        total += valor;
    } while (valor !== 0);

    alert("Total da compra: R$ " + total);
}

function exercicio4() {
    let nome = "";
    let sobrenome = "";

    while (nome.trim() === "") {
        nome = prompt("Digite seu primeiro nome:");
    }

    while (sobrenome.trim() === "") {
        sobrenome = prompt("Digite seu sobrenome:");
    }

    alert("Nome completo: " + nome + " " + sobrenome);
}

function exercicio5() {
    let saldo = 1000;
    let saque;

    while (saldo > 0) {
        alert("Saldo atual: R$ " + saldo);
        saque = Number(prompt("Digite o valor para saque:"));

        if (saque > saldo) {
            alert("Saldo insuficiente. Tente novamente.");
        } else {
            saldo -= saque;
            alert("Saque realizado!");
        }

        if (saldo <= 0) {
            alert("Saldo zerado ou negativo. Encerrando...");
            break;
        }
    }
}

// MENU PRINCIPAL
while (true) {
    let opcao = Number(prompt(
        "===== MENU =====\n" +
        "1 - Número positivo\n" +
        "2 - Média de notas\n" +
        "3 - Total de compras\n" +
        "4 - Nome completo\n" +
        "5 - Saque bancário\n" +
        "0 - Sair"
    ));

    switch (opcao) {
        case 1:
            exercicio1();
            break;
        case 2:
            exercicio2();
            break;
        case 3:
            exercicio3();
            break;
        case 4:
            exercicio4();
            break;
        case 5:
            exercicio5();
            break;
        case 0:
            alert("Encerrando...");
            throw new Error("Programa encerrado");
        default:
            alert("Opção inválida!");
    }
}
