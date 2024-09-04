### **Synthèse**
- **Concept** : La pyramide de la douleur, proposée par David Bianco, montre l'impact relatif sur l'attaquant lorsqu'un défenseur bloque certains types d'indicateurs de compromission (IoCs).
- **Niveaux** : Plus on monte dans la pyramide, plus il est difficile pour l'attaquant de continuer son attaque après la détection.
- **IoCs** : Les éléments bloqués incluent hash de fichier, adresse IP, nom de domaine, signature réseau, et techniques TTPs (Tactics, Techniques, and Procedures).

---

### **Développement**

#### **1. Définition générale**
La **Pyramide de la Douleur** est un modèle qui aide les défenseurs à comprendre l'efficacité des différents indicateurs de compromission (IoC) lorsqu'ils sont détectés et bloqués. Il montre que plus l'IoC est spécifique aux comportements des attaquants, plus son impact est significatif.

| **Niveau**           | **Type d'indicateur**               | **Description**                                                         | **Exemple**                                               |
| -------------------- | ----------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------- |
| **TTPs**             | Tactiques, Techniques et Procédures | Attaques basées sur des comportements récurrents spécifiques.           | Utilisation de PowerShell pour l'escalade des privilèges. |
| **Signature réseau** | Modèle de trafic réseau             | Modèles dans le trafic réseau générés par les malwares ou les C2.       | Beaconing C2 détecté via des modèles DNS anormaux.        |
| **Nom de domaine**   | Domaines malveillants               | Noms de domaine utilisés par les attaquants pour exfiltrer des données. | Utilisation de DGA pour créer des domaines.               |
| **Adresse IP**       | IP des attaquants                   | Adresses IP associées aux serveurs de commande et contrôle.             | Blocage des IP associées à un botnet.                     |
| **Hash de fichier**  | Empreintes de fichiers              | Identifiant unique d'un fichier malveillant (hash).                     | MD5/SHA256 d’un fichier exécutable malveillant.           |

#### **2. Importance des niveaux**
Voici une explication détaillée pour chaque partie de la pyramide
##### Niveau 1. **TTP (Tactics, Techniques, and Procedures)**
   - **Explication**: Les TTP représentent les tactiques, techniques et procédures utilisées par les attaquants pour atteindre leurs objectifs. Cela inclut les plans globaux des attaquants, la manière dont ils choisissent de réaliser leurs attaques, et leurs méthodes spécifiques pour contourner les défenses.
   - **Exemple**: Un acteur malveillant utilise une combinaison de phishing (technique) et d'exploitation de vulnérabilités non corrigées (procédure) pour obtenir un accès non autorisé aux systèmes.
   - **"The attackers plans and objectives."**
     - Les plans et les objectifs sont intégrés dans les TTP, décrivant comment l'attaquant atteint ses buts avec des méthodes spécifiques.

---

##### Niveau 2. **Tools (Outils)**
   - **Explication**: Les attaquants se servent d'outils spécifiques pour réaliser leur attaque. Ces outils peuvent être des logiciels malveillants (malwares), des exploits automatisés, ou des scripts pour contourner la sécurité.
   - **Exemple**: L'attaquant utilise **Mimikatz**, un outil populaire pour extraire des mots de passe en mémoire sur les systèmes Windows.
   - **"The attacker has utilised these to accomplish their objective."**
     - Les outils sont utilisés pour accomplir les objectifs de l'attaquant, comme l'accès non autorisé, l'exfiltration de données, ou la perturbation d'un service.

---

##### Niveau 3. **Network (Réseau)**
   - **Explication**: Cette étape concerne les artefacts liés à l'infrastructure réseau utilisée par l'attaquant. Cela inclut les protocoles de communication malveillants, les adresses IP de commande et de contrôle (C2), et les serveurs de livraison de logiciels malveillants.
   - **Exemple**: Un attaquant peut utiliser une adresse IP spécifique pour héberger un serveur de commande et de contrôle, à travers lequel il dirige des machines infectées par un malware.
   - **"These artefacts can present themselves as C2 traffic for example."**
     - L'infrastructure réseau peut inclure le trafic C2 (commande et contrôle), un exemple typique de l'utilisation d'artefacts réseau dans une attaque.

---

##### Niveau 4. **Domain Names (Noms de domaine)**
   - **Explication**: Les noms de domaine sont souvent utilisés par les attaquants pour servir de passerelles vers des serveurs malveillants. Ils peuvent acheter des noms de domaine qui ressemblent à des sites légitimes pour mener des attaques de type typosquatting ou pour héberger des pages de phishing.
   - **Exemple**: Un attaquant achète le domaine **"go0gle.com"** (au lieu de **"google.com"**) pour tromper les utilisateurs et voler leurs informations de connexion.
   - **"An attacker has purchased this and used it in a typo-squatting campaign."**
     - Un exemple classique d'utilisation malveillante de noms de domaine, typiquement dans des campagnes de phishing ou de typosquatting.

