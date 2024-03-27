# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_offline="false"
_git="false"
pkgname=media-tools
pkgver=0.0.0.1.1.1
pkgrel=1
_pkgdesc=(
  "A collection of media manipulation scripts."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  any
)
_http="https://github.com"
_ns="themartiancompany"
url="${_http}/${_ns}/${pkgname}"
license=(
  AGPL3
)
depends=(
  "ffmpeg"
)
_os="$( \
  uname \
    -o)"
optdepends=(
)
[[ "${_os}" != "GNU/Linux" ]] && \
[[ "${_os}" == "Android" ]] && \
  optdepends+=(
  )
makedepends=()
checkdepends=(
  "shellcheck"
)
source=()
sha256sums=()
_url="${url}"
[[ "${_offline}" == "true" ]] && \
  url="file://${HOME}/${_pkgname}"
[[ "${_git}" == true ]] && \
  makedepends+=(
    "git"
  ) && \
  source+=(
    "${pkgname}-${pkgver}::git+${_url}#tag=${pkgver}"
  ) && \
  sha256sums+=(
    SKIP
  )
[[ "${_git}" == false ]] && \
  source+=(
    "${pkgname}-${pkgver}.tar.gz::${_url}/archive/refs/tags/${pkgver}.tar.gz"
  ) && \
  sha256sums+=(
    '0b69f3e620beb0925eabff7739593285fbe1e4527d98467464154031cae66ab6'
  )

check() {
  cd \
    "${pkgname}i-${pkgver}"
  make \
    -k \
    check
}

package() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    PREFIX="/usr" \
    DESTDIR="${pkgdir}" \
    install
}

# vim: ft=sh syn=sh et
