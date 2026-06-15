# TypeScript Rules

Obrigatório:

strict: true

tsconfig:

{
"compilerOptions": {
"paths": {
"@/_": ["./src/_"]
}
},
"extends": "expo/tsconfig.base"
}

Importações:

import { Button } from "@/components/ui/Button"

Nunca utilizar:

../../../components
