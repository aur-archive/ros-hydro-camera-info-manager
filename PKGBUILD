# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - This package provides a C++ interface for camera calibration information."
url='http://ros.org/wiki/camera_info_manager'

pkgname='ros-hydro-camera-info-manager'
pkgver='1.11.3'
_pkgver_patch=1
arch=('any')
pkgrel=2
license=('BSD')

ros_makedepends=(ros-hydro-sensor-msgs
  ros-hydro-camera-calibration-parsers
  ros-hydro-image-transport
  ros-hydro-roscpp
  ros-hydro-roslib
  ros-hydro-catkin
  ros-hydro-rostest)
makedepends=('cmake' 'git' 'ros-build-tools'
  ${ros_makedepends[@]}
  boost)

ros_depends=(ros-hydro-image-transport
  ros-hydro-roscpp
  ros-hydro-sensor-msgs
  ros-hydro-roslib
  ros-hydro-camera-calibration-parsers)
depends=(${ros_depends[@]}
  boost)

_tag=release/hydro/camera_info_manager/${pkgver}-${_pkgver_patch}
_dir=camera_info_manager
source=("${_dir}"::"git+https://github.com/ros-gbp/image_common-release.git"#tag=${_tag})
md5sums=('SKIP')

build() {
  # Use ROS environment variables
  /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/hydro/setup.bash ] && source /opt/ros/hydro/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/hydro \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
