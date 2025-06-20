# SonarQube + PostgreSQL Helm Chart
 
## Установка/Installing

1. Добавьте репозиторий/Add repository

helm repo add sonarqube-nobises https://nobises.github.io/helm-sonarqube-postgresql
helm repo update

2. Установите релиз/Install release

helm install sonar sonarqube-nobises/sonarqube-nobises

3. Проверьте поды/Check pods

kubectl get pods

4. Пробросить порт/Forward port

kubectl port-forward sonar-sonarqube-nobises-"numbers" 9000:80

5. Открыть SonarQube в браузере/Open SonarQube in browser

http://localhost:9000

## Проверка подключения к БД/Checking database connection

kubectl run psql-client --rm -i -t --image=bitnami/postgresql -- bash
psql -h sonar-postgresql -U nobises -d sonarqube

CREATE TABLE TEST
(
	NAME CHARACTER_VARYING
);
