# Competency Questions avec DL Queries pour l'ontologie de football

## Questions sur les Compétitions

### CQ1: Quels types de compétitions existent dans le domaine du football?
**DL Query:**
```
Compétition
```

### CQ2: Quelles compétitions ont des équipes nationales comme participantes?
**DL Query:**
```
Compétition and hasParticipatingTeam some Equipe_Nationale
```

### CQ3: Quelles compétitions ont été remportées par une équipe de club?
**DL Query:**
```
Compétition and hasWinner some Equipe_de_club
```

### CQ4: Quelles compétitions incluent des matchs avec au moins un but?
**DL Query:**
```
Compétition and organiseMatch some (Match and hasEvent some But)
```

## Questions sur les Matchs

### CQ5: Quels matchs sont arbitrés par un arbitre?
**DL Query:**
```
Match and hasReferee some Arbitre
```

### CQ6: Quels matchs comportent des cartons jaunes?
**DL Query:**
```
Match and hasEvent some (Carton and Jaune)
```

### CQ7: Quels matchs ont impliqué des remplacements?
**DL Query:**
```
Match and hasEvent some Remplacement
```

### CQ8: Quels matchs ont été remportés par l'équipe jouant à domicile?
**DL Query:**
```
Match and hasHomeTeam some (Équipe and hasMatchWinner value "true"^^xsd:boolean)
```
ou plus simplement:
```
Match and (hasHomeTeam some Équipe) and (hasMatchWinner some Équipe)
```

## Questions sur les Événements de Match

### CQ9: Quels types d'événements peuvent se produire pendant un match?
**DL Query:**
```
But or Carton or Faute or Remplacement
```

### CQ10: Quels événements impliquent des attaquants?
**DL Query:**
```
(But or Carton or Faute or Remplacement) and involvePlayer some (Joueur and hasPosition some Attaquant)
```

### CQ11: Quelles fautes ont résulté en cartons?
**DL Query:**
```
Faute and resultsIn some Carton
```

## Questions sur les Personnes

### CQ12: Quels types de personnes sont impliqués dans le football?
**DL Query:**
```
Personne
```

### CQ13: Quels joueurs occupent le poste d'attaquant?
**DL Query:**
```
Joueur and hasPosition some Attaquant
```

### CQ14: Quels joueurs font partie à la fois d'une équipe nationale et d'une équipe de club?
**DL Query:**
```
Joueur and (memberOf some Equipe_Nationale) and (memberOf some Equipe_de_club)
```

### CQ15: Quels entraîneurs dirigent une équipe nationale?
**DL Query:**
```
Entraineur and coaches some Equipe_Nationale
```

## Questions sur les Postes

### CQ16: Quels sont les différents postes qu'un joueur peut occuper?
**DL Query:**
```
Poste
```

### CQ17: Quels postes sont considérés comme défensifs?
**DL Query:**
```
Défenseur or (Milieu and Poste_Milieu_Defensif)
```

## Questions sur les Équipes

### CQ18: Quels types d'équipes existent dans le football?
**DL Query:**
```
Équipe
```

### CQ19: Quelles équipes ont des gardiens de but?
**DL Query:**
```
Équipe and hasPlayer some (Joueur and hasPosition some Gardien_de_but)
```

### CQ20: Quelles équipes nationales représentent un pays?
**DL Query:**
```
Equipe_Nationale and representsCountry some Pays
```

### CQ21: Quelles équipes participent à des coupes?
**DL Query:**
```
Équipe and participatesIn some Coupe
```

## Questions sur les Buts

### CQ22: Quels buts ont été marqués par des attaquants?
**DL Query:**
```
But and scoredBy some (Joueur and hasPosition some Attaquant)
```

### CQ23: Quels buts ont été marqués pour des équipes nationales?
**DL Query:**
```
But and scoredFor some Equipe_Nationale
```

### CQ24: Quels buts ont été marqués contre des équipes de club?
**DL Query:**
```
But and scoredAgainst some Equipe_de_club
```

## Questions sur les Remplacements

### CQ25: Quels remplacements impliquent des milieux de terrain?
**DL Query:**
```
Remplacement and (replacesPlayer some (Joueur and hasPosition some Milieu) or replacedByPlayer some (Joueur and hasPosition some Milieu))
```

### CQ26: Quels remplacements ont eu lieu dans des matchs de championnat?
**DL Query:**
```
Remplacement and occursDuring some (Match and organiseMatch some Championnat)
```

## Questions complexes combinant plusieurs classes

### CQ27: Quels joueurs ont marqué des buts et reçu des cartons dans le même match?
**DL Query:**
```
Joueur and (involvePlayer some But) and (involvePlayer some Carton) and (involvePlayer min 2 (But or Carton))
```

### CQ28: Quelles équipes ont gagné des matchs avec des buts marqués par leurs attaquants?
**DL Query:**
```
Équipe and (hasMatchWinner value "true"^^xsd:boolean) and hasPlayer some (Joueur and hasPosition some Attaquant and scoredBy some But)
```

### CQ29: Quels entraîneurs dirigent des équipes qui ont remporté des compétitions?
**DL Query:**
```
Entraineur and coaches some (Équipe and hasWinner some Compétition)
```

### CQ30: Quels joueurs occupant le poste de gardien de but n'ont pas concédé de buts dans certains matchs?
**DL Query:**
```
Joueur and hasPosition some Gardien_de_but and memberOf some (Équipe and not (scoredAgainst some But))
```
