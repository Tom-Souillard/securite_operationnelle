
### **Synthèse**
- **Analyste SOC (Security Operations Center)** : Professionnel chargé de surveiller, détecter, analyser et répondre aux incidents de sécurité au sein d’un SOC.
- **Objectif** : Assurer une surveillance en temps réel des infrastructures IT pour détecter, analyser et neutraliser les menaces de sécurité.
- **Compétences clés** : Surveillance des SIEM (Security Information and Event Management), analyse de logs, gestion des incidents, réponse rapide aux menaces.
- **Niveaux d'expertise** : Analyste SOC niveau 1 (L1), niveau 2 (L2), et niveau 3 (L3).

---

### **Développement**

#### **1. Définition et mission d’un analyste SOC**
Un **analyste SOC** est un professionnel de la cybersécurité qui travaille dans un **centre des opérations de sécurité (SOC)**. Sa principale mission est de surveiller en continu les infrastructures informatiques d'une organisation afin d’identifier les incidents de sécurité, d'analyser les menaces potentielles, et de réagir rapidement pour limiter les dommages.

L’analyste SOC fait partie intégrante de la stratégie de défense de l’organisation, en tant qu'élément essentiel de la détection et de la réponse aux menaces de sécurité. Les responsabilités varient en fonction du **niveau d’expertise** (L1, L2, L3), chaque niveau étant spécialisé dans différentes étapes de la détection, de l’analyse et de la réponse.

#### **2. Niveaux et responsabilités des analystes SOC**
Les analystes SOC sont souvent organisés en **trois niveaux**, chacun ayant des responsabilités et des compétences spécifiques :

### **Détail des Niveaux et Responsabilités des Analystes SOC**

#### **2.1. Analyste SOC Niveau 1 (L1) – Détection initiale**

**Rôle principal** : L'analyste L1 est chargé de surveiller en temps réel les événements de sécurité à l’aide d’outils de monitoring tels que les **SIEM** (Security Information and Event Management). Sa tâche principale consiste à filtrer les alertes pour identifier celles qui nécessitent une analyse approfondie.

**Tâches spécifiques** :
1. **Surveillance des alertes** : L'analyste L1 passe en revue les alertes générées par les outils de surveillance comme un SIEM. Les alertes peuvent inclure des connexions suspectes, des tentatives d'accès non autorisées, ou des activités inhabituelles sur le réseau.
   - **Exemple concret** : Une alerte sur une connexion non autorisée à un serveur sensible apparaît dans le SIEM (ex. Splunk). L'analyste L1 vérifie les logs d'authentification pour déterminer si la tentative est légitime (par exemple, due à un administrateur travaillant à distance) ou malveillante (tentative de compromission).
   
2. **Validation des incidents** : Une fois une alerte identifiée, l'analyste L1 valide si elle nécessite une escalade ou non. Cela inclut la vérification des logs associés et la validation avec les utilisateurs concernés.
   - **Exemple concret** : L'analyste détecte une tentative de login via un compte administrateur à des heures inhabituelles. Après analyse des logs et vérification avec l'utilisateur, il découvre que c’est une tentative légitime, nécessitant donc aucune escalade.

3. **Documentation et rapports d'incidents** : L'analyste L1 documente toutes les alertes traitées, même celles qui ne nécessitent pas d'escalade, afin de maintenir une traçabilité complète.
   - **Exemple concret** : Chaque alerte est enregistrée dans un système de gestion des incidents (ex. : **ServiceNow**), et des rapports quotidiens sont envoyés aux équipes de supervision.

**Outils courants** :
- **SIEM** : Splunk, QRadar.
- **Gestion de tickets** : ServiceNow.
- **Surveillance des terminaux** : SentinelOne, CrowdStrike.

**L’escalade**
L’**escalade** dans le contexte d’un **SOC** fait référence au processus par lequel un incident ou une alerte de sécurité est transféré à un niveau supérieur d’analyse ou de gestion. Cela se produit lorsque l’incident dépasse les compétences ou les responsabilités d’un analyste de niveau inférieur (L1) et nécessite une analyse plus approfondie ou une expertise avancée.

