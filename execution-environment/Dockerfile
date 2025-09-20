FROM quay.io/ansible/awx-ee:latest

# Usuário root para instalar pacotes extras
USER 0
RUN dnf install -y git python3-pip && dnf clean all

# Copia e instala collections do requirements.yml
COPY requirements.yml /tmp/requirements.yml
RUN ansible-galaxy collection install -r /tmp/requirements.yml --collections-path /usr/share/ansible/collections

# Volta para usuário padrão do runner
USER 1000
