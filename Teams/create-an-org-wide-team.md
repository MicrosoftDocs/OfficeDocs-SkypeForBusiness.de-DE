---
title: Erstellen Sie ein Team Org geltende in Microsoft-Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Erstellen und Verwalten einer Org geltende Team in Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3980a73c817b83466c8c93c29fb60e7e20f4df48
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532809"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Erstellen Sie ein Team Org geltende in Microsoft-Teams

Org geltende Teams bieten eine automatische Möglichkeit für alle Benutzer in einem kleinen, mittelgroßen Unternehmen angehören eines einzelnen Teams für die Zusammenarbeit. 
 
Mit Org geltende-Teams können globale Administratoren auf einfache Weise öffentliche Teams erstellen, die in jeder Benutzer in der Organisation abruft und hält die Mitgliedschaft Stand mit Active Directory als Benutzer teilnehmen und die Organisation verlassen. Nur globale Administratoren können Org geltende Teams erstellen und ein gesamte Org Team ist derzeit auf Organisationen mit nicht mehr als 2.500 Benutzer beschränkt. Wenn diese Anforderungen erfüllt sind, sehen Admins **Org geltende** als Option unter **Datenschutz** , wenn ein Team erstellen.

![Screenshot der Option zum Erstellen eines Teams Org geltende Org geltende] (media/create-org-wide-team.png "Screenshot der Option zum Erstellen eines Teams Org geltende Org geltende")

> [!NOTE]
> Wenn die Option **gesamte Org** nicht angezeigt werden, wenn Sie ein Team erstellen und Sie ein globaler Administrator sind, das Feature möglicherweise noch Rollout oder Ihrer Organisation möglicherweise mehr als die aktuelle maximale Größe der 2.500 Elemente. Wir suchen, um diese in Zukunft erhöhen.

Wenn ein Team Org geltende erstellt wird, werden alle globale Administratoren als Team Besitzer hinzugefügt, und alle aktiven Benutzer werden als Teammitglieder hinzugefügt. Benutzer, die für Teams, Gastbenutzer und die meisten Chatrooms deaktiviert sind, werden nicht an das Team hinzugefügt. Verzeichnis Ihrer Organisation wird aktualisiert, sodass neue aktive Benutzer enthalten oder wenn der Benutzer ist nicht mehr in Ihrem Unternehmen arbeiten und die Lizenz Teams deaktiviert ist, automatisch Änderungen werden synchronisiert, und die Benutzer hinzugefügt oder aus dem Team entfernt werden. Teammitglieder können kein gesamte Org Team lassen. Sie können als Teambesitzer manuell hinzufügen oder Entfernen von Benutzern bei Bedarf.

> [!NOTE]
> Chatrooms, die nicht Teil einer Raum Liste, Equipment und Ressource Konten sind möglicherweise hinzugefügt oder an das Team der gesamte Org synchronisiert werden. Team Besitzer können auf einfache Weise diese Konten aus dem Team entfernen.

## <a name="best-practices"></a>Bewährte Methoden
Wenn die für die optimale Nutzung Ihrer Org geltende Team erhalten möchten, empfehlen wir Team Besitzer die folgenden Schritte aus.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Zulassen Sie nur Team Besitzer für die Bereitstellung auf den allgemeinen Kanal
Rauschen Sie DDE-Kanal Ausführungsstapel nur Team aus, dem Besitzer der allgemeinen Kanal veröffentlichen. Besuchen Sie das Team aus, und klicken Sie auf **Weitere Optionen (...)**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf **Member Berechtigungen** > Wählen Sie **nur die Eigentümer Nachrichten senden können**.
### <a name="turn-off-team-and-team-name-mentions"></a>Deaktivieren Sie @team und @ erwähnungen [Teamname]
 Reduzieren Sie um zu verhindern, dass die gesamte Organisation überladen @mentions. Besuchen Sie das Team aus, und klicken Sie auf **Weitere Optionen (...)**  >  **Team verwalten**. Klicken Sie auf der Registerkarte **Einstellungen** auf **@mentions** > deaktivieren **Member anzeigen die Option zum @team oder @[Teamname]**. 
### <a name="automatically-favorite-important-channels"></a>Automatisch bevorzugte wichtige Kanäle
 Bevorzugte wichtige Kanäle sicherzustellen, dass jede Person in Ihrer Organisation bestimmte Unterhaltungen abwickelt. Finden Sie weitere Informationen finden Sie unter [Automatische Favoriten Kanäle für das gesamte Team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Entfernen von Konten, die möglicherweise nicht angehören.
Obwohl die Mitglieder einer Organisation geltende Team, als Teambesitzer, lassen Sie können nicht können Sie das Teammitglied durch Entfernen von Konten, die nicht gehören verwalten. Stellen Sie sicher, dass Sie Teams verwenden, um Benutzer von Ihrem Team Org geltende zu entfernen.  Wenn Sie eine andere Möglichkeit zum Entfernen eines Benutzers, wie beispielsweise Microsoft 365 Administrationscenter oder aus einer Gruppe in Outlook verwenden, kann der Benutzer zurück an das Team der gesamte Org hinzugefügt. 
