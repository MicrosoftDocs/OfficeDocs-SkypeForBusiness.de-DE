---
title: Einrichten von Live-Ereignissen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Richten Sie Live für Ereignisse in Teams ein, einschließlich Einrichten Ihres Netzwerks, Zuweisen von Lizenzen, Aktivieren von Live-Ereignis Features und-Planung sowie Video verteilungslösungen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae30fdb824c62027d1a704435e80df2a9abf1f85
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140564"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Einrichten von Live-Ereignissen in Microsoft Teams

Wenn Sie für Live-Events einrichten, müssen Sie mehrere Schritte ausführen.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Schritt 1: Einrichten Ihres Netzwerks für Live-Events in Teams
Bei Live Ereignissen, die in Teams erstellt wurden, müssen Sie [das Netzwerk Ihrer Organisation für Teams vorbereiten](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
Stellen Sie sicher, dass Sie über korrekte Lizenzzuweisungen für [Personen verfügen, die Live Ereignisse erstellen und planen können](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) und [die Live Ereignisse sehen können](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Schritt 3: Einrichten von Live-Ereignisrichtlinien
Mithilfe von Live Ereignisrichtlinien können Sie steuern, wer in Ihrer Organisation Live Ereignisse und die Features enthalten kann, die in den von Ihnen erstellten Ereignissen zur Verfügung stehen. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Live Ereignisrichtlinien erstellen. Nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, weisen Sie Sie einem Benutzer oder Gruppen von Benutzern in Ihrer Organisation zu.

> [!NOTE]
> Benutzer in Ihrer Organisation erhalten die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen. Standardmäßig ist in der globalen Richtlinie die Live-Ereignisplanung für Teams-Benutzer aktiviert, Live Beschriftungen und Untertitel (Transkription) deaktiviert, jeder in der Organisation kann an Live Ereignissen teilnehmen, und die Aufnahmeeinstellung ist auf immer aufzeichnen festgelegt. 

### <a name="create-or-edit-a-live-events-policy"></a>Erstellen oder Bearbeiten einer Live Ereignis Richtlinie
<a name="bkcreatepolicy"> </a>

**![Ein Symbol, das das Microsoft Teams](../media/teams-logo-30x30.png) -Logo mit dem Microsoft Teams Admin Center zeigt**

1. Wechseln Sie in der linken Navigationsleiste zu **Besprechungen** > **Live-Ereignisrichtlinien**. 
2. Führen Sie einen der folgenden Schritte aus:
- Wenn Sie die vorhandene Standardrichtlinie bearbeiten möchten, wählen Sie **Global (org-Wide Standard)** aus. 
- Wenn Sie eine neue benutzerdefinierte Richtlinie erstellen möchten, wählen Sie **neue Richtlinie**aus. 
- Wenn Sie eine benutzerdefinierte Richtlinie bearbeiten möchten, wählen Sie die Richtlinie aus, und wählen Sie dann **Bearbeiten**aus. 

    Hier sind die Einstellungen, die Sie ändern können, um den Anforderungen Ihrer Organisation zu entsprechen.

    ![Screenshot der Richtlinieneinstellungen für Live Ereignisse](../media/teams-live-events-policies.png "Screenshot der Richtlinieneinstellungen für Live Ereignisse im Microsoft Teams Admin Center") 

|Einstellung  |Beschreibung  |
|---------|---------|
|**Titel**     |Dies ist der Titel der Richtlinie, die auf der Seite "Live-Ereignisrichtlinien" angezeigt wird. Sie darf nicht länger als 64 Zeichen sein oder Sonderzeichen enthalten.          |
|**Beschreibung**    |Verwenden Sie diese, um eine benutzerfreundliche Beschreibung für die Richtlinie hinzuzufügen.         |
|**Planen zulassen**     |Wenn Sie diese Option aktivieren, können Benutzer in Ihrer Organisation Live Ereignisse in Teams erstellen und planen. Es ist wichtig zu wissen, dass Sie, wenn Sie möchten, dass Benutzer ein Live-Ereignis planen, das mit einer externen APP oder einem Gerät erstellt wurde, weitere Schritte ausführen müssen. Weitere Informationen finden Sie unter [Aktivieren von Benutzern zum Planen von Ereignissen, die mit einer externen APP oder einem externen Gerät erstellt wurden](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Transkription für Teilnehmer zulassen** |Diese Einstellung kann nur auf Ereignisse angewendet werden, die in Teams erstellt wurden. Wenn Sie diese Option aktivieren, können Live-Event-Teilnehmer während des Ereignisses Live-Beschriftungen und Untertitel sehen.         |
|**Wer kann an geplanten Live-Events teilnehmen?**    |Wählen Sie eine der folgenden Optionen aus:<br><br>**Alle Personen** Benutzer können Live Ereignisse erstellen, an denen alle Personen, einschließlich Personen außerhalb Ihrer Organisation, teilnehmen können. Diese Einstellung aktiviert den **öffentlichen** Berechtigungstyp in Teams, wenn ein Benutzer ein Live-Ereignis plant.<br> **Jeder in der Organisation** Benutzer können Live Ereignisse erstellen, die Personen in Ihrer Organisation, einschließlich [Gastbenutzern](../add-guests.md) , die Ihrer Organisation hinzugefügt wurden, teilnehmen können. Benutzer können keine Live Ereignisse erstellen, die von anonymen Benutzern besucht werden. Mit dieser Einstellung wird der **organisationsweite** Berechtigungstyp in Teams aktiviert, wenn ein Benutzer ein Live-Ereignis plant.<br> **Bestimmte Benutzer oder Gruppen** Benutzer können Live Ereignisse erstellen, an denen nur bestimmte Benutzer oder Gruppen in Ihrer Organisation teilnehmen können. Benutzer können keine Live Ereignisse erstellen, die von allen Personen in Ihrer Organisation oder von anonymen Benutzern besucht werden. Diese Einstellung aktiviert den Berechtigungstyp **Personen und Gruppen** in Teams, wenn ein Benutzer ein Live Ereignis plant.       |
|**Aufnahmeeinstellung**  <br>     | Diese Einstellung kann nur auf Ereignisse angewendet werden, die in Teams erstellt wurden. Wählen Sie eine der folgenden Optionen aus: <br><br> **Immer aufzeichnen** Von Benutzern erstellte Live Ereignisse werden immer aufgezeichnet. Nachdem das Ereignis beendet ist, können die Mitglieder des veranstaltungsteams die Aufzeichnung herunterladen, und die Teilnehmer können das Ereignis sehen. <br> **Niemals aufzeichnen** Von Benutzern erstellte Live Ereignisse werden nie aufgezeichnet. <br>**Organizer kann Daten aufzeichnen oder nicht** Benutzer können entscheiden, ob Sie das Live-Ereignis aufzeichnen möchten. Wenn die Aufzeichnung nach dem Ereignis beendet ist, können die Mitglieder des veranstaltungsteams die Aufzeichnung herunterladen, und die Teilnehmer können das Ereignis sehen.      

Sie können dies auch mithilfe von Windows PowerShell tun. Weitere Informationen finden Sie unter [Verwenden von PowerShell zum Einrichten von Live Ereignisrichtlinien in Teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Zuweisen einer Live Ereignis Richtlinie zu Benutzern 

Wenn Sie eine benutzerdefinierte Richtlinie für Live Ereignisse erstellt haben, weisen Sie Sie Benutzern zu, damit die Richtlinie aktiv ist. 

![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu **Benutzer**, und wählen Sie dann den Benutzer aus.
2. Wählen Sie neben **Zugewiesene Richtlinien****Bearbeiten** aus. 
3. Wählen Sie die Richtlinie für Live Ereignisse aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus. 

Sie können einer oder mehreren Benutzern auch eine Live-Ereignis Richtlinie wie folgt zuweisen:

![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams admin Centers

1. Wechseln Sie zu den**Live Events-Richtlinien**für **Besprechungen** > .
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie fertig sind, klicken Sie auf **Speichern**.
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Benutzern das Planen von Ereignissen ermöglichen, die mit einer externen APP oder einem Gerät erstellt wurden

Damit Benutzerereignisse planen können, die mit einer externen APP oder einem Gerät erstellt wurden, müssen Sie auch die folgenden Aktionen ausführen:

1. Aktivieren Sie Microsoft Stream für Benutzer in Ihrer Organisation. Stream steht als Teil der zulässigen Office 365-Abonnements oder als eigenständiger Dienst zur Verfügung. Datenstrom ist nicht in Business Essentials-oder Business Premium-Plänen enthalten. Weitere Informationen finden Sie unter Übersicht über die [Datenstrom Lizenzierung](https://docs.microsoft.com/stream/license-overview) .

      Erfahren Sie mehr darüber, wie Sie [Benutzern in Office 365 Lizenzen zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) können, damit Benutzer auf Datenstrom zugreifen können. Stellen Sie sicher, dass Datenstrom nicht für die Benutzer blockiert ist, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

2. Stellen Sie sicher, dass Benutzer im Stream über die Berechtigung zum Erstellen von Ereignissen verfügen. Standardmäßig können Administratoren Ereignisse mit einer externen APP oder einem externen Gerät erstellen. Der Datenstrom Administrator kann [zusätzliche Benutzer für die Erstellung von Live Ereignissen](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) im Datenstrom aktivieren.  

3. Stellen Sie sicher, dass die Organisatoren des Unternehmens die vom Datenstrom Administrator festgelegte Unternehmensrichtlinie zugestimmt haben. Wenn ein Datenstrom Administrator [eine Richtlinie für Unternehmensrichtlinien eingerichtet](https://docs.microsoft.com/stream/company-policy-and-consent) hat und Mitarbeiter dazu auffordert, diese Richtlinie vor dem Speichern von Inhalten zu akzeptieren, müssen die Benutzer dies tun, bevor Sie ein Live Ereignis (mit einer externen APP oder einem externen Gerät) in Teams erstellen. Bevor Sie das Feature für Live Ereignisse in der Organisation bereitstellen, müssen Sie sicherstellen, dass die Benutzer, die diese Live Ereignisse erstellen, der Richtlinie zugestimmt haben. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Schritt 4: Einrichten einer Video Verteilungs Lösung für Live Ereignisse in Teams
Bei der Wiedergabe von Live-Ereignis Videos wird das adaptive Bitrate-Streaming (ABR) verwendet, aber es handelt sich um einen Unicast-Datenstrom, was bedeutet, dass jeder Betrachter seinen eigenen Videostream aus dem Internet erhält. Bei Live Ereignissen oder Videos, die an große Teile Ihrer Organisation gesendet wurden, kann es eine beträchtliche Menge an Internet Bandbreite geben, die von den Zuschauern genutzt wird. Für Organisationen, die diesen Internetdatenverkehr für Live-Events reduzieren möchten, sind Live-Event-Lösungen in die Microsoft-Partner für die zuverlässige Video Zustellung integriert, die Software Defined Networks (SDNs) oder Enterprise Content Delivery Networks (eCDNs) anbieten. Diese Sdn/ECDN-Plattformen ermöglichen Organisationen, die Netzwerkbandbreite zu optimieren, ohne die Benutzerfreundlichkeit des Endbenutzers zu beeinträchtigen. Unsere Partner können dazu beitragen, eine skalierbarere und effizientere Videoverteilung über Ihr Unternehmensnetzwerk zu ermöglichen.

**Kaufen und Einrichten Ihrer Lösung außerhalb von Teams** Erhalten Sie Hilfe beim Skalieren der Video Zustellung, indem Sie die vertrauenswürdigen Video Delivery-Partner von Microsoft nutzen. Bevor Sie die Verwendung eines Video Zustellungs Anbieters für Teams aktivieren können, müssen Sie die Sdn/ECDN-Lösung außerhalb und separat von Teams erwerben und einrichten.

Die folgenden Sdn/ECDN-Lösungen sind bereits integriert und können für die Verwendung mit Stream eingerichtet werden.

- **Hive-Streaming** bietet eine einfache und leistungsstarke Lösung für Live-und on-Demand-Unternehmens-Videoverteilung. Hive ist eine softwarebasierte Lösung, die keine zusätzliche Hardware oder Bandbreite benötigt und eine sichere Methode bietet, um Tausende von gleichzeitigen Videoprojektoren ohne Auswirkungen auf Ihr Netzwerk zu ermöglichen. Für Kunden, die das Impact-Video vor dem Kauf einer Sdn/ECDN-Lösung in Ihrem Netzwerk verstehen möchten, bietet Hive-Streaming auch eine browserbasierte Analyse Lösung für Microsoft-Kunden. [Weitere Informationen](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** ist eine Cloud-basierte, smarte Peer-Distributionsplattform, die Ihre vorhandene Netzwerkinfrastruktur nutzt, um Inhalte in vielen Formen (Live-Streaming-Video, on-Demand-Video, Software-Updates, Sicherheitspatches usw.) schneller, zuverlässiger und mit weniger Bandbreite zu liefern. Unsere sichere Plattform wird von den größten Finanzinstituten der Welt als vertrauenswürdig eingestuft, und ohne zusätzliche Hardware sind Setup und Wartung einfach. [Weitere Informationen](https://kollective.com/microsoft-pilot/).
 
- Das **OmniCache** bietet eine Netzwerk Verteilung der nächsten Generation und gewährleistet die nahtlose Bereitstellung von Videoinhalten über das globale WANs hinweg, wodurch Event Producer die Netzwerkbandbreite optimieren und erfolgreiche Live-Event-Broadcasts und on-Demand-Streaming unterstützen können. Die Unterstützung für OmniCache für Live-Events, die in Teams erstellt wurden, wird in Kürze verfügbar sein. [Weitere Informationen](http://www.ramp.com). 
 
> [!NOTE] 
> Ihre ausgewählte Sdn-oder ECDN-Lösung unterliegt den **Nutzungsbedingungen und Datenschutzrichtlinien**des ausgewählten Drittanbieters, die Ihre Nutzung der Lösung des Anbieters Regeln. Die Nutzung der Lösung des Anbieters unterliegt nicht den Microsoft-Volumenlizenz Bestimmungen oder den Online-Dienstbedingungen. Wenn Sie mit den **Bedingungen des Drittanbieters**nicht einverstanden sind, aktivieren Sie die Lösung nicht in Teams. 

Nachdem Sie die Sdn-oder ECDN-Lösung eingerichtet haben, können Sie den Anbieter für Live-Ereignisse in Teams konfigurieren. 

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zu [Einstellungen für Live Ereignisse in Teams konfigurieren](configure-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
