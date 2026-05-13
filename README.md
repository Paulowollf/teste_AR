# Cartão de Visita em Realidade Aumentada

Um cartão de visita interativo que ao apontar o QR Code, exibe um vídeo em realidade aumentada.

## 📋 O que você precisa

1. Uma conta no GitHub (gratuita)
2. Um vídeo MP4 (para colocar no cartão)
3. Impressora (para imprimir o QR Code no cartão)

## 🚀 Passo 1: Preparar os Arquivos

### 1.1 Criar pasta do seu vídeo
- Crie uma pasta chamada `assets` na raiz do projeto
- Coloque seu vídeo dentro dela com o nome: `video.mp4`
- **Tamanho recomendado**: Até 50MB (para carregar rápido)
- **Duração**: 10-30 segundos é ideal
- **Formato**: MP4 (H.264 codec)

### 1.2 Estrutura final do projeto
```
seu-repo/
├── index.html          (já criado)
├── README.md           (este arquivo)
├── assets/
│   └── video.mp4       (seu vídeo)
└── .gitattributes      (para vídeos no Git)
```

## 📤 Passo 2: Enviar para GitHub

### 2.1 Criar novo repositório
1. Acesse GitHub.com
2. Clique em **+** → **New repository**
3. Nome: `cartao-visita-ar`
4. Deixe como **Public**
5. Clique em **Create repository**

### 2.2 Configurar Git (primeira vez)
```bash
# Clone o repositório vazio
git clone https://github.com/SEU_USER/cartao-visita-ar.git
cd cartao-visita-ar

# Adicione os arquivos
# (copie index.html e pasta assets para aqui)

# Envie para GitHub
git add .
git commit -m "Initial commit: Cartão RA"
git push origin main
```

## 🌐 Passo 3: Ativar GitHub Pages

1. Acesse: **Settings** → **Pages**
2. Em "Source", selecione: **main branch**
3. Clique em **Save**
4. Aguarde 1-2 minutos

Sua página estará disponível em:
```
https://SEU_USER.github.io/cartao-visita-ar/
```

## 🎨 Passo 4: Gerar QR Code

1. Acesse: https://qr-code-generator.com/
2. Cole a URL do seu site
3. Baixe a imagem do QR Code
4. **Imprima junto com o cartão** ou **cole sobre o cartão**

## 🔧 Personalizações

### Alterar informações do cartão
Edite o arquivo `index.html`, procure por:
```html
<div class="info-overlay">
    <h2>Cartão de Visita</h2>
    <p><strong>Sua Empresa</strong></p>
    <p>seu.email@empresa.com</p>
    <p>(XX) XXXX-XXXX</p>
</div>
```

### Mudar o tamanho do vídeo
Procure por:
```html
<a-video 
    id="arVideo"
    src="assets/video.mp4" 
    width="4"        <!-- Largura -->
    height="3"       <!-- Altura -->
    ...
>
```

### Usar marcador customizado
Por padrão, usa o padrão "Hiro". Para usar seu próprio marcador:
1. Crie uma imagem quadrada de alto contraste
2. Gere o padrão em: https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html
3. Substitua `preset="hiro"` por `url="seu-marcador.patt"`

## 📱 Testando

1. Acesse a URL no seu celular
2. Permita acesso à câmera
3. Aponte para o **marcador Hiro** (símbolo no cartão)
4. O vídeo deve aparecer em RA!

**Marcador Hiro** - procure por "hiro marker" no Google para imprimir de referência.

## ⚙️ Solução de Problemas

### "Câmera não funciona"
- Permitiu acesso à câmera no navegador?
- Seu navegador suporta WebXR (Chrome, Firefox, Edge)?
- Tente em outro dispositivo

### "Vídeo não aparece"
- O arquivo está em `assets/video.mp4`?
- Teste enviando um vídeo menor (< 10MB)
- Verifique o console (F12 → Console)

### "Marcador não é detectado"
- Certifique-se de estar usando o marcador Hiro correto
- Boa iluminação é essencial
- Tente de ângulos diferentes

## 📤 Atualizando o vídeo depois

1. Substitua o arquivo `assets/video.mp4`
2. Faça o push:
```bash
git add assets/video.mp4
git commit -m "Atualizar vídeo"
git push origin main
```

3. Limpe o cache do navegador ou aguarde alguns minutos

## 🎬 Dicas para o Vídeo

- **Fundo**: Use cores sólidas ou degradês para contraste
- **Duração**: 8-15 segundos funciona bem
- **Resolução**: 1080p ou 720p
- **Formato**: MP4 com codec H.264
- **Compressão**: Use ffmpeg para reduzir tamanho:
```
ffmpeg -i video-original.mp4 -vcodec libx264 -crf 23 -acodec aac -b:a 128k video.mp4
```

## 📞 Contato e Suporte

Se tiver dúvidas:
- Verificar documentação do AR.js: https://ar-js-org.github.io/AR.js-Docs/
- Issues no GitHub do seu repositório

---

**Versão 1.0** | Criado com ❤️ para cartões interativos