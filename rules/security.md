# Security

Nunca:

- Expor secrets
- Expor API Keys
- Armazenar token em AsyncStorage sem criptografia

Sempre:

- Sanitizar entradas
- Validar dados com Zod
- Utilizar variáveis de ambiente