---

##### Niveau 5. **IP addresses (Adresses IP)**
   - **Explication**: Les adresses IP sont des éléments d'infrastructure critiques, identifiables et traçables. Elles sont utilisées par les attaquants pour héberger des serveurs, contrôler les bots, ou livrer des logiciels malveillants. Les chercheurs en sécurité utilisent les adresses IP pour identifier et bloquer les activités malveillantes.
   - **Exemple**: Un serveur malveillant utilisant l’adresse IP **192.168.1.1** pour rediriger des utilisateurs vers un site de phishing.
   - **"These addresses can be used to identify the infrastructure an attacker is using for their campaign."**
     - Les adresses IP permettent de relier les infrastructures à des activités malveillantes, aidant à identifier les campagnes d'attaque.

---

##### Niveau 6. **Hash values (Valeurs de hachage)**
   - **Explication**: Les valeurs de hachage sont des signatures uniques générées à partir de fichiers, souvent utilisées pour identifier et comparer des fichiers malveillants ou non modifiés. Elles permettent d'attribuer des artefacts ou des charges utiles à des attaquants connus.
   - **Exemple**: Le fichier malveillant **ransomware.exe** génère la valeur de hachage **d41d8cd98f00b204e9800998ecf8427e**, utilisée pour l’identifier et l'associer à une campagne de ransomware connue.
   - **"These signatures can be used to attribute payloads and artefacts to an actor."**
     - Les valeurs de hachage permettent de lier des fichiers malveillants à des acteurs ou des campagnes spécifiques, en se basant sur des signatures numériques.

Chaque niveau de la pyramide est important dans la recherche de traces d'activités malveillantes et permet de tracer et d'attribuer des attaques à des acteurs spécifiques.

#### **3. Utilisation par les défenseurs**
L'organisation de la **"pyramide de la douleur"** (ou **Pyramid of Pain**) en cybersécurité vise à maximiser l'impact des efforts de défense en fonction du niveau de difficulté qu'une attaque impose aux cybercriminels lorsqu'ils sont bloqués. Chaque étape de la pyramide correspond à un type d'indicateur de compromission (IOC) que les défenseurs peuvent utiliser pour perturber les attaquants, du plus simple au plus complexe à contourner.

Voici comment aborder chaque étape de cette pyramide, en commençant par le sommet (les TTP, qui causent le plus de douleur aux attaquants) et en descendant jusqu'à la base (les valeurs de hachage, qui causent relativement peu de perturbation).

##### 1. **Tactics, Techniques, and Procedures (TTP)**
   - **Description**: C'est la couche la plus élevée de la pyramide, représentant les tactiques, techniques et procédures qu'un attaquant utilise. Cela inclut les stratégies à long terme et les comportements généraux d'un groupe ou d'un individu.
   - **Comment aborder cette étape**: 
     - **Surveillance des TTP**: Utilisez des cadres comme MITRE ATT&CK pour documenter les TTP utilisés par les attaquants.
     - **Automatisation et Threat Hunting**: Mettez en place des systèmes de détection avancée comme l'EDR (Endpoint Detection and Response) pour détecter les comportements suspects associés à des TTP spécifiques.
     - **Apprentissage automatique**: Utilisez des systèmes qui apprennent à identifier les tactiques inhabituelles sur vos réseaux.
   - **Impact**: Changer leurs TTP est extrêmement coûteux pour les attaquants car cela demande de repenser fondamentalement leur approche et leurs méthodes d'attaque.
   - **Exemple**: Si vous pouvez identifier que les attaquants utilisent la tactique de l'élévation de privilèges par exploitation de vulnérabilités connues, en corrigeant ces vulnérabilités ou en changeant les configurations système, vous les forcez à changer totalement de stratégie.

---

##### 2. **Tools (Outils)**
   - **Description**: Les outils sont les logiciels, scripts ou kits utilisés par les attaquants pour réaliser leurs attaques. Il peut s'agir de malwares, d'outils d'exploitation de vulnérabilités ou de scanners de réseaux.
   - **Comment aborder cette étape**:
     - **Blocage des outils**: Identifiez les outils spécifiques qu'un attaquant utilise (par exemple, Cobalt Strike ou Mimikatz) et créez des règles de blocage ou des signatures dans vos systèmes de sécurité.
     - **Surveillance des indicateurs**: Utilisez des SIEM (Security Information and Event Management) pour détecter l'utilisation de certains outils sur vos réseaux.
     - **Gestion des privilèges**: Limitez les capacités des utilisateurs à télécharger ou exécuter des outils non autorisés sur les systèmes d'information.
   - **Impact**: Forcer les attaquants à changer d'outil est difficile et coûteux. Cela signifie qu'ils doivent trouver des alternatives ou développer de nouveaux outils.
   - **Exemple**: Si vous pouvez détecter et bloquer l'utilisation de Mimikatz sur vos réseaux, les attaquants devront chercher ou développer un autre outil pour voler des informations d'authentification.

