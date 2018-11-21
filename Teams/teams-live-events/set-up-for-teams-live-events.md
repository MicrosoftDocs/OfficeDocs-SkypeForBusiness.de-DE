---
title: Einrichten von Live-Ereignissen in Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Informationen Sie zu den Schritten für Ereignisse in Teams, einschließlich der Vorbereitung Ihres Netzwerks, Zuweisen von Lizenzen, mithilfe von Richtlinien zum Aktivieren von Features des live-Ereignis und für Benutzer planen und Einrichten von einem Drittanbieter-Verteilung Anbieter live einrichten.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fe13722bfc8b5aa7a9f57d0dfd39c67146e6c31
ms.sourcegitcommit: ff0c4bef4d4cbc71d51fce941aff63739a0016e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2018
ms.locfileid: "26626270"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Einrichten von Live-Ereignissen in Microsoft Teams

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Wenn Sie für live Ereignisse einrichten, sind mehrere Schritte, die Sie durchführen müssen:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Schritt 1: Richten Sie Ihres Netzwerks für live Ereignisse in der Microsoft-Teams ein
Schneller Einstieg in live Ereignisse, die Sie zum [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft-Teams,](https://docs.microsoft.com/microsoftteams/prepare-network)erforderlich.  

## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
Stellen Sie sicher, dass die richtige Lizenz Zuordnungen für und [Erstellen und Planen Sie live Ereignisse zu können](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) [, die live Ereignisse überwachen können](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Schritt 3: Einrichten von Richtlinien für live Ereignisse
Live Ereignisse, die den Richtlinien verwendet werden, um zu steuern, wer in Ihrer Organisation enthalten sein können live Ereignisse und die Features, die in den Ereignissen verfügbar sind, die sie erstellen. Verwenden Sie die Standardrichtlinie oder erstellen Sie eine, oder mehr benutzerdefinierten live Ereignisse Richtlinien. Nachdem Sie eine benutzerdefinierte Richtlinie erstellen, weisen sie einem Benutzer oder Gruppen von Benutzern in Ihrer Organisation.

> [!NOTE]
> Benutzer in Ihrer Organisation erhalten die globale Richtlinie, es sei denn, Sie erstellen, und weisen Sie eine benutzerdefinierte Richtlinie an. Standardmäßig in der globalen Richtlinie live-Ereignis planen für Teams Benutzer aktiviert ist, Lautschrift deaktiviert ist, kann alle Benutzer in der Organisation live Ereignisse teilnehmen und die Einstellung für die Aufzeichnung auf Aufzeichnen immer festgelegt ist. 

### <a name="create-or-edit-a-live-events-policy"></a>Erstellen oder Bearbeiten einer Richtlinie live Ereignisse

**![Teams-Logo-30x30.png](../media/teams-logo-30x30.png) verwenden die Microsoft-Teams & Skype für Business Administrationscenter**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live Ereignisse Richtlinien**. 
2. Führen Sie einen der folgenden Schritte aus:
- Wenn Sie die vorhandene Standardrichtlinie bearbeiten möchten, wählen Sie **Global (Org geltende Standard)**. 
- Wenn Sie eine neue benutzerdefinierte Richtlinie erstellen möchten, wählen Sie **neue Richtlinie**aus. 
- Wenn Sie eine benutzerdefinierte Richtlinie bearbeiten möchten, wählen Sie die Richtlinie, und wählen Sie dann auf **Bearbeiten**. 

    Hier sind die Einstellungen, die Sie ändern können, um die Anforderungen Ihrer Organisation entsprechen.

    ![Screenshot der live Ereignisse Richtlinieneinstellungen] (../media/teams-live-events-policies.png "Screenshot der live Ereignisse Richtlinieneinstellungen in der Microsoft-Teams & Skype für Business Administrationscenter") 

|Einstellung  |Beschreibung  |
|---------|---------|
|**Name**     |Dies ist der Name der Richtlinie, die auf der Seite live Ereignisse Richtlinien angezeigt wird. Es kann nicht länger als 64 Zeichen sein oder über keine Sonderzeichen.          |
|**Beschreibung**    |Verwenden Sie diese Option, um eine benutzerfreundliche Beschreibung für die Richtlinie hinzufügen.         |
|**Planung**     |Aktivieren Sie dies ermöglicht Benutzern in Ihrer Organisation erstellen und Planen Sie live Ereignisse in Teams. Es ist wichtig, zu wissen, dass, wenn Sie Benutzern, externe Encoder live Ereignisse planen möchten, sind zusätzliche Schritte, die Sie ausführen müssen. Weitere Informationen finden Sie finden Sie unter [Aktivieren von Benutzern zum Planen von externen Encoder Ereignisse](#enable-users-to-schedule-external-encoder-events).     |
|**Lautschrift für Teilnehmer zulassen** (bald verfügbar) |Diese Einstellung kann nur auf Schnellstart Ereignisse angewendet werden. Aktivieren Sie dies ermöglicht es den live-Ereignis Teilnehmern in Echtzeit Beschriftungen und Übersetzung während des Ereignisses angezeigt.         |
|**Wer kann an einer geplanten live Ereignisse teilnehmen**    |Wählen Sie eine der folgenden.<br> <br> **Jeder** Benutzer können live Ereignisse erstellen, die alle, auch Personen außerhalb Ihrer Organisation teilnehmen kann. <br> **Jede Person in der Organisation** Benutzer können live Ereignisse erstellen, die nur Personen in Ihrer Organisation teilnehmen können. Benutzer können keine live Ereignisse erstellen, die von anonymen Benutzern gesteuert werden. <br> **Bestimmte Benutzer oder Gruppen** Benutzer können live Ereignisse, die nur bestimmte Benutzer oder Gruppen in Ihrer Organisation teilnehmen können. Benutzer können keine live Ereignisse erstellen, die von jedem Benutzer in Ihrer Organisation oder von anonymen Benutzern gesteuert werden.        |
|**Aufzeichnen der Einstellung**  <br>     | Diese Einstellung kann nur auf Schnellstart Ereignisse angewendet werden. Wählen Sie eine der folgenden. <br><br> **Notieren Sie immer** Live Ereignisse, die von Benutzern erstellt wurden, werden immer aufgezeichnet. Nach Abschluss des Ereignisses über Ereignis Teammitglieder können die Aufzeichnung herunterladen und Teilnehmer können sehen Sie sich das Ereignis. <br> **Notieren Sie nie** Live Ereignisse, die von Benutzern erstellte werden nie aufgezeichnet. <br>**Organisatoren kann oder nicht aufzeichnen** Benutzer können entscheiden, ob das live-Ereignis aufgezeichnet. Wenn diese aufgezeichnet wird nach Abschluss des Ereignisses, Teammitglieder Ereignis können Sie die Aufzeichnung herunterladen und Teilnehmer können sehen Sie sich das Ereignis.      

Sie können auch dazu mithilfe von Windows PowerShell. Weitere Informationen finden Sie unter [Verwenden von PowerShell zum Festlegen von Richtlinien in Teams live Ereignisse](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Zuweisen einer Richtlinie auf live Ereignisse für Benutzer 

Wenn Sie eine benutzerdefinierte live Ereignisse Richtlinie erstellt haben, weisen Sie es, die Benutzern für die Richtlinie aktiv sein. 

![Teams-Logo-30x30.png](../media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business Administrationscenter

1. Klicken Sie im linken Navigationsbereich besuchen Sie **Benutzer**, und wählen Sie den Benutzer.
2. Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus. 
3. Wählen Sie die live Ereignisse Richtlinie ein, die Sie zuweisen möchten, und wählen Sie dann auf **Speichern**. 

### <a name="enable-users-to-schedule-external-encoder-events"></a>Aktivieren von Benutzern zum Planen von externen Encoder-Ereignisse

Um Benutzern externe Encoder Ereignisse planen müssen Sie auch Folgendes ausführen:

1. Aktivieren von Microsoft-Stream für Benutzer in Ihrer Organisation. Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst. Microsoft-Stream ist nicht in Business Essentials oder Business Premium-Plänen enthalten. Einzelheiten finden Sie unter [Stream Lizenzierung Overview](https://docs.microsoft.com/stream/license-overview) .

      Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können. Stellen Sie sicher, dass Microsoft Stream für die Benutzer blockiert nicht zur Verfügung, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.

2. Stellen Sie sicher, dass Benutzer über Berechtigungen zum Erstellen live-Ereignis im Microsoft Stream verfügen. In der Standardeinstellung können Administratoren externe Encoder live Ereignisse erstellen. Microsoft-Stream-Administrator können in Stream-Objekt [für die Erstellung des live-Ereignis weitere Benutzer aktivieren](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) .  

3. Stellen Sie sicher live-Ereignis, die Organisatoren zugestimmt haben die Unternehmensrichtlinie festlegen, indem Stream Admin. Wenn ein Microsoft-Stream-Administrator [eine Unternehmensrichtlinie Richtlinien einrichten hat](https://docs.microsoft.com/stream/company-policy-and-consent) und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, klicken Sie dann müssen Benutzer vor dem Erstellen einer live-Ereignis (mit der externen Encoder Produktion) in Teams. Bevor Sie das Feature live Ereignisse in der Organisation bereitstellen, stellen Sie sicher, dass Benutzer, die diese live Ereignisse erstellen werden die Richtlinie zugestimmt haben. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Schritt 4: Einrichten einer Lösung video Verteilung für live Ereignisse in Teams
Wiedergabe von Videos live-Ereignis verwendet adaptive Bitrate (ABR) streaming, aber es ist eine Unicast-Stream, was bedeutet, dass jeder Viewer eigene Videostream aus dem Internet abrufen ist. Für live Ereignisse oder Videos an große Teile Ihrer Organisation gesendet kann sehr viel Internetbandbreite Identitätsdaten durch Viewer handeln. Für Organisationen, die diesen Internet-Datenverkehr für live Ereignisse reduzieren möchten, vertrauenswürdige live Ereignisse, die von Microsoft Solutions integriert sind video Delivery Partner, anbietet Software Netzwerke (SDNs) oder Enterprise Content Delivery Networks (eCDNs) definiert. Diese Plattformen SDN/eCDN können Organisationen zum Optimieren der Netzwerkbandbreite ohne Beeinträchtigung Endbenutzer Erfahrungen anzeigen. Unsere Partner helfen, eine skalierbare und effiziente video Verteilung über Ihr Unternehmensnetzwerk zu aktivieren.

**Erwerb und richten Sie Ihre Lösung außerhalb von Teams** Hier erhalten Sie Hilfe Experten video Übermittlung durch die Nutzung von Microsoft vertrauenswürdigen video Delivery Partner skalieren. Bevor Sie einen video Delivery-Anbieter mit Teams verwendet werden, müssen Sie erwerben und richten Sie die Lösung SDN/eCDN äußeren und getrennt von Teams, aktivieren können.

SDN/eCDN Folgendes bereits integriert werden und können mit Microsoft-Stream eingerichtet werden.

- **Streaming Struktur** bietet eine einfache und leistungsstarke Lösung für die Live- und on-Demand Enterprise video Verteilung. Struktur ist eine softwarebasierte Lösung, die erfordert keine zusätzliche Hardware oder Bandbreite und auf sichere Weise Tausende von gleichzeitigen video Viewer ohne Auswirkung auf das Netzwerk zu aktivieren. Für Kunden, die zum Verständnis, dass das Video Auswirkung in ihrem Netzwerk vor dem Kauf einer Lösung SDN/eCDN hat bietet Streaming Struktur auch eine browserbasierte Analytics Lösung zur Microsoft-Kunden. [Erfahren Sie mehr](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** ist eine Cloud-basierten, intelligente Peers Verteilung Plattform, die nutzt die vorhandene Netzwerkinfrastruktur zum Übermitteln von Inhalten, in vielen Formen, (live Videostreams, bei Bedarf Video, Softwareupdates, Sicherheitspatches usw.), schneller zuverlässig und mit weniger Bandbreite. Unsere sichere Plattform ist vertrauenswürdig, von der weltweit größten Finanzinstituten und mit keine zusätzliche Hardware, Installation und Wartung einfach sind. [Erfahren Sie mehr](http://www.kollective.com).
 
- **Lernen OmniCache** ermöglicht die Verteilung der nächsten Generation Netzwerk und sorgt für nahtlose Bereitstellung von Videoinhalten auf globale WANs, Netzwerkbandbreite zu optimieren und unterstützen erfolgreiches Ereignis live Übertragungen und on-Demand Ereignis Hersteller helfen Streaming. Die Unterstützung für lernen OmniCache Schnellstart live Ereignisse wird in Kürze bereitgestellt.  [Erfahren Sie mehr](http://www.ramp.com). 
 
> [!NOTE] 
> Die gewählte Lösung SDN oder eCDN unterliegt den ausgewählten **3. Anbieters Bedingungen Service und der Datenschutzrichtlinie**, Ihre Verwendung des Anbieters Lösung, welche wird steuert. Die Verwendung des Anbieters Lösung werden nicht unter der Microsoft Volume licensing Begriffe oder Online Services-Ausdrücken. Wenn Sie nicht den **3. Anbieters Begriffe**zustimmen, aktivieren Sie dann nicht die Lösung in Teams. 

Nachdem Sie die Lösung SDN oder eCDN eingerichtet haben, können Sie zum Konfigurieren des Anbieters für live Ereignisse in Teams. 

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zur [Konfigurieren live Ereignisse Einstellungen in Teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams live Ereignisse?](what-are-teams-live-events.md)
- [Planen von Teams live-Ereignisse](plan-for-teams-live-events.md)
- [Konfigurieren von live Ereignisse Einstellungen in Teams](configure-teams-live-events.md)

