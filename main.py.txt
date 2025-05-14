import string
import getpass

# Função que verifica a força de uma senha
def verificar_forca_senha(senha, minimo_recomendado):
    # Verifica se o comprimento da senha é menor que o mínimo recomendado
    if len(senha) < minimo_recomendado:
        print(f"\n❌ Sua senha tem apenas {len(senha)} caracteres. O mínimo recomendado para esse contexto é {minimo_recomendado}.")
        print("Por favor, use uma senha mais longa.")
        return

    # Inicializa contadores para cada tipo de caractere
    minusculas = maiusculas = numeros = espacos = caracteres_especiais = 0

    # Loop que percorre cada caractere da senha e faz a contagem
    for caractere in list(senha):
        if caractere in string.ascii_lowercase:
            minusculas += 1
        elif caractere in string.ascii_uppercase:
            maiusculas += 1
        elif caractere in string.digits:
            numeros += 1
        elif caractere == ' ':
            espacos += 1
        else:
            caracteres_especiais += 1

    # Inicializa a pontuação da força da senha
    forca = 0
    observacao = ''

    # Atribui pontos de força com base nos tipos de caracteres presentes
    if minusculas >= 1:
        forca += 1
    if maiusculas >= 1:
        forca += 1
    if numeros >= 1:
        forca += 1
    if espacos >= 1:
        forca += 1
    if caracteres_especiais >= 1:
        forca += 1

    # Atribui observação com base na pontuação de força
    if forca == 1:
        observacao = "Essa é uma senha muito fraca. Troque-a o quanto antes."
    elif forca == 2:
        observacao = "Essa não é uma boa senha. Considere criar uma mais forte."
    elif forca == 3:
        observacao = "Sua senha é razoável, mas pode ser muito melhorada."
    elif forca == 4:
        observacao = "Sua senha é difícil de adivinhar. Mas ainda pode ficar mais segura."
    elif forca == 5:
        observacao = "Essa sim é uma senha forte! Os hackers não terão chance com ela."

    # Exibe os resultados da análise de senha
    print("\nSua senha contém:")
    print(f"{minusculas} letras minúsculas")
    print(f"{maiusculas} letras maiúsculas")
    print(f"{numeros} números")
    print(f'{espacos} espaços em branco')
    print(f"{caracteres_especiais} caracteres especiais")
    print(f"Força da senha: {forca}/5")
    print(f"Observação: {observacao}\n")


# Função que exibe o menu para o usuário selecionar o contexto de uso da senha
def menu_contexto():
    print("===== Bem-vindo ao Verificador de Força de Senha =====")
    while True:
        # Exibe as opções de contexto de uso da senha
        print("\nInforme o contexto de uso da senha:")
        print("1 - Sistema comum (web, email, etc.)")
        print("2 - Ambiente corporativo")
        print("3 - Acesso administrativo/sensível")
        print("4 - Wi-Fi pessoal (WPA2/WPA3)")
        print("5 - Outro")
        print("0 - Sair")

        # Solicita a escolha do contexto
        contexto = input("Escolha uma opção (0 a 5): ")

        # Se a opção for 0, sai do programa
        if contexto == '0':
            print("Saindo...")
            break

        # Define o comprimento mínimo de senha para cada contexto
        minimo = 8  # padrão
        if contexto == '1':
            minimo = 8
        elif contexto == '2':
            minimo = 12
        elif contexto == '3':
            minimo = 16
        elif contexto == '4':
            minimo = 12
        elif contexto == '5':
            try:
                minimo = int(input("Informe o número mínimo de caracteres desejado: "))
            except ValueError:
                print("Valor inválido, usando o padrão de 8 caracteres.")
                minimo = 8
        else:
            print("Opção inválida. Tente novamente.")
            continue

        # Solicita que o usuário digite a senha para verificação
        senha = getpass.getpass("Digite a senha para verificação: ")
        # Chama a função que verifica a força da senha com o comprimento mínimo adequado
        verificar_forca_senha(senha, minimo)

# Chama a função para exibir o menu de contexto e iniciar o processo de verificação
menu_contexto()