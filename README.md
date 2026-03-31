# 🛡️ SistemaRobusto: Prevenção de Erros (Lista 04)

Este repositório apresenta o projeto **SistemaRobusto**, desenvolvido em **C# (.NET)**. O foco central desta atividade foi a aplicação prática da **5ª Heurística de Nielsen: Prevenção de Erros**, utilizando o tratamento de exceções para criar uma interface de terminal resiliente e amigável.

---

## 🚀 O Desafio: "Sistema Inquebrável"

O objetivo desta missão foi abandonar o comportamento padrão de falha catastrófica dos softwares. Em vez de permitir que o programa feche abruptamente ao receber um dado inválido, implementamos uma camada de proteção que orienta o usuário sobre como proceder.

### Etapas de Desenvolvimento:
1. **Preparação Técnica:** Navegação via terminal até a pasta `LabDotnet`.
2. **Scaffolding:** Criação do projeto console com o comando `dotnet new console -n SistemaRobusto`.
3. **Refatoração de UX:** Implementação do bloco `try-catch-finally` para gerenciar a entrada de dados.
4. **Feedback Visual:** Uso de `ConsoleColor` para reforçar a semântica das mensagens de erro e sucesso.

---

## 🛠️ Tecnologias e Conceitos de IHC

* **Bloco try-catch:** Utilizado para cercar o comando `int.Parse()`, que é o ponto crítico onde o sistema poderia falhar caso recebesse texto em vez de números.
* **Heurística de Nielsen (Prevenção de Erros):** O sistema antecipa a falha do usuário e fornece uma "saída de emergência" com instruções claras de correção.
* **Bloco finally:** Garante que, independentemente do resultado da operação, o sistema limpe o estado e informe ao usuário o encerramento da tentativa.

---

## 💻 Estrutura Lógica (Program.cs)

O código foi estruturado para proteger a conversão de tipos de dados:

```csharp
try {
    // Tentativa de conversão de string para inteiro
    int idade = int.Parse(entrada);
    Console.WriteLine("✅ Acesso liberado!");
}
catch (FormatException) {
    // Feedback amigável em vez de erro técnico
    Console.WriteLine("\n[ERRO DE UX]: Você digitou letras em um campo numérico!");
}
```

---

## 📸 Evidências de Execução ("A Prova do Crime")

Abaixo estão os registros que comprovam a robustez do sistema em ambos os cenários:

### 1. Caminho Feliz (Sucesso)
Demonstra o sistema funcionando perfeitamente quando uma idade numérica é inserida:
<img src="./Captura de tela 2026-03-31 134126.png" alt="Caminho Feliz - Sucesso" width="100%">

### 2. Caminho do Erro (Prevenção)
Demonstra o sistema capturando a entrada inválida ("vinte") e exibindo a mensagem de erro amigável programada:
<img src="./Captura de tela 2026-03-31 134141.png" alt="Caminho do Erro - Captura de Exceção" width="100%">

---
**Desenvolvido por Lucas Nery Miranda**
*Estudante de Ciência da Computação - UNA Contagem*