Exemple d'escalade :
- **L1** : Un analyste reçoit une alerte de comportement suspect sur le réseau. Après une première validation, il découvre qu'il s'agit potentiellement d'une attaque sophistiquée. Il **escalade** l'incident à l'analyste **L2** pour une investigation plus poussée (par exemple, analyse réseau ou comportementale).
- **L2** : Si l’analyste L2 confirme la présence d’une attaque complexe comme un malware non répertorié ou une exfiltration de données, il peut **escalader** l’incident à un **L3** ou à l’équipe de gestion des incidents pour une réponse urgente ou des actions correctives stratégiques.

L'escalade permet de garantir que les incidents sont traités au niveau approprié de compétence et de priorité.
#### **2.2. Analyste SOC Niveau 2 (L2) – Analyse avancée**

**Rôle principal** : L’analyste L2 prend en charge les incidents escaladés par l’analyste L1. Il est responsable d’une analyse plus poussée pour comprendre les causes sous-jacentes des incidents et proposer des solutions de remédiation.

**Tâches spécifiques** :
1. **Analyse approfondie des incidents** : L’analyste L2 analyse les incidents en détail, notamment via l’inspection des **paquets réseau** (Wireshark) ou l’examen de fichiers suspects.
   - **Exemple concret** : Un analyste L2 reçoit une alerte sur un trafic réseau anormal. En utilisant **Wireshark**, il détecte une tentative de communication non autorisée vers un serveur C2 (Command & Control) via un canal DNS.

2. **Investigation sur les malwares** : En cas de détection de logiciels malveillants, l’analyste L2 effectue une analyse dynamique (exécution dans un environnement contrôlé) et statique (analyse du code source).
   - **Exemple concret** : Un analyste utilise **Cuckoo Sandbox** pour exécuter un fichier suspect et observer son comportement. Il découvre qu’il s’agit d’un malware tentant de voler des informations d’identification via un keylogger.

3. **Coordination avec l’équipe IR (Incident Response)** : L'analyste L2 collabore avec les équipes de réponse aux incidents pour implémenter des solutions correctives (isolation des systèmes compromis, suppression des malwares, réinitialisation des accès).
   - **Exemple concret** : Après analyse d'un malware, l'analyste recommande la désactivation temporaire des comptes compromis et la mise en place de nouveaux contrôles d'accès.

#### **Outils courants** :
- **Analyse réseau** : Wireshark.
- **Analyse de malware** : Cuckoo Sandbox, VirusTotal.
- **Threat Intelligence** : MISP, AlienVault OTX.

**1. Wireshark (Analyse Réseau)**

**Wireshark** est un outil open-source et gratuit utilisé pour capturer et analyser le trafic réseau en temps réel. Il permet de visualiser les paquets de données échangés entre différents appareils sur un réseau, facilitant l’identification d’activités suspectes, de fuites d’information, ou de problèmes de performance réseau. Wireshark offre une granularité fine dans l’analyse réseau, permettant de filtrer et d’inspecter les protocoles (TCP, UDP, HTTP, DNS, etc.).

- **Coût** : Gratuit (open-source).
- **Cas d’usage** : Identification de tentatives d'exfiltration de données, analyse d'attaques DDoS.

**2. Cuckoo Sandbox (Analyse de malware)**

**Cuckoo Sandbox** est un système open-source permettant d’analyser des malwares en exécutant les fichiers suspects dans un environnement isolé (sandbox). Il observe et enregistre le comportement des malwares, comme les modifications de fichiers, les connexions réseau, et les interactions avec le système, sans risquer de compromettre les machines de production.

- **Coût** : Gratuit (open-source).
- **Cas d’usage** : Analyse comportementale de malwares inconnus, détection de ransomwares ou de trojans via des échantillons exécutés en sandbox.

**3. VirusTotal (Analyse de malware)**

