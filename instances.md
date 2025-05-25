# Instances pour tester l'ontologie de football

## Instances de Pays
- `Pays_France`
- `Pays_Espagne`
- `Pays_Allemagne`
- `Pays_Angleterre`

## Instances de Club
- `Club_PSG` (Paris)
- `Club_RealMadrid` (Madrid)
- `Club_Bayern` (Munich)
- `Club_ManCity` (Manchester)

## Instances d'Équipe_de_club
- `Equipe_PSG` 
  - `representsClub: Club_PSG`
- `Equipe_RealMadrid` 
  - `representsClub: Club_RealMadrid`
- `Equipe_Bayern` 
  - `representsClub: Club_Bayern`
- `Equipe_ManCity` 
  - `representsClub: Club_ManCity`

## Instances d'Équipe_Nationale
- `Equipe_France` 
  - `representsCountry: Pays_France`
- `Equipe_Espagne` 
  - `representsCountry: Pays_Espagne`
- `Equipe_Allemagne` 
  - `representsCountry: Pays_Allemagne`
- `Equipe_Angleterre` 
  - `representsCountry: Pays_Angleterre`

## Instances de Poste
- `Poste_Attaquant_Centre` (type de `Attaquant`)
- `Poste_Ailier_Gauche` (type de `Attaquant`)
- `Poste_Ailier_Droit` (type de `Attaquant`)
- `Poste_Milieu_Defensif` (type de `Milieu`)
- `Poste_Milieu_Central` (type de `Milieu`)
- `Poste_Milieu_Offensif` (type de `Milieu`)
- `Poste_Defenseur_Central` (type de `Défenseur`)
- `Poste_Lateral_Droit` (type de `Défenseur`)
- `Poste_Lateral_Gauche` (type de `Défenseur`)
- `Poste_Gardien` (type de `Gardien_de_but`)

## Instances de Joueur (PSG)
- `Joueur_Dembele` 
  - `hasPosition: Poste_Ailier_Droit`
  - `memberOf: Equipe_PSG`
  - `memberOf: Equipe_France`
- `Joueur_Donnarumma` 
  - `hasPosition: Poste_Gardien`
  - `memberOf: Equipe_PSG`

## Instances de Joueur (Real Madrid)
- `Joueur_Mbappe` 
  - `hasPosition: Poste_Attaquant_Centre`
  - `memberOf: Equipe_RealMadrid`
  - `memberOf: Equipe_France`
- `Joueur_Bellingham` 
  - `hasPosition: Poste_Milieu_Offensif`
  - `memberOf: Equipe_RealMadrid`
  - `memberOf: Equipe_Angleterre`
- `Joueur_Courtois` 
  - `hasPosition: Poste_Gardien`
  - `memberOf: Equipe_RealMadrid`

## Instances d'Entraineur
- `Entraineur_Luis_Enrique` 
  - `coaches: Equipe_PSG`
- `Entraineur_Ancelotti` 
  - `coaches: Equipe_RealMadrid`
- `Entraineur_Deschamps` 
  - `coaches: Equipe_France`

## Instances d'Arbitre
- `Arbitre_Turpin`
- `Arbitre_Oliver`

## Instances de Supporter
- `Supporter_Jean` 
  - `supports: Equipe_PSG`
- `Supporter_Miguel` 
  - `supports: Equipe_RealMadrid`

## Instances de Personnel
- `Personnel_Medecin_PSG` 
  - `hasStaff: Equipe_PSG`
- `Personnel_Preparateur_Real` 
  - `hasStaff: Equipe_RealMadrid`

## Instances de Compétition
- `Competition_LigueDesChampions` (type de `Coupe`)
  - `hasParticipatingTeam: Equipe_PSG`
  - `hasParticipatingTeam: Equipe_RealMadrid`
  - `hasParticipatingTeam: Equipe_Bayern`
  - `hasParticipatingTeam: Equipe_ManCity`

