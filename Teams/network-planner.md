---
title: Verwenden des Netzwerkplaners für Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Administratoren erfahren, wie Sie den Netzwerkplaner verwenden, um die Netzwerkanforderungen für Microsoft Teams zu ermitteln.
ms.localizationpriority: medium
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
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045554"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Verwenden des Netzwerkplaners für Microsoft Teams

Netzwerkplaner ist ein neues Tool, das im Teams Admin Center verfügbar ist. Sie finden sie unter "**Planer für** das **Netzwerk planen** > ". In nur wenigen Schritten hilft Ihnen der Netzwerkplaner bei der Ermittlung und Organisation von Netzwerkanforderungen für die Verbindung Microsoft Teams Benutzern in Ihrer Organisation. Wenn Sie Ihre Netzwerkdetails und die Teams-Nutzung angeben, berechnet der Netzwerkplaner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud Voice über die physischen Standorte Ihrer Organisation hinweg.

![Screenshot des Netzwerkplaners.](media/network-planner.png)

Netzwerkplaner ermöglicht Ihnen Folgendes:

- Erstellen Sie Darstellungen Ihrer Organisation mithilfe von Websites und von Microsoft empfohlenen Personas (Büromitarbeiter, Remotemitarbeiter und Teams Raumsystem).

    > [!NOTE]
    > Die empfohlenen Personas wurden basierend auf Daten aus Teams best use scenarios und typischen Nutzungsmustern entwickelt. Sie können jedoch zusätzlich zu den drei empfohlenen Personas bis zu drei benutzerdefinierte Personas erstellen.

- Generieren Sie Berichte, und berechnen Sie die Bandbreitenanforderungen für Teams Nutzung.

Um den Netzwerkplaner verwenden zu können, müssen Sie ein globaler Administrator, Teams Administrator oder Teams Kommunikationsadministrator sein.

## <a name="create-a-custom-persona"></a>Erstellen einer benutzerdefinierten Persona

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Persona zu erstellen:

1. Wechseln Sie zum Netzwerkplaner im Microsoft Teams Admin Center.

2. Klicken Sie auf der Registerkarte " **Personas** " auf **+Benutzerdefinierte Persona**. 

3. Fügen Sie im Bereich " **Neue benutzerdefinierte Persona** " einen Namen und eine Beschreibung für die neue Persona hinzu.

4. Wählen Sie die Berechtigungen aus, die diese Persona innerhalb der Organisation verwenden wird.

5. Klicken Sie auf **Speichern**.

## <a name="build-your-plan"></a>Erstellen Ihres Plans

Führen Sie die folgenden Schritte aus, um mit der Erstellung Ihres Netzwerkplans zu beginnen:

1. Wechseln Sie zum Netzwerkplaner im Microsoft Teams Admin Center.

2. Klicken Sie auf der Registerkarte **"Netzwerkplan** " auf **"Netzwerkplan hinzufügen"**.

3. Geben Sie einen Namen und eine Beschreibung für Ihren Netzwerkplan ein. Der Netzwerkplan wird in der Liste der verfügbaren Pläne angezeigt.

4. Klicken Sie auf den Plannamen, um den neuen Plan auszuwählen.

5. Fügen Sie Websites hinzu, um eine Darstellung des Netzwerksetups Ihrer Organisation zu erstellen.

    Je nach Netzwerk Ihrer Organisation können Sie Websites verwenden, um ein Gebäude, einen Bürostandort oder etwas anderes darzustellen. Standorte sind möglicherweise über ein WAN verbunden, um die Freigabe von Internet- und/oder PSTN-Verbindungen zu ermöglichen. Um optimale Ergebnisse zu erzielen, erstellen Sie Websites mit lokalen Verbindungen, bevor Sie Websites erstellen, die remote eine Verbindung mit dem Internet oder dem PSTN herstellen.

    So erstellen Sie eine Website:

    1. Fügen Sie einen Namen und eine Beschreibung für Ihre Website hinzu.

    2. Fügen Sie unter **"Netzwerkeinstellungen**" die Anzahl der Netzwerkbenutzer an diesem Standort hinzu (erforderlich).

    3. Fügen Sie Netzwerkdetails hinzu: WAN-fähig, WAN-Kapazität, Internetausgang (**lokal** oder **Remote**) und PSTN-Ausgang (keine, lokale oder Remoteverbindung).

      > [!NOTE]
      > Sie müssen WAN- und Internetkapazitätsnummern hinzufügen, um bestimmte Bandbreitenempfehlungen anzuzeigen, wenn Sie einen Bericht generieren.

    4. Klicken Sie auf **Speichern**.

## <a name="create-a-report"></a>Erstellen eines Berichts

Nachdem Sie alle Websites hinzugefügt haben, können Sie wie folgt einen Bericht erstellen.

1. Klicken Sie auf der Registerkarte " **Berichte** " auf **"Bericht starten"**.

2. Verteilen Sie für jede Website, die Sie erstellen, die Anzahl der Benutzer auf die verfügbaren Personas. Wenn Sie die von Microsoft empfohlenen Personas verwenden, wird die Anzahl automatisch verteilt (80 % Büromitarbeiter und 20 % Remotemitarbeiter).

3. Nachdem Sie die Verteilung abgeschlossen haben, klicken Sie auf **"Bericht generieren"**.

    Der generierte Bericht zeigt die Bandbreitenanforderungen in verschiedenen Ansichten an, sodass Sie die Ausgabe klar verstehen können:
    - In einer Tabelle mit einzelnen Berechnungen werden die Bandbreitenanforderungen für jede zulässige Aktivität angezeigt.
    - In einer zusätzlichen Ansicht wird der Gesamtbandbreitenbedarf mit Empfehlungen angezeigt.

4. Klicken Sie auf **Speichern**. Ihr Bericht steht zur späteren Anzeige in der Berichtsliste zur Verfügung.

## <a name="example-scenario"></a>Beispielszenario

Ein Beispiel für die Verwendung des Netzwerkplaners zum Einrichten eines Netzwerkplans und zum Generieren eines Berichts mithilfe dieser Schritte finden Sie im [Download des Netzwerkplaners How-To PowerPoint Deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (nur in Englisch).
