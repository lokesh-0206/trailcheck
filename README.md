## yaml error file
---                                                                  
apiVersion: v1
kind: Pod
metadata:
 name: my-pod
 namespace: dev
 label: my-app
  app: my-app
spec:
  containers:
    - name: my-app
      image: nginx
      ports:
       - name: http
         protocol: TCP
         containerPort: 80
...

---
apiVersion: v1
kind: Service
metadata :
  name: my-service
  namespace: dev
spec:
  selector:
    app: my-app
  ports:
    - name: my-http
      protocol: TCP
      port: 80
      targetPort: 80
...

error: error parsing pods.yaml: error converting YAML to JSON: yaml: line 8: mapping values are not allowed in this context