- `Competition_Ligue1` (type de `Championnat`)
  - `hasParticipatingTeam: Equipe_PSG`
  - `hasWinner: Equipe_PSG`

- `Competition_LaLiga` (type de `Championnat`)
  - `hasParticipatingTeam: Equipe_RealMadrid`
  - `hasWinner: Equipe_RealMadrid`

- `Competition_CoupeDuMonde` (type de `Tournoi`)
  - `hasParticipatingTeam: Equipe_France`
  - `hasParticipatingTeam: Equipe_Espagne`
  - `hasParticipatingTeam: Equipe_Allemagne`
  - `hasParticipatingTeam: Equipe_Angleterre`
  - `hasWinner: Equipe_France`

## Instances de Match
- `Match_PSG_Real` 
  - `hasHomeTeam: Equipe_PSG`
  - `hasAwayTeam: Equipe_RealMadrid`
  - `hasReferee: Arbitre_Turpin`
  - `organiseMatch: Competition_LigueDesChampions`
  - `hasMatchWinner: Equipe_PSG`

- `Match_France_Espagne` 
  - `hasHomeTeam: Equipe_France`
  - `hasAwayTeam: Equipe_Espagne`
  - `hasReferee: Arbitre_Oliver`
  - `organiseMatch: Competition_CoupeDuMonde`
  - `hasMatchWinner: Equipe_Espagne`

## Instances de Résultat
- `Resultat_2_1` (PSG 2-1 Real Madrid)
- `Resultat_3_1` (France 3-1 Espagne)

## Instances d'Événements de Match (Match_PSG_Real)
- `But_Dembele_1` 
  - `scoredBy: Joueur_Dembele`
  - `scoredFor: Equipe_PSG`
  - `scoredAgainst: Equipe_RealMadrid`
  - `occursDuring: Match_PSG_Real`
  - `involvePlayer: Joueur_Dembele`

- `But_Dembele_2` 
  - `scoredBy: Joueur_Dembele`
  - `scoredFor: Equipe_PSG`
  - `scoredAgainst: Equipe_RealMadrid`
  - `occursDuring: Match_PSG_Real`
  - `involvePlayer: Joueur_Dembele`
  - 
- `But_Mbappe_1` 
  - `scoredBy: Joueur_Mbappe`
  - `scoredFor: Equipe_PSG`
  - `scoredAgainst: Equipe_RealMadrid`
  - `occursDuring: Match_PSG_Real`
  - `involvePlayer: Joueur_Mbappe`

- `Carton_Jaune_Bellingham` 
  - `involvePlayer: Joueur_Bellingham`
  - `occursDuring: Match_PSG_Real`

- `Faute_Bellingham` 
  - `involvePlayer: Joueur_Bellingham`
  - `occursDuring: Match_PSG_Real`
  - `resultsIn: Carton_Jaune_Bellingham`

- `Remplacement_Dembele` 
  - `replacesPlayer: Joueur_Dembele`
  - `replacedByPlayer: Joueur_Lee` (ajoutez cette instance)
  - `occursDuring: Match_PSG_Real`

## Instances d'Événements de Match (Match_France_Espagne)
- `But_Mbappe_3` 
  - `scoredBy: Joueur_Mbappe`
  - `scoredFor: Equipe_France`
  - `scoredAgainst: Equipe_Espagne`
  - `occursDuring: Match_France_Espagne`
  - `involvePlayer: Joueur_Mbappe`

- `But_Morata` (ajoutez cette instance de joueur)
  - `scoredBy: Joueur_Morata`
  - `scoredFor: Equipe_Espagne`
  - `scoredAgainst: Equipe_France`
  - `occursDuring: Match_France_Espagne`
  - `involvePlayer: Joueur_Morata`
 
- `But_Morata_2` 
  - `scoredBy: Joueur_Morata`
  - `scoredFor: Equipe_Espagne`
  - `scoredAgainst: Equipe_France`
  - `occursDuring: Match_France_Espagne`
  - `involvePlayer: Joueur_Morata`

