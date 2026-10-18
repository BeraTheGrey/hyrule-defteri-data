# Hyrule Defteri — rehber verisi

*The Legend of Zelda: Breath of the Wild* için yazılmış **Hyrule Defteri** overlay'inin (Ultrahand/Tesla) ve web sayfasının indirdiği rehber verisi.

| Dosya | İçerik |
|---|---|
| `version.json` | Veri sürümü. Overlay bunu kontrol edip yeni sürüm varsa indirir. |
| `guide.json` | Görevler: görevi veren, yer, ödül/bağlı shrine. Shrine'lar: koordinat, bölge (en yakın kule), yakındaki yer, bağlı shrine görevi. |
| `map.png` | 1200×1000 stilize Hyrule haritası (web için). |
| `map448.bin` | 448×373 RGBA4444 harita (overlay için, little-endian `u16`). |

## `guide.json` biçimi

```json
{
  "v": 1,
  "q": { "<görev adı>": ["görevi veren", "yer", "ödül veya shrine", "main|side|shrine"] },
  "s": [ [x, z, "bölge", "yakındaki yer", "bağlı shrine görevi veya null"] ]
}
```

`s` dizisi oyunun `Dungeon000`–`Dungeon135` sırasını izler (120 temel + 16 Champions' Ballad shrine'ı). Koordinatlar oyun dünyası birimidir: X −6000…6000 (batı→doğu), Z −5000…5000 (kuzey→güney).

## Kaynaklar ve lisanslar

- Görev veren / yer / ödül bilgileri: [Zelda Wiki](https://zeldawiki.wiki) — içerik [GNU Free Documentation License 1.3](https://www.gnu.org/licenses/fdl-1.3.html) ile lisanslıdır. Bu depodaki `guide.json`'ın görev alanları da aynı lisansla dağıtılır.
- Shrine koordinatları, yer adları ve harita yükseklik/su verisi: [MrCheeze/botw-tools](https://github.com/MrCheeze/botw-tools) üzerinden oyunun veri dosyalarından.
- Harita görüntüsü bu verilerden yeniden çizilmiştir; Nintendo'nun harita görsellerini içermez.

*The Legend of Zelda* ve *Breath of the Wild*, Nintendo'nun ticari markalarıdır. Bu proje Nintendo ile bağlantılı değildir.
