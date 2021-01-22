FROM openshift/jenkins-slave-base-centos7

LABEL com.redhat.component="jenkins-agent-centos" \
      io.k8s.description="The jenkins agent centos image has the tools buildings RPM packages on top of the jenkins slave base image." \
      io.k8s.display-name="Jenkins Agent - CentOS7" \
      io.openshift.tags="openshift,jenkins,agent,centos" \
      architecture="x86_64" \
      name="ci/jenkins-agent-centos" \
      maintainer="Samuel MARTIN MORO <faust64@gmail.com>" \
      help="For more information visit https://github.com/faust64/docker-jenkins-agent-centos" \
      version="1.0"

# Install Build Dependencies
RUN yum -y install epel-release \
    && if test "$DO_UPGRADE"; then \
	yum -y upgrade; \
    fi \
    && yum -y install @development-tools centos-packager rpmdevtools \
    && yum -y install make wget git curl \
    && yum clean all -y \
    && rm -rf /var/cache/yum /usr/share/doc /usr/share/man

USER 1001
