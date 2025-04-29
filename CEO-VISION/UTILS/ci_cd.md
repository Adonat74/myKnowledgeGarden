### **Overview: Docker and Podman Workflow**

1. **Dockerfile and Image Building:**
   - You are working with containers and using a `Dockerfile` to build images. Each container has its own image, which can be built using a specific `docker build` or `podman build` command.
   - The `COPY` command in your `Dockerfile` is used to add files or directories from your local machine (or build context) into the image during the build process.
   - **Issue with large file copying:** If the file being copied (like `sources/files/`) is too large, the build might fail, especially if there’s not enough space on the machine.

2. **Podman and Podman-Compose:**
   - **Podman** is an alternative to Docker that you are using for container management. `podman-compose` works similarly to Docker Compose but with Podman.
   - **`podman-compose` up** starts up containers based on a `docker-compose.yml` file, and will pull images, create networks, and start containers accordingly.

3. **CI/CD in GitLab:**
   - GitLab CI/CD allows you to define a pipeline for automating the build, test, and deployment of your containers.
   - During the pipeline, you define how the images are built (using the `Dockerfile`) and pushed to a registry (like GitLab's registry).

4. **Image Field in `docker-compose.yml`:**
   - The `image:` field in the `docker-compose.yml` file specifies which image to use for a service.
     - **With a tag:** `image: registry.gitlab.com/your-project/ceov-web-ng-drupal:your-tag` pulls the image from the registry (if not present locally).
     - **Without a tag:** The image will be pulled from the registry, and if no tag is provided, the default `latest` tag is assumed.
   - You can also leave it empty or use a locally available image, and it will use the local image without pulling from the registry.

5. **Image Management:**
   - **First Push:** When you first push an image to the registry (like GitLab), you can reference that image in the `docker-compose.yml` using the `image:` field. After the first push, you can let the pipeline pull the image during the build.
   - **Subsequent Pushes:** Every time you push a new version (with a different tag) of the image to the registry, GitLab CI/CD will pull the updated image, replacing the old version automatically.
   - **Local Images:** If you don't want to push images to the registry every time, you can pull them manually to the server (using `podman pull` or `docker pull`) and reference them in the `docker-compose.yml`. In this case, Docker or Podman will use the local image, and if it's not found, it will try to pull from the registry.

6. **Steps to Streamline the Workflow:**
   - **First Push:**
     1. Build the image locally (with `docker build` or `podman build`).
     2. Push the image to your registry (`docker push` or `podman push`).
     3. Add the image reference (including tag) to the `docker-compose.yml`.
   - **CI/CD:**
     1. When GitLab CI pipeline runs, it pulls the image from the registry using the `image:` reference in `docker-compose.yml`.
     2. If you update the image in your local build and push it to the registry with the same tag, the CI/CD pipeline will pull the latest image version, replacing the old one.
   - **Subsequent Updates:** You only need to update and push the new version to the registry; the CI/CD pipeline will handle the rest.

### **Issues You Encountered:**
   - **Space Issues:** While building images locally, you ran into space issues, especially when trying to copy large files. The error message `no space left on device` can occur if the system is running out of disk space.
   - **Network Issues:** While building images in the CI/CD pipeline, there were errors pulling dependencies or repositories (e.g., with `dnf install` failing because of network issues).

### **Key Takeaways:**
   - The `image:` field in `docker-compose.yml` lets you specify which image to pull and use for a service.
   - You can push images to a registry (like GitLab), and subsequent deployments or CI pipelines can pull the updated images automatically.
   - If images are pulled from the registry during the CI pipeline, they will overwrite any local images.
   - You can manage local images, especially during testing or initial setups, by referencing them in `docker-compose.yml` and not always pushing them to the registry.
