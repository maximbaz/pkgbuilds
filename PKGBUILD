# Maintainer: emersion <contact@emersion.fr>
pkgname=browserpass
pkgver=1.0.2
pkgrel=2
pkgdesc="Chrome & Firefox browser extension for pass, a UNIX password manager"
arch=('x86_64')
url="https://github.com/dannyvankooten/browserpass"
license=('MIT')
depends=('pass')
makedepends=()
optdepends=()
source=("https://github.com/dannyvankooten/browserpass/releases/download/$pkgver/browserpass-linux64.zip")
md5sums=('SKIP')

package() {
	cd "$srcdir"

	install -D browserpass-linux64 "$pkgdir/usr/bin/browserpass"

	host_file="/usr/bin/browserpass"
	escaped_host_file=${host_file////\\/}
	sed -i -e "s/%%replace%%/$escaped_host_file/" chrome-host.json
	sed -i -e "s/%%replace%%/$escaped_host_file/" firefox-host.json

	install -D chrome-host.json "$pkgdir/etc/opt/chrome/native-messaging-hosts/com.dannyvankooten.browserpass.json"
	install -D chrome-host.json "$pkgdir/etc/chromium/native-messaging-hosts/com.dannyvankooten.browserpass.json"
	install -D firefox-host.json "$pkgdir/usr/lib/mozilla/native-messaging-hosts/com.dannyvankooten.browserpass.json"
}
