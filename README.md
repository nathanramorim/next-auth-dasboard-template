# Next.js Dashboard Template with Authentication

Este é um template inicial para criar dashboards em Next.js com autenticação. O projeto inclui autenticação configurada com NextAuth.js e está preparado para usar tanto autenticação mock (para desenvolvimento) quanto Supabase.

## 🚀 Funcionalidades

- 🔐 Autenticação com NextAuth.js
- 🎨 Interface moderna com Tailwind CSS
- 📱 Design responsivo
- 🔄 Suporte a autenticação mock para desenvolvimento
- 🛠️ Integração pronta com Supabase
- 🛡️ Rotas protegidas
- 👤 Perfil de usuário no header
- 🚪 Funcionalidade de logout

## 🛠️ Tecnologias

- [Next.js 14](https://nextjs.org/)
- [NextAuth.js](https://next-auth.js.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Supabase](https://supabase.com/) (opcional)
- [TypeScript](https://www.typescriptlang.org/)
- [PNPM](https://pnpm.io/)

## 📦 Instalação

1. Clone o repositório:
```bash
git clone [url-do-repositorio]
cd [nome-do-projeto]
```

2. Instale as dependências:
```bash
pnpm install
```

3. Configure o ambiente:
   - O projeto inclui um arquivo `.env.example` com as variáveis necessárias
   - Crie um novo arquivo `.env.local` baseado no `.env.example`:
   ```bash
   cp .env.example .env.local
   ```
   - Edite o arquivo `.env.local` com suas configurações específicas

## ⚙️ Configuração do Ambiente

O arquivo `.env.example` serve como template para as variáveis de ambiente necessárias. Você deve criar um arquivo `.env.local` baseado nele e configurar de acordo com seu ambiente:

### Autenticação Mock (Desenvolvimento)

Para desenvolvimento rápido, você pode usar a autenticação mock. No seu `.env.local`:

```env
# Desabilite o Supabase
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=

# Habilite o mock
MOCK_USER=true
MOCK_USER_EMAIL=test@example.com
MOCK_USER_PASSWORD=password123

# NextAuth (obrigatório)
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=seu-secret-aqui # Gere com: openssl rand -base64 32
```

### Supabase (Produção)

Para usar o Supabase em produção, configure seu `.env.local`:

```env
# Desabilite o mock
MOCK_USER=false

# Configure o Supabase
NEXT_PUBLIC_SUPABASE_URL=sua-url-do-supabase
NEXT_PUBLIC_SUPABASE_ANON_KEY=sua-chave-anonima

# NextAuth (obrigatório)
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=seu-secret-aqui # Gere com: openssl rand -base64 32
```

> **Nota**: O arquivo `.env.local` não é versionado no git por questões de segurança. Cada desenvolvedor deve criar seu próprio arquivo baseado no `.env.example`.

## 🚀 Executando o Projeto

```bash
pnpm dev
```

O projeto estará disponível em `http://localhost:3000`

## 📁 Estrutura do Projeto

```
src/
├── app/
│   ├── api/
│   │   └── auth/
│   │       └── [...nextauth]/
│   ├── dashboard/
│   ├── login/
│   └── layout.tsx
├── components/
│   └── Header.tsx
└── middleware.ts
```

## 🔒 Autenticação

O projeto suporta dois modos de autenticação:

1. **Mock (Desenvolvimento)**
   - Usa credenciais definidas no `.env.local`
   - Ideal para desenvolvimento rápido
   - Não requer configuração externa

2. **Supabase (Produção)**
   - Autenticação completa com Supabase
   - Suporte a múltiplos provedores
   - Gerenciamento de usuários

## 🎨 Customização

- O tema pode ser personalizado através do arquivo `tailwind.config.js`
- Componentes podem ser modificados em `src/components/`
- Rotas protegidas podem ser ajustadas em `middleware.ts`

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

## 📧 Suporte

Para suporte, abra uma issue no repositório ou entre em contato através de [seu-email].
