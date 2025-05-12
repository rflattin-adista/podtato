# Application PodTato

1. Se connecter à **l’interface utilisateur** de Kumba
2. Télécharger le fichier **Kubeconfig**
3. Copier le fichier kubeconfig dans le répertoire ~/.kube/config de votre compte utilisateur
4. Télécharger et installer **kubectl**
```
https://kubernetes.io/fr/docs/tasks/tools/install-kubectl/
```
5. Vérifier l’accès avec la commande 
```
kubectl get pods -A
```
5. Cloner en local le repository **git@gitlab.corp.adista.fr:paas/podtato.git**
```
git clone git@gitlab.corp.adista.fr:paas/podtato.git
```
6. Modifier les manifests de l'application PodTato (namespace, ingress, menu item) afin de refléter le bon nom de namespace, de sous-domaine et de point de menu (eleve-X)
Les éléments à changer sont les suivants :
* Le nom du point de menu (ressource KumbaMenuItem utilisée)
* Le nom du fqdn (IngressRoute)
* Le nom du namespace (utilisé dans un certain nombre de ressources Kubernetes dans )
7. Installer l'application podtato dans **votre namespace** (kubectl)
```
kubectl -n eleve-X apply -f .
```
8. **Vérifier le déploiement** de l’application
```
kubectl -n eleve-X get pods
kubectl -n eleve-X get svc
kubectl -n eleve-X get ingressroutes
kubectl -n eleve-X get kumbamenuitems
```
9. Supprimer le Pod Hat et regarder le résultat. Que se passe-t’il dans l’interface utilisateur ?
```
kubectl -n eleve-X delete pods/POD-NAME
```
10. Découvrir pourquoi **le bras gauche** de PodTato n’apparaît pas
11. Découvrir pourquoi **la jambe gauche** de PodTato n’apparaît pas
12. Découvrir pourquoi **la jambe droite de** PodTato n’apparaît pas