**VirusTotal** est un service en ligne qui permet de soumettre des fichiers ou des URL pour les analyser à travers plusieurs moteurs d'antivirus simultanément. Il fournit une évaluation rapide pour déterminer si un fichier ou une URL est malveillant, ainsi que des informations sur les signatures de malware connues.

- **Coût** : Gratuit pour les utilisateurs basiques ; plans premium disponibles pour des analyses plus poussées.
- **Cas d’usage** : Vérification rapide de fichiers ou de liens potentiellement malveillants avant déploiement ou utilisation.

**4. MISP (Threat Intelligence)**

**MISP** (Malware Information Sharing Platform) est une plateforme open-source de partage d'informations sur les menaces (Threat Intelligence), permettant aux organisations de collaborer en partageant des indicateurs de compromission (IoCs), des rapports d'incidents et des données sur les cyberattaques. MISP aide à identifier les menaces émergentes et à réagir rapidement.

- **Coût** : Gratuit (open-source).
- **Cas d’usage** : Collaboration inter-entreprises ou entre CERTs pour échanger des IoCs sur des attaques récentes ou des campagnes de phishing.

**5. AlienVault OTX (Threat Intelligence)**

**AlienVault OTX** (Open Threat Exchange) est une plateforme communautaire de threat intelligence qui permet aux utilisateurs de partager et de consulter des informations sur les menaces. OTX fournit un accès aux indicateurs de menaces collectés globalement, et permet d'intégrer ces informations directement dans les systèmes de détection comme SIEM.

- **Coût** : Gratuit pour les fonctionnalités de base, offre premium via la suite **AlienVault USM**.
- **Cas d’usage** : Intégration des indicateurs de menaces dans les systèmes de détection d’une organisation pour anticiper et prévenir des attaques ciblées.

#### **2.3. Analyste SOC Niveau 3 (L3) – Expertise avancée et gestion des crises**

**Rôle principal** : L’analyste L3 est l'expert qui prend en charge les incidents les plus complexes ou critiques, souvent en coordination avec des équipes IT et les cadres de l'entreprise. Il est responsable de la gestion des crises et des investigations post-incidents pour identifier la cause racine et implémenter des améliorations de sécurité.

**Tâches spécifiques** :
1. **Gestion des incidents critiques** : L’analyste L3 est souvent responsable des incidents majeurs, tels que des attaques de **ransomware**, où une action rapide et coordonnée est nécessaire pour éviter des pertes de données massives.
   - **Exemple concret** : Une entreprise est victime d'une attaque par ransomware. L’analyste L3 coordonne les efforts de restauration des systèmes à partir de sauvegardes, coupe les accès réseau compromis, et supervise le processus de déchiffrement des systèmes affectés.

2. **Investigation post-incident** : Après la gestion de l'incident, l'analyste L3 mène une investigation approfondie pour identifier la faille de sécurité initiale et proposer des mesures de prévention afin d'éviter que l'incident ne se reproduise.
   - **Exemple concret** : L’analyste L3 mène une analyse approfondie après une compromission par phishing et découvre que le vecteur d'entrée était un mail contenant une macro malveillante. Il recommande de bloquer l’exécution de macros sur les comptes utilisateurs sensibles.

3. **Optimisation des processus de sécurité** : En tant qu’expert, l'analyste L3 améliore les processus et outils de sécurité de l’organisation, tels que la configuration des SIEM ou la définition de nouvelles règles de détection d’intrusion.
   - **Exemple concret** : L’analyste L3 constate que certaines attaques passent sous le radar du SIEM actuel. Il implémente de nouvelles règles de détection pour identifier plus efficacement les communications suspectes avec des serveurs C2.

#### **Outils courants** :
- **SOAR (Security Orchestration Automation and Response)** : Phantom, Demisto.
- **Threat Hunting** : Outils de chasse aux menaces pour identifier des indicateurs de compromission non encore détectés par le SIEM.
- **Investigation post-incident** : Enquêtes techniques approfondies pour identifier la cause racine des incidents.

