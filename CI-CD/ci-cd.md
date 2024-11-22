# CI - CD


## connexion à la machine distante

ssh debian@46.105.146.174


| ssh | debian | @ | 46.105.146.174 |
|-|-|-|-|
|méthode de connexion|Nom d'utilisateur sur le serveur| @ | adresse IP de la machine distante|

## git push on git lab and git hub 

après avoir renommer origin pour github en old-origin il faudra utiliser git push old-origin main pour gihub et git push origin main pour git lab.



## gitlab pipeline

Il faut ajouter un fichier .gitlab.ci.yml à la racine du projet et push sur gitlab ce fichier sert à déclarer les étapes à éxécuter lors du pipeline (CI)  (build, tests, déploiement)

```yml
# We use a pipeline with 2 stage
stages:
  # the first stage>
  - test
  # the second stage>
  - build

# We declare a job named "build-job"
build-job:
  # The docker image to use when running that job
  # We use minideb (A minimalist Debian-based image built specifically to be used as a base image for containers.)
  # see https://hub.docker.com/r/bitnami/minideb
  image: bitnami/minideb
  # this job is run inside the "build" stage
  stage: build
  # List of bash command to run
  script:
    - echo "Hello, $GITLAB_USER_LOGIN!"

test-job1:
  # The docker image to use when running that job
  image: bitnami/minideb
  # this job is run inside the "test" stage
  stage: test
  # List of bash command to run
  script:
    - echo "This job tests something"

vitest:
  image: node:20
  stage: test
  before_script:
    - npm ci
  script:
    - npm run test:ci
  artifacts:
    when: always
    reports:
      junit:
        - ./junit-report.xml
```

- ### tests

Il Faut configurer le package.json script pour éxécuter cette commande : 
```json
    "test:ci": "vitest --run --reporter=junit --outputFile=./junit-report.xml"
```
Il faut aussi configurer vite dans le fichier vite.config.js pour qu'il utilise le reporter Junit :

```js
import { resolve } from 'node:path'
import { defineConfig } from 'vite'

export default defineConfig({
    build: {
        rollupOptions: {
            input: {
                main: resolve(__dirname, 'index.html'),
                data: resolve(__dirname, 'data/index.html'),
            },
        },
    },
    test: {
        reporters: ['default', 'junit'],
        outputFile: {
            junit : './junit-report.xml',
        }
    },
})
```


## JUNIT

Junit est un framework de test pour Java dont la structure XML de réponse est largement utilisée et suportée par les autres langages et frameworks de tests
