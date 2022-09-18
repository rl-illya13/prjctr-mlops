## Pod & Deployment
    kubectl apply -f deployment.yaml
    kubectl get pods

## Service
    kubectl apply -f service.yaml
    kubectl get services

## Job
    kubectl apply -f job.yaml
    kubectl get pods    
    kubectl logs -f job.batch/job

## Port-Forward
    kubectl port-forward service/svc 8080:8080