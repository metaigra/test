build:
	docker-compose down
	docker volume prune -f
	cd "../.." && docker build -f docker/test/wordpress/Dockerfile -t test_wp/latest .
	cd "../.." && docker build -f docker/test/mysql/Dockerfile -t test_mysql/latest .
	cd "../.." && docker build -f docker/test/nginx/Dockerfile -t test_nginx/latest .
	docker-compose up -d 
up:
	docker-compose down
	docker volume prune -f
	docker-compose up -d 
down:
	docker-compose down
	docker volume prune -f

