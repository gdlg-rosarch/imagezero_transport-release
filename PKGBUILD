# Script generated with Bloom
pkgdesc="ROS - A plugin to image_transport for transparently sending images encoded with ImageZero."
url='http://www.ros.org/wiki/image_transport_plugins'

pkgname='ros-lunar-imagezero-image-transport'
pkgver='0.2.4_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-cv-bridge'
'ros-lunar-image-transport'
'ros-lunar-imagezero-ros'
'ros-lunar-message-runtime'
'ros-lunar-sensor-msgs'
)

depends=('ros-lunar-cv-bridge'
'ros-lunar-image-transport'
'ros-lunar-imagezero-ros'
'ros-lunar-message-runtime'
'ros-lunar-sensor-msgs'
)

conflicts=()
replaces=()

_dir=imagezero_image_transport
source=()
md5sums=()

prepare() {
    cp -R $startdir/imagezero_image_transport $srcdir/imagezero_image_transport
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

