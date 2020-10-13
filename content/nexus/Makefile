dup:
	docker run -d -p 8081:8081 -v $$(pwd)/nexus-data:/nexus-data --name nexus sonatype/nexus3

ddown:
	docker stop --time=120 nexus
	docker rm -f nexus 

test:
	curl http://localhost:8081/

clean:
	rm -Rf nexus-data
	mkdir nexus-data
	chown -R 200 nexus-data

setup:
	docker network create -d bridge br0
	docker network connect br0 nexus