# 🔐 Strong Password - A3 Engenharia de Software

Este é um projeto do curso de Engenharia de Software (A3), com foco na construção de um **verificador de força de senhas**, utilizando boas práticas de desenvolvimento, DevOps e segurança da informação. O sistema analisa a composição da senha digitada e fornece uma pontuação de 0 a 5 com base em critérios de robustez, além de recomendações de melhoria.

---

## 📌 Funcionalidades

- Escolha do **contexto de uso** da senha (pessoal, corporativo, administrativo, etc.)
- Verificação da senha com base em:
  - Letras maiúsculas e minúsculas
  - Números
  - Caracteres especiais
  - Comprimento mínimo (adaptado ao contexto)
- Pontuação de **0 a 5**
- Mensagem final com **observações e dicas**
- Interface simples via terminal
- Sem armazenamento de senhas (foco em privacidade)

---

## ⚙️ Tecnologias Utilizadas

- **Python 3.11**
- Bibliotecas padrão:
  - `string`
  - `getpass`
- Testes com `unittest`
- Integração contínua com **GitHub Actions**

---

## ▶️ Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/magictog/strong-password-a3.git
   cd strong-password-a3


Como rodar os testes
O projeto utiliza unittest. Para rodar os testes:
python -m unittest test_senha.py


CI/CD com GitHub Actions
Este projeto utiliza integração contínua (CI) por meio do GitHub Actions, que roda os testes automaticamente a cada push ou pull request. O pipeline está definido no arquivo:
.github/workflows/ci-cd.yml


Estrutura do Projeto:
strong-password-a3/
├── main.py               # Código principal
├── test_senha.py         # Testes automatizados
├── .gitignore            # Arquivos ignorados pelo Git
├── requirements.txt      # Dependências (nenhuma externa)
├── README.md             # Documentação
└── .github/workflows/    # CI/CD (GitHub Actions)


Equipe
Enrico Aguiar Vrunski

Thiago Ferreira Lima Gonçalves

Matheus Tognon Siqueira

Felipe Soares de Oliveira


Licença
Este projeto é acadêmico e de código aberto. Sinta-se à vontade para estudar, adaptar ou evoluir.

---

## ✅ Próximos passos

1. **Abra o arquivo `README.md` no seu editor** (ex: VS Code ou Bloco de Notas)
2. Apague o conteúdo antigo
3. Cole o conteúdo acima
4. Salve e **faça push para o GitHub**, se desejar atualizar lá também:

```bash
git add README.md
git commit -m "Atualiza README com documentação completa"
git push
