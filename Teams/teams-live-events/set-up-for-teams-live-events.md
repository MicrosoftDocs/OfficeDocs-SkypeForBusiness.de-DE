---
title: Einrichten von Live-Ereignissen in Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informieren Sie sich über die Schritte zum Einrichten von Live für Ereignisse in Microsoft Teams, einschließlich der Vorbereitung Ihres Netzwerks, dem Zuweisen von Lizenzen, dem Verwenden von Richtlinien zum Aktivieren von Live Ereignis Features und der Terminplanung für Benutzer sowie dem Einrichten eines Drittanbieters für den Vertrieb.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 827b0d9bcb6c66e2c8d8362773b789b3e4a0cf4f
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344170"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Einrichten von Live-Ereignissen in Microsoft Teams

Wenn Sie für Live-Events einrichten, müssen Sie mehrere Schritte ausführen:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Schritt 1: Einrichten Ihres Netzwerks für Live Ereignisse in Microsoft Teams
Bei Schnellstart-Live Ereignissen müssen Sie [das Netzwerk Ihrer Organisation für Microsoft Teams vorbereiten](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
Stellen Sie sicher, dass Sie über korrekte Lizenzzuweisungen für [Personen verfügen, die Live Ereignisse erstellen und planen können](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) und [die Live Ereignisse sehen können](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Schritt 3: Einrichten von Live-Ereignisrichtlinien
Mithilfe von Live Ereignisrichtlinien können Sie steuern, wer in Ihrer Organisation Live Ereignisse und die Features enthalten kann, die in den von Ihnen erstellten Ereignissen zur Verfügung stehen. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Live Ereignisrichtlinien erstellen. Nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, weisen Sie Sie einem Benutzer oder Gruppen von Benutzern in Ihrer Organisation zu.

> [!NOTE]
> Benutzer in Ihrer Organisation erhalten die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen. Standardmäßig ist in der globalen Richtlinie die Live-Ereignisplanung für Teams-Benutzer aktiviert, die Transkription ist deaktiviert, jeder in der Organisation kann an Live-Ereignissen teilnehmen, und die Aufnahmeeinstellung ist auf immer aufzeichnen festgelegt. 

### <a name="create-or-edit-a-live-events-policy"></a>Erstellen oder Bearbeiten einer Live Ereignis Richtlinie
<a name="bkcreatepolicy"> </a>

**![Ein Symbol, das das Microsoft Teams](../media/teams-logo-30x30.png) -Logo mit dem Microsoft Teams Admin Center zeigt**

1. Wechseln Sie in der linken Navigationsleiste zu **Besprechungen** > **Live-Ereignisrichtlinien**. 
2. Führen Sie einen der folgenden Schritte aus:
- Wenn Sie die vorhandene Standardrichtlinie bearbeiten möchten, wählen Sie **Global (org-Wide Standard)** aus. 
- Wenn Sie eine neue benutzerdefinierte Richtlinie erstellen möchten, wählen Sie **neue Richtlinie**aus. 
- Wenn Sie eine benutzerdefinierte Richtlinie bearbeiten möchten, wählen Sie die Richtlinie aus, und wählen Sie dann **Bearbeiten**aus. 

    Hier sind die Einstellungen, die Sie ändern können, um den Anforderungen Ihrer Organisation zu entsprechen.

    Screenshot ![der Richtlinieneinstellungen für Live Ereignisse] Screenshot (../media/teams-live-events-policies.png "der Richtlinieneinstellungen für Live Ereignisse im Microsoft Teams Admin Center") 

|Einstellung  |Beschreibung  |
|---------|---------|
|**Name**     |Dies ist der Name der Richtlinie, die auf der Seite "Live-Ereignisrichtlinien" angezeigt wird. Sie darf nicht länger als 64 Zeichen sein oder Sonderzeichen enthalten.          |
|**Beschreibung**    |Verwenden Sie diese, um eine benutzerfreundliche Beschreibung für die Richtlinie hinzuzufügen.         |
|**Planen zulassen**     |Wenn Sie diese Option aktivieren, können Benutzer in Ihrer Organisation Live Ereignisse in Teams erstellen und planen. Es ist wichtig zu wissen, dass Sie, wenn Sie möchten, dass Benutzer externe Encoder-Live Ereignisse planen, weitere Schritte ausführen müssen. Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen externer Encoder-Ereignisse](#enable-users-to-schedule-external-encoder-events).     |
|**Transkription für Teilnehmer zulassen** (in Kürze verfügbar) |Diese Einstellung kann nur auf Schnellstart Ereignisse angewendet werden. Wenn Sie diese Option aktivieren, können Live-Event-Teilnehmer während des Ereignisses Echt Zeit Beschriftungen und Übersetzungen anzeigen.         |
|**Wer kann an geplanten Live-Events teilnehmen?**    |Wählen Sie eine der folgenden Optionen aus:<br><br>**Alle Personen** Benutzer können Live Ereignisse erstellen, an denen alle Personen, einschließlich Personen außerhalb Ihrer Organisation, teilnehmen können. Diese Einstellung aktiviert den **öffentlichen** Berechtigungstyp in Teams, wenn ein Benutzer ein Live-Ereignis plant.<br> **Jeder in der Organisation** Benutzer können Live Ereignisse erstellen, an denen nur Personen in Ihrer Organisation teilnehmen können. Benutzer können keine Live Ereignisse erstellen, die von anonymen Benutzern besucht werden. Mit dieser Einstellung wird der **organisationsweite** Berechtigungstyp in Teams aktiviert, wenn ein Benutzer ein Live-Ereignis plant.<br> **Bestimmte Benutzer oder Gruppen** Benutzer können Live Ereignisse erstellen, an denen nur bestimmte Benutzer oder Gruppen in Ihrer Organisation teilnehmen können. Benutzer können keine Live Ereignisse erstellen, die von allen Personen in Ihrer Organisation oder von anonymen Benutzern besucht werden. Diese Einstellung aktiviert den Berechtigungstyp **Personen und Gruppen** in Teams, wenn ein Benutzer ein Live Ereignis plant.       |
|**Aufnahmeeinstellung**  <br>     | Diese Einstellung kann nur auf Schnellstart Ereignisse angewendet werden. Wählen Sie eine der folgenden Optionen aus: <br><br> **Immer aufzeichnen** Von Benutzern erstellte Live Ereignisse werden immer aufgezeichnet. Nachdem das Ereignis beendet ist, können die Mitglieder des veranstaltungsteams die Aufzeichnung herunterladen, und die Teilnehmer können das Ereignis sehen. <br> **Niemals aufzeichnen** Von Benutzern erstellte Live Ereignisse werden nie aufgezeichnet. <br>**Organizer kann Daten aufzeichnen oder nicht** Benutzer können entscheiden, ob Sie das Live-Ereignis aufzeichnen möchten. Wenn die Aufzeichnung nach dem Ereignis beendet ist, können die Mitglieder des veranstaltungsteams die Aufzeichnung herunterladen, und die Teilnehmer können das Ereignis sehen.      

Sie können dies auch mithilfe von Windows PowerShell tun. Weitere Informationen finden Sie unter [Verwenden von PowerShell zum Einrichten von Live Ereignisrichtlinien in Teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Zuweisen einer Live Ereignis Richtlinie zu Benutzern 

Wenn Sie eine benutzerdefinierte Richtlinie für Live Ereignisse erstellt haben, weisen Sie Sie Benutzern zu, damit die Richtlinie aktiv ist. 

![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu **Benutzer**, und wählen Sie dann den Benutzer aus.
2. Wählen Sie neben **zugewiesene Richtlinien**die Option **Bearbeiten**aus. 
3. Wählen Sie die Richtlinie für Live Ereignisse aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus. 

Sie können einer oder mehreren Benutzern auch eine Live-Ereignis Richtlinie wie folgt zuweisen:

![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams admin Centers

1. Wechseln Sie **** > zu den**Live Events-Richtlinien**für Besprechungen.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten**aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.
 

### <a name="enable-users-to-schedule-external-encoder-events"></a>Zulassen, dass Benutzer externe Encoder-Ereignisse planen

Damit Benutzer externe Encoder-Ereignisse planen können, müssen Sie auch die folgenden Aktionen ausführen:

1. Aktivieren Sie Microsoft Stream für Benutzer in Ihrer Organisation. Microsoft Stream steht als Teil der zulässigen Office 365-Abonnements oder als eigenständiger Dienst zur Verfügung. Microsoft Stream ist nicht in den Business Essentials-oder Business Premium-Plänen enthalten. Weitere Informationen finden Sie unter Übersicht über die [Datenstrom Lizenzierung](https://docs.microsoft.com/stream/license-overview) .

      Erfahren Sie mehr darüber, wie Sie [Benutzern in Office 365 Lizenzen zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) können, damit Benutzer auf Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft Stream nicht für die Benutzer blockiert ist, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

2. Stellen Sie sicher, dass Benutzer in Microsoft Stream über die Berechtigung zum Erstellen von Ereignissen verfügen. Standardmäßig können Administratoren externe Encoder-Live Ereignisse erstellen. Der Microsoft Stream-Administrator kann [zusätzliche Benutzer für die Erstellung von Live Ereignissen](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream aktivieren.  

3. Stellen Sie sicher, dass die Organisatoren des Unternehmens die vom Datenstrom Administrator festgelegte Unternehmensrichtlinie zugestimmt haben. Wenn ein Microsoft Stream-Administrator [eine Richtlinie für Unternehmensrichtlinien eingerichtet](https://docs.microsoft.com/stream/company-policy-and-consent) hat und die Mitarbeiter diese Richtlinie vor dem Speichern von Inhalten akzeptieren müssen, müssen die Benutzer dies tun, bevor Sie ein Live Ereignis (mit externer Encoder-Produktion) in Teams erstellen. Bevor Sie das Feature für Live Ereignisse in der Organisation bereitstellen, müssen Sie sicherstellen, dass die Benutzer, die diese Live Ereignisse erstellen, der Richtlinie zugestimmt haben. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Schritt 4: Einrichten einer Video Verteilungs Lösung für Live Ereignisse in Teams
Bei der Wiedergabe von Live-Ereignis Videos wird das adaptive Bitrate-Streaming (ABR) verwendet, aber es handelt sich um einen Unicast-Datenstrom, was bedeutet, dass jeder Betrachter seinen eigenen Videostream aus dem Internet erhält. Bei Live Ereignissen oder Videos, die an große Teile Ihrer Organisation gesendet wurden, kann es eine beträchtliche Menge an Internet Bandbreite geben, die von den Zuschauern genutzt wird. Für Organisationen, die diesen Internetdatenverkehr für Live-Events reduzieren möchten, sind Live-Event-Lösungen in die Microsoft-Partner für die zuverlässige Video Zustellung integriert, die Software Defined Networks (SDNs) oder Enterprise Content Delivery Networks (eCDNs) anbieten. Diese Sdn/ECDN-Plattformen ermöglichen Organisationen, die Netzwerkbandbreite zu optimieren, ohne die Benutzerfreundlichkeit des Endbenutzers zu beeinträchtigen. Unsere Partner können dazu beitragen, eine skalierbarere und effizientere Videoverteilung über Ihr Unternehmensnetzwerk zu ermöglichen.

**Kaufen und Einrichten Ihrer Lösung außerhalb von Teams** Erhalten Sie Hilfe beim Skalieren der Video Zustellung, indem Sie die vertrauenswürdigen Video Delivery-Partner von Microsoft nutzen. Bevor Sie die Verwendung eines Video Zustellungs Anbieters für Teams aktivieren können, müssen Sie die Sdn/ECDN-Lösung außerhalb und separat von Teams erwerben und einrichten.

Die folgenden Sdn/ECDN-Lösungen sind bereits integriert und können für die Verwendung mit Microsoft Stream eingerichtet werden.

- **Hive-Streaming** bietet eine einfache und leistungsstarke Lösung für Live-und on-Demand-Unternehmens-Videoverteilung. Hive ist eine softwarebasierte Lösung, die keine zusätzliche Hardware oder Bandbreite benötigt und eine sichere Methode bietet, um Tausende von gleichzeitigen Videoprojektoren ohne Auswirkungen auf Ihr Netzwerk zu ermöglichen. Für Kunden, die das Impact-Video vor dem Kauf einer Sdn/ECDN-Lösung in Ihrem Netzwerk verstehen möchten, bietet Hive-Streaming auch eine browserbasierte Analyse Lösung für Microsoft-Kunden. [Weitere Informationen](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** ist eine Cloud-basierte, intelligente Peering-Verteilungsplattform, die Ihre vorhandene Netzwerkinfrastruktur nutzt, um Inhalte in vielen Formularen zu liefern (Live-Streaming-Video, on-Demand-Video, Software-Updates, Sicherheitspatches usw.) schneller, mehr zuverlässig und mit geringerer Bandbreite. Unsere sichere Plattform wird von den größten Finanzinstituten der Welt als vertrauenswürdig eingestuft, und ohne zusätzliche Hardware sind Setup und Wartung einfach. [Weitere Informationen](http://www.kollective.com).
 
- Das **OmniCache** bietet eine Netzwerk Verteilung der nächsten Generation und gewährleistet die nahtlose Bereitstellung von Videoinhalten über das globale WANs hinweg, wodurch Event Producer die Netzwerkbandbreite optimieren und erfolgreiche Live-Event-Broadcasts und on-Demand unterstützen können. Streaming. Die Unterstützung für das OmniCache für Schnellstart-Live-Events wird in Kürze verfügbar sein.  [Weitere Informationen](http://www.ramp.com). 
 
> [!NOTE] 
> Ihre ausgewählte Sdn-oder ECDN-Lösung unterliegt den **Nutzungsbedingungen und den Datenschutzrichtlinien**des ausgewählten Drittanbieters, was die Nutzung der Lösung des Anbieters regelt. Die Nutzung der Lösung des Anbieters unterliegt nicht den Microsoft-Volumenlizenz Bestimmungen oder den Online-Dienstbedingungen. Wenn Sie mit den **Bedingungen des Drittanbieters**nicht einverstanden sind, aktivieren Sie die Lösung nicht in Teams. 

Nachdem Sie die Sdn-oder ECDN-Lösung eingerichtet haben, können Sie den Anbieter für Live-Ereignisse in Teams konfigurieren. 

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zu [Einstellungen für Live Ereignisse in Teams konfigurieren](configure-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Konfigurieren von Live Ereigniseinstellungen in Microsoft Teams](configure-teams-live-events.md)

