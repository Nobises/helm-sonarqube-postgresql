# SonarQube + PostgreSQL Helm Chart
 
## Установка/Installing

1. Клонируйте репозиторий/Clone repository

git clone https://github.com/Nobises/helm-sonarqube-postgresql
cd sonarqube-nobises

2. Установите зависимости/Install dependencies

helm dependency update

3. Установите Helm релиз/Install Helm release

helm upgrade --install sonar . -f values.yaml

4. Проверьте поды/Check pods

kubectl get pods

5. Пробросить порт/Forward port

kubectl port-forward sonar-sonarqube-nobises-"numbers" 9000:80

6. Открыть SonarQube в браузере/Open SonarQube in browser

http://localhost:9000

## Проверка подключения к БД/Checking database connection

kubectl run psql-client --rm -i -t --image=bitnami/postgresql -- bash
psql -h sonar-postgresql -U nobises -d sonarqube

CREATE TABLE TEST
(
	NAME CHARACTER_VARYING
);
