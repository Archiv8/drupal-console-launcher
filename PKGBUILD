#!/bin/bash

# Maintainer: Stefan Auditor <stefan.auditor@erdfisch.de>
# Please report issues at https://github.com/sanduhrs/arch-aur-drupalconsole

_binname="drupal"
_cvsorg="hechoendrupal"
_pkgname="drupal-console-launcher"


pkgname=${_pkgname}
pkgver=1.9.7
pkgrel=1
pkgdesc="The Drupal Console is a suite of tools that you run on a command line interface (CLI) to generate boilerplate code and interact with a Drupal installation. This package installs the global launcher"
arch=('any')
url="http://drupalconsole.com/"
license=('GPL')
depends=('php')
makedepends=("composer")
install="${_pkgname}.install"
source=("https://github.com/${_cvsorg}/${_pkgname}/releases/download/${pkgver}/drupal.phar"
"https://raw.github.com/${_cvsorg}/${_pkgname}/${pkgver}/LICENSE.txt")
sha512sums=('ddb992e65662dbde9e48d97d5d5900e341f24da92bf1bad0cdf28690d34229d037ef02f4995c9ca83c498a84cf98e66b75d1f12206746a633f8e0db030f8ca82'
            'aee80b1f9f7f4a8a00dcf6e6ce6c41988dcaedc4de19d9d04460cbfb05d99829ffe8f9d038468eabbfba4d65b38e8dbef5ecf5eb8a1b891d9839cda6c48ee957')

package() {
  install -D -m644 "${srcdir}/LICENSE.txt" "${pkgdir}/usr/share/licenses/${_pkgname}/LICENSE.txt"
  install -D -m755 "${srcdir}/${_binname}.phar" "${pkgdir}/usr/share/webapps/bin/${_binname}.phar"
  install -d "${pkgdir}/usr/bin"
  ln -s "/usr/share/webapps/bin/${_binname}.phar" "${pkgdir}/usr/bin/${_binname}"
}
