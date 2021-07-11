frontend:
		cd ../frontend; npm start

test-frontend:
		cd ../frontend; npm test

backend:
		cd ../src; docker-compose up api-dev

test-backend:
		cd ../src; docker-compose up test

migrate:
		cd ../src; docker-compose run api-dev /virtualenv/bin/python /var/www/main/manage.py makemigrations

destroy:
		cd ../src; docker-compose down

