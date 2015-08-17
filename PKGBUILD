# Maintainer: James Bulmer <nekinie@gmail.com>

pkgname="nova-deb"
pkgver=2014.1
pkgrel=1
pkgdesc="Openstack compute"
arch=("i686" "x86_64")
url="http://docs.openstack.org/developer/nova/"
license=("Apache")
groups=("openstack-deb")

depends=(
  "python2"
  "python2-pbr"
  "python2-sqlalchemy"
  "python2-amqplib"
  "python2-anyjson"
  "python2-boto"
  "python2-eventlet"
  "python2-jinja"
  "python2-kombu"
  "python2-lxml"
  "python2-routes"
  "python2-webob"
  "python2-greenlet"
  "python2-paste"
  "python2-paste-deploy"
  "python2-openstack-migrate"
  "python2-netaddr"
  "python2-suds"
  "python2-paramiko"
  "python2-pyasn1"
  "python2-babel"
  "python2-iso8601"
  "python2-jsonschema"
  "python2-cinderclient"
  "python2-neutronclient"
  "python2-glanceclient"
  "python2-keystoneclient"
  "python2-novaclient"
  "python2-six"
  "python2-stevedore"
  "websockify"
  "python2-wsgiref"
  "python2-oslo-config"
  "python2-pycadf"
  "python2-oslo-messaging"
  "python2-oslo-rootwrap"
)

optdepends=(
  "libvirt: virtualization support"
  "libvirt-python: virtualization support"
)

makedepends=("python2-setuptools")
conflicts=("nova", "openstack-nova-git")
source=("http://archive.ubuntu.com/ubuntu/pool/main/n/nova/nova_${pkgver}.orig.tar.gz")
md5sums=("b32fc758e851efe1815355930fcb815f")


build() {
  cd "${srcdir}/nova-${pkgver}/"
  python2 setup.py build
}

package() {
  cd "${srcdir}/nova-${pkgver}/"
  python2 setup.py install --root="${pkgdir}/" --optimize=1
  mkdir "${pkgdir}/etc/"
  cp -a "etc/nova" "${pkgdir}/etc/nova"
}