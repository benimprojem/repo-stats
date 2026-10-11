# GitHub Repo İstatistikleri Dashboard

Bu proje, belirli bir GitHub kullanıcısının repolarını listeleyip temel istatistiklerini gösteren tek sayfalık bir HTML dashboard'udur.

Özellikler:
- Kullanıcıya ait repoları listeler
- Toplam star, fork, issue ve clone istatistiklerini gösterir
- Repo adları için GitHub linki verir
- Son güncelleme tarihini gösterir
- Yerel bilgisayarda çalıştırılmaya uygundur

Not:
- `traffic/clones` verisi GitHub API üzerinden gelmektedir.
- Bu veriye erişmek için uygun bir GitHub token gerekir.
- Bu token'ı HTML dosyasına koyarsanız local tarayıcıda çalışır; ancak GitHub Pages gibi yayınlanan ortamlarda güvenlik riski oluşturur.
- Bu nedenle GitHub Pages paylaşımı için önerilen yöntem değildir.

## Kurulum

1. Bu repoyu klonlayın:
   ```bash
   git clone https://github.com/benimprojem/repo-stats.git
   cd repo-stats
   ```

2. `index.html` dosyasını açın.

3. Dosyanın içindeki `GITHUB_TOKEN` alanına GitHub personal access token (PAT) ekleyin.

4. Tarayıcıda `index.html` dosyasını açın.

## PAT Nasıl Alınır?

1. GitHub'da hesabınıza giriş yapın.
2. Sağ üst köşedeki profil resmine tıklayın.
3. `Settings` > `Developer settings` > `Personal access tokens` menüsüne gidin.
4. `Tokens (classic)` veya uygun token ekranını açın.
5. `Generate new token` seçin.
6. Gerekli yetkiyi verin. Genelde `public_repo` yeterlidir.
7. Token'ı kopyalayın ve `index.html` içindeki `GITHUB_TOKEN` alanına yapıştırın.

## Güvenlik Uyarısı

- Bu dosyada PAT saklamak güvenlik riski taşır.
- Eğer dosyayı paylaşacaksanız, PAT'i kaldırın veya ayrı bir yerel ortamda kullanın.
- GitHub Pages üzerinde yayınlamayın; çünkü herkes token'ı görebilir.

## Örnek Kullanım

`index.html` içinde kullanıcı adı alanına yazdığınız kullanıcı için otomatik olarak repo listesi ve toplam istatistikler görünür.

Örnek:
```text
benimprojem
```

## Dosya Yapısı

```text
repo-stats/
├── index.html
├── README.md
└── LICENSE   (opsiyonel)
```

## Geliştirme Notları

- Public repolar için çoğu durumda `public_repo` yetkisi yeterlidir.
- Clone sayısı, GitHub'ın traffic API'si tarafından verilir; bazı repolarda bu veri boş veya görünmeyebilir.
- İsterseniz daha sonra dashboard'a arama, sıralama, CSV export veya dark/light mode eklenebilir.

## Lisans

Projeyi kendi kullanımınıza göre düzenleyebilirsiniz.

Bu README örneği, kullanıcıların kendi başlarına çalıştırması için hazırlanmıştır.
