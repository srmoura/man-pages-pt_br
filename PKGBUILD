# Maintainer: Gabriel Moura <g@srmoura.com.br>

pkgname=man-pages-pt_br
pkgver=2015.11.09
pkgrel=1
pkgdesc="Brazilian Portuguese collection of manpages"
arch=('any')
license=('GPL')
url="http://br.tldp.org/projetos/man/man.html"
makedepends=("rpmextract")
depends=('man-pages')
source=('ftp://bo.mirror.garr.it/1/mageia/distrib/6/x86_64/media/core/release/man-pages-pt_BR-0.1-15.mga6.noarch.rpm' 'http://mandriva.c3sl.ufpr.br/official/current/i586/media/main/release/man-pages-pt_BR-0.1-6mdv2010.0.noarch.rpm')
md5sums=('SKIP' 'SKIP')

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
  cp -r $srcdir/usr/share/man/pt_BR/* $pkgdir/usr/share/man/pt_BR
  chown -R root:root $pkgdir/usr
}
post_install=mandb
