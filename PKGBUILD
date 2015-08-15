# Maintainer: megadriver <megadriver at gmx dot com>

pkgname=emacs-visual-regexp-git
_gitname=visual-regexp.el
pkgver=27
pkgrel=1
pkgdesc="A regexp/replace command for Emacs with interactive visual feedback"
arch=('any')
url="https://github.com/benma/visual-regexp.el"
license=('GPL3')
depends=('emacs')
install=emacs-visual-regexp.install
makedepends=('git')
source=("git://github.com/benma/$_gitname.git")
md5sums=('SKIP')

pkgver() {
  cd "$_gitname"
  git rev-list --count HEAD
}

build() {
  cd "$_gitname"
  emacs -batch -f batch-byte-compile "$_gitname"
}

package() {
  cd "$_gitname"
  mkdir -p $pkgdir/usr/share/emacs/site-lisp
  install -Dm644 *.el *.elc $pkgdir/usr/share/emacs/site-lisp
}
