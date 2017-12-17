# Gruppen Finder

Es soll eine datenbankbasierte Webanwendung implementiert werden, die es in künftigen Jahren erlaubt Gruppen im Programmierpraktikum zu bilden. Es kann sinnvoll sein, die Anwendung entsprechend in [Self Contained Systems](http://scs-architecture.org/) aufzuteilen.

## Funktionsprinzip
* Studierende legen ein Profil an, auf dem sie ihre für das Praktikum relevanten Informationen ablegen können. Name, Github Profilname, Arbeitsproben, Intro-Text, ...
* Die Gründung einer Gruppe erfolgt ebenfalls durch die Studierenden. Für eine Gruppengründung wird ein Name benötigt und es müssen die Regeln für den Gruppenbeitritt und -ausschluss festgelegt werden. Es soll auch ein Profil für die Gruppe angelegt werden können.
* Es gibt eine Übersichtsseite auf der alle Gruppen gelistet sind. Gruppen mit freien Plätzen sind hervorgehoben, es können aber alle Gruppenprofile eingesehen werden.
* Studierende bewerben sich bei Gruppen. Bewerbungen bei mehreren Gruppen sind möglich. Es ist auch möglich, sich bei bereits vollständig belegten Gruppen zu bewerben, für den Fall, dass noch ein Platz frei wird.
* Wenn die Gruppe eine Bewerbung akzeptiert kann sie eine Frist geben, bis zu der die Aufnahme bestätigt werden muss, danach verfällt das Aufnahmeangebot
* Es sollten mehrere auswählbare Regelsätze für den Gruppenbeitritt und -ausschluss geben, vorstellbar wären zum Beispiel
	* Über beides entscheidet die Person, die die Gruppe gegründet hat.
	* Die Mehrheit entscheidet. Offen: Was passiert bei einem Patt? Kann die Person, die die Gruppe gegründet hat ausgeschlossen werden? Wer wird dann zum Gründer erhoben?
	* Für den Beitritt reicht eine Mehrheit, für den Ausschluss muss die Entscheidung einstimmig sein.
	* Beides muss einstimmig erfolgen (exklusive der Person, die ausgeschlossen werden soll)
	* Es gibt keinen Ausschluss.
	* ...
* Das System muss parametrisiert werden, so dass die minimale und maximale Gruppengrösse, sowie Zeiträume für die Gründung einstellbar sind.
* Sie können das System mit der [Github API](https://developer.github.com/v3/) integrieren, zum Beispiel um die Rechte der Gruppenrepositories automatisch einzustellen
* Sie könnten auch GitHub zur Authentifizierung der Nutzer verwenden (das Stichwort hier lautet OAuth)

# Hinweise
Das Setup in diesem Repository ist nur als Vorschlag gedacht, Sie können es nach eigenen Vorstellungen verändern.

Das Docker Setup in diesem Repository ist eine Musterlösung für das Projekt aus Woche 3.

Es kann hilfreich sein, nur die Datenbank per Docker zu starten und die Webanwendung in der IDE auszuführen.
Mit `docker-compose --file docker-compose_dbonly.yml up` können Sie die Datenbank ohne Webanwendung starten.