##### **1. SOAR (Security Orchestration, Automation, and Response)**

**SOAR** est une plateforme qui aide à automatiser et orchestrer les tâches liées à la gestion des incidents de sécurité. Il intègre diverses sources de données (logs, alertes, rapports d'incidents) et permet d’automatiser des réponses aux incidents, réduisant ainsi le temps de réponse.

**Phantom**
- **Description** : Phantom (acquis par Splunk) est l’une des plateformes SOAR les plus populaires. Il permet d'automatiser des playbooks de réponse à des incidents de sécurité, d'orchestrer des actions (comme le blocage d'IP, l'isolement de systèmes), et de générer des rapports.
- **Prix** : La solution fait partie de l'écosystème Splunk, et peut coûter environ **150 à 200 $ par Go/jour de données ingérées**. Les prix varient selon le volume de données et les options de déploiement.
  
**Demisto**
- **Description** : Demisto (acquis par Palo Alto Networks) est une autre plateforme SOAR qui offre des capacités d'automatisation, de gestion des incidents et de collaboration. Elle permet aux équipes SOC de partager des données en temps réel et d’automatiser les tâches répétitives.
- **Prix** : Incluse dans la suite **Cortex XSOAR** de Palo Alto, dont le coût moyen varie entre **40 000 et 70 000 $ par an**, en fonction des modules et de la taille de l'entreprise.

**Alternatives plus abordables**
- **Shuffle** (open-source) : Alternative gratuite et open-source pour les petites organisations. Shuffle propose des automatisations et des intégrations avec des solutions SIEM ou EDR.
- **TheHive Project** (open-source) : TheHive est une plateforme gratuite qui propose des capacités de gestion d'incidents, d'enquêtes et de collaboration. Il peut être intégré avec **Cortex** pour les réponses automatisées.

##### **2. Threat Hunting (Chasse aux menaces)**

La **chasse aux menaces** est une approche proactive de la cybersécurité qui consiste à rechercher des signes d'intrusion ou de comportement malveillant dans un réseau, souvent avant qu'ils ne déclenchent des alertes traditionnelles comme celles d'un SIEM.

**Outils populaires de Threat Hunting**

- **CrowdStrike Falcon OverWatch** :
  - **Description** : Service de threat hunting managé, intégré à la plateforme CrowdStrike. L’équipe OverWatch utilise des techniques d’analyse comportementale pour identifier des menaces sophistiquées non détectées par les solutions automatiques.
  - **Prix** : CrowdStrike propose une facturation par terminal surveillé. Les coûts varient en fonction du service choisi, mais pour une entreprise de taille moyenne, cela peut être de **8 à 15 $ par terminal par mois**.
  
- **Carbon Black** (VMware):
  - **Description** : Solution qui permet aux équipes SOC d'effectuer des recherches actives sur les menaces à travers les terminaux de l'entreprise, avec des fonctionnalités de surveillance en temps réel et d'analyse.
  - **Prix** : Environ **50 $ par terminal par an** pour les fonctionnalités basiques, mais peut varier selon les fonctionnalités avancées.

**Alternatives plus abordables**
- **OpenEDR** (open-source) : Un outil gratuit et open-source permettant d’effectuer une surveillance des terminaux et d’analyser des menaces pour des petites et moyennes entreprises.
- **Wazuh** (open-source) : Wazuh est une plateforme de détection d’intrusion et de chasse aux menaces qui est gratuite et open-source. Elle offre une gestion centralisée des incidents de sécurité.

##### **3. Investigation post-incident**

L’**investigation post-incident** consiste à mener une enquête approfondie après un incident de sécurité pour identifier les causes profondes, évaluer les impacts, et définir des mesures correctives pour prévenir des incidents futurs.

**Outils populaires pour l'investigation post-incident**

- **Splunk Enterprise Security** :
  - **Description** : Plateforme SIEM qui permet de centraliser les logs et d'effectuer des enquêtes approfondies sur les incidents grâce à l'analyse des logs historiques et en temps réel.
  - **Prix** : Splunk fonctionne sur un modèle basé sur la quantité de données ingérées. Le coût moyen est d’environ **150 $ par Go/jour** de données ingérées.

- **ELK Stack** (Elasticsearch, Logstash, Kibana) :
  - **Description** : Outil open-source permettant de collecter, stocker, et visualiser les logs pour une analyse approfondie des incidents.
  - **Prix** : Gratuit (open-source), mais des frais peuvent être associés à l'hébergement ou aux services managés comme **Elastic Cloud**, qui commencent à **16 $ par mois** pour des capacités de base.

**Alternatives plus abordables**
- **Graylog** (open-source) : Une alternative open-source pour l’analyse des logs et l’investigation post-incident, similaire à ELK mais plus facile à configurer.
- **Sentry** (open-source) : Sentry est une plateforme gratuite qui aide à suivre et analyser les erreurs et incidents dans les applications.


#### **3. Outils et technologies utilisés par les analystes SOC**
Les analystes SOC s'appuient sur une panoplie d'outils technologiques pour surveiller, détecter et répondre aux incidents de sécurité. Parmi les outils couramment utilisés :
- **SIEM (Security Information and Event Management)** : Systèmes centralisant les logs pour la corrélation d’événements de sécurité (ex : **Splunk**, **QRadar**).
- **EDR (Endpoint Detection and Response)** : Outils permettant de surveiller et de réagir aux activités suspectes sur les postes de travail et serveurs (ex : **CrowdStrike Falcon**, **SentinelOne**).
- **Surveillance réseau** : Capture et analyse du trafic réseau pour identifier des comportements anormaux (ex : **Wireshark**, **Zeek**).
- **Sandboxing** : Analyse de logiciels malveillants dans un environnement sécurisé (ex : **Cuckoo Sandbox**, **FireEye**).

#### **4. Compétences et qualifications requises**
Pour réussir dans ce rôle, un analyste SOC doit posséder une combinaison de compétences techniques et analytiques, ainsi qu'une bonne compréhension des menaces actuelles en cybersécurité.
- **Compétences techniques** : Maîtrise des systèmes d'exploitation (Windows, Linux), des réseaux (TCP/IP, firewalls, VPN), des outils d’analyse de logs et des technologies de sécurité (SIEM, EDR, IDS/IPS).
- **Compétences analytiques** : Capacité à analyser des événements complexes, comprendre les schémas de menace, et recommander des mesures de sécurité appropriées.
- **Certifications recommandées** :
  - **CompTIA Security+**
  - **Certified Information Systems Security Professional (CISSP)**
  - **Certified Ethical Hacker (CEH)**
  - **GIAC Security Essentials (GSEC)**

#### **5. Responsabilités transversales et collaboration**
Les analystes SOC travaillent en collaboration étroite avec d’autres départements de sécurité et IT :
- **Collaboration avec l'équipe de gestion des incidents** : Lorsque des incidents sont identifiés, les analystes SOC jouent un rôle crucial dans la coordination avec l'équipe IR (Incident Response) pour minimiser les dommages.
- **Formation continue** : Les analystes doivent suivre les dernières tendances en matière de menaces (APT, ransomware, vulnérabilités zero-day) et mettre à jour en conséquence les procédures de sécurité.
- **Amélioration continue des processus** : Les analystes SOC contribuent à la définition et l’optimisation des processus de sécurité, et identifient les faiblesses pour renforcer les contrôles existants.

---

### **Conclusion**
Le rôle d’un **analyste SOC** est central dans la stratégie de défense d'une organisation. Leur responsabilité de surveillance, détection et réponse aux menaces de sécurité permet de limiter les impacts des cyberattaques et d'assurer la continuité des opérations. La répartition des niveaux (L1, L2, L3) garantit une approche structurée, de la détection initiale à la gestion de crises complexes. Les analystes SOC doivent rester en constante formation pour s'adapter à l'évolution des menaces et des technologies.