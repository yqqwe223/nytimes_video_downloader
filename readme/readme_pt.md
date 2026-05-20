# 🗽 Analisador de Vídeos do NYTimes

> Uma ferramenta leve, rápida e versátil para extrair conteúdo de vídeo do The New York Times (Versão educacional e de pesquisa)

[🌐 Demonstração online](https://twittervideodownloaderx.com/nytimes_downloader_po) • [📝 Guia de uso](#-guia-de-uso) • [❓ Perguntas frequentes](#-perguntas-frequentes)

---

## 📋 Visão geral do projeto

Este projeto é uma ferramenta de análise de vídeo baseada na web, projetada para extrair com segurança metadados de recursos de mídia de artigos publicamente acessíveis no site do The New York Times, oferecendo opções de conversão de formato e salvamento local. Não requer instalação de software cliente nem registro de conta: utilize diretamente pelo seu navegador.

> ⚠️ **Aviso importante**: Esta ferramenta destina-se exclusivamente a fins de aprendizado pessoal, pesquisa técnica e uso dentro de limites razoáveis. Por favor, respeite os [Termos de Serviço do NYTimes](https://www.nytimes.com/content/help/rights/sale/terms-of-service.html), a 《Lei de Direitos Autorais dos Estados Unidos》 e outras regulamentações aplicáveis. Respeite o trabalho das organizações de notícias e dos criadores; não utilize o conteúdo baixado para fins comerciais ou para infringir direitos de terceiros. **Esta ferramenta suporta exclusivamente conteúdo de vídeo acessível publicamente e não contorna paywalls, restrições de assinatura ou conteúdo que exija login.**

---

## ✨ Funcionalidades principais

- 🔗 **Análise de links**: Compatível com URLs padrão de artigos/páginas de vídeo do NYTimes; detecção automática de recursos de vídeo disponíveis publicamente
- 📥 **Exportação em múltiplos formatos**:
  - Fluxos de vídeo públicos (suporta opções de resolução públicas fornecidas pela plataforma)
  - Extração de áudio → Formato MP3 (conveniente para ouvir reportagens/podcasts offline)
  - Clipe de vídeo → Conversão para GIF animado (ideal para criar materiais educacionais/resumos de conteúdo)
- 🌍 **Interface multilíngue**: Suporte para português, inglês, chinês, japonês, coreano e mais idiomas
- 📱 **Compatibilidade multiplataforma**: Funciona perfeitamente em Chrome / Firefox / Safari / Edge; experiência otimizada para dispositivos móveis e tablets
- 🔒 **Privacidade em primeiro lugar**: Nenhum login de conta do NYTimes necessário, nenhuma coleta de dados pessoais; processo de análise totalmente anônimo
- ⚡ **Processamento rápido**: Análise concluída em média em 5-10 segundos; suporte para solicitações simultâneas

---

## 🚀 Início rápido

### Uso online (recomendado)
1. Acesse [https://twittervideodownloaderx.com/nytimes_downloader_po](https://twittervideodownloaderx.com/nytimes_downloader_po)
2. Copie o link da página de vídeo de destino (exemplo: `https://www.nytimes.com//01/01/world/example-video.html`)
3. Cole o link no campo de entrada → Clique no botão 「Analisar」
4. Selecione o formato desejado → Salve o arquivo seguindo as instruções do navegador

### Implantação local (para desenvolvedores)
```bash
# Clonar o repositório
git clone https://github.com/your-repo/nytimes-video-parser.git

# Instalar dependências
cd nytimes-video-parser && npm install

# Configurar variáveis de ambiente (opcional)
cp .env.example .env

# Iniciar servidor de desenvolvimento
npm run dev
```

> 💡 Nota: Este projeto utiliza uma arquitetura baseada em Node.js + Express. Consulte a documentação detalhada de implantação em `/docs/DEPLOY.md`

---

## 🛠 Stack tecnológico

| Módulo | Tecnologias utilizadas |
|--------|------------------------|
| Frontend | Vue 3 + TypeScript + Vite |
| Backend | Node.js + Express + Axios |
| Processamento de vídeo | ffmpeg.wasm (conversão leve no lado do cliente) |
| Proxy de encaminhamento | Cloudflare Workers / Middleware personalizado |
| Internacionalização | vue-i18n + Pacotes de idioma JSON |

---

## 📚 Guia de uso

### Fluxo operacional básico
```
1. Obter o link do vídeo
   └─ Abra o artigo/página de vídeo de destino no NYTimes → Copie a URL da barra de endereços do navegador

2. Enviar solicitação de análise
   └─ Cole o link no campo de entrada da ferramenta → Clique em 「Iniciar análise」

3. Selecionar configuração de saída
   ├─ 🎬 Baixar vídeo: Escolher resolução disponível (apenas conteúdo público)
   ├─ 🎵 Extrair áudio: Gerar arquivo MP3 (ideal para ouvir notícias/podcasts offline)
   └─ 🎞 Gerar GIF: Criar animação a partir de intervalo de tempo especificado (recomendado: ≤15 segundos)

4. Salvar o arquivo
   └─ O recurso será aberto em uma nova aba → Clique direito/menu → 「Salvar como」
```

### Dicas para uso em dispositivos móveis
- iOS Safari: Botão Compartilhar → 「Salvar em Arquivos」
- Android Chrome: Pressionar e segurar a prévia do vídeo → 「Baixar vídeo」
- Se o vídeo reproduzir automaticamente: Clique em `⋮` no canto superior direito do player → Selecione 「Baixar」

---

## ❓ Perguntas frequentes

**P: Onde os arquivos baixados são salvos?**  
R: Os arquivos são salvos na pasta de download configurada no seu navegador. Você pode verificar ou alterar este caminho nas configurações do navegador.

**P: Posso analisar conteúdo atrás de paywall, exclusivo para assinantes ou que requer login?**  
R: Não. Esta ferramenta funciona apenas com conteúdo de vídeo acessível publicamente e respeita as configurações de acesso do conteúdo original. Conteúdo protegido por paywall, sujeito a restrições de assinatura ou que exija login não é suportado.

**P: A qualidade de imagem/áudio é reduzida após a conversão?**  
R: Os downloads de vídeo mantêm a taxa de bits original da resolução selecionada. O formato MP3 utiliza codificação padrão de 128 kbps. O formato GIF otimiza a taxa de quadros conforme a duração para equilibrar tamanho do arquivo e fluidez.

**P: O histórico de downloads ou cache é armazenado?**  
R: Não. Todos os recursos são transmitidos diretamente ao dispositivo do usuário por meio de um proxy temporário; o servidor não armazena nenhuma solicitação ou arquivo de mídia.

**P: O que fazer se a análise falhar?**  
R: Por favor, verifique: ① Se o link aponta para uma página de vídeo pública válida ② Se sua conexão com a internet está estável ③ Tente usar outro navegador. Se o problema persistir, não hesite em relatá-lo por meio de uma Issue.

---

## ⚖️ Conformidade regulatória e Isenção de responsabilidade

- Esta ferramenta **não contorna nem viola nenhuma medida de proteção técnica, paywall ou controle de acesso** da plataforma; limita-se a obter metadados por meio de interfaces disponíveis publicamente
- O usuário é responsável por verificar se seu uso está em conformidade com a legislação local e os termos de serviço da plataforma
- Casos de uso recomendados: Arquivamento pessoal para aprendizado, referência para pesquisa de notícias, preparação de material educacional... sempre dentro do marco do uso justo (Fair Use)
- Se identificar conteúdo que possa violar direitos ou tiver dúvidas sobre direitos autorais, entre em contato com o canal oficial por meio da [Página de Contato de Direitos Autorais do NYTimes](https://www.nytimes.com/content/help/rights/copyright/copyright-contact.html)
- Esta ferramenta não é afiliada, endossada nem autorizada pelo The New York Times Company. Todas as marcas comerciais e direitos autorais do conteúdo pertencem aos seus respectivos proprietários

---

## 🤝 Guia de contribuição

Agradecemos suas Pull Requests e relatos de Issues! Antes de contribuir, por favor, consulte:
- [Padrões de código](/CONTRIBUTING.md)
- [Guia de tradução multilíngue](/locales/README.md)
- [Requisitos de segurança e conformidade](/SECURITY.md)

---

## 📄 Licença

Este projeto é publicado sob a [Licença MIT](/LICENSE). Pode ser utilizado gratuitamente para fins educacionais e de pesquisa. Para uso comercial, por favor, verifique cuidadosamente o cumprimento das regulamentações legais aplicáveis.

---

> 🌟 Se esta ferramenta foi útil para você, não hesite em ✨atribuir uma Estrela (Star)! Seu apoio é a maior motivação para continuarmos mantendo e melhorando este projeto~

*Última atualização: Maio de  | Versão: v1.0.0*