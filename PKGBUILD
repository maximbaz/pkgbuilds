# Maintainer: Maxim Baz <$pkgname at maximbaz dot com>
# Maintainer: Mohammadreza Abdollahzadeh <morealaz at gmail dot com>

pkgname=ttf-emojione
pkgver=4.0
pkgrel=1
pkgdesc="Official colorful EmojiOne font"
url="https://github.com/emojione/emojione-assets"
arch=(any)
license=(custom)
depends=('fontconfig')
conflicts=('ttf-emoji' 'noto-fonts-emoji' 'ttf-emojione-color' 'ttf-twemoji')
provides=('ttf-emoji')
replaces=('emojione-fonts')
source=("emojione-android-${pkgver}.ttf::https://github.com/emojione/emojione-assets/releases/download/${pkgver}/emojione-android.ttf"
        "70-emojione-color.conf"
        "license-free.pdf")
sha256sums=('1d53b160fb9b9bdb5fceea110f4cc2c1e26be7d7184a6f17c81b56527574f8a8'
            '2489d0211cb2c8b119df8d69fdd4b12a5ebc9f28c47853f7af24e646f69e9df6'
            '2898feeb41e03acd1a655ba5ddad0072aac83a014ee184fdcdebc7a66d353650')

package() {
  install -d "${pkgdir}/etc/fonts/"{conf.d,conf.avail}
  install -Dm644 emojione-android-${pkgver}.ttf "${pkgdir}/usr/share/fonts/emojione/emojione.ttf"
  install -t "${pkgdir}/etc/fonts/conf.avail/" -m644 70-emojione-color.conf
  ln -sf ../conf.avail/70-emojione-color.conf ${pkgdir}/etc/fonts/conf.d/70-emojione-color.conf
  install -Dm644 license-free.pdf "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE.pdf"
}
# vim:set ts=2 sw=2 et:
