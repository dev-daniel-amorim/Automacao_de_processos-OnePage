# Selenium - Automação de processos

- Neste projeto iremos realizar análise de dados e automação de processos para executar tarefas rotineiras.

# Entendimento do negócio

- Imagine que voçê é analista de dados de uma empresa que tem 25 filiais espalhadas em todo o Brasil, todos os dias voçê tem que enviar relatórios por e-mail (One Page) para cada gerente de loja e para a diretoria, esse relatório deve conter todo o resumo em uma página (por isso o nome One Page) informando os indicadores e enviando uma planilha com resumo diário de movimentações financeiras.<br>
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
    
#### Dica interessante:
Um e-mail pode ser enviado em formato HTML, caso queira enviar uma tabela no corpo do e-mail, basta<br>
pra isso transformar a tabela em HTML da seguinte maneira:

    mail.HTMLBody = f'''
    Bom dia,
    Segue a tabela de pesquisa de preços!
    {tabela.to_html(index=False)} #index false exclui a coluna de index
    '''

    
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

# Desenvolvedor

| [<img src="https://user-images.githubusercontent.com/115194365/202005566-f6278b6c-4f75-416f-b01c-e79b8d04f02e.jpg" width=115><br><sub>Daniel de Souza Amorim</sub>](https://github.com/DaniellsamorimGit) |
| :---: | 

#### Mais sobre o autor: <br>
Graduado em Engenharia de computação;<br>
Pós-graduado em Petróleo e gás;<br>
Desenvolvedor de dispositivos embarcados, C++, Python;<br>
Tecnologias Django, Flask, Selenium, Pandas, MySQL, HTML, Css e Javascript;<br>
Áreas de interesse: Desenvolvimento BackEnd, Data science.<br>


