#### When activo images namely `activo-api_app` and `activo-web_web` are started they spawn up 5 containers all together. 
The `activo-api_app` image creates:
 - activo-api_celery_flower_1 container. This is used to schedule tasks.
 - activo-api_app_1 container. This holds the back-end application functionality
 - activo-api_database_1 container. This holds applications data in relational tables
 - activo-api_redis_1 container. This is used for perform data backups



#### Image link
- https://drive.google.com/file/d/1bh4bkPO46Y_h_e0QwvJIW2Til3nIYukd/view?usp=sharing


The `activo-web_web` image creates:
- activo-web_web container. The container contains the frontend functionality of the application.

#### Image Link
- https://drive.google.com/file/d/1ZWS_cnza40rtOL2T5F2ib57tYJeOnEBP/view?usp=sharing


The above demonstration is on development environment but on staging and production there is a change in the workflow.

On staging, the environment is on a gcp cluster `activo-staging` this bundles up the `activo-api-staging` and the `activo-web-staging` containers. The *activo-api-staging* and *activo-web-staging* are deployed when either a feature, chore or bug branch has been successfully merged into develop, then the codebase on branch develop is deployed to the staging container with help of the set pipeline on Circle CI. The pipeline runs on a container that is set to work with circle CI configuration created.

#### Images
##### Circle CI workflow that deploys to staging.
1.[The web](https://drive.google.com/file/d/1xqk-hyeYBTwtM22SWHkEunLncMTytaed/view?usp=sharing)

2.[The api](https://drive.google.com/file/d/1Oha6SSDjF0_w6HGxAhpS1oD4buE214Aj/view?usp=sharing)



On production, the containers run on the `activo-production` cluster. The cluster comprises of the `activo-api-production` and `activo-web-production`. This containers are deployed with the help of the set pipeline on circle ci container. When a PR from branch develop is merged into master. The pipeline workflow changes to deploy the updated codebase on master to production for both the api and the web.

#### Images
##### Circle CI workflow that deploys to production
1.[The api](https://drive.google.com/file/d/1PmaNn1E2_6ch8kB0AsOhuI6noPaI69x-/view?usp=sharing)

2.[The web](https://drive.google.com/file/d/12Xq2fH_B3Q6T0aHnVADYodZy4CNSp97h/view?usp=sharing)



##### Images to circle CI configuration that helps with the deployment

1. activo-api-configuration: 
- https://drive.google.com/file/d/1IcnbgbM-4Cglp6tGYK6BTkKQaMYg00Rj/view?usp=sharing
- https://drive.google.com/file/d/1M3x9cqxQRAL_N12FXZUjBiWyohU8R_aj/view?usp=sharing
- https://drive.google.com/file/d/1Lninj1URYlY2uvCOMQ4j35OJ-SFnJYHg/view?usp=sharing
- https://drive.google.com/file/d/1OxN9HaQGwa6gOXJQE5C8LRn97X2UHPD8/view?usp=sharing


2. activo-web-configuration
- https://drive.google.com/file/d/17QMtWJBUOV4T75BAoQSF9kdZejOfKnyV/view?usp=sharing
- https://drive.google.com/file/d/1vV2ckxdRhC0JfKDlmTuUDuXr7pvZLQSE/view?usp=sharing
- https://drive.google.com/file/d/1-X_ri3jwzcYFgPZ4Ne6VLIRfpZuDuUOw/view?usp=sharing

