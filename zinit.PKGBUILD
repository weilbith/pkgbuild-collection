# shellcheck disable=SC2034

_pkgname=zinit
pkgname=${_pkgname}-git
pkgrel=1
pkgver=1
pkgdesc="Ultra-flexible and fast Zsh plugin manager"
arch=('any')
url="https://github.com/zdharma/zinit.git"
license=('MIT')
makedepends=('git')
source=("git+https://github.com/zdharma/zinit#branch=master")
sha256sums=('SKIP')

pkgver() {
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$_pkgname"
  install -D --mode=644 LICENSE "$pkgdir/usr/share/licenses/$_pkgname/LICENSE"
  install -D --mode=644 README.md "$pkgdir/usr/share/doc/$_pkgname/README.md"
  mkdir --parents "$pkgdir/usr/share/zsh/scripts/zinit"
  cp --recursive ./* "$pkgdir/usr/share/zsh/scripts/zinit/"
}

# vim: tabstop=2 shiftwidth=2 filetype=PKGBUILD
