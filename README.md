# Automação de processos

Neste projeto iremos automatizar uma tarefa, ou seja, algum processo rotineiro usando automação no computador para realizar atividades do dia a dia poupando tempo e mão de obra.<br>
(OBS: Todo o código fonte está bem comentado para facilitar o entendimento das soluções)

# Entendimento do negócio

Imagine que voçê é analista de dados de uma empresa que tem 25 filiais espalhadas em todo o Brasil, todos os dias voçê tem que enviar relatórios por e-mail (One Page) para cada gerente de loja e para a diretoria, esse relatório deve conter todo o resumo em uma página (por isso o nome One Page) informando os indicadores e enviando uma planilha com resumo diário de movimentações financeiras.<br>
Devemos também manter um backup diário com histórico de vendas de todas as lojas organizados por dia.

### Indicadores OnePage

- Faturamento;
- Diversidade de produtos (quantos produtos diferentes foram vendidos naquele período);
- Ticket médio por venda.
 
### Metas

- Faturamento por dia = 1000;
- Faturamento por ano = 1650000;
- Quantidade de vendas de produtos por dia = 4;
- Quantidade de vendas de produtos por ano = 120;
- Ticket médio por dia = 500;
- Ticket médio por ano = 500.


# Configurações importantes do projeto

### Configurando email outlook
Os emails deste projeto serão enviados via "outlook" abaixo a configuração para envio:

    import win32com.client as win32
    outlook = win32.Dispatch('outlook.application')

    mail = outlook.CreateItem(0)
    mail.To = 'dev.daniel.amorim@gmail.com'
    # Com copia? (não obrigatório)
    mail.CC = 'email@gmail.com'
    # Com copia oculta? (não obrigatório)
    mail.BCC = 'email@gmail.com'
    mail.Subject = 'Email vindo do outlook'
    mail.Body = 'texto do email'
    # ou mail.HTML.Body = '<p>email em HTML</p>'

    # Anexos (pode ser quantos quiser):
    attachment = "caminho do arquivo"
    mail.Attachments.Add(attachment)
    # Envia o email
    mail.Send()
    
# Modelo em produção
Abaixo a imagem do modelo em produção de disparo de e-mails:<br>
- ENVIAR PARA LOJA: Ao digitar no input o nome da loja dispara e-mail somente para a loja específica;
- ENVIAR PARA TODAS AS LOJAS: Envia para todas as lojas cadastradas de uma vez;
- ENVIAR PARA DIRETORIA: Envia e-mails com resumo das lojas somente para diretoria.

#### Modelo em produção:
![Captura de tela_20230102_153601](https://user-images.githubusercontent.com/115194365/210268658-5b085dd6-61bc-4b22-aefd-8976c9f1fde8.png)


# E-mails enviados:
Segue abaixo os exemplos de e-mails enviados:<br>

#### E-mail para loja:
![Captura de tela_20230102_153006](https://user-images.githubusercontent.com/115194365/210268112-0c516ca7-4382-4580-959b-ea759320ee8e.png)

#### E-mail para diretoria:
![Captura de tela_20230102_152911](https://user-images.githubusercontent.com/115194365/210268164-b0583acc-01c6-4948-98bc-fda5e1333dda.png)

