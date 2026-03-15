# ClipMaker — AI Viral Moments

Uma *demo* web que transforma qualquer vídeo em um **clipe viral** usando:

- **Cloudinary** para upload/armazenamento e transcrição automática (via upload preset).
- **Gemini (Google Generative AI)** para analisar a transcrição e sugerir o momento mais viral.
- **Tailwind CSS + GSAP** para animação e UI fluida.

---

## 🚀 Como funciona

1. Você faz upload de um vídeo.
2. O Cloudinary gera automaticamente uma **transcrição** do áudio.
3. O app envia essa transcrição para o **Gemini**/AI com um prompt que pede um trecho viral (30–60s).
4. Recebe de volta a timestamp do momento viral e reproduz o vídeo cortado diretamente no navegador.

---

## ✅ Recursos

- Upload de vídeo (Cloudinary Upload Widget)
- Transcrição automática do vídeo
- Geração automática de trecho viral usando Gemini (IA)
- Player embutido com animações suaves

---

## 🧩 Pré-requisitos

1. **Chave de API do Gemini (Google Generative AI)**
2. Conta no **Cloudinary** com um **upload preset** configurado

> Esta demo usa um `cloudName` e `uploadPreset` codificados no `index.html`.

---

## ⚙️ Como rodar localmente

1. Clone ou baixe este repositório.
2. Abra `index.html` no seu navegador (não precisa de servidor). 
3. Insira sua **Gemini API Key** no campo superior.
4. Clique em **Começar Upload** e selecione um vídeo.

> Observação: é necessário que o arquivo carregado seja processado pelo Cloudinary (transcrição) antes da IA gerar o trecho viral.

---

## 🔧 Ajustes e customizações

### Cloudinary
No `index.html`, ajuste estas constantes:

```js
const app = {
  cloudName: "suaCloudName",
  uploadPreset: "seuUploadPreset",
  ...
};
```

### Modelo Gemini
Por padrão, o app usa:

```js
const model = "gemini-2.5-flash";
```

Você pode trocar para outro modelo compatível (por exemplo, `gemini-2.1`), mas mantenha o prompt e o formato de resposta.

---

## 🧪 Testando

1. Insira sua Gemini API Key.
2. Faça upload de um vídeo curto.
3. Aguarde a transcrição e o resultado da IA.
4. O player exibirá automaticamente o trecho viral gerado.

---

## 📝 Observações

- O app depende de **Cloudinary** para gerar a transcrição (`.transcript`).
- Se o Cloudinary demorar a gerar a transcrição, a aplicação faz várias tentativas antes de falhar.
- Se o Gemini retornar algo fora do padrão (`so_...,eo_...`), o vídeo pode não carregar corretamente.

---

## 📦 Estrutura de arquivos

- `index.html` — código principal da aplicação

---

## 📜 Licença

Use à vontade! Este projeto é livre para estudo e experimentação.

---

<div align="center">
  Desenvolvido por Vitória Miranda (NLW Operator) - 2026
</div>
