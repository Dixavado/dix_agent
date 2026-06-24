# WPF Architecture Guide (.NET 8 / 9 / 10) — 2026

Guia completo e estruturado das principais arquiteturas modernas para WPF, com foco em escalabilidade, manutenção e padrões profissionais de desenvolvimento.

---

## 1. Visão Geral

O WPF não impõe uma arquitetura obrigatória além do MVVM. Em projetos modernos, a qualidade arquitetural depende da combinação de padrões como:

- MVVM como base obrigatória
- Separação por Features
- Injeção de Dependência (DI)
- Isolamento de domínio (Clean Architecture)
- Modularização para escala

Este guia consolida as principais abordagens utilizadas em sistemas reais em 2026.

---

## 2. Top 7 Estruturas para WPF (.NET)

### Ranking Geral

| Rank | Estrutura | Descrição | Relevância |
|------|-----------|-----------|------------|
| 🥇 1 | MVVM | Base arquitetural padrão do WPF | Obrigatória |
| 🥈 2 | Hybrid MVVM | MVVM + Services + DI + organização moderna | Muito Alta |
| 🥉 3 | Feature-Based Architecture | Organização por funcionalidades | Muito Alta |
| 4 | Clean Architecture | Separação total entre domínio e UI | Alta |
| 5 | MVVM Modular | MVVM dividido em módulos independentes | Alta |
| 6 | Prism Architecture | Framework completo com módulos e navegação | Média/Alta |
| 7 | DDD + MVVM | Modelagem focada em domínio complexo | Média |

---

## 3. Comparação Prática

| Estrutura | Quando Usar | Cenários | Vantagens | Desvantagens |
|-----------|-------------|----------|------------|---------------|
| MVVM | Pequenos/médios projetos | Tools, dashboards | Simples e padrão | Escala mal sozinho |
| Hybrid MVVM | Projetos profissionais | Sistemas comerciais | Escalável e moderno | Mais estrutura |
| Feature-Based | Sistemas grandes | ERP, CRM | Organização excelente | Planejamento necessário |
| Clean Architecture | Longo prazo | Sistemas empresariais | Baixo acoplamento | Complexidade alta |
| MVVM Modular | Grandes sistemas | Apps corporativos | Módulos independentes | Estrutura complexa |
| Prism | Enterprise | Grandes soluções | DI + navegação pronta | Curva de aprendizado |
| DDD + MVVM | Domínio complexo | Financeiro, logística | Modelagem forte | Muito complexo |

---

## 4. Quando Usar Cada Estrutura

| Tipo de Projeto | Recomendação |
|-----------------|-------------|
| Pequeno | MVVM |
| Médio | Hybrid MVVM |
| Grande | Hybrid MVVM + Feature-Based + Clean Architecture |
| Enterprise | Prism + Clean Architecture |
| Domínio complexo | DDD + MVVM |

---

## 5. Explicação das Arquiteturas

### 5.1 MVVM (Base WPF)

Arquitetura fundamental do WPF baseada em separação de responsabilidades.

**Uso:**
- Bindings
- Commands
- ViewModels simples

**Cenários:**
- Ferramentas simples
- Aplicações iniciais

---

### 5.2 Hybrid MVVM

Extensão moderna do MVVM.

**Inclui:**
- Services layer
- Dependency Injection
- Navigation service
- Base ViewModel estruturado

**Cenários:**
- Aplicações profissionais
- Sistemas escaláveis

---

### 5.3 Feature-Based Architecture

Organização baseada em funcionalidades.

**Estrutura típica:**
- Features/Auth
- Features/Dashboard
- Features/Settings

**Vantagem:**
- Escalabilidade horizontal

---

### 5.4 Clean Architecture

Separação em camadas independentes.

**Camadas:**
- Domain
- Application
- Infrastructure
- Presentation

**Benefícios:**
- Testabilidade
- Baixo acoplamento
- Independência de UI

---

### 5.5 MVVM Modular

Arquitetura baseada em módulos independentes.

**Uso:**
- Sistemas extensíveis
- Plugins internos

---

### 5.6 Prism Architecture

Framework completo para WPF.

**Recursos:**
- Dependency Injection
- Region navigation
- Event Aggregator
- Module system

---

### 5.7 DDD + MVVM

Modelagem baseada em domínio.

**Uso:**
- Sistemas financeiros
- ERP avançado
- Logística complexa

---

## 6. Templates de Estrutura

### 6.1 MVVM Simples

```
App/
 ├── Models/
 ├── Views/
 ├── ViewModels/
 ├── Services/
 ├── Helpers/
 └── App.xaml
```

---

### 6.2 Hybrid MVVM

```
App/
 ├── Core/
 │   ├── DI/
 │   ├── Navigation/
 │   ├── Base/
 │   └── Services/
 ├── Features/
 ├── Models/
 ├── Views/
 ├── ViewModels/
 └── App.xaml
```

---

### 6.3 Feature-Based

```
App/
 ├── Features/
 │   ├── Auth/
 │   ├── Dashboard/
 │   └── Settings/
 ├── Core/
 └── App.xaml
```

---

### 6.4 Clean Architecture

```
Solution/
 ├── Domain/
 ├── Application/
 ├── Infrastructure/
 └── Presentation/
     ├── Views/
     ├── ViewModels/
     └── Core/
```

---

### 6.5 MVVM Modular

```
App/
 ├── Modules/
 │   ├── AuthModule/
 │   ├── DashboardModule/
 │   └── SettingsModule/
 ├── Shell/
 └── Core/
```

---

### 6.6 Prism Architecture

```
App/
 ├── Modules/
 ├── Views/
 ├── ViewModels/
 ├── Services/
 ├── Regions/
 ├── Bootstrapper/
 └── Core/
```

---

### 6.7 DDD + MVVM

```
Solution/
 ├── Domain/
 ├── Application/
 ├── Infrastructure/
 ├── Presentation/
 └── Shared/
```

---

## 7. Recomendação Atual (2026)

A abordagem mais utilizada em projetos modernos WPF:

**Hybrid MVVM + Feature-Based Architecture + Dependency Injection**

Motivos:
- Escalabilidade consistente
- Organização clara
- Baixo acoplamento
- Flexível para projetos pequenos e grandes
