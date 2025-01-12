# Projet NLP : Extraction et Recherche Sémantique à partir de PDF

## Description
Ce projet est une solution d'analyse de documents PDF utilisant des techniques de traitement du langage naturel (NLP). Il extrait du texte brut depuis un fichier PDF, le nettoie, l'analyse, puis construit un système de recherche sémantique performant en utilisant des modèles d'embeddings et un index vectoriel.

## Fonctionnalités
- **Extraction de texte** : Lecture du contenu textuel de fichiers PDF.
- **Nettoyage des données** : Suppression des espaces, sauts de ligne et métadonnées inutiles.
- **Analyse linguistique** : Découpage du texte en phrases grâce à SpaCy.
- **Embeddings** : Transformation des phrases en vecteurs numériques avec OpenAI (`text-embedding-ada-002`).
- **Indexation Faiss** : Construction d'un index vectoriel pour la recherche rapide.
- **Recherche sémantique** : Trouve la phrase la plus pertinente répondant à une question.

## Structure du Code
- **Extraction de texte** :
  - La fonction `extract_text(file_path)` utilise PyPDF2 pour lire un fichier PDF et en extraire le texte.
- **Nettoyage du texte** :
  - La fonction `clean_text(text)` nettoie le texte en supprimant les éléments inutiles (espaces multiples, numéros de pages, liens, etc.).
- **Embeddings et Indexation** :
  - Les phrases sont transformées en vecteurs via la fonction `get_embedding(text)`, puis indexées avec Faiss.
- **Recherche Sémantique** :
  - La fonction `search_answer(question, document_text, index, embedding_sentences)` recherche et retourne la phrase la plus pertinente dans le texte.
