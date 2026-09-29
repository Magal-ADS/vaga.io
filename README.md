# Plataforma de eventos e excursões

Protótipo web para divulgar eventos e excursões da comunidade, reservar vagas e acompanhar inscrições. A aplicação inteira está em um único arquivo [`index.html`](index.html), com HTML, CSS e JavaScript puro. Não precisa de build, backend ou banco de dados.

Veja o [tutorial de uso e a demonstração gravada](docs/TUTORIAL.md).

## O que já funciona

- Catálogo público de eventos, com busca, filtro por categoria, detalhes, vagas e preços.
- Cadastro e login de demonstração para participantes. A conta é necessária apenas para reservar uma vaga.
- Reservas, cancelamento e consulta em **Minhas inscrições**.
- Painel administrativo com indicadores, criação, edição e exclusão de eventos, inscrições manuais, controle de pagamento e exportação CSV.
- Dados fictícios iniciais e persistência local no navegador.
- Interface responsiva em português do Brasil.

Pagamento online, envio de confirmações, upload de imagens, recuperação de senha, gestão de administradores e relatórios financeiros avançados aparecem na interface como funcionalidades **Em breve**.

## Executar

Abra o arquivo `index.html` diretamente no navegador. A fonte do Google Fonts precisa de internet; se estiver indisponível, a página usa fontes alternativas.

Para servir com Docker:

```bash
docker build -t vaga-eventos .
docker run --rm -p 8081:80 vaga-eventos
```

Depois, acesse `http://localhost:8081`. Troque `8081` por outra porta livre, se necessário.

## Contas de demonstração

| Perfil | E-mail | Senha |
| --- | --- | --- |
| Administradora | `admin@excursoes.com` | `admin123` |
| Participante | `maria@email.com` | `maria123` |

Outros participantes de exemplo estão no objeto `USERS`. Novas contas criadas pelo formulário ficam salvas somente no navegador usado para o cadastro.

## Personalização

No início do script de `index.html`, edite:

- `CONFIG.APP_NAME` e `CONFIG.TAGLINE` para o nome e a descrição curta.
- `CONFIG.COLORS` para as cores principais.
- `USERS` para as contas de demonstração.
- `SEED_DATA` para os seis eventos e as inscrições iniciais.

O painel administrativo oferece **Restaurar dados de demonstração** para repor os eventos e inscrições iniciais.

## Limites do protótipo

Eventos, inscrições e contas criadas ficam em `localStorage`; a sessão fica em `sessionStorage`. Os dados não são compartilhados entre navegadores ou dispositivos. A autenticação é apenas demonstrativa e guarda credenciais no navegador. Antes de usar em produção, é necessário implementar backend, autenticação segura e integração de pagamentos.
