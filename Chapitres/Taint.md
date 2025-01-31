# Taint & Tolération
## Role de la taint
Elles servent à empêcher un pod d'être déployé sur le node si le pod ne tolère pas ses taints.
Les Taints sont posées exclusivement sur les nodes. Elles peuvent être posées/enlevées par l'administrateur ou par les controllers de kubernetes. 
Une Taint va se servir par exemple :  
- pour signifier un hardware spécifique du node (ex architecture ARM,AMD,...),  seule des images compatibles avec ce hardware sont acceptées sur ce node.
- pour dédier des Nodes à certains pods (en évitant ainsi que les autres Pod ne s'y installent)
- pour palier à un problème temporaire, un controller Kubernetes va poser des taints pour signifier que :
    - `node.kubernetes.io/not-ready`  Le Node n'est pas opérationnel.
    - `node.kubernetes.io/unreachable` Le Node n'est pas joignable.
    - `node.kubernetes.io/memory-pressure`: Le Node est n'a plus assez de mémoire disponible.
    - `node.kubernetes.io/disk-pressure` Le Node n'a plus assez d'espace disque disponible.
    - `node.kubernetes.io/pid-pressure` Le Node manque de PID disponible.
    - `node.kubernetes.io/network-unavailable` Le réseau du Node est indisponible.
    - `node.kubernetes.io/unschedulable` Le Node n'accepte pas d'assignation de pod par le scheduler.

Une taint consiste en une clef, une valeur (optionnelle), et un effet ( `NoSchedule`, `PreferNoSchedule` ou `NoExecute`).

Regardons en détail les effets :
- `NoSchedule` Les pods qui ne tolèrent pas cette taint ne seront pas éligibles à l'installation sur ce Node, mais s'ils sont déjà présents ils y restent.
- `PreferNoSchedule` C'est une version best effort de la taint NoSchedule. Les pods qui ne tolèrent pas cette taint ne s'y installeront quand dernier recours s'ils ne trouvent pas un autre Node mieux disposé à les accueillir.
- `NoExecute` Les pod qui ne tolèrent pas cette taint sont expulsés du node 

## Role de la toleration
Elles servent à un pod pour dire qu'il accepte la contrainte posée par une taint.


> Attention tolérer une taint n'implique pas pour le pod de forcement aller sur le node qui porte cette taint.
## Structure
```yaml
tolerations:
- key: "key1"
  operator: "Equal"
  value: "value1"
  effect: "NoSchedule"
```

`operator` peut prendre la valeur `Exists`  (plus besoin de fournir de valeur), ou `Equal`

Un Pod peut tolérer une taint seulement un temps limité.
Ainsi dans le cas où l'effet est `NoSchedule`, la toleration peut préciser une durée en seconde. Après le pod sera reschedulé ailleurs.
Cas exemple : il peut tolérer d'être sur un Node Master le temps que son Worker se reconstruise ou attendre un laps de temps qu'une situation dégradée se résolve.

```yaml
tolerations:
- key: "node.kubernetes.io/unreachable"
  operator: "Exists"
  effect: "NoExecute"
  tolerationSeconds: 6000
```

## exercice:
- retrouver les taints posées sur les nodes de vos clusters. 

[Retour](https://obeyler.github.io/Formation-K8S/Chapitres/PodPlacement.html), [Menu](https://obeyler.github.io/Formation-K8S/), [Suite](https://obeyler.github.io/Formation-K8S/Chapitres/Securite.html)
