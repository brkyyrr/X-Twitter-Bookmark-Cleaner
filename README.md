# X (Twitter) Bookmark Cleaner 🧹

X (eski Twitter) üzerinde biriken **Kaydedilenler (Bookmarks)** gönderilerini,
tek tek uğraşmadan **tarayıcı konsolu (F12)** üzerinden **her 2 saniyede bir otomatik olarak kaldıran**
küçük bir JavaScript script’i.

## ✨ Özellikler

- ✅ Dil bağımsız (TR / EN fark etmez)
- ✅ Menü açmaz, direkt “Remove Bookmark” butonuna tıklar
- ✅ X’in en stabil selector’ı olan `data-testid="removeBookmark"` kullanır
- ✅ Ban riskini azaltmak için 2 saniyede 1 çalışır
- ✅ Kurulum gerektirmez

---

## 🚀 Nasıl Kullanılır?

1. **X (Twitter)**’da **Kaydedilenler (Bookmarks)** sayfasını aç  
2. `F12` → **Console** sekmesine gir  
3. Aşağıdaki kodu yapıştır ve **Enter**’a bas  

```js
// varsa eski çalışmayı durdur
if (window._bookmarkCleaner) {
  clearInterval(window._bookmarkCleaner);
}

window._bookmarkCleaner = setInterval(() => {
  const btn = document.querySelector('button[data-testid="removeBookmark"]');

  if (btn) {
    btn.click();
    console.log('✅ Bookmark kaldırıldı');
  } else {
    console.log('❌ Kaldırılacak bookmark bulunamadı');
  }
}, 2000);


clearInterval(window._bookmarkCleaner);
