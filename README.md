# ☁️ **Stack com AWS CloudFormation**

## 🧾 Descrição  
Repositório criado para estudo e compreensão dos **conceitos sobre Stack com AWS CloudFormation**, um dos serviços fundamentais da **AWS Cloud** que permite automatizar a criação, modificação e exclusão de recursos de infraestrutura de forma **declarativa e organizada**.  

---

## 🧠 **Conceito**
O **AWS CloudFormation** é um serviço que permite **modelar e provisionar** recursos de infraestrutura da AWS utilizando **templates** em **YAML** ou **JSON**.  
Com ele, é possível criar **pilhas (stacks)** — que são **conjuntos de recursos AWS** (como EC2, S3, RDS, IAM, entre outros) — de maneira **padronizada, segura e reprodutível**.  

💡 **Em resumo:**  
> Você descreve sua infraestrutura como código (IaC - *Infrastructure as Code*), e o CloudFormation faz o trabalho de criar e gerenciar tudo para você.

---

## ⚙️ **Como Funciona**

1. 🧩 **Template:** Defina os recursos em um arquivo `.yaml` ou `.json`.  
2. 🚀 **Deploy da Stack:** Faça o upload do template via **Console**, **CLI** ou **API**.  
3. 🏗️ **Criação de Recursos:** O CloudFormation lê o template e cria todos os recursos na ordem correta.  
4. 🔄 **Atualização e Exclusão:** É possível atualizar ou excluir toda a stack com poucos cliques, mantendo rastreabilidade e consistência.

---

## 🧱 **Componentes Principais**

| Componente | Descrição |
|-------------|------------|
| **Template** | Arquivo que define os recursos e suas configurações. |
| **Stack** | Conjunto de recursos criados e gerenciados como uma única unidade. |
| **Change Set** | Prévia das alterações antes de aplicar uma atualização em uma stack. |
| **Resources** | Recursos da AWS definidos no template (EC2, S3, RDS, etc.). |
| **Outputs** | Informações de saída geradas após a criação da stack (ex: endpoints, IDs). |

---

## 💡 **Casos de Uso**
✅ Criação automatizada de ambientes de **desenvolvimento, teste e produção**.  
✅ Implementação de **infraestrutura como código (IaC)**.  
✅ **Gerenciamento de dependências** entre recursos (ex: VPC → Subnet → EC2).  
✅ **Recuperação rápida de ambientes** em caso de falhas.  
✅ **Padronização e auditoria** em projetos de grande escala.  

---

## 🌍 **Importância na Nuvem AWS**

O **AWS CloudFormation** é essencial em projetos **Cloud Native** e **DevOps**, pois:
- Automatiza e documenta a infraestrutura.
- Reduz erros humanos em configurações manuais.
- Facilita a escalabilidade e a replicação de ambientes.
- Integra-se com outros serviços AWS como **CodePipeline**, **Step Functions**, **Lambda** e **CloudWatch**.

---

## 🖼️ **Exemplo de Arquitetura CloudFormation**
<img src="/Images/Diagrama Cloud Formation.png">

---

## 📘 **Exemplo de Template (YAML)**

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Exemplo simples de Stack para criação de uma instância EC2

Resources:
  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: ami-0abcdef1234567890
      InstanceType: t2.micro
      Tags:
        - Key: Name
          Value: "Exemplo-EC2-CloudFormation"
