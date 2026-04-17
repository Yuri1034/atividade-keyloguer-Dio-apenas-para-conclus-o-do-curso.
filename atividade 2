import datetime

def registrar_log(mensagem):
    with open("log.txt", "a", encoding="utf-8") as f:
        data = datetime.datetime.now()
        f.write(f"[{data}] {mensagem}\n")

# Exemplo de uso
registrar_log("Programa iniciado")
registrar_log("Usuário executou ação X")
registrar_log("Erro simulado")
import smtplib
from email.message import EmailMessage

def enviar_email():
    email = EmailMessage()
    email["Subject"] = "Relatório de Logs"
    email["From"] = "seuemail@gmail.com"
    email["To"] = "destino@gmail.com"

    email.set_content("Segue em anexo o log do sistema.")

    # Anexar arquivo
    with open("log.txt", "rb") as f:
        email.add_attachment(
            f.read(),
            maintype="application",
            subtype="octet-stream",
            filename="log.txt"
        )

    # Configuração SMTP (Gmail)
    with smtplib.SMTP_SSL("smtp.gmail.com", 465) as smtp:
        smtp.login("seuemail@gmail.com", "SENHA_DE_APP")
        smtp.send_message(email)

    print("E-mail enviado!")

# Executar
enviar_email()
