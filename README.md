## This will install a Bamboo compatible Java JDK on a Rapsberry Pi 3
##
### Why ?
#### A fairly common error with remote agents:
####   https://confluence.atlassian.com/bamkb/a-remote-agent-is-loading-on-bamboo-ui-never-finishes-744326117.html
#### caused by an incompatible version of JDK on the remote agent server. (in this case the rpi).
####   https://confluence.atlassian.com/bamboo/supported-platforms-289276764.html
####
#### Proposed solution (Robert Watson , Atlassian)
#### Use the official Oracle JDK.
#### http://www.rpiblog.com/2014/03/installing-oracle-jdk-8-on-raspberry-pi.html

```bash
#Extract jdk-8-linux-arm-vfp-hflt.tar.gz to /opt directory
sudo tar zxvf jdk-8u144-linux-arm32-vfp-hflt.tar.gz -C /opt

#Set default java and javac to the new installed jdk8.
sudo update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_144/bin/javac 1
sudo update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_144/bin/java 1
sudo update-alternatives --config javac
sudo update-alternatives --config java

#Verify java and javac version
java -version
javac -version
```
