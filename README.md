# 🚀 Projeto CI/CD com Versionamento Automático

Este projeto demonstra como configurar um fluxo de **CI/CD completo com GitHub Actions**, incluindo:

- Deploy automático via SSH com `rsync`
- Versionamento semântico com `semantic-release`
- Controle de fluxo com Pull Requests
- CI básico para validação de código (via `ci.yml`)

---

## 📌 Fluxo de Trabalho

1. Crie uma branch:
   ```bash
   git checkout -b feat/nova-funcionalidade
   ```

2. Edite os arquivos dentro da pasta `system/`

3. Faça um commit com padrão semântico:
   ```bash
   git commit -m "feat: adiciona nova funcionalidade X"
   ```

4. Envie a branch e crie um Pull Request para a `main`

5. Ao fazer merge:
   - O CI (ci.yml) valida o código
   - O `semantic-release`:
     - Gera nova versão automaticamente (ex: `v1.0.0`, `v1.1.0`, `v2.0.0`)
     - Cria uma tag no GitHub
   - O `deploy.yml` realiza o deploy via `rsync` para os servidores

---

## 🔐 Secrets obrigatórios no GitHub

No repositório, vá até:

```
Settings > Secrets and variables > Actions
```

Crie:

- `SSH_PRIVATE_KEY`: chave privada usada para acessar o servidor via SSH

---

## 🧠 Padrão de Commits (Conventional Commits)

| Tipo               | Versão | Exemplo                             |
|--------------------|--------|-------------------------------------|
| `feat:`            | minor  | `feat: adiciona botão de login`     |
| `fix:`             | patch  | `fix: corrige erro de layout`       |
| `BREAKING CHANGE:` | major  | `feat!: altera estrutura da API`    |

---

## 📂 Estrutura Esperada

```
.
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── deploy.yml
├── system/
│   ├── index.html
│   ├── exemplo.txt
│   └── teste.txt
├── .deployignore
├── package.json
└── README.md
```

---

## ✅ Tecnologias Utilizadas

- GitHub Actions
- semantic-release
- rsync + SSH
- Node.js (para semantic-release)
