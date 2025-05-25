# Hiérarchie d'Object Properties pour l'ontologie

Voici une hiérarchie d'object properties (propriétés d'objets) organisée pour répondre aux competency questions précédemment identifiées. Ces propriétés établissent les relations entre les classes de l'ontologie.

## Propriétés de haut niveau

### hasParticipant
- **Domaine**: Thing
- **Range**: Thing
- **Description**: Relation générique de participation

### hasTemporalRelation
- **Domaine**: Thing
- **Range**: Thing
- **Description**: Relation temporelle entre entités

### hasSpatialRelation
- **Domaine**: Thing
- **Range**: Thing
- **Description**: Relation spatiale entre entités

### hasRole
- **Domaine**: Thing
- **Range**: Thing
- **Description**: Relation de rôle

## Propriétés liées aux Compétitions

### organiseMatch (sous-propriété de hasParticipant)
- **Domaine**: Compétition
- **Range**: Match
- **Description**: Relie une compétition aux matchs qui la composent
- **Répond aux questions**: "Quels matchs font partie d'une compétition?"

### hasParticipatingTeam (sous-propriété de hasParticipant)
- **Domaine**: Compétition
- **Range**: Équipe
- **Description**: Relie une compétition aux équipes participantes
- **Répond aux questions**: "Quelles équipes participent à une compétition?"

### hasWinner (sous-propriété de hasParticipant)
- **Domaine**: Compétition
- **Range**: Équipe
- **Description**: Indique l'équipe gagnante d'une compétition
- **Répond aux questions**: "Quelle équipe a gagné une compétition?"

### hasFormat
- **Domaine**: Compétition
- **Range**: Format (classe à ajouter)
- **Description**: Spécifie le format d'une compétition
- **Répond aux questions**: "Comment est structurée une compétition?"

## Propriétés liées aux Matchs

### hasHomeTeam (sous-propriété de hasParticipant)
- **Domaine**: Match
- **Range**: Équipe
- **Description**: Indique l'équipe qui joue à domicile
- **Répond aux questions**: "Quelle est l'équipe à domicile?"

### hasAwayTeam (sous-propriété de hasParticipant)
- **Domaine**: Match
- **Range**: Équipe
- **Description**: Indique l'équipe qui joue à l'extérieur
- **Répond aux questions**: "Quelle est l'équipe à l'extérieur?"

### hasReferee (sous-propriété de hasParticipant)
- **Domaine**: Match
- **Range**: Arbitre
- **Description**: Relie un match à son arbitre
- **Répond aux questions**: "Qui arbitre un match?"

### hasEvent (sous-propriété de hasTemporalRelation)
- **Domaine**: Match
- **Range**: But | Carton | Faute | Remplacement
- **Description**: Relie un match aux événements qui s'y produisent
- **Répond aux questions**: "Quels événements ont lieu pendant un match?"

### hasResult
- **Domaine**: Match
- **Range**: Résultat (classe à ajouter)
- **Description**: Indique le résultat d'un match
- **Répond aux questions**: "Quel est le résultat d'un match?"

## Propriétés liées aux Événements de Match

### involvePlayer (sous-propriété de hasParticipant)
- **Domaine**: But | Carton | Faute | Remplacement
- **Range**: Joueur
- **Description**: Relie un événement au joueur impliqué
- **Répond aux questions**: "Quel joueur est impliqué dans cet événement?"

### occursDuring (sous-propriété de hasTemporalRelation)
- **Domaine**: But | Carton | Faute | Remplacement
- **Range**: Match
- **Description**: Indique le match pendant lequel l'événement se produit
- **Répond aux questions**: "Pendant quel match cet événement s'est-il produit?"

### occursAtTime
- **Domaine**: But | Carton | Faute | Remplacement
- **Range**: xsd:int
- **Description**: Indique à quel moment l'événement se produit (minute)
- **Répond aux questions**: "À quel moment cet événement s'est-il produit?"

### resultsIn (sous-propriété de hasTemporalRelation)
- **Domaine**: Faute
- **Range**: Carton
- **Description**: Relie une faute au carton qui en résulte
- **Répond aux questions**: "Quelle sanction résulte de cette faute?"

## Propriétés spécifiques aux Remplacements

### replacesPlayer (sous-propriété de involvePlayer)
- **Domaine**: Remplacement
- **Range**: Joueur
- **Description**: Joueur qui sort
- **Répond aux questions**: "Quel joueur est remplacé?"

### replacedByPlayer (sous-propriété de involvePlayer)
- **Domaine**: Remplacement
- **Range**: Joueur
- **Description**: Joueur qui entre
- **Répond aux questions**: "Quel joueur entre en remplacement?"

### decidedBy (sous-propriété de hasParticipant)
- **Domaine**: Remplacement
- **Range**: Entraineur
- **Description**: Entraineur qui décide du remplacement
- **Répond aux questions**: "Qui a décidé ce remplacement?"

