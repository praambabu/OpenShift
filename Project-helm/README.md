helm repo add bitnami https://charts.bitnami.com/bitnami

helm repo list
NAME    URL                               
bitnami https://charts.bitnami.com/bitnami

oc project
Using project "proj-helm" on server "https://api.crc.testing:6443".

mkdir payment
mkdir shipping

helm create payment
Creating payment

helm create shipping
Creating shipping

helm lint .\payment\
==> Linting .\payment\
[INFO] Chart.yaml: icon is recommended

1 chart(s) linted, 0 chart(s) failed

helm lint .\shipping\
==> Linting .\shipping\
[INFO] Chart.yaml: icon is recommended

1 chart(s) linted, 0 chart(s) failed

<img width="924" height="356" alt="image" src="https://github.com/user-attachments/assets/0ce9edcb-8bee-41ab-bc1e-b389a77500f6" />

helm install payments-service .\payment\

NAME: payments-service
LAST DEPLOYED: Sat Mar 28 16:58:17 2026
NAMESPACE: proj-helm
STATUS: deployed
REVISION: 1
DESCRIPTION: Install complete
TEST SUITE: None

helm install shipping-service .\shipping\ 

NAME: shipping-service
LAST DEPLOYED: Sat Mar 28 18:34:34 2026
NAMESPACE: proj-helm
STATUS: deployed
REVISION: 1
DESCRIPTION: Install complete
TEST SUITE: None

helm list
NAME                    NAMESPACE       REVISION        UPDATED                                 STATUS          CHART           APP VERSION
payments-service        proj-helm       1               2026-03-28 16:58:17.665458 +0530 IST    deployed        payment-0.1.0   1.0.0      
shipping-service        proj-helm       1               2026-03-28 18:34:34.5951192 +0530 IST   deployed        shipping-0.1.0  1.0.0      
test-nginx              proj-helm       1               2026-03-28 09:37:02.3097515 +0530 IST   deployed        nginx-22.6.10   1.29.7     


<img width="1702" height="206" alt="image" src="https://github.com/user-attachments/assets/f0604a38-d0fe-4033-be0f-229bb4095365" />


<img width="1186" height="442" alt="image" src="https://github.com/user-attachments/assets/d1759b4e-de28-4dde-9381-dfd8cbf6a056" />
