# MotoFIPE - Lojista Pro 🏍️

Plataforma SaaS para consulta da Tabela FIPE com dashboard comercial, checklist de inspeção e geração de relatórios em PDF.

## 🎯 Funcionalidades

- **🔍 Consulta FIPE**: Busca rápida de motos por modelo, ano ou código FIPE
- **📊 Dashboard**: Visualização de estatísticas, tabela comercial com margem de compra (-20%)
- **✅ Checklist**: Avaliação estruturada de inspeção visual, motor e documentação
- **📄 Relatórios PDF**: Geração automática de propostas de compra e relatórios de avaliação

## 🚀 Deploy no Vercel

### Pré-requisitos
- Conta no GitHub
- Conta no Vercel
- Projeto já pushado no repositório

### Passo a passo

1. **Acesse Vercel**
   - Vá para [vercel.com](https://vercel.com)
   - Faça login com sua conta GitHub

2. **Importe o Projeto**
   - Clique em "Add New..." → "Project"
   - Selecione o repositório `FIPESaaS`
   - Vercel detectará automaticamente a configuração

3. **Configure o Deploy**
   - Framework Preset: Selecione "Other" (site estático)
   - Build Command: deixe em branco (opcional: `echo 'No build required'`)
   - Output Directory: deixe em branco
   - Clique em "Deploy"

4. **Acesse o Projeto**
   - Após o deploy, copie a URL fornecida
   - Seu app estará disponível em: `https://seu-projeto.vercel.app`

## 📁 Estrutura do Projeto

```
FIPESaaS/
├── index.html          # Aplicação principal (SPA)
├── vercel.json         # Configuração Vercel (SPA routing)
├── package.json        # Metadados e scripts
└── README.md           # Este arquivo
```

## 🔐 Integração Supabase

A aplicação conecta ao banco de dados Supabase (chaves incluídas em `index.html`).

**Banco de dados esperado:**
- Tabela: `motos_fipe`
- Colunas: `fipe_modelo`, `modelo_original`, `codigo_fipe`, `fipe_marca`, `ano_modelo`, `fipe_ano`, `preco`, `combustivel`, `mes_referencia`

## 💡 Uso Local

Para testar localmente:

```bash
# Opção 1: Usando Python
python -m http.server 8000

# Opção 2: Usando Node.js
npx http-server -p 8000

# Opção 3: Usando Live Server (VS Code)
# Abra com extensão Live Server
```

Depois acesse `http://localhost:8000`

## 🛠️ Customização

### Alterar cores do tema
Edite as variáveis CSS em `index.html` (linhas 12-24):
```css
--green: #1D9E75;        /* cor principal */
--green-dark: #0F6E56;   /* verde escuro */
--green-light: #E1F5EE;  /* verde claro */
```

### Adicionar mais marcas
Edite o select de filtro em `index.html` (linhas ~370):
```html
<option value="KAWASAKI">Kawasaki</option>
<option value="SUZUKI">Suzuki</option>
```

## 📊 Dashboard

O dashboard exibe:
- Total de motos indexadas
- Preço médio FIPE
- Referência de atualização (mês)
- Tabela com os 20 primeiros modelos

## 📝 Checklist

Estrutura de inspeção com 3 categorias:
- **Inspeção Visual** (4 itens)
- **Motor e Mecânica** (5 itens)
- **Documentação** (3 itens)

Pontuação automática:
- ✅ **80%+**: Moto em boa condição
- ⚠️ **50-79%**: Atenção - negociar desconto
- ❌ **<50%**: Muitos itens irregulares

## 📄 Geração de PDFs

Dois tipos de relatórios disponíveis:
1. **Proposta de Compra**: Dados do veículo + valores FIPE e sugestão de compra
2. **Relatório de Avaliação**: Resultado do checklist com data e pontuação

## 🌐 Compatibilidade

- ✅ Chrome, Firefox, Safari, Edge
- ✅ Mobile (responsivo)
- ✅ PWA-ready

## 📧 Suporte

Para dúvidas sobre o deploy, consulte:
- [Documentação Vercel](https://vercel.com/docs)
- [Documentação Supabase](https://supabase.com/docs)

---

**Versão**: 1.0.0  
**Última atualização**: 2026-06-09
