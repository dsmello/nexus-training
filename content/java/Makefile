compile:
	mvn compile
	mvn package 

test:
	mvn test

docker:
	docker pull maven:3-jdk-8

dbuild:
	docker run -it --rm --name my-maven-project -v $$(pwd):/usr/src/mymaven -v $$(pwd)/config/settings.xml:/usr/share/maven/ref/settings.xml  -w /usr/src/mymaven maven:3-jdk-8 mvn clean package

dbuild-nexus:
	docker run -it --rm --name my-maven-project -v $$(pwd):/usr/src/mymaven -v $$(pwd)/config/settings-nexus.xml:/usr/share/maven/ref/settings.xml --network br0 -w /usr/src/mymaven maven:3-jdk-8 mvn clean package

ddeploy-nexus:
	docker run -it --rm --name my-maven-project -v $$(pwd):/usr/src/mymaven -v $$(pwd)/config/settings-nexus.xml:/usr/share/maven/ref/settings.xml --network br0 -w /usr/src/mymaven maven:3-jdk-8 mvn clean deploy

clean:
	rm -Rf target
