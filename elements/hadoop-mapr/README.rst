Creates images with local mirrors of MapR repositories: `core <http://package.mapr.com/releases/>`_ and `ecosystem <http://package.mapr.com/releases/ecosystem-4.x/>`_.
Installs `OpenJDK <http://http://openjdk.java.net/>`_ and `Scala <http://www.scala-lang.org/>`_.

In order to create the MapR images with the diskimage-create.sh script, use the following syntax to select the "MapR" plugin:
.. sourcecode:: bash

  sudo bash diskimage-create.sh -p mapr [-i ubuntu|centos] [-r 3.1.1|4.0.1]

NOTE: By default MapR 4.0.1 version will be used

In order to speed up image creation process you can download archives with MapR repositories and specify environment variable:
``DIB_MAPR_CORE_DEB_REPO``, ``DIB_MAPR_CORE_RPM_REPO``, ``DIB_MAPR_ECO_DEB_REPO``, ``DIB_MAPR_ECO_RPM_REPO``

For example:
.. sourcecode:: bash

  export DIB_MAPR_CORE_DEB_REPO="file://<path-to-archive>/mapr-v4.0.1GA.deb.tgz"
  export DIB_MAPR_CORE_RPM_REPO="file://<path-to-archive>/mapr-v4.0.1GA.rpm.tgz"
  export DIB_MAPR_ECO_DEB_REPO="http://<URL>/mapr-ecosystem.deb.tgz"
  export DIB_MAPR_ECO_RPM_REPO="http://<URL>/mapr-ecosystem.rpm.tgz"
  sudo -E bash diskimage-create.sh -p mapr -r 4.0.1
