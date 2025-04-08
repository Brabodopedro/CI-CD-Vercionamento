# Meu Projeto CD + Versionamento Automático

## Fluxo
1. Criar branch e editar arquivos
2. Fazer commit com padrão semântico (ex: feat: adiciona X)
3. Abrir Pull Request para main
4. Após merge:
   - semantic-release gera nova versão e cria tag
   - arquivos de system/ são enviados via rsync para os servidores

## Secrets Necessários (no GitHub)
- SSH_PRIVATE_KEY (sua chave privada para rsync via SSH)

