<script setup>
import { kullanKullanici } from '../stores/kullanici'
import { useRouter } from 'vue-router'


const kullanici = kullanKullanici()
const router = useRouter()
function cikisYap() {
  
  router.push('/') 
}
function todogit()
{
  router.push('/todo')
}
const indexcan[];
  function sayican()
    {
      for(let i = 0; i < kullanici.kullaniciListesi.length; i ++)
        {  
          indexcan.push(i);
        }
    }
  sayican();
</script>

<template>
  <div>
    <h2>Hoş geldiniz, {{ kullanici.aktifKullanici.kullaniciAdi }}!</h2>
    <ul>
      <li><b>Kullanıcı Adı:</b> {{ kullanici.aktifKullanici.kullaniciAdi }}</li>
      <li><b>Ad:</b> {{ kullanici.aktifKullanici.ad }}</li>
      <li><b>Soyad:</b> {{ kullanici.aktifKullanici.soyad }}</li>
      <li><b>Email:</b> {{ kullanici.aktifKullanici.email }}</li>
      <li><b>Telefon:</b> {{ kullanici.aktifKullanici.telefon }}</li>
      <li><b>Telefon:</b> {{ kullanici.aktifKullanici.kullaniciID }}</li>

      <button @click="cikisYap">Çıkış Yap</button>
    </ul>
  </div>

  <div>
    <h3> 
      Todolara git
    </h3>
    <button @click="todogit"> TODO SAYFASINA GİT </button>
  </div>
  <div>
    <ul>
      Diğer Kullanıcıların Bilgileri
      <li v-for = "index in indexcan">{{kullanici.kullaniciListesi[index].ad}}</li>
    </ul>
    </div>
</template>
