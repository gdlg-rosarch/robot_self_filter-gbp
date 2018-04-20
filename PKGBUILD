# Script generated with Bloom
pkgdesc="ROS - Filters the robot's body out of point clouds."
url='http://ros.org/wiki/robot_self_filter'

pkgname='ros-kinetic-robot-self-filter'
pkgver='0.1.30_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('assimp'
'bullet'
'ros-kinetic-catkin'
'ros-kinetic-filters'
'ros-kinetic-pcl-ros'
'ros-kinetic-resource-retriever'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-visualization-msgs'
)

depends=('assimp'
'bullet'
'ros-kinetic-filters'
'ros-kinetic-pcl-ros'
'ros-kinetic-resource-retriever'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
'ros-kinetic-urdf'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=robot_self_filter
source=()
md5sums=()

prepare() {
    cp -R $startdir/robot_self_filter $srcdir/robot_self_filter
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

