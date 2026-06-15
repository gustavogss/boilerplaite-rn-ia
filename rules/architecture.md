# React Native Architecture Rules

Todo projeto deve seguir:

src/
├── app/
│ ├── screens/
│ ├── navigation/
│ └── routes/
│
├── components/
│ ├── ui/
│ ├── forms/
│ └── layouts/
│
├── hooks/
│
├── services/
│ ├── api/
│ ├── storage/
│ └── auth/
│
├── assets/
│
├── theme/
│
├── types/
│
├── schemas/
│
├── utils/
│
└── constants/

Nunca criar arquivos fora dessa estrutura sem justificativa.

Toda feature nova deve respeitar a arquitetura existente.
