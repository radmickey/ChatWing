postgresinit:
	docker run --name messanger_postgres -p 5433:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=password -d postgres:15.5-bullseye

postgres:
	docker exec -it messanger_postgres psql

createdb:
	docker exec -it messanger_postgres createdb --username=root --owner=root messanger

dropdb:
	docker exec -it messanger_postgres dropdb messanger

migrateup:
	migrate -path db/migrations -database "postgresql://root:password@localhost:5433/messanger?sslmode=disable" -verbose up

migratedown:
	migrate -path db/migrations -database "postgresql://root:password@localhost:5433/messanger?sslmode=disable" -verbose up


.PHONY: postgresinit postgres createdb dropdb migrateup migratedown
