# Evasion Program Readme

Ce projet, intitulé "Evasion", est une étude avancée sur la manière dont les hackers contournent les antivirus et sur le fonctionnement interne de ces derniers. Il s'agit de développer un programme Windows capable de chiffrer un autre programme de manière à échapper à la détection par les logiciels de sécurité.

## 🔍 Objectif
L'objectif principal est de comprendre comment les antivirus détectent les menaces et comment certains attaquants les contournent. Cela implique une analyse des techniques de chiffrement, obfuscation, et retardement d'exécution.

Le projet consiste à :

Développer un programme sous Windows qui chiffre un autre programme.
Ajouter des caractéristiques spécifiques pour contourner une détection antivirus.
Tester la capacité de ce programme à modifier la signature d'un binaire sans le corrompre.

Remarque : ce programme doit être utilisé uniquement à des fins éducatives ou expérimentales et ne doit pas être utilisé pour des activités malveillantes ou un accès non autorisé aux fichiers.

Exigences
Python 3.x
Usage
Pour exécuter le programme Evasion, utilisez la commande suivante :

python3 evasion.py <file>
Où <file>se trouve le chemin d'accès au fichier que vous souhaitez crypter, exécuter et décrypter.

Un petit programme « Hello World » en C est également fourni dans le fichier helloc.c. L'utilisateur peut le compiler et tester le programme d'évasion sur ce fichier. Un exemple est fourni ci-dessous :

gcc helloc.c -o hello
python3 evasion.py hello
Algorithme
Le programme utilise un algorithme de cryptage et de décryptage simple pour modifier le contenu du fichier d'entrée.

Algorithme de cryptage
La constante Kest définie comme 5.
La constante Iest définie comme 100001.
La constante PADest définie comme 101 * 1024 * 1024 (101 Mo).
La constante TIMEest définie comme 101 secondes.
Le processus de cryptage comprend les étapes suivantes :

La taille du fichier avant le cryptage ( before) est déterminée.
PADdes octets remplis de zéros sont ajoutés à la fin du fichier pour garantir une taille constante après le cryptage.
Le contenu du fichier est itéré octet par octet.
Pour chaque octet b, le programme calcule la valeur de l'octet chiffré comme [(b + K + (j * I)) % 256], où jreprésente la position de l'octet dans le fichier.
L'octet chiffré est réécrit dans le fichier.
Algorithme de décryptage
Le processus de décryptage est l'inverse du processus de cryptage :

Le contenu du fichier est itéré octet par octet.
Pour chaque octet b, le programme calcule la valeur de l'octet déchiffré comme [(b - K - (j * I)) % 256], où jreprésente la position de l'octet dans le fichier.
L'octet déchiffré est réécrit dans le fichier.
Exécution
Le programme prend le fichier spécifié en entrée.
Il crypte le fichier à l'aide de l'algorithme de cryptage décrit ci-dessus.
Le programme imprime ensuite « Fichier crypté » pour indiquer que le processus de cryptage est terminé.
Le programme attend TIMEquelques secondes.
Si le temps d'attente dépasse TIME, il décrypte le fichier à l'aide de l'algorithme de décryptage.
Le programme imprime « Fichier décrypté » pour indiquer que le processus de décryptage est terminé.
Enfin, le programme tente d’exécuter le fichier décrypté à l’aide de la subprocess.runméthode.
Comment les logiciels antivirus détectent les logiciels malveillants
Les logiciels antivirus utilisent diverses méthodes pour détecter et protéger contre les logiciels malveillants. Parmi les techniques courantes, on peut citer :

