
# Desafio Terraform - AWS

# 1. Descrição Técnica

# Arquivo Original:
O arquivo fornecido `main.tf` cria os seguintes recursos na AWS:

- **VPC**: Uma VPC com suporte a DNS e nomes de host habilitados.
- **Sub-rede**: Uma sub-rede dentro da VPC com um bloco CIDR específico e vinculada à zona de disponibilidade us-east-1a.
- **Internet Gateway**: Um gateway de internet associado à VPC permitindo o tráfego de entrada e saída.
- **Chave SSH (Par de Chaves)**: Um par de chaves SSH gerado para permitir a conexão às instâncias EC2.
- **Instância EC2**: Uma instância EC2 poderia ser adicionada ao código, mas não foi configurada no arquivo inicial.

# Modificações e Melhorias:

# 1. Segurança:
  - Foi adicionado um security group para controlar o tráfego de entrada e saída:
  - Porta 22 (SSH) e porta 80 (HTTP) abertas para qualquer endereço IP.
  - Regras de saída irrestritas, permitindo assim o tráfego de saída em qualquer porta.

# 2. Automação da Instalação do Nginx:
- A instância EC2 foi configurada com um script de `user_data` que faz as seguintes modificações: 
  - Atualização dos pacotes.
  - Instalação do Nginx.
  - Início automático e habilitação do Nginx para rodar no boot.

# 2. Instruções de Uso

# Pré-requisitos:
- Terraform instalado.
- Conta AWS configurada com credenciais válidas.
- Permissões adequadas na AWS para criar os recursos (VPC, Subnet, EC2, Security Groups, etc.).

# Passos:

1. **Inicializar o Terraform**:
   ```bash
   terraform init
   ```

2. **Visualizar o que será criado**:
   ```bash
   terraform plan
   ```

3. **Aplicar a configuração**:
   ```bash
   terraform apply
   ```
   - Confirme com `yes` quando o Terraform solicitar.

4. **Destruir os recursos criados**:
   Caso deseje remover os recursos criados após o uso, execute:
   ```bash
   terraform destroy
   ```

# Arquivo Modificado
O arquivo `main.tf` modificado está no github, link a seguir: 

