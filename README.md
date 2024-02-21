# Adicionando o próprio IP público a uma regra de entrada (NSG ou Security Group) com Terraform

Como deixar uma máquina virtual exposta para internet é muito perigoso, o uso acima restringe o acesso somente do computador que executamos o código e mesmo sendo uma máquina de testes/laboratório aumentamos um pouco a segurança.

O código deste reositório pode ser usado para qualquer provider cloud: Azure, AWS, GCP e etc, mas nesse artigo irei usar para criar um Azure NSG (Network Security Group)  mas com a idéia voce pode adaptar a Cloud e recurso que necessita:

Na linha 19 eu associo o IP público com o resultado do bloco data.http.myip acima pegando o retorno response_body: "${chomp(data.http.myip.response_body)}". O uso do chomp é para retirar todo espaço em branco que possa haver.

Espero que gostem e qualquer feedback é bem vindo!
