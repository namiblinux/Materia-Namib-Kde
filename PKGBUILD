# Maintainer: Bruno Pagani <archange@archlinux.org>
# Modified by Frederic2ec for Namib

pkgbase=materia-kde
pkgname=('materia-kde' 'kvantum-theme-materia')
pkgver=20180614
pkgrel=1
pkgdesc="Materia theme for KDE Plasma 5"
arch=('any')
url="https://github.com/PapirusDevelopmentTeam/${pkgbase}"
license=('GPL3')
options=('!strip')
source=(${pkgbase}-${pkgver}.tar.gz::"${url}/archive/${pkgver}.tar.gz")
sha256sums=('5bdac7c14ffa9667fe088769ccfe28640b2161531f39af4de07e9c4ead614795')

package_materia-kde() {
    optdepends=('materia-gtk-theme: Matching GTK theme'
                'kvantum-theme-materia: Materia theme for Kvantum Qt style (recommended)')

    cd ${pkgbase}-${pkgver}
    install -d "${pkgdir}"/usr/share

    cp -r plasma "${pkgdir}"/usr/share
    cp -r aurorae "${pkgdir}"/usr/share
    cp -r color-schemes "${pkgdir}"/usr/share
    cp -r konsole "${pkgdir}"/usr/share
    cp -r yakuake "${pkgdir}"/usr/share
}

package_kvantum-theme-materia() {
    pkgdesc="Materia theme for KDE Plasma 5"
    depends=('kvantum-qt5')

    cd ${pkgbase}-${pkgver}
    install -d "${pkgdir}"/usr/share

    cp -r Kvantum "${pkgdir}"/usr/share
}
