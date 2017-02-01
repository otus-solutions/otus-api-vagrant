# Otus Api Vagrant

## Pré Requisitos
* [Vagrant](https://www.vagrantup.com/)
* [Virtual Box](https://www.virtualbox.org/)

## Recursos Disponíveis

* Mongo 
> Versão : 2.6.4
> Port : 27017
  
* Wildfly
  > Versão : 9.0.1
  > Port : 8080
  
* Java
  > Versão : 8

## Construção de box
      > $ vagrant up
      > $ vagrant package --output dist/otus-api.box
      > $ vagrant box add otus-api dist/otus-api.box
      > $ vagrant halt

## Executanto box
      > $ cd dist/
      > $ vagrant up

## Utilizando URL Customizada
Considerando que a vm esta iniciada.

      > $ vagrant ssh
      > $ ifconfig **Identificar ip da maquina**
      > $ exit
      > $ vim /etc/hosts
          {IP_VAGRANT} api-otus.localhost

      * IP_VAGRANT : Ip atribuido a VM
      * api-otus.localhost : Url que sera utilizada para acesso a VM como padrão. Customizar caso necessário.

## Realizar Deploy API
      > $ mvn -f otus-root/pom.xml clean install && mvn -f otus-ear/pom.xml wildfly:deploy -Dwildfly-hostname=api-otus.localhost