---

##### 3. **Network (Réseau)**
   - **Description**: Les éléments de réseau incluent les serveurs de commande et de contrôle (C2), les proxys utilisés par les attaquants et les infrastructures de communication.
   - **Comment aborder cette étape**:
     - **Surveillance du trafic réseau**: Implémentez des systèmes de détection d'intrusion (IDS/IPS) pour surveiller et bloquer les communications avec les serveurs C2.
     - **Blocage du C2**: Identifiez et bloquez les adresses IP ou les noms de domaine associés aux serveurs de commande et contrôle.
     - **Segmentation du réseau**: Segmentez votre réseau pour réduire les mouvements latéraux d'un attaquant et isolez les systèmes vulnérables.
   - **Impact**: En bloquant les communications réseau malveillantes, vous empêchez l'attaquant de contrôler ou d'exfiltrer des données de vos systèmes. Cela peut forcer l'attaquant à trouver une nouvelle infrastructure réseau, ce qui est coûteux en temps et en ressources.
   - **Exemple**: Si vous identifiez un serveur C2 utilisé pour diriger des machines infectées, vous pouvez bloquer cette IP ou ce domaine, coupant ainsi l'accès des attaquants à leur infrastructure.

---

##### 4. **Domain Names (Noms de domaine)**
   - **Description**: Les attaquants utilisent des noms de domaine pour héberger des serveurs malveillants ou pour des campagnes de phishing et de typosquatting. Ils peuvent également utiliser des noms de domaine temporaires pour masquer leurs activités.
   - **Comment aborder cette étape**:
     - **Surveillance des noms de domaine** : Mettez en place des systèmes de détection DNS qui surveillent les noms de domaine utilisés dans votre trafic réseau, et vérifiez s'ils sont associés à des menaces connues.
     - **Bloquer les domaines malveillants** : Utilisez des outils de filtrage DNS pour bloquer l'accès aux domaines malveillants ou suspects, souvent utilisés pour le phishing, les campagnes de typosquatting ou l'hébergement de malwares.
     - **Liste noire de domaines** : Créez et maintenez une liste noire des domaines malveillants fréquemment associés à des activités suspectes et mettez-la à jour régulièrement.
   - **Impact** : Forcer les attaquants à changer de domaine est gênant mais relativement facile pour eux. Toutefois, cela complique leurs efforts, surtout s'ils comptent sur des noms de domaine qui sont déjà associés à leurs campagnes.
   - **Exemple** : Si un attaquant a acheté un domaine utilisé dans une campagne de phishing, comme **"microsoft-support-login.com"**, et que vous bloquez l'accès à ce domaine dans votre organisation, l'attaquant devra en acheter un autre, retardant ainsi l'attaque.

---

##### 5. **IP addresses (Adresses IP)**
   - **Description** : Les attaquants utilisent des adresses IP pour héberger des serveurs de commande et de contrôle, ou pour lancer des attaques. Bloquer une adresse IP peut perturber la communication avec leurs infrastructures malveillantes.
   - **Comment aborder cette étape** :
     - **Liste noire des adresses IP** : Mettez en place des systèmes de filtrage pour bloquer les adresses IP malveillantes connues dans vos pare-feux et systèmes de prévention d'intrusion.
     - **Surveillance des connexions réseau** : Utilisez des outils de monitoring pour identifier les connexions réseau suspectes vers des IP malveillantes, et bloquez-les en temps réel.
     - **Threat Intelligence** : Utilisez des sources de renseignement sur les menaces (threat intelligence) pour mettre à jour votre liste d'adresses IP suspectes ou malveillantes.
   - **Impact** : Bloquer des adresses IP est une mesure facile à contourner pour les attaquants, car ils peuvent changer d'IP ou utiliser des proxies ou des VPN. Cependant, cela peut encore leur faire perdre du temps et des ressources.
   - **Exemple** : Si vous bloquez une adresse IP associée à un serveur C2 utilisé par des attaquants pour exfiltrer des données, ils devront changer d'infrastructure pour continuer leurs opérations.

---

