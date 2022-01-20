# docker-ansible
  This repo is about provisioning docker with ansible.
  This repository contains two roles:

  - docker-latest: which installs latest docker release
  - docker-compose: which installs docker compose
  
  There are two main yaml files:
  - install-docker.yaml : will refer to docker-latest role
  - install-docker-compose.yaml : will refer to docker-compose role

# what is Ansible?

![image](https://user-images.githubusercontent.com/16374030/150411459-de785816-92bb-4165-a69d-d3343e8b3ace.png)

Ansible is a software tool that provides simple but powerful automation for cross-platform computer support. 
It is primarily intended for IT professionals, who use it for application deployment, updates on workstations 
and servers, cloud provisioning, configuration management, intra-service orchestration, and nearly anything a 
systems administrator does on a weekly or daily basis. Ansible doesn't depend on agent software and has no 
additional security infrastructure, so it's easy to deploy.Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications. By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

# what is docker?

![image](https://user-images.githubusercontent.com/16374030/150411735-a0938f7e-de79-4d36-9452-f99f9ac99df2.png)

Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate 
your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage 
your infrastructure in the same ways you manage your applications. By taking advantage of Docker’s methodologies
for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.
