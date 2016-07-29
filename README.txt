Otus API

1º Iniciar Vagrant API Otus
   $ vagrant up

2º Realizar Deploy API
   $ mvn -f otus-root/pom.xml clean install  && mvn -f otus-ear/pom wildfly:deploy

3º Atribuir Url
   $ vim /etc/hosts
      {IP_VAGRANT} {URL}

   IP_VAGRANT : Ip atribuido a VM
   URL        : Url que sera utilizada para acesso a VM


