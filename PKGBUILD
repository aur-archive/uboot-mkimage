# Maintainer: Michael Lass <bevan@bi-co.net>
# Contributor: Philipp Schrader <philipp.schrader+arch@gmail.com>
pkgname=uboot-mkimage
pkgver=2014.10
pkgrel=1
pkgdesc="U-Boot mkimage utility, which encapsulates a compressed uImage Linux kernel image with header information, CRC32 checksum, etc, for use with the U-Boot bootloader"
arch=('i686' 'x86_64')
url="http://www.denx.de/wiki/U-Boot/WebHome"
license=('GPL')
depends=('glibc')

source=(ftp://ftp.denx.de/pub/u-boot/u-boot-${pkgver}.tar.bz2)
md5sums=('3ddcaee2f05b7c464778112ec83664b5')

build() {
  cd "$srcdir/u-boot-${pkgver}"

  # Build tools only
  make defconfig
  make tools-only
}

package() {
  install -Dm 755 $srcdir/u-boot-${pkgver}/tools/mkimage $pkgdir/usr/bin/mkimage
  install -Dm 644 $srcdir/u-boot-${pkgver}/doc/mkimage.1 $pkgdir/usr/share/man/man1/mkimage.1
}
