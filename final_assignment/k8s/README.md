# K8s Module Readme

### Collaborators 
Prem Kumar Pavuluri, Shreya Haridas

### Basic Commands 
- To create a namespace:
  ```bash
  kubectl create namespace crud-app
  ```
- To create a secret:
  ```bash
    kubectl create secret generic my-secret --from-literal=password=somepassword -n crud-app
    ```
- To create volumes and pvcs:
  ```bash
    kubectl apply -f db-volume.yaml
    kubectl apply -f db-volume-claim.yaml
  ```
- To start the database:
  ```bash
  kubectl apply -f db.yaml
  ```
- To create services for db:
  ```bash
  kubectl apply -f db-service.yaml
  ```
- To start the backend:
  ```bash
    kubectl apply -f backend.yaml
    ```
- To create services for backend:
  ```bash
  kubectl apply -f backend-service.yaml
  ```

To use the application, you can use the following curl commands:
- To get the list of users:
  ```bash
    curl -X GET http://localhost:8000/users
  ```
- To create a new user:
  ```bash
    curl -X POST http://localhost:8000/users -d '{"name":"John Doe", "email":"jdoe@example.com"}' -H "Content-Type: application/json"
    ```
- To get a specific user by ID:
  ```bash
    curl -X GET http://localhost:8000/users/1
    ```
- To delete a user by ID:
  ```bash
    curl -X DELETE http://localhost:8000/users/1 -H "Content-Type: application/json"
  ```
