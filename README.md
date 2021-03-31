# Suivi des publications

L'objectif est d'avoir un suivi des articles publiés par l'observatoire ainsi que celle à partir de ces données.

Le recencement se fait dans un fichier au format **bibtex** et se décompose comme suit :

- **publication_interne_ob7** liste les productions de l'équipe.
- **publication_externe_ob7** liste les productions issues des données de l'observatoire (sans auteur de l'équipe).

Ce resencement des articles publiés par l'observatoire permettra également de les inserer en volume au sein de l'archive ouverte HAL. Il est necessaire de mettre un standard commun à l'équipe pour décrire les références. De plus, afin de les intégrer dans HAL, il est necessaire de la formalisation de leur outils.

Le format standardisé pour les ORGPs est le suivant:

```bib
@inproceedings{test_inproceeding,
 title = {Ceci est le titre},
 author = {Nom, Prénom and Nom, Pr\’enom and {N}om, Prénom },
 booktitle  = {Titre de la conférence},
 address={Paris,France},
 year = {2015},
 url = {},
 abstract = {Abstract},
 keywords = {},
 organization = {{}},
 x-conferencestartdate = {2015},
 x-audience  = {Valeurs possibles:Internationale, International, Nationale, National, Non spécifiée, Not set},
 x-language  = {en},
 x-invitedcommunication = {Valeurs possibles:Non, No, Oui, Yes},
 x-peerreviewing = {Valeurs possibles:Oui, Yes, Non, No},
 x-popularlevel = {Valeurs possibles:Non, No, Oui, Yes},
 x-proceedings  = {Valeurs possibles:Oui, Yes, Non, No},
 x-localreference = {}
 }
```

## Exemple pour un papier soumis en 2020

```bib
@inproceedings{duparc_development_2020,
 title = {Development status of the new {Tropical} {Tunas} {Treatment} ({T3}) software},
 author = {Duparc, Antoine and Depetris, Mathieu and Floch, Laurent and Cauquil, Pascal and Bach, Pascal and Lebranchu, Julien},
 booktitle = {22nd session of the {IOTC} {Working} {Party} on {Tropical} {Tunas} - {Data} preparatory meeting},
 url = {https://iotc.org/sites/default/files/documents/2020/06/IOTC-2020-WPTT22DP-INF01.pdf}
 address={Victoria, Seychelles},
 year = {2020},
 abstract = {This paper is an information note on the progress of the development of the new version of T3 following the development of a new statistical model.},
 pages = {1--5},
 organization = {{IOTC}},
 x-conferencestartdate = {2020},
 x-audience  = {International},
 x-language  = {en},
 x-invitedcommunication = {no},
 x-peerreviewing = {No},
 x-popularlevel = {No},
 x-proceedings  = {Yes},
 x-localreference = {IOTC-2020-WPTT22(DP)-INF01}
 }
 ```

## Formalisation pour HAL

La référence est des champ pour HAL est disponible à l'adresse suivante : <https://doc.archives-ouvertes.fr/x2hal/champs-bibtex-obligatoiresoptionnels-par-type/>.
Un bref rappel adapté à nos besoins est décrit ci après.

### Champs optionnels communs à tous les types BibTeX

- abstract {Abstract}
- doi (MT HAL : doi)
- keywords (MT HAL : keyword). Obligatoire dans le domaine des shs
- note (MT HAL : comment)
- pmcid (MT HAL : identifiant PubMed central)
- pmid (MT HAL : identifiant PubMed)
- url (MT HAL : seeAlso)
- x-abstract_fr et x-abstract_en (MT HAL : abstract) si on veut spécifier le résumé dans une autre langue (sinon champ abstract)
- x-anrproject (MT HAL : anrProject)
- x-classification (MT HAL : classification)
- x-collaboration (MT HAL : collaboration)
- x-domain (MT HAL : domain)
- x-europeanproject (MT HAL : europeanProject)
- x-funding (MT HAL : funding)
- x-jel (MT HAL : jel) : ATTENTION, non pris en compte actuellement
- x-keywords_fr et x-keywords_en (MT HAL : keyword) si on veut spécifier les mot-clés dans une autre langue (sinon champ keywords)
- x-licence (MT HAL : licence, valeurs possibles : Marque du Domaine Public, Public Domain Mark, Paternité – Pas d’utilisation commerciale – Pas de modification, Attribution – NonCommercial – NoDerivatives, Paternité – Pas d’utilisation commerciale – Partage selon les Conditions Initiales, Attribution – NonCommercial – ShareAlike, Paternité – Pas d’utilisation commerciale, Attribution – NonCommercial, Paternité – Pas de modifications, Attribution – NoDerivatives, Paternité – Partage selon les Conditions Initiales, Attribution – ShareAlike, Paternité, Attribution, CC0 – Transfert dans le Domaine Public, CC0 – Public Domain Dedication, Copyright (Tous droits réservés), Copyright, Domaine public, Public Domain, Licence Ouverte – etalab, Open licence – etalab)
- x-localreference (MT HAL : localReference)
- x-mesh (MT HAL : mesh)
- x-onbehalfof (listes des comptes HAL séparés par ‘;’ pour ajouter les propriétaires au dépôt). Ex: x-onbehalfof={test;identifiant;compte;1}
- x-subtitle (MT HAL : subTitle)
- x-title_fr et x-title_en (MT HAL : title) si on veut spécifier le titre dans une autre langue (sinon champ title)
- x-writingdate (MT HAL : writingDate)

### Nos besoins

Nous sommes concernés principalement par les blocs de citations suivants :

#### @inproceedings (COMM) = Communication

Champs obligatoires

```bib
@inproceedings{test_inproceeding,
 title = {Ceci est le titre},
 author = {Nom, Prénom and Nom, Pr\’enom and {N}om, Prénom },
 booktitle  = {Titre de la conférence},
 address={Paris,France},
 year = {2015},
 x-conferencestartdate = {2015},
 x-audience  = {Valeurs possibles:Internationale, International, Nationale, National, Non spécifiée, Not set},
 x-language  = {en},
 x-invitedcommunication = {Valeurs possibles:Non, No, Oui, Yes},
 x-peerreviewing = {Valeurs possibles:Oui, Yes, Non, No},
 x-popularlevel = {Valeurs possibles:Non, No, Oui, Yes},
 x-proceedings  = {Valeurs possibles:Oui, Yes, Non, No},
 }
```

Les champs obligatoires x-country (MT HAL : country) et x-city (MT HAL : city) peuvent être saisi directement ou calculés par X2hal à partir du champ address.

Champs optionnels

- editor (MT HAL : scientificEditor)
- number (MT HAL : issue)
- pages (MT HAL : page)
- publisher (MT HAL : publisher)
- series (MT HAL : serie)
- volume (MT HAL : volume)
- year (MT HAL : date)
- x-conferenceenddate (MT HAL : conferenceEndDate)
- x-conferenceorganizer (MT HAL : conferenceOrganizer)
- x-publisherlink (MT HAL : publisherLink)
- x-serieseditor (MT HAL : seriesEditor)
- x-source (MT HAL : source)
- Champs optionnels communs à tous les types BibTeX
