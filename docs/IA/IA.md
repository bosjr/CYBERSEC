## PROMPTS

**OPRO** : Vous permet d’utiliser le modèle comme un générateur de prompt optimisé. Par exemple :  

Commencez par demander au modèle de générer 3 prompt pour une question donnée  

Puis demandez ensuite pour chaque prompt le “score” d’efficacité ou une note sur 10  

Ensuite, demandez de prendre en compte les scores pour sélectionner le prompt optimisé  

**CIDI** : Acronyme pour :  

*Contexte* – contexte ou rôle du modèle  

Tu es un expert en SQL.  

*Instructions* – ce que l’on attend précisément (étapes, style…)  

Explique ta démarche étape par étape.  

*Détails* – contraintes ou informations supplémentaires  

Répond en français, utilise des jointures explicites.  

*Input* – données ou contenu à traiter  

{ma question en langage naturel}   

**RISEN**, qui est utile pour encadrer des tâches complexes en plusieurs étapes et générer des réponses structurées, précises et adaptées. C’est l'acronyme de :   

*Rôle* : le persona du modèle (ex. : un expert)  

Tu es un expert en SQL.  

*Instructions* : la tâche principale à accomplir  

Ecris-moi une requête SQL permettant de lister les clients ayant commandé en janvier  

*Steps* : étapes numérotées à suivre  

Identifie les tables, les jointures, les filtres.  

*End goal* : résultat attendu  

Client(id, nom), Commande(client_id, date)  

*Narrowing* : contraintes ou limites à respecter (style, longueur, exclus, etc.)  

Utilise un langage SQL compatible PostgreSQL  

**RELIC**, très utile pour les tâches complexes comme la génération de code, l’analyse logique, ou le raisonnement mathématique. Là encore il s’agit d’un acronyme de :  

*Rôle* : rôle ou posture du LLM  

Tu es un UX Designer expérimenté  

*Emphasis* : quelques exemples de cas d’usage ou de requêtes  

Concentre-toi sur l’accessibilité pour les personnes malvoyantes  

*Limitation* : processus logique ou règles à suivre  

Ta réponse doit tenir en moins de 200 mots, en français professionnel  

*Information* : tâche explicite à faire  

Le site web visé est un outil de prise de rendez-vous médical  

*Challenge* : contraintes à respecter (format, longueur…)  

Donne-moi 3 améliorations concrètes à proposer à l’équipe produit  

**SCAMPER**, qui peut être utilisé, comme **OPRO**, pour améliorer un prompt existant ou trouver des formulations alternatives. Là toujours, un acronyme se cache derrière :  

*Substitute* : Changer un élément (mot, rôle…)  

*Combine* : Fusionner idées ou approches  

*Adapt* : S’inspirer d’une autre tâche ou domaine  

*Modify* : Modifier la structure ou l’échelle  

Put to another use : Réutiliser pour autre chose  

*Eliminate* : Enlever les parties inutiles  

*Rearrange* : Réorganiser l’ordre  

Par exemple :  

Applique la méthode **SCAMPER** ce concept : "{idée ou problème}". Pour chaque étape, propose une variation.”  

**Chain Of Though** qui incite le modèle à détailler son raisonnement étape par étape. Cette méthode est particulièrement puissante pour comprendre le raisonnement et éviter des biais. Par exemple :  

Explique comment résoudre 3x2+4 en disant tes étapes.    

Testez le même prompt sur plusieurs LLM différents (ChatGPT, Mistral, Claude AI …) et testez différentes structures de la même question. Constatez les différences dans les réponses  

Vous pouvez vous aider d’outils comme OpenRouter ou Poe pour interroger plusieurs modèles en même temps. Pour rester sur des modèles gratuits, sélectionnez ceux avec “free” entre parenthèse  

 

**IA** : chatGPT, Mistral, Claude AI,Copilot, ollama, OpenRouter, Poe, https://jan.ai/  

 

**Ressources  **  

Le chapitre Écrivez vos premiers prompts avec ChatGPT du cours Utilisez ChatGPT pour améliorer votre productivité  
https://openclassrooms.com/fr/courses/8204091-utilisez-chatgpt-pour-ameliorer-votre-productivite/8207121-ecrivez-vos-premiers-prompts-avec-chatgpt  

L’article 18 Prompt Frameworks à usage professionnel de Reglo.ai
https://reglo.ai/prompt-frameworks  

Le guide Comment créer des prompts efficaces : guide du débutant de France Numérique  
https://www.francenum.gouv.fr/guides-et-conseils/intelligence-artificielle/generation-de-contenus-texte-image-son-video/comment-0  

Guide d'utilisation de jan.ai en local  
https://s3.eu-west-1.amazonaws.com/course.oc-static.com/paths/1048+-+ASRC/P8/Utilisation+de+Jan.ai+en+local.pdf  

Le guide Complete Guide to Prompt Engineering with Temperature and Top-p du Prompt Engineering and AI Institute  
https://promptengineering.org/prompt-engineering-with-temperature-and-top-p/  

L’article Comprendre les paramètres d’un prompt IA de Tribes  
https://www.followtribes.io/parametres-prompt-intelligence-artificielle/  