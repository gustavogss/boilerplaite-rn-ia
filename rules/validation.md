# Validation

Toda entrada do usuário deve ser validada.

Utilizar:

- Zod

Exemplo:

const LoginSchema = z.object({
email: z.email(),
password: z.string().min(8),
});