Détection basée sur les signatures : les logiciels antivirus conservent une base de données des signatures de logiciels malveillants connus. Ils analysent les fichiers à la recherche de séquences d'octets correspondant à ces signatures. Si la signature d'un fichier correspond à une signature de logiciel malveillant connu, l'antivirus génère une alerte.
Analyse heuristique : Les logiciels antivirus utilisent des heuristiques pour détecter les comportements suspects ou les schémas de code révélateurs de programmes malveillants. Ces méthodes permettent de détecter des menaces jusque-là inconnues ou « zero-day » en fonction de leur comportement.
Analyse comportementale : Les logiciels antivirus surveillent le comportement des programmes en temps réel. Si un programme présente un comportement malveillant, comme une tentative de modification des fichiers système ou de chiffrement des données utilisateur sans autorisation, il peut être signalé comme malveillant.
Sandboxing : certaines solutions antivirus exécutent des fichiers suspects dans un environnement virtuel appelé sandbox. Cela permet à l'antivirus d'observer le comportement du fichier sans risquer d'endommager le système hôte. Si le fichier présente un comportement malveillant dans le sandbox, il est considéré comme une menace.
Apprentissage automatique : Les logiciels antivirus avancés utilisent des algorithmes d'apprentissage automatique pour analyser de grands ensembles de données et identifier de nouveaux modèles de logiciels malveillants. L'apprentissage automatique peut aider à détecter des menaces jusqu'alors inconnues en identifiant des modèles et des anomalies dans les fichiers et les programmes.
Moyens de contourner la détection des logiciels malveillants
Logiciel malveillant polymorphe : logiciel malveillant qui modifie la structure et l'apparence de son code pour éviter la détection basée sur la signature.
Malware métamorphique : Malware qui réécrit son propre code à chaque infection, ce qui le rend difficile à détecter à l'aide de signatures statiques.
Charges utiles chiffrées : logiciel malveillant qui chiffre sa charge utile ou ses communications pour échapper à la détection basée sur des modèles.
Logiciel malveillant sans fichier : logiciel malveillant qui réside uniquement dans la mémoire, ne laissant aucune trace sur le disque pour que les méthodes d'analyse traditionnelles puissent le détecter.
Packers et Crypters : Techniques qui compressent ou cryptent les logiciels malveillants pour masquer leur véritable nature aux logiciels de sécurité.
Obfuscation de code : utilisation de transformations de code complexes pour rendre l'intention et le comportement du logiciel malveillant moins évidents pour l'analyse statique.
Techniques anti-VM : logiciels malveillants conçus pour détecter et échapper à l'exécution dans des environnements de machines virtuelles souvent utilisés par les chercheurs en sécurité.
Injection de DLL : logiciel malveillant qui injecte du code malveillant dans des processus légitimes pour masquer sa présence et contourner la détection.
Techniques de rootkit : logiciel malveillant qui modifie le noyau du système d'exploitation pour dissimuler sa présence aux logiciels de sécurité.
Kits d'exploitation : outils qui exploitent les vulnérabilités logicielles connues pour diffuser des logiciels malveillants, ce qui rend la détection difficile.
Attaques Living off the Land (LoL) : logiciels malveillants qui utilisent des outils et des utilitaires système légitimes pour se fondre dans le trafic réseau normal et échapper à la détection.
Exploits zero-day : attaques qui ciblent des vulnérabilités jusqu'alors inconnues, laissant peu de temps aux logiciels de sécurité pour développer des signatures ou des méthodes de détection.
Problèmes potentiels et améliorations
Les algorithmes de chiffrement et de déchiffrement utilisés dans le programme ne sont pas suffisamment puissants pour assurer une protection sécurisée des données. Si l'objectif est de garantir un certain niveau d'opacité des données, un algorithme de chiffrement plus puissant doit être utilisé.
Le programme suppose que la taille du fichier reste constante après le chiffrement (en raison de la PADconstante). Cette hypothèse peut ne pas être valable dans tous les cas, et une approche plus flexible devrait être envisagée.
Les constantes codées en dur ( K, I, PAD, TIME) peuvent ne pas convenir à toutes les situations et peuvent être rendues configurables via des arguments de ligne de commande ou un fichier de configuration.
Le programme ne dispose pas d'une gestion des erreurs appropriée. Il devrait inclure une gestion des exceptions pour gérer les erreurs correctement et fournir des messages d'erreur clairs aux utilisateurs.
L' subprocess.runexécution d'un fichier déchiffré peut être risquée si le fichier n'est pas fiable, car il pourrait potentiellement exécuter du code malveillant. Des mesures de sécurité supplémentaires, comme l'ajout de commandes autorisées à une liste blanche ou la réalisation de vérifications supplémentaires sur le fichier, doivent être mises en œuvre pour garantir une exécution sécurisée.
Le déchiffrement intervient après le délai d'attente ( TIME). Dans certains cas, cela peut entraîner des délais d'exécution plus longs si le déchiffrement prend beaucoup de temps. Envisagez de déchiffrer le fichier en parallèle pendant l'attente afin de réduire le temps d'exécution global.

Clause de non-responsabilité
Ce programme est fourni en l'état, sans aucune garantie. L'auteur décline toute responsabilité en cas de dommages ou d'utilisation abusive résultant de son utilisation. Il est conseillé aux utilisateurs d'utiliser ce programme de manière responsable et légale, en respectant toutes les lois et réglementations en vigueur.