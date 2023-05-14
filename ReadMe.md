Step 1
gcloud auth login
gcloud source repos create [REPOSITORY_NAME]
gcloud source repos clone [REPOSITORY_NAME]
push app to repo, you can see repo <img src="media/source_repo.png">
docker build -t [DOCKER_IMAGE_NAME] .
docker tag [DOCKER_IMAGE_NAME] us-central1-docker.pkg.dev/[PROJECT_ID]/[REPOSITORY_NAME]/[DOCKER_IMAGE_NAME]:[TAG]
gcloud auth configure-docker us-central1-docker.pkg.dev
docker push us-central1-docker.pkg.dev/[PROJECT_ID]/[REPOSITORY_NAME]/[DOCKER_IMAGE_NAME]:[TAG]
![artifact.png](media/artifact.png)
Test result:
![test_image.png](media/test_image.png)

Step 2
Trigger for pipeline
![trigger.png](media/trigger.png)

Step 3
