# Maintainer: Elijah Gregg <lovetocode999 at tilde dot team>
gitversion=f623ad3e06d190de60b9d4ffa5f0fd91b831b66d
pkgname=halmak-git
pkgver=2.1.0.r30.gf623ad3
pkgrel=1
pkgdesc="The final version of the AI designed keyboard layout"
arch=("any")
url="https://github.com/MadRabbit/halmak"
license=("MIT")
depends=("libxkbcommon")
provides=("halmak")
conflicts=("halmak")
source=("git+https://github.com/MadRabbit/halmak.git#commit=$gitversion")
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/halmak"

    _tag=$(git tag --sort=v:refname | tail -n1)
    printf '%s.r%s.g%s' "${_tag#v}" "$(git rev-list "$_tag"..HEAD --count)" "$(git rev-parse --short HEAD)"
}

package() {
    cd "$srcdir/halmak"
    mkdir -p "${pkgdir}/usr/share/X11/xkb"
    cp -R "linux/symbols" "${pkgdir}/usr/share/X11/xkb"
    rm "${pkgdir}/usr/share/X11/xkb/symbols/halmak"
    mv "${pkgdir}/usr/share/X11/xkb/symbols/halmak_no_qwerty" "${pkgdir}/usr/share/X11/xkb/symbols/halmak"
}
