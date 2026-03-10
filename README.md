# GitHub-Homework

## Leírás

Ez a repository egy DevOps házi feladat megoldását tartalmazza, amely egy egyszerű nginx webszervert futtat Docker konténerben.

## Tartalom

- **Dockerfile**: Egy nginx Alpine alapú Docker image, amely egy egyedi HTML oldalt szolgál ki
- **index.html**: Egy egyszerű HTML oldal, amely megjeleníti a "DevOps homework by: Mátyás János Gubis" szöveget
- **GitHub Actions workflow**: Automatikus CI/CD pipeline a Docker image buildeléséhez és DockerHub-ra való feltöltéséhez

## Működés

### Lokális futtatás

A Docker image buildelése és futtatása:

```bash
# Image buildelése
docker build -t devops-homework .

# Konténer futtatása
docker run -d -p 8080:80 devops-homework
```

Ezután nyisd meg a böngészőben: `http://localhost:8080`

### GitHub Actions Workflow

A repository tartalmaz egy automatikus CI/CD workflow-t (`.github/workflows/docker-build-push.yml`), amely:

1. **Trigger**: Minden `main` ágra történő push esetén automatikusan elindul
2. **Build**: Buildeli a Dockerfile-t Docker Buildx használatával
3. **Push**: Feltölti az image-et a DockerHub-ra `homework:latest` tag-gel

## Technológiák

- **Docker**: Konténerizáció
- **nginx**: Webszerver
- **GitHub Actions**: CI/CD automatizálás
- **DockerHub**: Docker image registry