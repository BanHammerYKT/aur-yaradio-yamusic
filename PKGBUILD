# Maintainer: BanHammer

pkgname=yaradio-yamusic
pkgver=1.0.6
pkgrel=1
#epoch=1

pkgdesc="Yandex Radio and Yandex Music"
arch=("x86_64")
license=("MIT")
categories=("multimedia")

options=(!strip)
url=https://github.com/dedpnd/yaradio-yamusic

provides=(yaradio-yamusic)
conflicts=(yaradio-yamusic)

source=("${pkgname}-${pkgver}.deb::https://github.com/dedpnd/yaradio-yamusic/releases/latest/download/yaradio-yamusic_${pkgver}_amd64.deb")
md5sums=("SKIP")

prepare() {
    tar -xf data.tar.xz
}

package() {
    cp -dr --no-preserve=ownership opt usr "${pkgdir}"/
    sed -i 's/Categories=Audio/Categories=AudioVideo/g' "${pkgdir}"/usr/share/applications/yaradio-yamusic.desktop
    sed -i 's/Name=YaMusic.app/Name=YaMusic/g' "${pkgdir}"/usr/share/applications/yaradio-yamusic.desktop
    install -D -m0644 "${pkgdir}"/usr/share/icons/hicolor/0x0/apps/${pkgname}.png "${pkgdir}"/usr/share/pixmaps/${pkgname}.png
}