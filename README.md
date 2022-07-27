# Elastic stack (ELK) on Docker + Elastic APM

# WSL2 docker > ELK + Elastic APM 세팅
```vim
# wsl2
cd /home/hahahoho5915/docker

# clone docker-compose
git clone https://github.com/deviantony/docker-elk
cd docker-elk

# docker-compose build
docker-compose -f docker-compose.yml -f extensions/apm-server/apm-server-compose.yml up -d
```

# Elastic APM (java)agent 설정
```vim
# https://repo1.maven.org/maven2/co/elastic/apm/elastic-apm-agent/1.33.0/
# elastic-apm-agent-1.33.0.jar 파일 다운

-javaagent:C:/workspace/elastic-apm-agent-1.33.0.jar
-Delastic.apm.server_urls=http://localhost:8200
-Delastic.apm.service_name=toygraphqls
-Delastic.apm.application_packages=com.example,org.example
-Delastic.apm.capture_body=ALL
```
