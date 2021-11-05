# homework_depolymemnt_pipeline
## pipeline objectives:
  * (Build) create a docker package for the following artifacts:
    * python flask app
    * nginx reverse proxy
  * (IasC) create an infrastructure for deployment on AWS consisting of:
    * 1 vpc
    * 2 subnets
      * 1 private
      * 1 public
    * 1 igw
    * 1 eip
    * 2 route tables
    * 1 nat gw (ngw)
    * appropriate security groups
    * 2 ec2 instances
      * nginx reverse proxy (rev_prox)
        * 2 interfaces
          * frontend interface
          * backend interface
      * python app (app)
        * 1 interface
          * backend interface
    * 1 s3 bucket
  * (Config Mgmt) use ansible to perform the following configs on ec2 instances:
    * rev_prox
      * install docker engine
      * pull nginx image artifact from github package repo
      * copy ssl key pairs from s3 bucket onto ec2 instance
      * deploy a container from the nginx image using a docker-compose file
    * app
      * install docker engine
        * ```apt install docker.io```
      * pull app image artifact from github package repo
        * ```docker pull ghcr.io/glitch2k/homework_nginx:main```
      * deploy a container from the app image using a docker-compose file
        * ```docker-compose up -d```