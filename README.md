# Sınav Masası

Tek dosyalık, kurulum gerektirmeyen interaktif quiz uygulaması. Quizler düz metin belgeleridir; Claude ile saniyeler içinde yenisi üretilebilir.

## Kullanım

1. `quiz.html` dosyasını tarayıcıda aç (çift tıklaman yeterli).
2. En son eklenen quiz otomatik başlar; diğerleri **Quizlerim** listesindedir.
3. Başka bir quizi **Quiz belgesi yükle** bölümünden dosya seçerek ya da metnini yapıştırarak açabilirsin.

## Quiz belgesi biçimi

```
# Quiz başlığı
? Soru metni
- yanlış şık
+ doğru şık
- yanlış şık
> Cevaptan sonra gösterilecek açıklama (isteğe bağlı)
```

| Satır başı | Anlamı |
|---|---|
| `#` | Quiz başlığı |
| `?` | Soru |
| `-` | Yanlış şık |
| `+` | Doğru şık (her soruda en az bir tane) |
| `>` | Açıklama |

## Claude ile quiz üretmek

**Claude Code + `quiz-yap` skill'i ile:** `quiz yap: Osmanlı tarihi` yaz. Claude quizi `quizler/` klasörüne `.txt` olarak kaydeder ve `quizler/liste.js` dosyasına ekler. Sayfayı yenileyince listede görünür.

**Herhangi bir Claude sohbetiyle:** uygulamadaki **Claude'dan quiz nasıl istenir?** bölümündeki hazır metni kopyala, konuyu yaz, gelen cevabı uygulamaya yapıştır.

## Klasör yapısı

```
quiz.html          uygulama
quizler/
  *.txt            quiz belgeleri
  liste.js         uygulamanın okuduğu quiz listesi
```

`liste.js`'e elle quiz eklemek için sonuna şu satırı ekle:

```js
QUIZZES.push("# Başlık\n? Soru\n- yanlış\n+ doğru");
```
