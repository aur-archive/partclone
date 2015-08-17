# Maintainer: jsteel <mail at jsteel dot org>
# Contrinutor: Dan Serban
# Contributor: Franz Burgmann
# Contributor: Todd Partridge (Gen2ly)
# Contributor: Ivan Sichmann Freitas

pkgname=partclone
pkgver=0.2.48
pkgrel=4
pkgdesc="Back up and restore used-blocks of a partition"
arch=('i686' 'x86_64')
url="http://partclone.org"
license=('GPL')
depends=('progsreiserfs' 'ntfs-3g')
conflicts=('partclone-testing' 'partclone-git')
source=(https://downloads.sourceforge.net/project/$pkgname/stable/$pkgver/${pkgname}_$pkgver.tar.gz)
md5sums=('c873588f26185d6ce8db7b4c5470aa00')

build() {
  cd "$srcdir"/$pkgname-$pkgver

  ./configure --prefix=/usr --enable-extfs --enable-reiserfs --enable-fat \
    --enable-hfsp --enable-btrfs --enable-ncursesw --enable-ntfs

  make
}

package() {
  cd "$srcdir"/$pkgname-$pkgver

  make DESTDIR="$pkgdir" install
}

