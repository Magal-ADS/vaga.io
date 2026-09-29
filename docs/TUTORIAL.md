# Tutorial de uso do Vaga.io

[Assista à demonstração gravada](./demonstracao.webm). O vídeo dura cerca de 1 minuto e 42 segundos, tem legendas na tela e mostra os principais fluxos de participante e administração. É uma gravação do protótipo local, sem narração por voz.

## Acessar o sistema

Abra `index.html` no navegador. O catálogo de eventos aparece mesmo sem login. Para testar uma reserva, use a conta de participante `maria@email.com` com senha `maria123`. Para acessar o painel administrativo, use `admin@excursoes.com` com senha `admin123`.

Na interface, o nome ainda aparece como **Nome do Sistema**. Ele pode ser alterado em `CONFIG.APP_NAME`, no início do script de `index.html`.

## Como usar como participante

1. Na página **Eventos**, percorra os cards para ver data, local, preço e vagas. Use **Buscar por nome** ou **Categoria** para filtrar.
2. Clique em **Ver detalhes** para consultar a descrição completa, a programação, o local de saída e o que levar.
3. Clique em **Quero me inscrever**. Se ainda não estiver conectado, crie uma conta ou entre. Preencha telefone, quantidade de pessoas e, se quiser, observações. Clique em **Confirmar reserva**.
4. Abra **Minhas inscrições** para consultar o evento, a quantidade de pessoas, o valor total e o status. A reserva começa como **Pendente** até a organização confirmar o pagamento.
5. Para desistir, clique em **Cancelar inscrição** e confirme. As vagas são liberadas novamente. Uma inscrição cancelada continua aparecendo no histórico.

## Como usar como administrador

1. Entre com a conta administrativa. A **Visão geral** mostra indicadores e os próximos eventos.
2. Em **Eventos**, clique em **+ Novo evento** para preencher título, categoria, data, horário, local, saída, preço, número de vagas, descrição, programação e o que levar. Salve para publicar no catálogo.
3. Clique em **Gerenciar evento** para consultar vagas e inscrições. Nessa página, use **Editar** para alterar o evento ou **Excluir** para apagá-lo com suas inscrições.
4. Na lista de inscrições, filtre por nome ou status. Use **Marcar pago** para confirmar um pagamento; **Voltar a pendente** desfaz essa marcação. **Cancelar** libera as vagas da inscrição.
5. Use **+ Inscrição manual** para cadastrar alguém pela organização. **Exportar lista (CSV)** baixa os inscritos do evento.
6. **Restaurar dados de demonstração** repõe os eventos e inscrições iniciais. Esse comando descarta as mudanças feitas naquele navegador.

## O que está disponível e o que ainda falta

O catálogo, os filtros, cadastro e login de demonstração, reservas, cancelamentos, criação e edição de eventos, gestão de inscrições e exportação CSV funcionam no protótipo. Os botões marcados **Em breve** indicam recursos ainda indisponíveis: pagamento online, envio de confirmações, upload de imagens, recuperação de senha, gestão de outros administradores e relatórios financeiros avançados.

Os dados ficam apenas no navegador usado. Eventos, inscrições e contas novas são guardados em `localStorage`; a sessão usa `sessionStorage`. Não há sincronização entre dispositivos nem cobrança real. Para uso em produção, será preciso implementar backend, autenticação segura e integração de pagamentos.
