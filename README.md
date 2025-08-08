# projeto-EC2-RDS
Uma arquitetura de três camadas que recebe solicitações de consultas, via aplicativo WEB, de banco de dados MySQL, com alta disponibilidade. Foi usado Amazon VPC, Amazon EC2, Amazon RDS com implantação Multi-AZ, Amazon Cloudwatch e o Elastic Load Balancing (ELB).

Ao receber uma solicitação via WEB, o Internet Gateway encaminha ao Aplication Load Balancer (ELB) que distribue a carga entre as instâncias EC2.
As consultas retornam dados do Amazon RDS, com implantação Multi-AZ para garantir a alta disponibilidade.
O Amazon Cloudwatch faz o monitoramento das instâncias e, quando atinge utilização de CPU acima de 80%, dispara alertas para o Amazon EC2 Auto Scaling que provisiona novas instâncias para atender a demanda. Quando a utilização de CPU volta aos níveis normais, as instãncias excedentes são interrompidas automaticamente.
