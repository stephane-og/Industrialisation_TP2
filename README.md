# TP2

## Quelles étapes (steps) sont réalisées par cette action ?

1. Set up Python 3.10
2. Install dependencies
3. Lint with flake8
4. Test with pytest

## Une étape est définie au minimum par 2 éléments, lesquels sont-ils et à quoi servent-ils ?

1. "name" : nom de l'étape, utilisé pour identifier et afficher l'étape lors de l'exécution du flux de travail
2. Action ou commande à exécuter (run, uses, etc.) : peut prendre différentes formes selon l'action à effectuer, par exemple run pour exécuter une commande shell, uses pour utiliser une action GitHub, etc

## La première étape contient le mot-clé ‘with’, a quoi sert-il ?

Le mot-clé 'with' dans une étape de configuration YAML pour GitHub Actions est utilisé pour fournir des options ou des paramètres supplémentaires à l'action ou à la commande qui est exécutée dans cette étape

## Sur l’onglet Summary d’une analyse de code, SonarCloud fournit 4 indicateurs. Quels sont-ils et quelles sont leurs utilités ?

- Bugs : Ces indicateurs identifient les parties du code source qui contiennent des erreurs potentielles qui pourraient causer des problèmes de fonctionnement ou de sécurité dans l'application.

- Vulnérabilités : Ces indicateurs signalent les vulnérabilités de sécurité dans le code source qui pourraient être exploitées par des attaquants pour compromettre le système ou les données.

- Code Smells : Ces indicateurs mettent en évidence les parties du code qui ne respectent pas les bonnes pratiques de développement, ce qui peut entraîner une complexité accrue, une maintenance difficile ou des performances médiocres.

- Security Hotspots : Cet indicateur représente le temps supplémentaire nécessaire pour corriger tous les problèmes identifiés dans le code, en termes de développement ou de révision de code. Il s'agit essentiellement d'un estimatif du coût futur de la maintenance du code.

## À quoi sert l’indicateur Quality Gate ?

L'indicateur Quality Gate dans SonarCloud évalue la qualité globale du code analysé en fonction de critères prédéfinis. Il indique si le code satisfait ou non à ces critères, fournissant ainsi un aperçu rapide de la qualité du code.

## Quelle est la différence entre les sections New code et Overall Code dans l’onglet Summary ?


1. New code : Cette section analyse uniquement les modifications récentes apportées au code depuis la dernière analyse. Elle met en évidence les problèmes détectés dans le nouveau code ajouté ou modifié depuis la dernière analyse.

2. Overall Code : Cette section analyse l'ensemble du code, y compris le nouveau code ainsi que le code existant. Elle présente une vue d'ensemble des problèmes détectés dans tout le code, qu'il s'agisse de code existant ou de nouvelles modifications.

## Y a-t-il des Code Smells ? Si oui, combien et pour quelle(s) raisons(s) ?

Il y en a 3 dans src/wallet.py.

1. def spend_cash(self, amount, deferred=False): => Remove the unused function parameter "deferred".
2. def spend_money(self, amount, deferred=False): => Update this function so that its implementation is not identical to spend_cash on line 16.
3. def spend_money(self, amount, deferred=False): => remove the unused function parameter "deferred".

## Y a-t-il des Security Hotspots ? Si oui, combien et pour quelle(s)raison(s) ?

Il y en a 1 dans Dockerfile.

1. FROM python:3.9 => The python image runs with root as the default user. Make sure it is safe here.