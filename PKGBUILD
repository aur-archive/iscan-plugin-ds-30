# Maintainer: ItsTheSource <itsthesource at gmail dot com>
# Contributor: ItsTheSource <itsthesource at gmail dot com>

pkgname=iscan-plugin-ds-30
pkgver=1.0.0
pkgrel=3
pkgdesc="iscan plugin for Epson WorkForce DS-30"
arch=('i686' 'x86_64')
url="http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX"
license=('custom:AVASYSPL')
depends=('iscan-data' 'iscan')
install=ds-30.install
changelog=ChangeLog

if [ "$CARCH" = "i686" ]; then
  _ARCH=i386
  source=("http://a1227.g.akamai.net/f/1227/40484/7d/download.ebz.epson.net/dsc/f/01/00/01/84/60/9018908ffd7a0ecab2dc54cef547f8cbfc0dfee2/$pkgname"_"$pkgver-3_$_ARCH.deb")
  md5sums=('c82053dee50e1853e0d743eb1ac6f82a')
elif [ "$CARCH" = "x86_64" ]; then
  _ARCH=amd64
  source=("http://a1227.g.akamai.net/f/1227/40484/7d/download.ebz.epson.net/dsc/f/01/00/01/84/60/6af6aa32b61c47a3722bebb35d824c899d28ab51/$pkgname"_"$pkgver-3_$_ARCH.deb")
  md5sums=('c29a43ac31608411a3bb64999fbb4c8e')
fi

build(){
  cd $srcdir
  ar vx $pkgname"_"$pkgver-3_$_ARCH.deb
  tar -zxvf data.tar.gz
}

package(){
  install -d $pkgdir/usr/lib/iscan
  install -m755 $srcdir/usr/lib/iscan/libiscan-plugin-ds-30.so.0.0.0 $pkgdir/usr/lib/iscan/
  install -m755 $srcdir/usr/lib/iscan/libiscan-plugin-ds-30.so.0 $pkgdir/usr/lib/iscan/
  install -m755 $srcdir/usr/lib/iscan/libiscan-plugin-ds-30.so $pkgdir/usr/lib/iscan/
  install -d $pkgdir/usr/share/licenses/$pkgname/
  install -m644 $srcdir/usr/share/doc/$pkgname/{AVASYSPL.en.txt,AVASYSPL.ja.txt,copyright} $pkgdir/usr/share/licenses/$pkgname/
}

