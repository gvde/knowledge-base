# Installation NodeJS

!!! attention "Die Installation wurde zuletzt mit NodeJS v17.4 getestet"

Abhängigkeiten sind [hier](https://nodejs.org/en/docs/meta/topics/dependencies/) zu finden.<br>
Ein manueller Download sowie Installation ist von [hier](https://nodejs.org/en/download/) möglich.

Für den nächsten Schritt benötigen wir cURL:

    sudo apt-get install curl

NodeJS wird via package manager automatisch installiert dazu verwenden wir [nodesource](https://github.com/nodesource/distributions/blob/master/README.md):

    curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -

Nun können wir NodeJS installieren:

    sudo apt-get install -y nodejs

[Weiter zur Konfiguration das Forms Backend](./konfiguration-des-forms-backend.md){ .md-button .md-button--primary }
