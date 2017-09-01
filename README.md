# This will install a Bamboo compatible Java JDK on a Rapsberry Pi 3

# Why ?
# A fairly common error with remote agents:
#   https://confluence.atlassian.com/bamkb/a-remote-agent-is-loading-on-bamboo-ui-never-finishes-744326117.html
# caused by an incompatible version of JDK on the remote agent server. (in this case the rpi).
#   https://confluence.atlassian.com/bamboo/supported-platforms-289276764.html

# Proposed solution (Robert Watson , Atlassian)
    # For my environments I use the official Oracle JDK, with the following script:
    #   sudo apt-get update
    #   sudo add-apt-repository ppa:webupd8team/java -y
    #   sudo apt-get update
    #   sudo apt-get install oracle-java8-installer -y
    # manually accept the license agreement
    #
    # the following line may change depending on linux distro
    #   sudo echo 'JAVA_HOME="/usr/lib/jvm/java-8-oracle/jre"' >> /etc/environment
    # You can also use the following to ensure the version of java used by default is the latest (in case there are multiple versions present on the server):
    #   sudo update-alternatives --config javac
    #   sudo update-alternatives --config java

# Problem : adding debian repository on arm is a big no-no
# Proposed solution : http://www.rpiblog.com/2014/03/installing-oracle-jdk-8-on-raspberry-pi.html
