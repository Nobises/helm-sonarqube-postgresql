# SonarQube + PostgreSQL Helm Chart
 
## Установка

1. Клонируйте репозиторий

git clone https://github.com/Nobises/helm-sonarqube-postgresql
cd sonarqube-nobises

2. Установите зависимости

helm dependency update

3. Установите Helm релиз

helm upgrade --install sonar . -f values.yaml

4. Проверьте поды

kubectl get pods

5. Пробросить порт

kubectl port-forward sonar-sonarqube-nobises-<numbers> 9000:80

6. Открыть SonarQube в браузере

http://localhost:9000

## Проверка подключения к БД

kubectl run psql-client --rm -i -t --image=bitnami/postgresql -- bash
psql -h sonar-postgresql -U nobises -d sonarqube

CREATE TABLE TEST
(
	NAME CHARACTER_VARYING
);
