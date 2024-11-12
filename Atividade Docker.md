## Passo a Passo: Configuração de Microsserviços com Docker em 3 Máquinas Virtuais
<br>
### Pré-requisitos
- Instale Docker em cada VM.<br>
- Configure a rede entre as VMs para que possam se comunicar (usando IPs estáticos ou DNS interno).<br>
<br>
### Passo 1: Configurar a VM do Banco de Dados (MariaDB ou MySQL)<br>
- Subir o container do banco de dados.<br>
- Configurar as variáveis de ambiente com o usuário, senha e nome do banco de dados.<br>
- Testar a conexão para garantir que o banco está acessível a partir das outras VMs.<br>
<br>
### Passo 2: Configurar a VM do Aplicativo PHP (Back-end)<br>
- Criar um Dockerfile para o aplicativo PHP.<br>
- Configurar o código PHP para se conectar ao banco de dados usando as variáveis de ambiente.<br>
- Build e subir o container PHP.<br>
<br>
### Passo 3: Configurar a VM do Proxy (Nginx como Balanceador de Carga)<br>
- Criar um arquivo de configuração para o Nginx (nginx.conf) para o balanceamento de carga.<br>
- Subir o container do Nginx com o arquivo de configuração.<br>
- Testar o balanceador de carga acessando o endereço IP da VM proxy. Ele deve redirecionar para as VMs do aplicativo.<br>
<br>
### Passo 4: Testar o Ambiente<br>
- Acessar o IP do balanceador de carga (proxy) em um navegador ou usando curl.<br>
- Verificar o funcionamento do aplicativo PHP e a conexão com o banco de dados.<br>
- Testar o balanceamento atraves de simulações de requisioções pelo site loader.io.<br>
- Voce pode como o professor utilizar o nano para fazer a configuração e edição dos textos de código.<br>
<br>
### Observações:<br>
- Configure o firewall para permitir o tráfego entre as VMs e para a porta do proxy.<br>
- Use ferramentas como Docker Compose para orquestrar e simplificar o gerenciamento dos serviços.<br>
