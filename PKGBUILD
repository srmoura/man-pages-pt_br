# Maintainer: Gabriel Moura <g@srmoura.com.br>

pkgname=man-pages-pt_br
pkgver=2015.11.09
pkgrel=2
pkgdesc="Brazilian Portuguese collection of manpages"
arch=('any')
license=('GPL')
url="http://br.tldp.org/projetos/man/man.html"
makedepends=("rpmextract")
depends=('man-pages')
source=('ftp://bo.mirror.garr.it/1/mageia/distrib/6/x86_64/media/core/release/man-pages-pt_BR-0.1-15.mga6.noarch.rpm' 'http://mandriva.c3sl.ufpr.br/official/current/i586/media/main/release/man-pages-pt_BR-0.1-6mdv2010.0.noarch.rpm' 'http://archive.ubuntu.com/ubuntu/pool/universe/m/manpages-pt/manpages-pt_20040726-4_all.deb')
md5sums=('c4e3b2e6ff0a0b5408b2a3008a3ec39b' '0b9477f47bc1410b3a190df82a4a8c97' '56003c5336bf4d6a1e4952b58e3bc571')

build() {
  rpmextract.sh *.rpm
}

package() {
  install -d $pkgdir/usr/share/man/pt_BR
  cd $srcdir/usr/share/man/pt_BR/man1 && unlzma *.lzma && gzip *
  cd .. && cd man2 && unlzma *.lzma && gzip *
  cd .. && cd man3 && unlzma *.lzma && gzip *
  cd .. && cd man4 && unlzma *.lzma && gzip *
  cd .. && cd man5 && unlzma *.lzma && gzip *
  cd .. && cd man6 && unlzma *.lzma && gzip *
  cd .. && cd man7 && unlzma *.lzma && gzip *
  cd .. && cd man8 && unlzma *.lzma && gzip *
  rm -r $srcdir/usr/share/man/pt_BR/man5/passwd.5.gz
rm -r $srcdir/usr/share/man/pt_BR/man{1,2,3,4,5,6,7,8}/*.xz.gz
  cp -r $srcdir/usr/share/man/pt_BR/* $pkgdir/usr/share/man/pt_BR
  chown -R root:root $pkgdir/usr
}
post_install=(mandb)
