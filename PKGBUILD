# Maintainer: Jiri Pospisil <jiri@jpospisil.com>

pkgname=marcel
pkgver=0.27.2
pkgrel=1
pkgdesc='A modern shell'
url='https://github.com/geophile/marcel'
source=("https://github.com/geophile/marcel/archive/refs/tags/v$pkgver.tar.gz")
arch=('any')
depends=('python' 'python-dill' 'python-psutil')
makedepends=(
  'python-build'
  'python-installer'
  'python-wheel'
  'python-setuptools'
)
license=('GPL-3.0-only')
b2sums=('e3ca0a0520529eef4afc7e2c47139aa8d86766cebb2aa978d67ac709578e327351086399f91a706b1d06d1a2580f996727f11e77b462d176fa92c16afe3b3d83')

prepare() {
  cd marcel-"$pkgver"
  rm -rf 'test'
}

build() {
  cd marcel-"$pkgver"
  python -m build --wheel --no-isolation
}

package() {
  cd marcel-"$pkgver"
  python -m installer --destdir="$pkgdir" dist/*.whl
}
