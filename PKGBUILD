# Maintainer: Philipp A. <flying-sheep@web.de>
# Contibutor: Mathieu OTHACEHE <m.othacehe@gmail.com>

pkgname=sencha-cmd-6
pkgver=6.5.1
pkgrel=1
pkgdesc='Sencha Cmd provides a collection of powerful, time-saving features that work together and in conjunction with the Sencha Ext JS and Sencha Touch frameworks'
url='https://www.sencha.com/products/extjs/cmd-download/'
arch=('x86_64')
license=('custom: commercial')
depends=('java-runtime' 'ttf-font' 'fontconfig')
provides=('sencha-cmd')
conflicts=('sencha-cmd' 'sencha-cmd-5')
source_x86_64=("http://cdn.sencha.com/cmd/$pkgver/no-jre/SenchaCmd-$pkgver-linux-amd64.sh.zip")
sha512sums_x86_64=('c528eca3dfa325657543fca60a8e5563b17f9c7215dfc5038ad54032dc4dbdfd1348b624e7e36ecc3d512bc01f186704e56bc0310dc4c0b6dbff87be63098d19')

build() {
	#tail -c 1397056  SenchaCmd-$pkgver.*-linux-amd64.sh > sfx_archive.tar.gz
	bash SenchaCmd-$pkgver.*-linux-amd64.sh -q \
		-Dall=true \
		-V'addToPath$Integer'=1 \
		-dir "$srcdir/$pkgname-$pkgver"
}

package() {
	install -d "$pkgdir/opt/Sencha"
	mv "$pkgname-$pkgver" "$pkgdir/opt/Sencha/Cmd"
	
	install -dm777 "$pkgdir/var/cache/sencha-repo"
	ln -s /var/cache/sencha-repo "$pkgdir/opt/Sencha/repo"
	
	install -d "$pkgdir/usr/bin/"
	ln -s /opt/Sencha/Cmd/sencha "$pkgdir/usr/bin/sencha"
}