## Propriétés liées aux Personnes

### memberOf (sous-propriété de hasRole)
- **Domaine**: Personne
- **Range**: Équipe
- **Description**: Relie une personne à l'équipe dont elle est membre
- **Répond aux questions**: "À quelle équipe appartient cette personne?"

### coaches (sous-propriété de hasRole)
- **Domaine**: Entraineur
- **Range**: Équipe
- **Description**: Relie un entraineur à l'équipe qu'il entraîne
- **Répond aux questions**: "Quelle équipe cet entraineur dirige-t-il?"

### hasPosition (sous-propriété de hasRole)
- **Domaine**: Joueur
- **Range**: Poste
- **Description**: Indique le poste d'un joueur
- **Répond aux questions**: "Quel est le poste de ce joueur?"

### supports (sous-propriété de hasRole)
- **Domaine**: Supporter
- **Range**: Équipe
- **Description**: Relie un supporter à l'équipe qu'il soutient
- **Répond aux questions**: "Quelle équipe ce supporter soutient-il?"

## Propriétés liées aux Équipes

### hasPlayer (sous-propriété de hasParticipant)
- **Domaine**: Équipe
- **Range**: Joueur
- **Description**: Relie une équipe à ses joueurs
- **Répond aux questions**: "Quels joueurs font partie de cette équipe?"

### hasCoach (sous-propriété de hasParticipant)
- **Domaine**: Équipe
- **Range**: Entraineur
- **Description**: Relie une équipe à son entraineur
- **Répond aux questions**: "Qui entraîne cette équipe?"

### hasStaff (sous-propriété de hasParticipant)
- **Domaine**: Équipe
- **Range**: Personnel
- **Description**: Relie une équipe à son personnel
- **Répond aux questions**: "Qui fait partie du personnel de cette équipe?"

### representsClub (sous-propriété de hasRole)
- **Domaine**: Equipe_de_club
- **Range**: Club (classe à ajouter)
- **Description**: Relie une équipe au club qu'elle représente
- **Répond aux questions**: "Quel club cette équipe représente-t-elle?"

### representsCountry (sous-propriété de hasRole)
- **Domaine**: Equipe_Nationale
- **Range**: Pays (classe à ajouter)
- **Description**: Relie une équipe nationale au pays qu'elle représente
- **Répond aux questions**: "Quel pays cette équipe nationale représente-t-elle?"

### participatesIn (sous-propriété de hasRole)
- **Domaine**: Équipe
- **Range**: Compétition
- **Description**: Relie une équipe aux compétitions auxquelles elle participe
- **Répond aux questions**: "À quelles compétitions cette équipe participe-t-elle?"

## Propriétés liées aux Buts

### scoredBy (sous-propriété de involvePlayer)
- **Domaine**: But
- **Range**: Joueur
- **Description**: Joueur qui marque le but
- **Répond aux questions**: "Qui a marqué ce but?"

### assistedBy (sous-propriété de involvePlayer)
- **Domaine**: But
- **Range**: Joueur
- **Description**: Joueur qui fait la passe décisive
- **Répond aux questions**: "Qui a fait la passe décisive pour ce but?"

### scoredFor (sous-propriété de hasParticipant)
- **Domaine**: But
- **Range**: Équipe
- **Description**: Équipe pour laquelle le but est marqué
- **Répond aux questions**: "Pour quelle équipe ce but a-t-il été marqué?"

### scoredAgainst (sous-propriété de hasParticipant)
- **Domaine**: But
- **Range**: Équipe
- **Description**: Équipe contre laquelle le but est marqué
- **Répond aux questions**: "Contre quelle équipe ce but a-t-il été marqué?"

## Propriétés inverses

- **isParticipantOf** (inverse de hasParticipant)
- **isMatchOf** (inverse de organiseMatch)
- **isTeamOf** (inverse de hasParticipatingTeam)
- **isWinnerOf** (inverse de hasWinner)
- **isHomeTeamOf** (inverse de hasHomeTeam)
- **isAwayTeamOf** (inverse de hasAwayTeam)
- **isRefereeOf** (inverse de hasReferee)
- **isEventOf** (inverse de hasEvent)
- **isPlayerInvolvedIn** (inverse de involvePlayer)
- **occursIn** (inverse de occursDuring)
- **isMemberOf** (inverse de memberOf)
- **isCoachOf** (inverse de coaches)
- **isPositionOf** (inverse de hasPosition)
- **isSupporterOf** (inverse de supports)
- **isPlayerOf** (inverse de hasPlayer)
- **isCoachOf** (inverse de hasCoach)
- **isStaffOf** (inverse de hasStaff)
- **isScorerOf** (inverse de scoredBy)
- **isAssistOf** (inverse de assistedBy)
- 
