all: update run-detached
	@echo Nextcloud should be running now

update:
	docker compose pull

stop:
	docker compose down

run:
	docker compose up

run-detached:
	docker compose up --detach
