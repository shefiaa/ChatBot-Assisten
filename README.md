![Alt text](<Screenshot 2024-01-02 090631.png>)

<video src="How%20to%20Record%20Your%20Screen%20on%20Windows%2011%20_%20Microsoft%20Windows%20and%202%20more%20pages%20-%20Personal%20-%20Microsoft%E2%80%8B%20Edge%202024-01-02%2009-15-26.mp4" controls title="video"></video>

## 1. Membuat Proyek React
membuatnya dengan menggunakan perintah berikut:
npx create-react-app openai-react-app
cd openai-react-app

## 2. Instalasi Axios
Install axios untuk mengirim permintaan HTTP dari aplikasi React Anda:
npm install axios

## 3. Mendapatkan API Key OpenAI
Pastikan  telah mendaftar di situs web OpenAI dan mendapatkan kunci API. Gantilah YOUR_OPENAI_API_KEY dengan kunci API yang valid.

## 4. Membuat Fungsi Pengiriman Pesan ke OpenAI
Buat file openai.js untuk menangani logika pengiriman pesan ke OpenAI menggunakan axios:

// openai.js
import axios from 'axios';

const apiKey = 'YOUR_OPENAI_API_KEY';
const apiUrl = 'https://api.openai.com/v1/engines/davinci-codex/completions';

export async function sendMsgToOpenAI(input) {
  try {
    const response = await axios.post(apiUrl, {
      prompt: input,
      max_tokens: 150,
    }, {
      headers: {
        'Content-Type': 'application/json',
        'Authorization': `Bearer ${apiKey}`,
      },
    });

    return response.data.choices[0].text;
  } catch (error) {
    throw error;
  }
}

## 5. Menjalankan Aplikasi React
Jalankan aplikasi React Anda dengan perintah:

npm start

