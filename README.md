# fastapi-exercises-v1

## Instructions

1) Setup

<sub>Instructions for Linux/Ubuntu</sub>
     
Install:
     
   * pipenv
   * PostgreSQL


Setup db:
     
        # Create local db
        sudo -u postgres createdb fastapi_exercise_db
        
        # Enter postgres
        sudo -u postgres psql
        
        # Create new user and grant privileges
        CREATE USER fastapi_exercise_user WITH ENCRYPTED PASSWORD 'fastapi_exercise_db_pass';
        GRANT ALL PRIVILEGES ON DATABASE fastapi_exercise_db to fastapi_exercise_user;
        
        # For testing purposes - add permission to create db
        ALTER USER fastapi_exercise_user CREATEDB;
        
        # Connect to our new local db
        \c fastapi_exercise_db


3) Start a project
        
        # Create and enter virtual environment
        pipenv shell
        
        # Install dependencies
        pipenv install
        
        # Add PYTHONPATH to your environment variables or run this command:
        export PYTHONPATH=$PWD
        
        # Run migrations
        alembic upgrade head
        
        # Run the app
        uvicorn main:app --reload
        
        # Go to http://127.0.0.1:8000/docs
        