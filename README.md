# magento_on_gke
Deploy Magento on GKE with Cloud SQL for MySQL as the database and Memorystore Redis for cache and session management.

####################Redis##########################
Provide the Redis private IP address in the env.php configmap

####################CloudSQL for MySQL############

CloudSQL will be connected through private ip address
 - create a user 
 - provide privileges
 - Use this username and password in the env.php configmap file 
example :-
        - CREATE USER 'dev_user'@'%' IDENTIFIED BY 'sasGraDeHJ0mK1vP';
        - GRANT ALL ON db_dbname.* TO 'dev_user'@'%';

######################Ingress#######################

Ingress annotation "kubernetes.io/ingress.global-static-ip-name" needs a static ip address name which has to reserved on GCP. Make sure it is a global IP to make it accessible accross the world.


