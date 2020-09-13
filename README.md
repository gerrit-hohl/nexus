# nexus

This project is part of the tutorial [Installing Nexus artifact repository](http://gerrit-hohl.users.sourceforge.net/cheatsheets/0006_installing_nexus_artifact_repository.html).

Check out the project and perform a Maven build using the ``clean package``. If
you want you also can create the site to see if any plug-ins need to be updated:
``clean package site``.

You should get an error message that the Nexus archive is missing and were the
build expects it. Maybe you also have to adapt the ``pom.xml`` to the Nexus
version for which you want to build the Debian package. This also includes the
dependency on the Java version, as currently the dependency is on Java 1.8.

As Nexus is a Java application / service, it is architecture independent, as
long as a matching Java runtime is provided.

You also should compare the files in the ``src/main/config`` folder, namely:

* ``nexus`` - The script for the service.  
  See ``bin/nexus`` within the Nexus archive.
* ``nexus.properties`` - The properties of Nexus.  
  See ``etc/nexus-default.properties`` within the Nexus archive.
* ``nexus.rc`` - The file which tells the service which user to use.  
  See ``bin/nexus.rc`` within the Nexus archive.
* ``nexus.vmoptions`` - The Java VM options of the service.  
  See ``bin/nexus.vmoptions`` within the Nexus archive.

Maybe they also have changed between the version of the project and the version
of Nexus you want to use.
