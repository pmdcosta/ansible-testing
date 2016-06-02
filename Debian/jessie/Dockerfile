FROM debian:8
MAINTAINER Pedro Costa

# Users: root & ansible
# Password: ansible
RUN apt-get update && apt-get upgrade -y && \
	usermod --password XT7/q1XkHlXSs root && \
	useradd --password XT7/q1XkHlXSs --create-home --groups users ansible && \
	apt-get install -y python && \
	apt-get install -y sudo && \
	echo 'ansible	ALL=(ALL)	NOPASSWD: ALL' >> /etc/sudoers && \
	apt-get install -y openssh-server && \
	/etc/init.d/ssh start && /etc/init.d/ssh stop && \
	apt-get clean && \
	echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]