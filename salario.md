# salario
class Funcionario {
  double salarioBase;
  double horasExtras;
  double horasFaltas;

  Funcionario(this.salarioBase, this.horasExtras, this.horasFaltas);

  // Calcula o valor da hora normal
  double get valorHora => salarioBase / (30 * 8);

  // Calcula o valor da hora extra (50% a mais)
  double get valorHoraExtra => valorHora * 1.5;

  // Total recebido por horas extras
  double get totalHorasExtras => horasExtras * valorHoraExtra;

  // Total descontado por faltas
  double get totalHorasFaltas => horasFaltas * valorHora;

  // Salário final
  double get salarioFinal => salarioBase + totalHorasExtras - totalHorasFaltas;
}

void main() {
  // Definir valores diretamente (DartPad não permite entrada pelo console)
  double salario = 3000.0; // Exemplo: salário base de R$ 3000,00
  double horasExtras = 10.0; // Exemplo: 10 horas extras
  double horasFaltas = 5.0; // Exemplo: 5 horas faltadas

  // Criando o objeto
  var funcionario = Funcionario(salario, horasExtras, horasFaltas);

  // Exibindo resultados
  print("\n--- Resumo do Salário ---");
  print("Salário Base: R\$ ${funcionario.salarioBase.toStringAsFixed(2)}");
  print("Valor da Hora: R\$ ${funcionario.valorHora.toStringAsFixed(2)}");
  print("Valor da Hora Extra: R\$ ${funcionario.valorHoraExtra.toStringAsFixed(2)}");
  print("Total Recebido por Horas Extras: R\$ ${funcionario.totalHorasExtras.toStringAsFixed(2)}");
  print("Total Descontado por Faltas: R\$ ${funcionario.totalHorasFaltas.toStringAsFixed(2)}");
  print("Salário Final: R\$ ${funcionario.salarioFinal.toStringAsFixed(2)}");
}
