# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Mike Dacre <mike.dacre@gmail.com>
pkgname=tophat-bin
pkgver=2.0.13
pkgrel=1
pkgdesc="A fast splice junction mapper for RNA-Seq reads. x86_64 binaries"
arch=('x86_64')
license=('PerlArtistic')
url="http://tophat.cbcb.umd.edu"
depends=('python2')
pkgfullname="tophat-$pkgver.Linux_x86_64"
source=("http://ccb.jhu.edu/software/tophat/downloads/$pkgfullname.tar.gz")
md5sums=('af0e1a34b667df56f78597138f45e661')

prepare() {
  cd "$srcdir/$pkgfullname"
  python_files="bed_to_juncs contig_to_chr_coords sra_to_solid tophat tophat-fusion-post"
  sed -i "s|#!/usr/bin/env python$|#!/usr/bin/env python2|" $python_files
}

package() {
  mkdir -p "$pkgdir/usr/bin"
  find "$srcdir/$pkgfullname" -type f -executable -exec cp {} "$pkgdir/usr/bin" \;
}
