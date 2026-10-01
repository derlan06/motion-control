# Motion Control Studio

Site enxuto para gerar vídeos com Kling 3.0 Motion Control via Kie.ai.

## Requisitos
- Node.js 20+
- Chave da API Kie.ai com saldo/acesso ao modelo
- URLs públicas e acessíveis pela Kie.ai para imagem e vídeo (o endpoint documentado recebe URLs; este projeto não implementa hospedagem/upload de arquivos)

## Executar
1. Descompacte o projeto e rode `npm install`.
2. Copie `.env.example` para `.env.local` e preencha `KIE_API_KEY`.
3. Rode `npm run dev` e abra http://localhost:3000.

A chave fica no servidor e não é enviada ao navegador. O site cria a tarefa e consulta o status a cada 4 segundos por até 6 minutos. Se a tarefa demorar mais, o ID aparece na tela; consulte novamente após recarregar/reimplementar o acompanhamento.

## Deploy
Publique em um host compatível com Next.js (por exemplo, Vercel) e configure `KIE_API_KEY` nas variáveis de ambiente. Não coloque a chave em variáveis `NEXT_PUBLIC_*`.

O mapeamento de resolução segue os valores `std`/`pro` descritos no exemplo da API; a documentação fornecida também menciona rótulos 720p/1080p em uma tabela, portanto confirme os valores aceitos na sua conta/API se houver erro de validação.