##### 6. **Hash values (Valeurs de hachage)**
   - **Description** : Les valeurs de hachage sont des signatures numériques uniques pour des fichiers spécifiques, notamment des malwares. Elles permettent d'identifier rapidement si un fichier donné a déjà été utilisé dans des campagnes malveillantes.
   - **Comment aborder cette étape** :
     - **Liste noire de hachages** : Utilisez des outils de sécurité qui comparent les fichiers téléchargés ou exécutés dans votre environnement à une base de données de valeurs de hachage malveillantes.
     - **Surveillance des fichiers** : Utilisez des outils antivirus et des systèmes de gestion des menaces pour bloquer les fichiers malveillants identifiés par leurs valeurs de hachage.
     - **Mises à jour régulières** : Mettez à jour régulièrement les bases de données de hachage malveillant pour vous assurer que vous bloquez les fichiers malveillants les plus récents.
   - **Impact** : Les attaquants peuvent facilement modifier un fichier ou un malware pour générer une nouvelle valeur de hachage, ce qui rend cette défense moins efficace à long terme. Cependant, cela peut quand même empêcher la diffusion de versions non modifiées de malwares connus.
   - **Exemple** : Si un ransomware est détecté et bloqué dans votre réseau en raison de sa valeur de hachage, les attaquants devront créer une nouvelle version du malware pour continuer leurs attaques, un processus qui peut leur prendre du temps.

---

##### Conclusion et stratégie d'organisation

Lorsque vous abordez la pyramide de la douleur, la meilleure stratégie est de se concentrer sur les étapes qui causent le plus de perturbation aux attaquants, c'est-à-dire les **TTP** et les **outils**, avant de descendre aux niveaux plus facilement contournables comme les **IP** et les **valeurs de hachage**. Voici une approche générale :

1. **Priorité à l'analyse des TTP** : Concentrez-vous sur la détection et la réponse aux TTP (Tactiques, Techniques, et Procédures) spécifiques utilisés par les attaquants. C'est ici que vous pouvez vraiment ralentir et perturber leurs efforts.
   
2. **Surveillance des outils utilisés** : Identifiez les outils malveillants et les logiciels utilisés par les attaquants dans vos environnements. En bloquant ces outils ou en les rendant inutilisables, vous forcez les attaquants à adopter de nouvelles méthodes.

3. **Surveillance réseau et blocage des C2** : Identifiez les artefacts réseau (trafic malveillant, C2) et les bloquer. Le suivi du trafic réseau peut empêcher l'attaquant de communiquer avec ses infrastructures.

4. **Gestion des noms de domaine** : Bloquez les noms de domaine malveillants et surveillez les domaines utilisés dans les attaques, comme ceux utilisés dans les campagnes de phishing ou typosquatting.

5. **Surveillance des adresses IP** : Mettez en place des règles de blocage d'adresses IP connues pour des activités malveillantes, bien que les attaquants puissent contourner cela en changeant d'IP.

6. **Valeurs de hachage** : Utilisez des listes de hachages malveillants pour détecter et bloquer des malwares déjà connus, mais soyez conscient que cette stratégie est facilement contournable par des changements mineurs dans le code des malwares.

Cette approche hiérarchique permet d'optimiser vos efforts en cybersécurité en maximisant la "douleur" pour l'attaquant à chaque étape.
#### **4. Cas pratiques**
- **Ransomware** : Identifier des hashes de fichiers malveillants ou des IPs de serveurs C2 peut fournir une défense immédiate mais limitée. Identifier les techniques comme l’utilisation de **WMI** ou **PowerShell** pour l’exécution du ransomware permet une meilleure prévention.
  
- **APT (Advanced Persistent Threat)** : Les TTPs spécifiques d'un groupe comme APT29 peuvent être beaucoup plus difficiles à modifier. Par exemple, APT29 utilise des outils de mouvement latéral précis et des comportements récurrents, comme l'exploitation de **Windows Management Instrumentation (WMI)** ou des **tâches planifiées**.

#### **5. Recommandations et bonnes pratiques**
- **Investissement dans la détection comportementale** : Se concentrer sur la surveillance des TTPs via des solutions comme **MITRE ATT&CK**.
- **Mise à jour des signatures réseau** : Assurez-vous que les modèles de trafic suspect sont continuellement mis à jour dans vos outils de détection.
- **Collaboration avec des Threat Intelligence Providers** : Utiliser des services tels que **VirusTotal**, **AlienVault**, ou **MISP** pour obtenir des données en temps réel sur les IoCs, mais combiner avec des défenses orientées sur le comportement.

---

### **Conclusion**
La **Pyramide de la Douleur** est un modèle puissant pour prioriser les efforts de défense. Se concentrer sur la détection et l'atténuation des TTPs apporte le plus grand impact pour contrer les cyberattaquants sophistiqués.