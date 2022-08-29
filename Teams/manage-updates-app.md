---
title: Verwalten der Aktualisierungen-App für Ihre Organisation
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: Erfahren Sie, wie Sie die Aktualisierungen-App in Teams für Benutzer in Ihrer Organisation verwalten.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 66ff8f642e3e006221507953a2fff1740237aea0
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397106"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Aktualisierungen-App für Ihre Organisation in Microsoft Teams

## <a name="what-is-the-updates-app"></a>Was ist die Aktualisierungen-App?

Die Aktualisierungen in der Microsoft Teams-App bietet Mitgliedern Ihrer Organisation einen zentralen Ort zum Erstellen, Überprüfen und Übermitteln von Updates. Durch das Erstellen von Vorlagen können Sie die Aktualisierungen-App verwenden, um alles nachzuverfolgen, was Ihre Organisation benötigt. Aktualisierungen ist sowohl für Desktops als auch mobile Geräte verfügbar.

In Teams können Benutzer Aktualisierungen aus dem Teams-App Store abrufen. Alle aktualisierungen, die sie übermitteln müssen, werden auf der Seite **"Absenden** " angezeigt. Sie können den [Artikel "Erste Schritte in Aktualisierungen"](https://support.microsoft.com/office/get-started-in-updates-c03a079e-e660-42dc-817b-ca4cfd602e5a) mit Ihren Benutzern teilen, damit sie sich mit Aktualisierungen vertraut machen können.

[![Abbildung der Seite "Absenden" in Teams für Desktop.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

Benutzer können Updates, die sie zugewiesen haben, auf der Seite **"Überprüfen"** anzeigen.

[![Abbildung der Seite "Überprüfen" in Teams für Desktop.](media/updates-home-small.png)](media/updates-home.png#lightbox)

Wenn einem Benutzer ein Update zugewiesen ist, wird es in ihrem Teams-Aktivitätsfeed angezeigt. Benutzer können auch alle aktuellen Updateanforderungen und vorherigen Übermittlungen in der Aktualisierungen-App anzeigen. Darüber hinaus kann jeder Vorlagen erstellen und Aktualisierungsanforderungen senden.

Aktualisierungen enthält sowohl out-of-the-box-Vorlagen für allgemeine Geschäftsszenarien als auch die Option zum Erstellen einer eigenen Vorlage. Jeder kann eine Vorlage für neue Arten von Updates erstellen.

## <a name="example-scenario"></a>Beispielszenario

Mitarbeiter eines Bekleidungsgeschäfts sind täglich für die Eröffnung und Schließung des Ladens verantwortlich. Jeden Morgen füllt der Schichtleiter das Store-Öffnungsupdate aus, bei dem es sich um eine vordefinierte Vorlage in der Aktualisierungen-App handelt. In diesem Update beschreiben sie alle Probleme mit der Schließung der vorherigen Nacht, beantworten Fragen zur Sauberkeit des Ladens und melden alle Vorräte, die aufgefüllt werden müssen. Wenn sie ein Update übermitteln, können sie ihre Anforderungen für den Store und alle Probleme schnell und effizient kommunizieren. Tägliche Updates geben den Store-Mitarbeitern auch die Möglichkeit, hervorzuheben, was gut läuft.

In den Fertigungsstätten des Stores führen Mitarbeiter Sicherheitsüberprüfungen mit Aktualisierungen mit mobilen Geräten durch.

![Abbildung der exemplarischen Vorgehensweisenvorlage "Wöchentliche Sicherheit" auf einem mobilen Gerät.](media/updates-mobile.png)

In der Zwischenzeit aktualisiert ein Team von Remotemitarbeitern die Website des Stores. Sie sind über Zeitzonen verteilt, sodass tägliche Stand-up-Besprechungen nicht bequem sind. Stattdessen übermittelt jedes Teammitglied täglich Aktualisierungen berichte über den Fortschritt an den Teamleiter.

[Laden Sie das Aktualisierungen-Lookbook herunter](https://go.microsoft.com/fwlink/?linkid=2197649&clcid=0x409), um weitere Beispiele dafür zu sehen, was Sie mit Aktualisierungen tun können.

## <a name="required-permissions-and-licenses"></a>Erforderliche Berechtigungen und Lizenzen

Sie benötigen die Berechtigung für die folgenden Elemente, um Aktualisierungen bereitzustellen:

- Berechtigungen zum Erstellen einer Microsoft Dataverse-Datenbank.

- Ein Konto auf [powerautomate.microsoft.com](https://powerautomate.microsoft.com/).

- Administratorrolle in Ihrer Zielumgebung.

- Lizenz für Power Automate, Office 365 oder Dynamics 365.

- Eine Lizenz für Microsoft Forms ist erforderlich, damit Benutzer neue Vorlagen einrichten können.

## <a name="storage-with-microsoft-dataverse"></a>Speicher mit Microsoft Dataverse

Das Common Data Model (CDM) ist die freigegebene Datensprache, die von Geschäfts- und Analyseanwendungen in Microsoft Dataverse verwendet wird. Es besteht aus einer Reihe standardisierter, erweiterbarer Datenschemas, die von Microsoft und unseren Partnern veröffentlicht werden und die Konsistenz von Daten und deren Bedeutung über Anwendungen und Geschäftsprozesse hinweg ermöglichen. Erfahren Sie mehr über das [allgemeine Datenmodell](/common-data-model/).

Aktualisierungen, die anhand einer Vorlage erstellt werden, speichern weiterhin Daten in Microsoft Dataverse, z. B. Titel, Details, Vorlagen-ID und vieles mehr. Weitere Informationen zur  [Datenspeicherung für Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Wenn Sie die Formularvorlage auf der Microsoft Forms Website löschen, wird ihre Aktualisierungen Vorlage unterbrochen, und benutzer können die Aktualisierung nicht übermitteln. Benutzer erhalten die Fehlermeldung "CDB TableNotFound", wenn sie versuchen, eine Vorlage zu öffnen, die auf Microsoft Forms gelöscht wurde.

## <a name="updates-teams-app-permissions"></a>Aktualisierungen Von Teams-App-Berechtigungen

Mit der Aktualisierungen Teams-App können Sie auf die folgenden Features zugreifen:

- Empfangen von Nachrichten und Daten, die Sie bereitstellen.

- Versand von Nachrichten und Benachrichtigungen an Sie.

- Rendern persönlicher Apps und Dialogfelder ohne eine von Microsoft Teams bereitgestellte Kopfzeile.

- Zugriff auf Ihre Profilinformationen wie Name, E-Mail-Adresse, Firmenname und bevorzugte Sprache.

- Empfangen von Nachrichten und Daten, die Teammitglieder in einem Kanal bereitstellen.

- Senden von Nachrichten und Benachrichtigungen in einem Kanal.

- Zugriff auf die Informationen Ihres Teams:
  - Teamname
  - Kanalliste
  - Liste (Namen und E-Mail-Adressen von Teammitgliedern)

- Verwenden der Teaminformationen zur Kontaktaufnahme.

## <a name="disable-the-updates-app"></a>Deaktivieren der Aktualisierungen-App

Die Aktualisierungen-App ist standardmäßig verfügbar. Sie können die App im Microsoft Teams Admin Center deaktivieren.

  1. Melden Sie sich beim Microsoft Teams Admin Center an.

  2. Wechseln Sie **Teams-Apps** > **Apps verwalten**.

  3. Suchen Sie nach der Aktualisierungen-App.

     [![Screenshot der Admin Center-Navigation mit hervorgehobener Option "Teams-Apps > Apps verwalten".](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. Wählen Sie **Aktualisierungen** aus.

  5. Deaktivieren Sie die App für Ihre Organisation mithilfe des Schalters.
    ![Abbildung des Umschalters zum Aktivieren oder Deaktivieren Aktualisierungen.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>Anheften Aktualisierungen an Teams

Mit App-Setuprichtlinien können Sie Teams so anpassen, dass Apps angeheftet werden, die für Ihre Benutzer in Ihren Benutzern am wichtigsten sind. Die Apps sind an die App-Leiste angeheftet – die Leiste auf der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients, auf die Benutzer schnell und einfach zugreifen können.

Um die Aktualisierungen-App für Ihre Benutzer anzuheften, können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten oder eine benutzerdefinierte App-Setuprichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Aufbewahrungsrichtlinie

Aktualisierungen, die über die Aktualisierungen-App erstellt wurden, werden in der Microsoft Dataverse-Standardumgebung gespeichert, die derzeit keine Sicherungen unterstützt. Erfahren Sie mehr über das [Sichern und Wiederherstellen von Umgebungen – Power Platform \| Microsoft-Dokumentation](/power-platform/admin/backup-restore-environments).

In Formularen gespeicherte Daten werden erst gelöscht, wenn die Vorlagenersteller sie von der Registerkarte **"Gelöschte Formulare**" in der Microsoft Forms Web-App bereinigen.

## <a name="conditional-access-and-permission-policies"></a>Richtlinien für bedingten Zugriff und Berechtigungen

Die Aktualisierungen-App in Teams unterstützt derzeit keine Richtlinien für bedingten Zugriff, die für Microsoft Teams festgelegt sind.

Sie können [Teams-App-Berechtigungsrichtlinien](teams-app-permission-policies.md) verwenden, um Aktualisierungen zu verwalten.

## <a name="data-limitations"></a>Dateneinschränkungen

Jeder Benutzer kann maximal 400 Aktualisierungen Vorlagen erstellen, und jede Vorlage kann maximal 50.000 Anforderungen basierend auf der aktuellen Funktion in Microsoft Forms sammeln.

## <a name="security"></a>Sicherheit

Über die Teams Aktualisierungen-App haben Benutzer Zugriff, um neue Updates zu erstellen und Updates anzuzeigen, die sie gesendet und empfangen haben. Benutzer haben keinen Zugriff auf Aktualisierungen, die von anderen Personen erstellt werden, es sei denn, sie sind ein Viewer der Anforderung.

> [!Note]
> Einem Benutzer wird eine Viewerrolle einer Anforderung zugewiesen, wenn er Teil des Chats oder Kanals ist, in dem der Updatebericht erstellt wurde, oder der Vorlagenersteller sie manuell als Viewer hinzufügt. Sie haben nicht die Möglichkeit, Maßnahmen für die Anforderung zu ergreifen, wenn ihnen diese Rolle beim Erstellen des Berichts nicht zugewiesen wurde.
