---
title: Verwenden des Netzwerkplaners für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Der Administrator kann erfahren, wie er mithilfe von Netzwerkplaner die Netzwerkanforderungen für Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13cccda1c51e1706cc83b83667dff6e2f00e535e4afd1fd50ea869633199c4d3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332607"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Verwenden des Netzwerkplaners für Microsoft Teams

Netzwerkplaner ist ein neues Tool, das im Teams Admin Center verfügbar ist. Sie finden sie unter **Planungsnetzwerkplaner**  >  . Mit nur wenigen Schritten können Sie mithilfe von Netzwerkplaner Netzwerkanforderungen für Verbindungen zwischen Microsoft Teams in Ihrer Organisation ermitteln und organisieren. Wenn Sie Ihre Netzwerkdetails und die Teams-Nutzung angeben, berechnet der Netzwerkplaner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud Voice über die physischen Standorte Ihrer Organisation hinweg.

![Screenshot von "Netzwerkplaner"](media/network-planner.png)

Mit Netzwerkplaner können Sie:

- Erstellen Sie Darstellungen Ihrer Organisation mithilfe von Websites und von Microsoft empfohlenen Personen (Büromitarbeiter, Remotemitarbeiter und Teams Raumsystem).

    > [!NOTE]
    > Die empfohlenen Personen wurden basierend auf Daten aus Teams Szenarien mit optimaler Verwendung und typischen Verwendungsmustern entwickelt. Sie können jedoch zusätzlich zu den drei empfohlenen Personas bis zu drei benutzerdefinierte Personen erstellen.

- Generieren Sie Berichte, und berechnen Sie die Bandbreitenanforderungen Teams Nutzung.

Um Netzwerkplaner verwenden zu können, müssen Sie ein globaler Administrator, Teams Oder Teams Communications Administrator sein.

## <a name="create-a-custom-persona"></a>Erstellen einer benutzerdefinierten Persona

Gehen Sie wie folgt vor, um eine benutzerdefinierte Persona zu erstellen:

1. Wechseln Sie im Microsoft Teams Admin Center zum Netzwerkplaner.

2. Klicken Sie **auf der Registerkarte Personas** auf **+ Benutzerdefinierte Persona**. 

3. Fügen Sie **im Bereich Neue benutzerdefinierte Persona** einen Namen und eine Beschreibung für die neue Persona hinzu.

4. Wählen Sie die Berechtigungen aus, die diese Persona innerhalb der Organisation verwenden soll.

5. Klicken Sie auf **Speichern**.

## <a name="build-your-plan"></a>Erstellen Ihres Plans

Führen Sie die folgenden Schritte aus, um mit dem Erstellen Ihres Netzwerkplans zu beginnen:

1. Wechseln Sie im Microsoft Teams Admin Center zum Netzwerkplaner.

2. Klicken Sie **auf der Registerkarte** Netzwerkplan auf **Netzwerkplan hinzufügen**.

3. Geben Sie einen Namen und eine Beschreibung für Ihren Netzwerkplan ein. Der Netzwerkplan wird in der Liste der verfügbaren Pläne angezeigt.

4. Klicken Sie auf den Plannamen, um den neuen Plan auszuwählen.

5. Fügen Sie Websites hinzu, um eine Darstellung der Netzwerkeinrichtung Ihrer Organisation zu erstellen.

    Je nach dem Netzwerk Ihrer Organisation möchten Sie websites möglicherweise verwenden, um ein Gebäude, einen Bürostandort oder etwas anderes zu repräsentieren. Standorte können über ein WAN verbunden sein, um die Freigabe von Internet- und/oder PSTN-Verbindungen zu ermöglichen. Um optimale Ergebnisse zu erzielen, erstellen Sie Websites mit lokalen Verbindungen, bevor Sie Websites erstellen, die remote eine Verbindung mit dem Internet oder PSTN herstellen.

    So erstellen Sie eine Website

    1. Fügen Sie einen Namen und eine Beschreibung für Ihre Website hinzu.

    2. Fügen **Sie unter** Netzwerkeinstellungen die Anzahl der Netzwerkbenutzer an dieser Website hinzu (erforderlich).

    3. Hinzufügen von Netzwerkdetails: WAN-fähig, WAN-Kapazität, Internet-Ausgangs **(** Lokal oder **Remote)** und PSTN-Ausgangsadresse (kein, lokaler oder remoteer Standort).

      > [!NOTE]
      > Sie müssen WAN- und Internetkapazitätsnummern hinzufügen, um spezifische Bandbreitenempfehlungen einsenden zu können, wenn Sie einen Bericht generieren.

    4. Klicken Sie auf **Speichern**.

## <a name="create-a-report"></a>Erstellen eines Berichts

Nachdem Sie alle Websites hinzugefügt haben, können Sie wie folgt einen Bericht erstellen.

1. Klicken Sie **auf** der Registerkarte Berichte **auf Bericht starten**.

2. Verteilen Sie für jede Website, die Sie erstellen, die Anzahl der Benutzer an die verfügbaren Personas. Wenn Sie die von Microsoft empfohlenen Personen verwenden, wird die Nummer automatisch verteilt (80 % Büromitarbeiter und 20 % Remote-Mitarbeiter).

3. Nachdem Sie die Verteilung abgeschlossen haben, klicken Sie **auf Bericht generieren**.

    Im generierten Bericht werden die Bandbreitenanforderungen in mehreren unterschiedlichen Ansichten angezeigt, damit Sie die Ausgabe deutlich verstehen:
    - In einer Tabelle mit einzelnen Berechnungen wird der Bandbreitenbedarf für jede zulässige Aktivität angezeigt.
    - In einer zusätzlichen Ansicht werden die Bandbreitenanforderungen insgesamt mit Empfehlungen angezeigt.

4. Klicken Sie auf **Speichern**. Der Bericht wird in der Berichtsliste zur späteren Anzeige verfügbar sein.

## <a name="example-scenario"></a>Beispielszenario

Wenn Sie ein Beispiel für die Verwendung des Netzwerkplaners zum Einrichten eines Netzwerkplans und zum Generieren eines Berichts anhand dieser Schritte verwenden können, laden Sie den Netzwerkplaner How-To PowerPoint [Deck (nur](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) in Englisch) herunter.
