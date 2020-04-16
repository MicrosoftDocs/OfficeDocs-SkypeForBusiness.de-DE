---
title: Einrichtung für Liveereignisse in Microsoft Teams
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
description: Richten Sie Liveereignisse in Teams ein, einschließlich der Einrichtung Ihres Netzwerks, der Zuweisung von Lizenzen, der Aktivierung von Funktionen und Planung von Liveereignissen sowie Lösungen für die Videoverteilung.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae30fdb824c62027d1a704435e80df2a9abf1f85
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140564"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Einrichtung für Liveereignisse in Microsoft Teams

Wenn Sie Liveereignisse einrichten, müssen Sie mehrere Schritte ausführen.

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Schritt 1: Einrichten Ihres Netzwerk für Liveereignisse in Teams
Für Liveereignisse, die in Teams produziert werden, müssen Sie [das Netzwerk Ihrer Organisation für Teams](https://docs.microsoft.com/microsoftteams/prepare-network) vorbereiten.  

## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
Stellen Sie sicher, dass Sie die korrekten Lizenzzuweisungen für [ haben, die Liveereignisse](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) erstellen und planen können, und für [, die Liveereignisse](plan-for-teams-live-events.md#who-can-watch-live-events) verfolgen können.

## <a name="step-3-set-up-live-events-policies"></a>Schritt 3: Einrichten von Richtlinien für Liveereignisse
Richtlinien für Liveereignisse werden verwendet, um zu steuern, wer in Ihrer Organisation Liveereignisse abhalten kann und welche Funktionen in den von ihnen erstellten Ereignissen verfügbar sind. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Richtlinien für Liveereignisse erstellen. Nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, weisen Sie sie einem Benutzer oder Benutzergruppen in Ihrer Organisation zu.

> [!NOTE]
> Benutzer in Ihrer Organisation erhalten die globale Richtlinie, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Standardmäßig ist in der globalen Richtlinie die Planung von Liveereignissen für Teams-Benutzer aktiviert, Live-Untertitel und Untertitel (Transkription) sind deaktiviert, jeder in der Organisation kann an Liveereignissen teilnehmen, und die Aufzeichnungseinstellung ist so eingestellt, dass immer aufgezeichnet wird. 

### <a name="create-or-edit-a-live-events-policy"></a>Erstellen oder Bearbeiten einer Richtlinie für Liveereignisse
<a name="bkcreatepolicy"> </a>

**![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) Unter Verwendung des Microsoft Teams Admin Centers**

1. Gehen Sie in der linken Navigation auf **Besprechungen** > **Richtlinien für Liveereignisse**. 
2. Führen Sie einen der folgenden Schritte aus:
- Wenn Sie die vorhandene Standardrichtlinie bearbeiten möchten, wählen Sie **Global (organisationsweiter Standard)** aus. 
- Wenn Sie eine neue benutzerdefinierte Richtlinie erstellen möchten, wählen Sie **Neue Richtlinie**aus. 
- Wenn Sie eine benutzerdefinierte Richtlinie bearbeiten möchten, markieren Sie die Richtlinie, und wählen Sie dann **Bearbeiten** aus. 

    Hier sind die Einstellungen, die Sie ändern können, um sie an die Bedürfnisse Ihrer Organisation anzupassen.

    ![Screenshot der Richtlinieneinstellungen für Liveereignisse](../media/teams-live-events-policies.png "Screenshot der Richtlinieneinstellungen für Liveereignisse im Microsoft Teams Admin Center") 

|Einstellung  |Beschreibung  |
|---------|---------|
|**Titel**     |Dies ist der Titel der Richtlinie, die auf der Seite „Liveereignisrichtlinien“ angezeigt wird. Sie darf nicht länger als 64 Zeichen sein und keine Sonderzeichen enthalten.          |
|**Beschreibung**    |Verwenden Sie dies, um eine freundliche Beschreibung der Richtlinie hinzuzufügen.         |
|**Planung erlauben**     |Wenn Sie diese Option aktivieren, können Benutzer in Ihrer Organisation Liveereignisse in Teams erstellen und planen. Es ist wichtig zu wissen, dass Sie zusätzliche Schritte ausführen müssen, wenn Sie möchten, dass Benutzer ein Liveereignis planen, das mit einer externen Anwendung oder einem externen Gerät produziert wird. Weitere Informationen finden Sie unter [Benutzern ermöglichen, Ereignisse zu planen, die mit einer externen Anwendung oder einem externen Gerät erstellt werden](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Transkription für Teilnehmer zulassen** |Diese Einstellung kann nur auf Ereignisse angewendet werden, die in Teams produziert werden. Wenn Sie diese Option aktivieren, können die Teilnehmer des Liveereignisses während des Ereignisses Liveuntertitel und Untertitel sehen.         |
|**Wer an geplanten Liveereignissen teilnehmen kann**    |Wählen Sie eine der folgenden Aktionen aus:<br><br>**Jeder** Benutzer können Liveereignisse erstellen, an denen alle, auch Personen außerhalb Ihrer Organisation, teilnehmen können. Diese Einstellung aktiviert in Teams den Berechtigungstyp **Öffentlich**, wenn ein Benutzer ein Liveereignis plant.<br> **Jeder in der Organisation** Benutzer können Liveereignisse erstellen, an denen Personen in Ihrer Organisation, einschließlich [Gastbenutzer](../add-guests.md), die Ihrer Organisation hinzugefügt wurden, teilnehmen können. Benutzer können keine Liveereignisse erstellen, an denen anonyme Benutzer teilnehmen. Diese Einstellung aktiviert in Teams den Berechtigungstyp **Organisationsweit**, wenn ein Benutzer ein Liveereignis plant.<br> **Bestimmte Benutzer oder Gruppen** Benutzer können Liveereignisse erstellen, an denen nur bestimmte Benutzer oder Gruppen in Ihrer Organisation teilnehmen können. Benutzer können keine Liveereignisse erstellen, an denen jeder in Ihrer Organisation oder anonyme Benutzer teilnehmen können. Diese Einstellung aktiviert den Berechtigungstyp **Personen und Gruppen** in Teams, wenn ein Benutzer ein Liveereignis plant.       |
|**Aufzeichnungseinstellung**  <br>     | Diese Einstellung kann nur auf Ereignisse angewendet werden, die in Teams produziert werden. Wählen Sie eine der folgenden Aktionen aus: <br><br> **Immer aufzeichnen** Von Benutzern erstellte Liveereignisse werden immer aufgezeichnet. Nach Ende des Ereignisses können die Teammitglieder die Aufzeichnung herunterladen, und die Teilnehmer können sich das Ereignis ansehen. <br> **Nie aufzeichnen** Von Benutzern erstellte Liveereignisse werden nie aufgezeichnet. <br>**Organisator kann aufzeichnen oder nicht** Benutzer können entscheiden, ob das Liveereignis aufgezeichnet werden soll. Falls das Ereignis aufgezeichnet wird, können die Teammitglieder nach dessen Ende die Aufzeichnung herunterladen, und die Teilnehmer können sich das Ereignis ansehen.      

Sie können dies auch mithilfe von Windows PowerShell tun. Weitere Informationen erhalten Sie unter [Verwenden von PowerShell zum Festlegen von Richtlinien für Liveereignisse in Microsoft Teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Zuweisen einer Richtlinie für Liveereignisse zu Benutzern 

Wenn Sie eine benutzerdefinierte Richtlinie für Livereignisse erstellt haben, weisen Sie sie Benutzern zu, damit die Richtlinie aktiv wird. 

![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Gehen Sie im linken Navigationsbereich zu **Benutzer**, und markieren Sie dann den Benutzer.
2. Wählen Sie neben **Zugewiesene Richtlinien** **Bearbeiten** aus. 
3. Markieren Sie die Richtlinie für Liveereignisse, die Sie zuweisen möchten, und wählen Sie dann **Speichern** aus. 

Sie können einem oder mehreren Benutzern eine Richtlinie für Liveereignisse auch folgendermaßen zuweisen:

![Symbol, das das Microsoft Teams-Logo zeigt](../media/teams-logo-30x30.png) Verwenden des Microsoft Teams Admin Centers

1. Gehen Sie zu **Besprechungen** > **Richtlinien für Liveereignisse**.
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie fertig sind, klicken Sie auf **Speichern**.
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Benutzern die Planung von Ereignissen ermöglichen, die mit einer externen App oder einem externen Gerät erstellt werden

Damit Benutzer Ereignisse planen können, die mit einer externen Anwendung oder einem externen Gerät erstellt werden, müssen Sie auch Folgendes vornehmen:

1. Microsoft Stream für Benutzer in Ihrer Organisation aktivieren. Microsoft Stream ist im Rahmen berechtigter Office 365-Abonnements oder als eigenständiger Dienst verfügbar. Stream ist nicht in Business Essentials- oder Business Premium-Plänen enthalten. Weitere Details finden Sie unter [Übersicht über die Stream-Lizenzierung](https://docs.microsoft.com/stream/license-overview).

      Erfahren Sie mehr darüber, wie Sie [Benutzern in Office 365 Lizenzen zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) können, damit Benutzer auf Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft Stream für die Benutzer nicht blockiert ist, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization) beschrieben.

2. Vergewissern Sie sich, dass die Benutzer über die Berechtigung zum Erstellen eines Liveereignisses in Stream verfügen. Administratoren können standardmäßig mit einer externen App oder einem externen Gerät Ereignisse erstellen. Ein Stream-Administrator kann in Stream [zusätzliche Benutzer für die Erstellung von Liveereignissen](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) aktivieren.  

3. Vergewissern Sie sich, dass Organisatoren von Liveereignissen der Unternehmensrichtlinie, die vom Stream-Administrator festgelegt wurde, zugestimmt haben. Wenn ein Stream-Administrator [eine Richtlinie für Unternehmensrichtlinien eingerichtet hat](https://docs.microsoft.com/stream/company-policy-and-consent) und die Mitarbeiter diese Richtlinie vor dem Speichern von Inhalten akzeptieren müssen, müssen Benutzer dies tun, bevor Sie in Teams ein Liveereignis (mit einer externen App oder einem externen Gerät) erstellen. Bevor Sie das Liveereignisfeature in der Organisation bereitstellen, stellen Sie sicher, dass Benutzer, die diese Liveereignisse erstellen, der Richtlinie zugestimmt haben. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Schritt 4: Einrichten einer Videoverteilungslösung für Liveereignisse in Teams
Bei der Wiedergabe von Liveereignisvideos wird Adaptive Bitrate Streaming (ABR) verwendet, aber es ist ein Unicast-Stream, was bedeutet, dass jeder Zuschauer einen eigenen Videostream aus dem Internet erhält. Bei Liveereignissen oder Videos, die an große Teile Ihrer Organisation gesendet werden, kann von den Zuschauern ein beträchtlicher Anteil der Internetbandbreite verbraucht werden. Bei Organisationen, die diesen Internetdatenverkehr für Liveereignisse reduzieren möchten, werden Lösungen für Liveereignisse mit den vertrauenswürdigen Videobereitstellungspartnern von Microsoft integriert, die softwaredefinierte Netzwerke (SDNs) oder Enterprise Content Delivery Networks (eCDNs) anbieten. Diese SDN-/eCDN-Plattformen ermöglichen Organisationen, die Netzwerkbandbreite zu optimieren, ohne das Videoerlebnis der Endbenutzer zu schmälern. Unsere Partner ermöglichen eine skalierbarere und effizientere Videoverteilung in Ihrem Unternehmensnetzwerk.

**Erwerben und Einrichten Ihrer Lösung außerhalb von Teams** Lassen Sie sich beim Skalieren von Videobereitstellungen durch die vertrauenswürdigen Videobereitstellungspartner von Microsoft helfen. Bevor Sie die Verwendung eines Videobereitstellungsanbieters für Teams aktivieren können, müssen Sie die SDN-/eCDN-Lösung außerhalb und von Teams getrennt erwerben und einrichten.

Die folgenden SDN-/eCDN-Lösungen sind vorintegriert und können für die Verwendung mit Stream eingerichtet werden.

- **Hive-Streaming** bietet eine einfache und leistungsstarke Lösung für die Live- und On-Demand-Videoverteilung in Unternehmen. Bei Hive handelt es sich um eine softwarebasierte Lösung, die keine zusätzliche Hardware oder Bandbreite erfordert und eine sichere Möglichkeit bietet, ein Video ohne Auswirkungen auf Ihr Netzwerk zu Tausenden gleichzeitig abzurufen. Wenn Sie wissen möchten, welche Auswirkungen Video auf Ihr Netzwerk hat, bevor Sie eine SDN-/eCDN-Lösung erwerben, bietet Hive-Streaming auch eine browserbasierte Analyselösung für Microsoft-Kunden. [Weitere Informationen](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** ist eine cloudbasierte, intelligente Plattform für Peeringverteilung, die Ihre vorhandene Netzwerkinfrastruktur nutzt, um Inhalte in vielen Formen (Livestreaming-Video, On-Demand-Video, Softwareupdates, Sicherheitspatches usw.) schneller, zuverlässiger und mit weniger Bandbreite bereitzustellen. Unsere sichere Plattform wird von den weltweit größten Finanzinstituten als vertrauenswürdig eingestuft, und da keine zusätzliche Hardware nötig ist, sind das Setup und die Wartung einfach. [Weitere Informationen](https://kollective.com/microsoft-pilot/).
 
- **Ramp OmniCache** bietet Netzwerkverteilung der nächsten Generation und sorgt für eine reibungslose Bereitstellung von Videoinhalten über globale WANs hinweg. Dies hilft Produzenten von Ereignissen bei der Optimierung der Netzwerkbandbreite und Unterstützung von erfolgreichen Liveereignis-Übertragungen und On-Demand-Streaming. Die Unterstützung für Ramp OmniCache für in Teams produzierte Liveereignisse ist in Kürze verfügbar. [Weitere Informationen](http://www.ramp.com). 
 
> [!NOTE] 
> Die von Ihnen ausgewählte SDN- oder eCDN-Lösung unterliegt den **Vertragsbedingungen und Datenschutzrichtlinien des gewählten Drittanbieters**, die die Nutzung der Lösung des Anbieters regeln. Ihre Nutzung der Anbieterlösung unterliegt nicht den Microsoft-Volumenlizenzierungsbedingungen oder den Nutzungsbedingungen für Online Services. Wenn Sie den **Vertragsbedingungen des Drittanbieters** nicht zustimmen, aktivieren Sie die Lösung nicht in Teams. 

Nachdem Sie die SDN- oder eCDN-Lösung eingerichtet haben, können Sie den Anbieter für Liveereignisse in Teams konfigurieren. 

## <a name="next-steps"></a>Nächste Schritte
Gehen Sie zu [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
