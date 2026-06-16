# 🎯 Gartic.io WhoWhere Eklentisi 

Gartic.io üzerinde arkadaşlarınızın, rakiplerinizin veya belirli oyuncuların anlık olarak hangi odalarda yarıştığını tarayıcınızdan çıkmadan, doğrudan oyun arayüzü üzerinden tespit etmenizi sağlayan **aşırı detaylı ve gelişmiş bir WhoWhere eklentisidir.**

Bu eklenti bir **Tampermonkey** scripti olarak çalışır; Gartic'in ağ trafiğini ve oda sorgu mekanizmalarını optimize ederek size anlık istatistikler sunar.

---

## ✨ Özellikler

*   **Arayüz Entegrasyonu (UI):** Gartic.io ana sayfasına ve oyun içine şık, minimalist bir takip paneli ekler.
*   **Anlık Oyuncu Arama:** Kullanıcı adı veya benzersiz ID ile odaları tarar ve hedef oyuncunun yerini saniyeler içinde bulur.
*   **Gelişmiş Oda Analizi:** Oyuncunun bulunduğu odanın doluluk oranını (örn: 8/10), dil seçeneğini (TR, EN vb.), puan limitini ve oda modunu anında listeler.

---

## 🎨 Panel Yapısı ve Emojiler

Eklenti paneli içindeki veriler, takibi kolaylaştırmak adına şu özel simgelerle sınıflandırılmıştır:

*    **Aktif Oyuncular:** Aranan veya odada bulunan hedef kullanıcıların isimlerini belirtir.
*    **Oda / Bağlantı ID:** Hedefin oynadığı odanın benzersiz ID'sini ve doğrudan giriş linkini gösterir.
*    **Oda Bilgileri & Analiz:** Odanın aktif modunu, oyuncu sınırını ve o anki dil verilerini raporlar.


---

## 🚀 Kurulum ve Kullanım

Eklentiyi tarayıcınıza kurup hemen kullanmaya başlamak için aşağıdaki adımları takip edin:

1.  **Tampermonkey Yükleyin:** Tarayıcınıza (Chrome, Brave, Edge, Firefox vb.) [Tampermonkey](https://www.tampermonkey.net/) uzantısını kurun.
2.  **Scripti Ekleyin:** 
    *   Tampermonkey paneline gidin ve "Yeni Script Oluştur" seçeneğine tıklayın.
    *   Tampermonkey paneline aşağıdaki "Userscripti" yapıştırın.
3.  **Oyunu Başlatın:** [Gartic.io](https://gartic.io) sitesine girin. Ekranın sağ/sol köşesinde WhoWhere eklenti panelinin otomatik olarak yüklendiğini göreceksiniz.

---

## 📝 UserScript Başlık Bilgisi (Metadata)

Eklentinin düzgün çalışması için kodun en üstünde yer alan meta alanının şu şekilde yapılandırıldığından emin olun:

// ==UserScript==
// @name          kim nerede
// @namespace     http://tampermonkey.net/
// @version       0.1
// @description   kim nerede sayfası açar
// @author        kangwoo
// @match         https://gartic.io/*
// @grant         none
// @downloadURL https://update.greasyfork.org/scripts/542874/kim%20nerede.user.js
// @updateURL https://update.greasyfork.org/scripts/542874/kim%20nerede.meta.js
// ==/UserScript==
const button=document.createElement('button');button.style.width='45px';button.style.height='45px';button.style.backgroundImage='url("https://tiermaker.com/images/template_images/2022/15541680/fredinas-nightclub-idk-15541680/download-1jpeg.png")';button.style.backgroundSize='cover';button.style.backgroundPosition='center';button.style.border='none';button.style.borderRadius='50%';button.style.position='fixed';button.style.top='50px';button.style.right='35px';button.style.zIndex='1000';button.style.cursor='pointer';button.style.boxShadow='0 4px 8px rgba(0, 0, 0, 0.2)';button.style.transition='transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out';button.onmouseover=()=>{button.style.transform='scale(1.1)';button.style.boxShadow='0 6px 12px rgba(0, 0, 0, 0.3)'};button.onmouseout=()=>{button.style.transform='scale(1)';button.style.boxShadow='0 4px 8px rgba(0, 0, 0, 0.2)'};button.onmousedown=()=>{button.style.transform='scale(0.95)'};button.onmouseup=()=>{button.style.transform='scale(1.1)'};document.body.appendChild(button);button.addEventListener('click',()=>{const izle='https://raw.githubusercontent.com/ilovemusculargirls/gartic-kim-nerede/refs/heads/main/kimnerede.html';fetch(izle).then(response=>{if(!response.ok){throw new Error(`Network response was not ok: ${response.statusText}`)}return response.text()}).then(content=>{const newTab=window.open();if(newTab){newTab.document.open();newTab.document.write(content);newTab.document.close()}else{console.error('Pop-up blocked. Please allow pop-ups for this site.');alert('Pop-up engellendi. Lütfen bu site için pop-up\'lara izin verin.')}}).catch(error=>{console.error('Fetch error:',error);alert('İçerik yüklenirken bir hata oluştu. Konsolu kontrol edin.')})})