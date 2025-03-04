
# <font color='orange'>**Projet Python Netflix**</font>
Analyse approfondie des données Netflix à l'aide de Python. Le code inclut l'importation des données, leur nettoyage, l'analyse statistique, ainsi que la visualisation des résultats obtenus. Grâce à ces outils, il sera possible d'explorer les tendances et les comportements des utilisateurs sur la plateforme Netflix.
### Sujet 1 :  IMPACT DU BUDGET SUR LA POPULARITÉ 
 - Impact sur le score
 - Impact sur le revenu
 - Impact sur le nombre de vue

### Sujet 2 : INFLUENCE GÉOGRAPHIQUE SUR LA POPULARITÉ
 - Nombre de votes par pays
 - Revenu par pays 
 - Score par pays

### Sujet 3 : Quel est le genre le plus populaire sur Netflix, et quels films de ce genre, absents de la plateforme, pourraient être intéressants à envisager ?
  - Analyse des genres présents sur Netflix
  - Analyse du top 10 des films du genre "History", indépendamment de la plateforme.

### SUJET 4 : Quels genres sont les plus populaires et à quels moments ?
  - Top 10 genres les plus populaires en diagramme en secteurs
  - Genres les plus populaires en termes de visionnements par mois
  - Nombre d'heures visionnées par semaine
  - L’évolution des vues moyenne par mois sans considérer le genre

### Conclusion : Performance de Netflix par rapport à d'autres plateformes, selon le score moyen de leurs films sur Rotten Tomatoes



# Informations sur les Dataframes 
1. **Movies.csv  &rarr; df_movies**\
 url: https://www.kaggle.com/datasets/danielgrijalvas/movies/data \
 Ce que les catégories signifient:
 - budget: le budget d'un film (Les films qui n'ont pas ces données ont un 0)
 - company: La compagnie de production
 - country: Le pays d'orgine
 - director: le directeur 
 - genre: le genre principal du film
 - gross: le revenu du film
 - name: le nom du film
 - rating: les classifications du film (R, PG, etc.)
 - released: date de sortie du film (YYYY-MM-DD)
 - runtime: durée du film
 - score: Note des utilisateurs sur IMDb
 - votes: nombre de votes des utilisateurs 
 - star: acteur principal
 - writer: scénariste du film
 - year: année de sortie du film

2. **Netflix_titles.csv &rarr; df_netflix_titles**\
url: https://www.kaggle.com/datasets/shivamb/netflix-shows \
Ce que les catégories signifient: 
- show_id : Identifiant unique pour chaque film ou série TV
- type : Identifiant - Un film ou une série TV
- title : Titre du film ou de la série TV
- director : Réalisateur du film
- cast : Acteurs impliqués dans le film ou la série
- country : Pays où le film ou la série a été produit(e)
- date_added : Date à laquelle il a été ajouté sur Netflix
- release_year : Année de sortie réelle du film ou de la série
- rating : Classification TV du film ou de la série
- duration : Durée totale - en minutes ou en nombre d'épisodes

3. **imdb_top_1000.csv &rarr; df_top1000_imdb** \
url : https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows \
Ce que les catégories signifient: 
- Poster_Link : Lien vers l'affiche utilisée par IMDb
- Series_Title : Titre du film
- Released_Year : Année de sortie du film
- Certificate : Classification obtenue par le film
- Runtime : Durée totale du film
- Genre : Genre du film
- IMDB_Rating : Note du film sur le site IMDb
- Overview : Résumé ou mini-histoire du film
- Meta_score : Score obtenu par le film
- Director : Nom du réalisateur
- Star1, Star2, Star3, Star4 : Noms des acteurs principaux
- No_of_votes : Nombre total de votes
- Gross : Montant d'argent gagné par le film

4. **n_movies.csv &rarr; df_netflix_title** \ 
url : https://www.kaggle.com/datasets/narayan63/netflix-popular-movies-dataset \
Ce que les catégories signifient: 
- title : Titre du film
- year : Année de sortie du film
- certificate : Classification obtenue par le film
- duration : Durée totale du film
- genre : Tous les genres du film
- rating : Classification TV du film ou de la série
- description : Description du film
- stars : Noms des acteurs principaux
- votes : Nombre total de votes

5. **MoviesOnStreamingPlatforms.csv &rarr; df_movies_diff_plat** \
url : https://www.kaggle.com/datasets/ruchi798/movies-on-netflix-prime-video-hulu-and-disney \
Ce que les catégories signifient: 
- Row ID
- Title : Titre du film
- Year : Année de sortie du film
- Age : Age de recommandation pour visionner le film
- Rotten Tomatoes : Note de rotten Tomatoes 
- Netflix : 0 oui 1 non
- Hulu : 0 oui 1 non
- Prime Video : 0 oui 1 non
- Disney+ : 0 oui 1 non
- Type : Type Movie: 0 TV Show
  
6. **All-weeks-global.tsv &rarr; df_top10_global** \
url : https://www.netflix.com/tudum/top10/data/all-weeks-global.tsv \
Ce que les catégories signifient: 
- week : Correspond à la semaine où les données ont été enregistrées.
- category : Désigne le type de contenu, comme un film ou une série TV.
- weekly_rank : Classement du contenu en fonction de ses performances pour la semaine donnée.
- show_title : Le titre principal de l’émission, du film ou de la série.
- season_title : Le titre de la saison spécifique d'une série.
- weekly_hours_viewed : Le nombre total d’heures regardées pour ce contenu au cours de la semaine.
- runtime : La durée totale (en minutes ou heures) d'un épisode, d'un film ou d'une saison.
- weekly_views : Le nombre total de fois que le contenu a été regardé cette semaine.
- cumulative_weeks_in_top_10 : Nombre total de semaines où le contenu est resté dans le top 10 des classements.
- is_staggered_launch : Indique si le lancement de la série ou du contenu est progressif.
- runtime_override_flag : Indique si la durée (runtime) a été modifiée ou ajustée.
- episode_launch_dtls : Détails sur le lancement des épisodes (dates, modalités, etc.).

7. **titles.csv &rarr; df_titlescsv** \
url : https://www.netflix.com/tudum/top10/data/all-weeks-global.tsv \
Ce que les catégories signifient:  
- id : Identifiant unique attribué au contenu.
- title : Le titre principal du film, de la série ou de l'émission.
- type : Catégorie du contenu, comme "film" ou "série".
- description : Résumé ou présentation succincte du contenu.
- release_year : L’année de sortie ou de première diffusion du contenu.
- age_certification : Classification d’âge attribuée au contenu pour indiquer à quel public il s’adresse (par exemple : tout public, 13+, 18+).
- runtime : Durée totale du contenu, en minutes.
- genres : Les catégories ou styles du contenu (par exemple : comédie, action, drame).
- production_countries : Liste des pays où le contenu a été produit.
- seasons : Nombre total de saisons (pour une série).
- imdb_id : Identifiant unique du contenu sur la plateforme IMDb.
- imdb_score : Note moyenne attribuée au contenu sur IMDb (sur 10).
- imdb_votes : Nombre total de votes ou évaluations reçus sur IMDb.
- tmdb_popularity : Indicateur de popularité du contenu sur la plateforme TMDb (The Movie Database).
- tmdb_score : Note moyenne attribuée au contenu sur TMDb (sur 10).nne attribuée au contenu sur TMDb (sur 10).  
