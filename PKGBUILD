# Maintainer: Rxt01 <rxt012713@proton.me>

pkgname=rxtdwm
_pkgname=dwm
pkgver=6.2.r6.9bce143
pkgrel=1
epoch=1
pkgdesc="My dwm - dynamic window manager"
url='https://github.com/rxt01/dwm'
arch=('i686' 'x86_64')
license=('MIT')
options=('zipman')
depends=('libxft')
makedepends=('git')
optdepends=('python-pywal: make the colors fit with wallpaper')
source=('git+https://github.com/rxt01/dwm')
sha1sums=('SKIP')


provides=("${_pkgname}")
conflicts=("${_pkgname}")


pkgver() {
	cd "${_pkgname}"
	printf "%s.r%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" \
		"$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}


package() {
	cd "${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	make DESTDIR="${pkgdir}" install-font
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}




