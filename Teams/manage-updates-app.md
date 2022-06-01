---
title: Verwalten der Updates-App für Ihre Organisation
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
description: Erfahren Sie, wie Sie die Updates-App in Teams für Benutzer in Ihrer Organisation verwalten.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 39b0e358e57a8780918c6969a562b28d9e3fe49d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823726"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Updates-App für Ihre Organisation in Microsoft Teams

## <a name="what-is-the-updates-app"></a>Was ist die Updates-App?

Die App "Updates in Microsoft Teams" bietet Mitgliedern Ihrer Organisation einen zentralen Ort zum Erstellen, Überprüfen und Übermitteln von Updates. Durch das Erstellen von Vorlagen können Sie die Updates-App verwenden, um alles nachzuverfolgen, was Ihre Organisation benötigt. Updates sind sowohl für Desktops als auch mobile Geräte verfügbar.

In Teams können Benutzer Updates aus dem Teams App Store abrufen. Alle aktualisierungen, die sie übermitteln müssen, werden auf der Seite **"Absenden** " angezeigt.

[![Abbildung der Seite "Absenden" in Teams für Desktop.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

Benutzer können Updates, die sie zugewiesen haben, auf der Seite **"Überprüfen"** anzeigen.

[![Abbildung der Seite "Überprüfen" in Teams für Desktop.](media/updates-home-small.png)](media/updates-home.png#lightbox)

Wenn einem Benutzer ein Update zugewiesen ist, wird es im Teams Aktivitätsfeed angezeigt. Benutzer können auch alle aktuellen Updateanforderungen und vorherigen Übermittlungen in der Updates-App anzeigen. Darüber hinaus kann jeder Vorlagen erstellen und Aktualisierungsanforderungen senden.

Updates enthalten sowohl out-of-the-box-Vorlagen für allgemeine Geschäftsszenarien als auch die Option zum Erstellen einer eigenen Vorlage. Jeder kann eine Vorlage für neue Arten von Updates erstellen.

## <a name="example-scenario"></a>Beispielszenario

Mitarbeiter eines Bekleidungsgeschäfts sind täglich für die Eröffnung und Schließung des Ladens verantwortlich. Jeden Morgen füllt der Schichtleiter das Store öffnende Update aus, bei dem es sich um eine vordefinierte Vorlage in der Updates-App handelt. In diesem Update beschreiben sie alle Probleme mit der Schließung der vorherigen Nacht, beantworten Fragen zur Sauberkeit des Ladens und melden alle Vorräte, die aufgefüllt werden müssen. Wenn sie ein Update übermitteln, können sie ihre Anforderungen für den Store und alle Probleme schnell und effizient kommunizieren. Tägliche Updates geben den Store-Mitarbeitern auch die Möglichkeit, hervorzuheben, was gut läuft.

In den Fertigungsstätten des Stores führen Mitarbeiter Sicherheitsüberprüfungen mit Updates mit mobilen Geräten durch.

![Abbildung der exemplarischen Vorgehensweisenvorlage "Wöchentliche Sicherheit" auf einem mobilen Gerät.](media/updates-mobile.png)

In der Zwischenzeit aktualisiert ein Team von Remotemitarbeitern die Website des Stores. Sie sind über Zeitzonen verteilt, sodass tägliche Stand-up-Besprechungen nicht bequem sind. Stattdessen übermittelt jedes Teammitglied tägliche Updates-Berichte über den Fortschritt an den Teamleiter.

[Laden Sie das Update-Lookbook herunter](https://go.microsoft.com/fwlink/?linkid=2197649&clcid=0x409) , um weitere Beispiele für die Möglichkeiten von Updates anzuzeigen.

## <a name="required-permissions-and-licenses"></a>Erforderliche Berechtigungen und Lizenzen

Sie benötigen die Berechtigung für die folgenden Elemente, um Updates bereitzustellen:

- Berechtigungen zum Erstellen einer Microsoft Dataverse-Datenbank.

- Ein Konto auf [powerautomate.microsoft.com](https://powerautomate.microsoft.com/).

- Administratorrolle in Ihrer Zielumgebung.

- Lizenz für Power Automate, Office 365 oder Dynamics 365.

- Eine Lizenz für Microsoft Forms ist erforderlich, damit Benutzer neue Vorlagen einrichten können.

## <a name="storage-with-microsoft-dataverse"></a>Storage mit Microsoft Dataverse

Das Common Data Model (CDM) ist die freigegebene Datensprache, die von Geschäfts- und Analyseanwendungen in Microsoft Dataverse verwendet wird. Es besteht aus einer Reihe standardisierter, erweiterbarer Datenschemas, die von Microsoft und unseren Partnern veröffentlicht werden und die Konsistenz von Daten und deren Bedeutung über Anwendungen und Geschäftsprozesse hinweg ermöglichen. Erfahren Sie mehr über das [allgemeine Datenmodell](/common-data-model/).

Updates, die anhand einer Vorlage erstellt werden, speichern weiterhin Daten in Microsoft Dataverse, z. B. titel, Details, Vorlagen-ID und vieles mehr. Weitere Informationen zur  [Datenspeicherung für Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Wenn Sie die Formularvorlage auf der Microsoft Forms Website löschen, wird ihre Aktualisierungsvorlage unterbrochen, und benutzer können die Aktualisierung nicht übermitteln. Benutzer erhalten die Fehlermeldung "CDB TableNotFound", wenn sie versuchen, eine Vorlage zu öffnen, die auf Microsoft Forms gelöscht wurde.

## <a name="updates-teams-app-permissions"></a>Aktualisiert Teams App-Berechtigungen

Mit der App "Updates Teams" können Sie auf die folgenden Features zugreifen:

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

## <a name="disable-the-updates-app"></a>Deaktivieren der Updates-App

Die Updates-App ist standardmäßig verfügbar. Sie können die App im Microsoft Teams Admin Center deaktivieren.

  1. Melden Sie sich beim Microsoft Teams Admin Center an.

  2. Wechseln Sie **Teams-Apps** > **Apps verwalten**.

  3. Suchen Sie nach der Updates-App.

     [![Screenshot der Admin Center-Navigation mit hervorgehobener Option Teams Apps > "Apps verwalten".](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. Wählen Sie **"Updates" aus**.

  5. Deaktivieren Sie die App für Ihre Organisation mithilfe des Schalters.
    ![Abbildung des Umschalters zum Aktivieren oder Deaktivieren von Updates.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>Aktualisierungen an Teams anheften

### <a name="use-the-tailored-frontline-app-experience-to-pin-updates-and-other-apps-to-teams"></a>Verwenden Sie die Benutzeroberfläche der maßgeschneiderten Frontline-App, um Updates und andere Apps an Teams

Die maßgeschneiderte Frontline-App-Erfahrung in Teams heftet die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz verfügen](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Angeheftete Apps umfassen Updates, Genehmigungen, Walkie Talkie, Aufgaben und Schichten. Standardmäßig ist dieses Feature aktiviert, sodass Ihre Mitarbeiter in Service und Produktion eine out-of-the-box-Erfahrung erhalten, die auf ihre Anforderungen zugeschnitten ist.

Die Apps werden an die App-Leiste angeheftet – die Leiste auf der Seite des Teams Desktopclients und am unteren Rand der Teams mobilen Clients, auf die Benutzer schnell und einfach zugreifen können.

Weitere Informationen, einschließlich der Funktionsweise der Umgebung mit von Ihnen festgelegten App-Richtlinien, finden Sie unter ["Anpassen Teams Apps für Mitarbeiter in Service und Produktion](pin-teams-apps-based-on-license.md)".

### <a name="use-an-app-setup-policy-to-pin-updates-to-teams"></a>Verwenden einer App-Setuprichtlinie zum Anheften von Updates an Teams

Mit App-Setuprichtlinien können Sie Teams anpassen, um Apps anzuheften, die für Ihre Benutzer in Ihren Benutzern am wichtigsten sind.

Um die Updates-App für Ihre Benutzer anzuheften, können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten oder eine benutzerdefinierte App-Setuprichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Aufbewahrungsrichtlinie

Updates, die mit der Updates-App erstellt wurden, werden in der Standardmäßigen Microsoft Dataverse-Umgebung gespeichert, die derzeit keine Sicherungen unterstützt. Erfahren Sie mehr über das [Sichern und Wiederherstellen von Umgebungen – Power Platform \| Microsoft-Dokumentation](/power-platform/admin/backup-restore-environments).

In Formularen gespeicherte Daten werden erst gelöscht, wenn die Vorlagenersteller sie von der Registerkarte **"Gelöschte Formulare**" in der Microsoft Forms Web-App bereinigen.

## <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Derzeit unterstützt die Updates-App in Teams keine Richtlinien für bedingten Zugriff, die für Microsoft Teams festgelegt sind.

## <a name="data-limitations"></a>Dateneinschränkungen

Jeder Benutzer kann maximal 400 Aktualisierungsvorlagen erstellen, und jede Vorlage kann maximal 50.000 Anforderungen basierend auf der aktuellen Funktion in Microsoft Forms sammeln.

## <a name="security"></a>Sicherheit

Über die Teams Updates-App haben Benutzer Zugriff, um neue Updates zu erstellen und Updates anzuzeigen, die sie gesendet und empfangen haben. Benutzer haben keinen Zugriff auf updates, die von anderen erstellt werden, es sei denn, sie sind ein Viewer der Anforderung.

> [!Note]
> Einem Benutzer wird eine Viewerrolle einer Anforderung zugewiesen, wenn er Teil des Chats oder Kanals ist, in dem der Updatebericht erstellt wurde, oder der Vorlagenersteller sie manuell als Viewer hinzufügt. Sie haben nicht die Möglichkeit, Maßnahmen für die Anforderung zu ergreifen, wenn ihnen diese Rolle beim Erstellen des Berichts nicht zugewiesen wurde.
