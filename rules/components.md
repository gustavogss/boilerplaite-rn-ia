# Component Rules

Todo componente deve possuir tipagem.

Exemplo:

Button.tsx

interface ButtonProps extends TouchableOpacityProps {
title: string;
loading?: boolean;
}

Input.tsx

interface InputProps extends TextInputProps {
error?: string;
}

Text.tsx

interface TextProps extends RNTextProps {
children: ReactNode;
}

Não utilizar any.
