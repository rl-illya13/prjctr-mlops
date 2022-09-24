## Persistent Volume
    kubectl apply -f minio-pv.yaml

## Deploy MinIO
    kubectl apply -f minio-pvc.yaml    
    kubectl apply -f minio-deployment.yaml
    kubectl apply -f minio-service.yaml  
    
    kubectl get pods
    kubectl get services

## Port-Forward
    kubectl port-forward service/minio-service 9001:9001

## MinIO Console
    http://localhost:9001/

### MinIO Console Login
- user: minio
- password: minio123
