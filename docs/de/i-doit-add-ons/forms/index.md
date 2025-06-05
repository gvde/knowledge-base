---
title: Forms
description: Forms installation
icon:
status: updated
lang: de
---

# Forms

Mit diesem Add-on können Sie Formulare erstellen, die Sie an anderen Mitarbeitern zum ausfüllen via Link zusenden können. Dieses Add-on kann ein Formular erstellen, dass zum Beispiel neuen Mitarbeitern hilft Computer in Ihrem Unternehmen zu dokumentieren.

Beim Erfassen von neuen Objekten ist es häufig so, dass zwar mehrere Kategorien angezeigt werden, aber aus jeder Kategorie nur einzelne Felder gepflegt werden müssen. In dem Fall ist es für den User (speziell wenn es neue Kollegen sind) einfacher, wenn nur die Attribute angezeigt werden, die tatsächlich ausgefüllt werden müssen.

Eine Vorstellung des Add-ons finden Sie auch auf unserem Blog, [hier](https://www.i-doit.com/blog/das-neue-i-doit-pro-forms-add-on/). Außerdem wurde ein [Video](https://www.youtube.com/watch?v=3jpzrK_cR0M) erstellt.

!!! info "Das Forms Add-on wird aktuell in Englisch bereitgestellt. Übersetzungen die von i-doit stammen werden auch in Deutsch übersetzt."

[![forms-ansicht](../../assets/images/de/i-doit-add-ons/forms/1-forms.png)](../../assets/images/de/i-doit-add-ons/forms/1-forms.png)

## Anforderungen

Das Forms Add-on benötigt:

*   i-doit Version **\>= v23**
*   MongoDB Server Version **\>=8**
*   NodeJS Version **\>= v22.x**

Es müssen die Systemvoraussetzungen von [MongoDB](https://docs.mongodb.com/manual/administration/production-notes/#mongodb-binaries) beachtet werden. Außerdem hat MongoDB eine [Checkliste für den Einsatz im Betrieb](https://docs.mongodb.com/manual/administration/production-checklist-operations/#operations-checklist).

[NodeJS](https://nodejs.org/en/download/current/) hat seine [Abhängigkeiten hier Dokumentiert](https://nodejs.org/en/docs/).

## Installation

Folgende Schritte sind notwendig um das Add-on nutzen zu können:

*   Installieren des Forms Add-on über das [Admin-Center](../../administration/admin-center.md)
*   [MongoDB Server **v8**](https://docs.mongodb.com/manual/installation/) installation
*   anschließend wird [NodeJS **v22**](https://nodejs.org/en/download/current/) installiert via [nvm Package Manager](https://github.com/nvm-sh/nvm)
*   das Forms Backend konfiguriert
*   und dann i-doit konfiguriert

[Weiter zur Installation des Forms Add-on](forms-installation.md){ .md-button .md-button--primary }

## Rechtevergabe

Damit Benutzer in der Lage sind, Formulare zu erstellen, ist es nötig entsprechende [Rechte](../../effizientes-dokumentieren/rechteverwaltung/index.md) zu vergeben. Dies ist in der i-doit Verwaltung unterRechtesystem > Rechtevergabe > Forms möglich, wenn das Add-on installiert ist.

[![Rechtevergabe](../../assets/images/de/i-doit-add-ons/forms/2-forms.png)](../../assets/images/de/i-doit-add-ons/forms/2-forms.png)

!!! attention "Cache für das Rechtesystem leeren"
    Nachdem die Rechte vergeben oder geändert wurden ist es notwendig, in der i-doit [Verwaltung](../../administration/verwaltung/index.md) unter **Verwaltung → [Mandanten-Name] Verwaltung → Systemreparatur und Berechtigungen** [Cache](../../administration/verwaltung/mandanten-name-verwaltung/systemreparatur-und-bereinigung.md) zu leeren, damit die Änderungen vom System übernommen werden.

## Aufruf des Add-ons

Nachdem alle Vorbereitungen abgeschlossen sind ist der Zugriff auf das Add-on ist über `Add-ons → Forms` möglich. Die Ansicht des Menüs "Add-ons" kann sich Aufgrund unterschiedlicher Rechte und/oder weiterer installierter Add-ons unterscheiden.

## Verwendung der API

Dieses Dokument enthält eine rudimentäre Beschreibung der Forms-API.

!!! info "[Verwendung der Forms API](verwenden-der-forms-api.md)"

## Releases

| Version | Date       | Changelog                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1.2.1   | 2025-05-14 | [Task] Allow removal of instances and their data over cli<br> [Task] Implement health endpoint on backend-server<br>[Task] Add support for node v22 on backend-server<br>[Task] Add support for mongodb v8.x on backend-server                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 1.2.0   | 2023-05-03 | [Bug] Fix Investment cost and cost center with Forms<br> [Bug] Align categories on the left side<br>[Bug] Fix right to delete or create Forms<br>[Bug] Fix empty list in object browser if category names should be used in header<br>[Bug] Show objects if attribute type is missing<br>[Bug] Improve rendering performance of object browser fields with multiple objects<br>[Bug] Filter child values after parent values                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 1.1.0   | 2022-06-27 | [Bug] Allow all default characters to be used in Forms-secret key  <br>[Bug] Do not show time selection in Start date for license keys  <br>[Bug] Allow to publish form if load balancer and HTTP2 is used  <br>[Bug] Save Form when publishing  <br>[Bug] Create Logbook entries when creating an object and category data via "Forms" add-on  <br>[Bug] Filter down connectable objects for custom categories with object relations in Forms  <br>[Bug] Allow user to copy link in Forms table  <br>[Bug] Allow user to select multiple objects in Forms object browser  <br>[Bug] Inform user about required attributes in category  <br>[Task] Add tooltip to disabled state of copy link button in Forms add-on  <br>[Task] Allow to add child attribute only when parent dependent is added  <br>[Task] Change real text to placeholder text in text field in Forms add-on  <br>[Task] Do not allow to add same attribute multiple times in Forms  <br>[Task] Give user warning before publishing if form will be empty  <br>[Task] Add dependencies of object browser to Forms add-on  <br>[Task] Split hostaddress category into virtual IPv4 and IPv6 categories for Forms add-on  <br>[Task] Take default template values in consideration in Forms  <br>[Task] Update attribute name in pre-defined field in Forms add-on  <br>[Task] Disable child attribute until a value for parent is assigned  <br>[Task] Implement Pagination in Attribute Type Object Browser Single- and Multi-Selection |
| 1.0.0   | 2022-02-21 | Initial release                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
