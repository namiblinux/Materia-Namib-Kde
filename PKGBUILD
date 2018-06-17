# Maintainer: Bruno Pagani <archange@archlinux.org>
# Modified by Frederic2ec for Namib

pkgbase=materia-kde
pkgname=('materia-namib-kde' 'kvantum-theme-materia-namib')
pkgver=20180614
pkgrel=1
pkgdesc="Materia theme for KDE Plasma 5 with Numix color"
arch=('any')
url="https://github.com/PapirusDevelopmentTeam/${pkgbase}"
license=('GPL3')
options=('!strip')
source=(${pkgbase}-${pkgver}.tar.gz::"${url}/archive/${pkgver}.tar.gz")
sha256sums=('5bdac7c14ffa9667fe088769ccfe28640b2161531f39af4de07e9c4ead614795')

prepare() {
    cd materia-kde-${pkgver}
    # Replace color
    find ./ -type f -exec sed -i 's/01a299/d64937/g' {} \;
	find ./ -type f -exec sed -i 's/4285f4/d64937/g' {} \;
    find ./ -type f -exec sed -i 's/009688/d64937/g' {} \;
    find ./ -type f -exec sed -i 's/338dd6/d64937/g' {} \;
    
    find ./aurorae/themes/Materia-Dark -type f -exec sed -i 's/Materia Dark/Materia Namib Dark/g' {} \;
    find ./aurorae/themes/Materia-Light -type f -exec sed -i 's/Materia Light/Materia Namib Light/g' {} \;

    find ./color-schemes -type f -exec sed -i 's/Materia Dark/Materia Namib Dark/g' {} \;
    find ./color-schemes -type f -exec sed -i 's/Materia Light/Materia Namib Light/g' {} \;

    find ./konsole -type f -exec sed -i 's/Materia/Materia Namib/g' {} \;

    find ./plasma/desktoptheme/Materia -type f -exec sed -i 's/Materia Dark/Materia Namib Dark/g' {} \;
    find ./plasma/desktoptheme/Materia/metadata.desktop -type f -exec sed -i 's/Materia/Materia Namib/g' {} \;

    find ./plasma/look-and-feel/com.github.varlesh.materia/contents/defaults -type f -exec sed -i 's/ColorScheme=Materia Dark/ColorScheme=Materia Namib Dark/g' {} \;
    find ./plasma/look-and-feel/com.github.varlesh.materia/contents/defaults -type f -exec sed -i 's/name=Materia/name=Materia Namib/g' {} \;
    find ./plasma/look-and-feel/com.github.varlesh.materia/contents/defaults -type f -exec sed -i 's/theme=__aurorae__svg__Materia-Dark/theme=__aurorae__svg__Materia-Namib-Dark/g' {} \;

    find ./plasma/look-and-feel/com.github.varlesh.materia/metadata.desktop -type f -exec sed -i 's/Comment=Materia Style/Comment=Materia Namib Style/g' {} \;
    find ./plasma/look-and-feel/com.github.varlesh.materia/metadata.desktop -type f -exec sed -i 's/Name=Materia/Name=Materia Namib/g' {} \;

    find ./yakuake/skins/materia-dark/tabs.skin -type f -exec sed -i 's/Skin=Materia Dark/Skin=Materia Namib Dark/g' {} \;
    find ./yakuake/skins/materia-dark/title.skin -type f -exec sed -i 's/Skin=Materia Dark/Skin=Materia Namib Dark/g' {} \;
   
    find ./yakuake/skins/materia/tabs.skin -type f -exec sed -i 's/Skin=Materia/Skin=Materia Namib/g' {} \;
    find ./yakuake/skins/materia/title.skin -type f -exec sed -i 's/Skin=Materia/Skin=Materia Namib/g' {} \;
    
    # Move file and folder
    mv aurorae/themes/Materia-Dark/Materia-Darkrc aurorae/themes/Materia-Dark/Materia-Namib-Darkrc
    mv aurorae/themes/Materia-Light/Materia-Lightrc aurorae/themes/Materia-Light/Materia-Namib-Lightrc
    mv aurorae/themes/Materia-Dark aurorae/themes/Materia-Namib-Dark
    mv aurorae/themes/Materia-Light aurorae/themes/Materia-Namib-Light

    mv color-schemes/MateriaDark.colors color-schemes/MateriaNamibDark.colors
    mv color-schemes/MateriaLight.colors color-schemes/MateriaNamibLight.colors

    mv konsole/Materia.colorscheme konsole/MateriaNamib.colorscheme
    mv konsole/MateriaDark.colorscheme konsole/MateriaNamibDark.colorscheme

    mv Kvantum/Materia/Materia.kvconfig Kvantum/Materia/MateriaNamib.kvconfig
    mv Kvantum/Materia/Materia.svg Kvantum/Materia/MateriaNamib.svg
    mv Kvantum/MateriaDark/MateriaDark.kvconfig Kvantum/MateriaDark/MateriaNamibDark.kvconfig
    mv Kvantum/MateriaDark/MateriaDark.svg Kvantum/MateriaDark/MateriaNamibDark.svg
    mv Kvantum/MateriaLight/MateriaLight.kvconfig Kvantum/MateriaLight/MateriaNamibLight.kvconfig
    mv Kvantum/MateriaLight/MateriaLight.svg Kvantum/MateriaLight/MateriaNamibLight.svg
    mv Kvantum/Materia Kvantum/MateriaNamib
    mv Kvantum/MateriaDark Kvantum/MateriaNamibDark
    mv Kvantum/MateriaLight Kvantum/MateriaNamibLight

    mv plasma/desktoptheme/Materia plasma/desktoptheme/MateriaNamib
    mv yakuake/skins/materia yakuake/skins/materia-namib
    mv yakuake/skins/materia-dark yakuake/skins/materia-namib-dark
}

package_materia-namib-kde() {
    optdepends=('materia-namib-gtk-theme: Matching GTK theme'
                'kvantum-theme-materia-namib: Materia theme for Kvantum Qt style (recommended)')

    cd ${pkgbase}-${pkgver}
    install -d "${pkgdir}"/usr/share

    cp -r plasma "${pkgdir}"/usr/share
    cp -r aurorae "${pkgdir}"/usr/share
    cp -r color-schemes "${pkgdir}"/usr/share
    cp -r konsole "${pkgdir}"/usr/share
    cp -r yakuake "${pkgdir}"/usr/share
}

package_kvantum-theme-materia-namib() {
    pkgdesc="Materia theme for KDE Plasma 5"
    depends=('kvantum-qt5')

    cd ${pkgbase}-${pkgver}
    install -d "${pkgdir}"/usr/share

    cp -r Kvantum "${pkgdir}"/usr/share
}
