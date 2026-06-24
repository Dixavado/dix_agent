# WPF Project Types Guide (Visual Studio 2026)

> Guia completo para escolher corretamente os tipos de projetos WPF em aplicações modernas usando C#, .NET 10, MVVM e arquitetura modular.

---

# Índice

- O que é WPF
- Tipos de Projetos WPF
- Quando usar cada projeto
- Comparativo rápido
- Arquitetura recomendada
- Estrutura profissional de Solution
- MVVM e Navegação
- Boas práticas 2026
- O que evitar
- Conclusão

---

# O que é WPF

**WPF (Windows Presentation Foundation)** é o framework desktop da Microsoft para criação de aplicações Windows modernas utilizando:

- XAML
- Data Binding
- MVVM
- Templates
- Styles
- Animações
- Renderização acelerada por hardware
- Controles personalizados

Atualmente o WPF continua sendo oficialmente suportado e evoluído sobre o ecossistema .NET moderno.

---

# Tipos de Projetos WPF

## 1. WPF App (.NET)

### O que é

Projeto principal executável.

Gera:

```text
MeuSistema.exe
```

### Quando usar

- ERP
- Dashboard
- Ferramentas internas
- Automação
- Launchers
- Sistemas corporativos
- Utilitários desktop

### Vantagens

- Projeto principal da aplicação
- Suporte completo ao WPF
- MVVM
- Dependency Injection
- Navegação dinâmica
- Single-file publish

### Recomendação

✅ Escolha padrão para novos projetos.

---

## 2. WPF Class Library (.NET)

### O que é

Biblioteca WPF sem executável.

Gera:

```text
MinhaBiblioteca.dll
```

### Utilizado para

- Resource Dictionaries
- Styles
- Temas
- Janelas compartilhadas
- Helpers visuais
- Componentes reutilizáveis

### Quando usar

Quando vários projetos precisam compartilhar recursos visuais.

### Exemplo

```text
App.exe

Theme.dll
SharedUI.dll
```

### Recomendação

✅ Excelente para modularização.

---

## 3. WPF User Control Library (.NET)

### O que é

Biblioteca focada em UserControls.

### Estrutura típica

```text
DashboardView.xaml
LoginView.xaml
SettingsView.xaml
```

### Quando usar

- MVVM
- Navegação por Views
- Módulos independentes
- Componentes internos da aplicação

### Vantagens

- Desenvolvimento rápido
- Fácil manutenção
- XAML simples
- Excelente integração com MVVM

### Limitações

- Menos flexível para customização profunda
- Não é ideal para controles públicos altamente reutilizáveis

### Recomendação

✅ Melhor escolha para telas e módulos.

---

## 4. WPF Custom Control Library (.NET)

### O que é

Biblioteca especializada em controles profissionais.

### Exemplos

```text
ModernButton
ModernCard
ModernDataGrid
NavigationView
SidebarControl
```

### Quando usar

Quando deseja criar componentes reutilizáveis em diversos projetos.

### Vantagens

- Totalmente estilizável
- Suporte a Templates
- Dependency Properties
- Visual States
- Theming

### Complexidade

Alta.

### Recomendação

✅ Ideal para frameworks internos e bibliotecas de UI.

---

## 5. WPF Application (.NET Framework)

### O que é

Versão antiga baseada no .NET Framework 4.x.

### Quando usar

Somente:

- Sistemas legados
- Migrações graduais
- Compatibilidade empresarial

### Recomendação

⚠️ Evitar novos projetos.

---

## 6. WPF User Control Library (.NET Framework)

Versão legada do User Control Library.

### Uso

- Sistemas antigos
- Projetos .NET Framework

### Recomendação

⚠️ Apenas manutenção.

---

## 7. WPF Custom Control Library (.NET Framework)

Versão legada da biblioteca de controles.

### Uso

- Frameworks internos antigos
- Produtos corporativos legados

### Recomendação

⚠️ Apenas manutenção.

---

# Comparativo Rápido

| Projeto | Executável | XAML | Reutilização | Complexidade |
|-----------|-----------|-----------|-----------|-----------|
| WPF App | Sim | Sim | Baixa | Baixa |
| WPF Class Library | Não | Sim | Média | Baixa |
| User Control Library | Não | Sim | Alta | Média |
| Custom Control Library | Não | Sim | Muito Alta | Alta |
| .NET Framework | Sim/Não | Sim | Variável | Legado |

---

# Como Escolher

## Quero criar um programa

```text
Use:
WPF App (.NET)
```

---

## Quero criar telas reutilizáveis

```text
Use:
WPF User Control Library (.NET)
```

---

## Quero criar uma biblioteca visual

```text
Use:
WPF Class Library (.NET)
```

---

## Quero criar componentes profissionais

```text
Use:
WPF Custom Control Library (.NET)
```

---

# Arquitetura Recomendada 2026

```text
Solution

├── MyApp
│   └── WPF App (.NET)

├── MyApp.Core
│   └── Class Library

├── MyApp.Services
│   └── Class Library

├── MyApp.Infrastructure
│   └── Class Library

├── MyApp.UI
│   └── User Control Library

├── MyApp.Controls
│   └── Custom Control Library

└── MyApp.Themes
    └── WPF Class Library
```

---

# MVVM Moderno

Estrutura sugerida:

```text
Views
ViewModels
Models
Services
Commands
Themes
Controls
Resources
```

---

# Boas Práticas 2026

## Use

- .NET 10
- MVVM
- Dependency Injection
- CommunityToolkit.Mvvm
- Async/Await
- Resource Dictionaries
- Modularização

## Evite

- Code Behind excessivo
- Lógica dentro de Views
- Singletons globais desnecessários
- Misturar UI e regras de negócio

---

# Escolha Recomendada para Projetos Novos

```text
WPF App (.NET)
+
Class Library (.NET)
+
User Control Library (.NET)
```

Esta combinação oferece:

- Escalabilidade
- Organização
- Reutilização
- Facilidade de manutenção
- Compatibilidade com .NET moderno
- Excelente suporte para MVVM

---

# Resumo Final

| Objetivo | Projeto |
|-----------|-----------|
| Aplicação principal | WPF App (.NET) |
| Lógica compartilhada | Class Library |
| Telas reutilizáveis | User Control Library |
| Componentes profissionais | Custom Control Library |
| Sistemas antigos | .NET Framework |

---

## Referências Oficiais

- Microsoft Learn - WPF Overview
- Microsoft Learn - WPF Documentation
- Microsoft Learn - Desktop Development for .NET

