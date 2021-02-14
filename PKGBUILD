pkgname=dwm-wolfhechel
pkgver=r1694.491026c
pkgrel=1
pkgdesc="Fork of suckless dwm"
url="https://github.com/wolfhechel/dwm.git"
arch=('i686' 'x86_64')
license=('MIT')
depends=('libx11' 'libxinerama' 'libxft' 'freetype2' 'rxvt-unicode' 'rofi')
provides=('dwm')
conflicts=('dwm')
source=(
    config.h
    drw.c
    drw.h
    dwm.1
    dwm.c
    util.c
    util.h
    config.mk
    Makefile
    LICENSE
    README
    dwm.desktop
)

sha1sums=('458d4edf760c2649f309d238a90967c6fc34c984'
          'c9e5548a5e17ddad34a86a4183bd77405ab6f198'
          '3a2561a541689ad41f1e195a631946db6f6cee1d'
          'fcb56718af585b34ad7d082be1cd1743edfa30cd'
          'ac5b053417b1b41d7962c664ba524fac490cdf2f'
          'fa2d06bbede3c84e95e292e35a0a1438c4f42ea5'
          'cd8778bfef80985633469bd4fdb415f33cad8e66'
          'e661c9c2a5d9cc7b0e736d2af417055591fd089b'
          '594221400a81f269eddd57dd86b4073251fb6815'
          'fc74573a10e20e86d7da8a2d030843f374f7e775'
          '93cfab1e54ab47b67226ba6ec3d11e773cf98056'
          '9dc7ba48e3270d0e6273b4f3ca7d22cb1eb1599b')

pkgver() {
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2 VERSION=`pkgver`
}

package() {
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname/README"
  install -m644 -D "$srcdir/dwm.desktop" "$pkgdir/usr/share/xsessions/dwm.desktop"
}
