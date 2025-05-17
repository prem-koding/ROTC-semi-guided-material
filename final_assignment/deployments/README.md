- Create resources using backend.yaml, resource.yaml and database.yaml

- Apply the deployment files: 
  
```
  kubectl apply -f deployments
```

- Verify all the resources

```
    kubectl get pods -n crud-app
    kubectl get deploy -n crud-app
    kubectl get svc -n crud-app
```

- Port forward the backend api service

```
    kubectl port-forward service/backend-api-service 8000:8000 -n crud-app
```

- Hit the get users endpoint and add user

```
    curl -X GET http://localhost:8000/users
    curl -X POST http://localhost:8000/users -d '{"name":"John Doe", "email":"jdoe@example.com"}' -H "Content-Type: application/json"
```

- To verify the data persistence, create the user and restart the postgres pod(by deleting the pod), now try to hit the get users url, we should get an empty list
- After enabling the persistence volume, even after restarting the pod, we should be able to get the old data.