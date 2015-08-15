# Maintainer: TDY <tdy@archlinux.info>

pkgname=fonter
pkgver=1.7
pkgrel=1
pkgdesc="An interactive viewer and editor for console fonts (8x16 .fnt)"
arch=('i686' 'x86_64')
url="http://freshmeat.net/projects/fonter/"
license=('GPL')
depends=('ncurses')
install=fonter.install
source=(http://www.ibiblio.org/pub/Linux/apps/misc/fonter-1.7.tar.gz
        fonter-$pkgver.diff)
sha256sums=('3fc648b71e080479779799bfa9092b508c5d36251ee84191085ea3fd6c9599a6'
            'b0af62d414aa8adf727d5fbc7e602ab5e3a000b82eaf6364dad46e6b0393d610')

build() {
  cd "$srcdir/fonter-$pkgver"
  patch -Np1 -i ../fonter_$pkgver-9.diff
  make
}

package() {
  cd "$srcdir/fonter-$pkgver"
  install -Dm755 fonter "$pkgdir/usr/bin/fonter"
  install -Dm644 debian/fonter.1 "$pkgdir/usr/share/man/man1/fonter.1"
  install -Dm644 fonts/crakrjak.fnt "$pkgdir/usr/share/fonter/crakrjak.fnt"
  install -Dm644 fonts/elite.fnt "$pkgdir/usr/share/fonter/elite.fnt"
  install -Dm644 fonts/ledfont.fnt "$pkgdir/usr/share/fonter/ledfont.fnt"
  install -Dm644 fonts/sloppy.fnt "$pkgdir/usr/share/fonter/sloppy.fnt"
  install -Dm644 docs/FONT_CREDITS "$pkgdir/usr/share/doc/fonter/FONT_CREDITS"
  install -Dm644 docs/NOTES "$pkgdir/usr/share/doc/fonter/F1_NOTES"
}

# vim:set ts=2 sw=2 et:
