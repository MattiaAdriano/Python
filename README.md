# Python
Código Python - enviar email para vários destinatários

import smtplib
import email.message

lista = list()

def enviar_email():   
    corpo_email = """
    <p>TEXTO,</p>
    <p>TEXTO.</p>
    <p>TEXTO,</p>
    <p>TEXTO</p>
    """.strip().title()
    
    extremo_zl = email.message.Message()
    extremo_zl["Subject"] = 'teste Python'
    extremo_zl["From"] = 'remetenteemail'
    email_que_recebe = 'email','email','email'
    senha = 'senhaemailremetente'
    extremo_zl.add_header('Content-Type', 'text/html')   
    extremo_zl.set_payload(corpo_email)
   
    try:
        extremo = smtplib.SMTP('smtp.gmail.com: 587')
        extremo.starttls()
        extremo.login(extremo_zl["From"], senha)
        extremo.sendmail(extremo_zl["From"], email_que_recebe, extremo_zl.as_string().encode('utf-8'))
                
        print('\n\033[1;4m{:=^43}\033[m'.format(''))
        print(f'\033[1;33m{"<PARABÉNS!! Email Enviado Com Sucesso>":^43}\033[m')
        print('\033[1;4m{:=^43}\033[m'.format(''))
   
    except Exception as err:
        print('\n\033[1;31m{:=^43}\033[m'.format(''))
        print(f'\033[1;31m{"<ATENÇÃO!! Falha Ao Enviar O Email>":^43}\033[m')
        print('\033[1;31m{:=^43}\033[m'.format(''))
    
        print(f'\n\033[1;31m{"Tipo Do Erro: "}\033[m\n')
          
        print('\033[1;31m{:=^43}\033[m'.format(''))
        print(f'\033[1;31m{f"{err}":^43}\033[m')
        print('\033[1;31m{:=^43}\033[m'.format(''))  
        
        
        Linha nova(insert Cell Below)
        enviar_email ()
        
   
    
