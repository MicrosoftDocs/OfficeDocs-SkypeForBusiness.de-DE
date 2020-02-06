---
title: Planen von Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über Konferenzfeatures und Funktionen in Skype for Business Server zu erfahren.'
ms.openlocfilehash: f91c815cf0b5d0b69ad5815157cba7a56bb28307
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816003"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planen von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über Konferenzfeatures und Funktionen in Skype for Business Server zu erfahren.
  
Konferenzen in Skype for Business Server ermöglichen es Benutzern, Konferenzen online mithilfe Ihres Skype for Business-Clients zu treffen und abzuhalten, anstatt dass sich alle im gleichen Raum zusammenfinden. Besprechungsteilnehmer können mit dem Skype for Business-Client eine Verbindung mit einer Besprechung herstellen, um eine vollständige Audio-und Videowiedergabe zu erhalten, oder sich mit einem Telefon in eine Konferenz einwählen. Die Konferenzen unterstützen außerdem Funktionen wie Chat, Desktop- und Anwendungsfreigabe sowie interaktive Whiteboards.
  
Dieses Thema enthält die folgenden Abschnitte:
  
- Konferenzfunktionen und -optionen
    
- Konferenzkomponenten
    
- Konferenzrichtlinien
    
- Unterstützung für große Besprechungen
    
- Festlegen der Anforderungen Ihres Unternehmens
    
## <a name="conferencing-features-and-capabilities"></a>Konferenzfunktionen und -optionen

In Skype for Business Server stehen vier Konferenz Arten zur Verfügung: Webkonferenzen, Audio-und Videokonferenzen (A/V), Einwahlkonferenzen und Sofortnachrichten (im). 
  
Ganz nach Ihren Bedürfnissen können Sie entweder alle Konferenzarten aktivieren oder nur einen einzigen Typen nutzen. So können Sie beispielsweise alle Typen, einschließlich Einwahlkonferenzen, aktivieren, um Benutzern, die nicht in der Lage sind, an einer Konferenz teilzunehmen, mit einem Skype for Business-Client zu ermöglichen, sich über ein Telefon anzurufen und an der Audiokonferenz teilzunehmen. Bei der Bereitstellung von Skype for Business Server werden Sofortnachrichten-Konferenzfunktionen automatisch bereitgestellt. Sie können mithilfe des Topologie-Generators angeben, ob Web-, A/V-und Einwahlkonferenzen bereitgestellt werden sollen. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
In den folgenden Unterabschnitten werden die Funktionen und Optionen der einzelnen Konferenzarten beschrieben.
  
### <a name="web-conferencing"></a>Webkonferenzen

Mit Webkonferenzen können Besprechungsteilnehmer an Dokumenten zusammenarbeiten, die während der Besprechung freigegeben sind, und für den besprechungsreferenten die gemeinsame Nutzung von Anwendungen über den Skype for Business-Client. Webkonferenzen bieten die folgenden Funktionen: 
  
- **Whiteboard und Anmerkungen.** Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Die Whiteboard-Funktion verbessert die Zusammenarbeit, indem Besprechungsteilnehmer die Möglichkeit erhalten, Ideen zu diskutieren, ein Brainstorming durchzuführen, Notizen zu machen, usw.
    
- **Abruf.** Das Polling-Feature verbessert die Zusammenarbeit, indem es Referenten ermöglicht, die Einstellungen der Teilnehmer schnell festzulegen. In Onlinebesprechungen und Unterhaltungen können Referenten mithilfe von Umfragen anonyme Antworten von Teilnehmern sammeln. Alle Referenten können die Ergebnisse sehen und entweder die Ergebnisse ausblenden oder alle Teilnehmer anzeigen.
    
- **Anwendungs- und Desktopfreigabe.** Während einer Konferenz kann der Referent der Besprechung seinen gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Andere Teilnehmer der Konferenz können nicht nur die Inhalte sehen, sondern auch die Kontrolle über Ihren Bildschirm anfordern und mit Ihrer Erlaubnis mit den Inhalten interagieren (einschließlich Bildlauf und Bearbeitung). Teilnehmer können außerdem als Referenten die Kontrolle übernehmen und während der Besprechung Inhalte freigeben.
    
- **Power Point-Freigabe.** Benutzer können PowerPoint-Präsentationen in der Besprechung über einen Office Web App-Server freigeben. Daraus ergeben sich folgende Möglichkeiten:
    
  - Hochauflösende Displays und Unterstützung von PowerPoint-Funktionen wie Animationen, Folienübergänge und eingebettete Videos.
    
  - Mobile Geräte erhalten Zugriff auf diese Präsentationen.
    
  - Benutzer mit entsprechenden Berechtigungen können unabhängig von der Präsentation einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während Klaus beispielsweise seine Bildschirmpräsentation ablaufen lässt, kann Helga sich eine beliebige Folie ansehen, ohne Klaus Präsentation zu beeinträchtigen.
    
### <a name="audio-and-video-conferencing"></a>Audio- und Videokonferenzen

Mit der AV-Konferenzfunktion können in der Besprechung Audio- und Videodaten übertragen werden. Über den Audioteil können die Attendants miteinander sprechen, als befänden sie sich in demselben Raum. Video ermöglicht die Videoanzeige im Skype for Business-Client von Teilnehmern oder Referenten, die an einer Besprechung teilnehmen, mit einem Webcam-oder Konferenzgerät, das Video unterstützt.
  
 Skype for Business Server bietet verschiedene Funktionen, die Benutzer verwenden können, um die Audiokonferenz-Oberfläche für den Benutzer zu konfigurieren, einschließlich der folgenden:
  
- **Publikum stumm schalten.** Der Referent kann mit dieser Einstellung alle Audioteilnehmer der Konferenz stummschalten und die Konferenz so in einen Modus versetzen, in dem die Teilnehmer die Stummschaltung nicht selbst aufheben können.
    
- **Konferenz Eintrag/-Exit-Ankündigungen.** Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten über diese Einstellung Ansagen beim Beitreten und Verlassen ein- oder ausschalten, um Ablenkungen während der Konferenz zu vermeiden.
    
- **Hinzufügen eines Benutzers durch wählen aus.** Referenten und Teilnehmer, denen die Berechtigung erteilt wurde, können den Konferenzen PSTN-Nummern hinzufügen und die Konferenz an diese Nummern abwählen.
    
  Skype for Business Server bietet verschiedene Funktionen, mit denen Benutzer die Videokonferenzfunktionalität für den Benutzer konfigurieren können, einschließlich der folgenden:
  
- **Katalogansicht.** In Videokonferenzen, an denen mehr als zwei Personen teilnehmen, sehen die Benutzer automatisch alle Teilnehmer der Konferenz. Wenn die Konferenz mehr als fünf Teilnehmer hat, werden in der ersten Zeile die Videos der aktivsten Teilnehmer angezeigt und für die übrigen Teilnehmer Fotos. Die Videoaushandlung ist standardmäßig aktiviert.
    
- **Panorama Video** Wenn im Konferenzraum ein Round Table-Videokonferenzgerät installiert ist, bietet diese Funktion eine vollständige 360-Grad-Ansicht des Konferenzraums. Panoramavideo ist nur mit Round Table verfügbar.
    
- **Videomodus für Referenten.** Referenten können Besprechungen so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dies verhindert bei großen Besprechungen Ablenkungen, wenn mehrere Videostreams verfügbar und mit verschiedenen Quellen verbunden sind. Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräte aufgenommen und bereitgestellt werden.
    
- **Video-Spotlight.** Referenten können die Besprechung so konfigurieren, dass die Teilnehmer der Konferenz nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, sehen. Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräten aufgenommen und bereitgestellt werden.
    
### <a name="dial-in-conferencing"></a>Einwahlkonferenzen

Einwahlkonferenzen ermöglichen es Besprechungsteilnehmern, am Audioteil einer Besprechung teilzunehmen, indem Sie von einem Telefon aus in die Besprechung einwählen. Einwahlkonferenzen sind ein Unterbereich der Audiokonferenzen und müssen zusätzlich konfiguriert werden. Weitere Informationen zu Einwahlkonferenzen finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](dial-in-conferencing.md) und Konfigurieren von [Einwahlkonferenzen in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Chatkonferenzen

Über die Chatkonferenzfunktion können mehr als zwei Parteien in einer einzigen Sofortnachrichtensitzung miteinander kommunizieren. Details zu Chat Konferenzen finden Sie unter [Planen von Sofortnachrichten und Anwesenheitsinformationen in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Konferenzkomponenten

Zu den Komponenten, die für die Unterstützung der Konferenzfunktionen erforderlich sind, gehören:
  
- **Anwendungsdienst.** Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications-Anwendungen (UC). Bei Einwahlkonferenzen werden zwei UC-Anwendungen verwendet, die den Anwendungsdienst benötigen: Die Konferenzzentrale und die Konferenzankündigungsanwendung. Der Anwendungsdienst wird standardmäßig auf jedem Front-End-Server in einem Front-End-Pool installiert und aktiviert. Darüber hinaus wird er auf jedem Standard Edition-Server installiert, um Einwahlkonferenzen zu aktivieren und zu konfigurieren.
    
- **Die Konferenzzentrale.** Die Anwendung „Konferenzzentrale“ ist eine Unified Communications-Anwendung, die Festnetzanrufe annimmt, Ansagen wiedergibt und Anrufe mit einer A/V-Konferenz verbindet. Sie wird standardmäßig installiert und aktiviert, wenn Sie die Option für Einwahlkonferenzen aktivieren.
    
- **Konferenzankündigungsanwendung.** Die Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung zur Wiedergabe von Signaltönen und Ansagen für Festnetzteilnehmer bei bestimmten Aktionen (z. B. wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, Teilnehmer stumm geschaltet werden oder die Stummschaltung aufgehoben wird, Benutzer in der Lobby platziert werden oder wenn die Konferenz gesperrt bzw. entsperrt wird). Die Konferenzankündigungsanwendung unterstützt zudem DTMF-Befehle (Dual-Tone Multifrequency, Tonwahlverfahren) über die Telefontastatur. Die Konferenzankündigungsanwendung wird standardmäßig automatisch installiert und aktiviert, wenn Sie die Option für Einwahlkonferenzen aktivieren.
    
- **Die Einrichtungsseite für Einwahlkonferenzen.** Auf der Einrichtungsseite für Einwahlkonferenzen werden die Konferenzeinwahlnummern mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und die in einer Konferenz verfügbaren DTMF-Steuerelemente angezeigt. Darüber hinaus können Benutzer auf dieser Seite ihre persönliche Identifikationsnummer (PIN) sowie zugewiesene Konferenzinformationen verwalten. Die Einrichtungsseite für Einwahlkonferenzen wird automatisch als Teil der Web Services installiert.
    
- **Vermittlungs Server und PSTN-Gateway** Für Einwahlkonferenzen ist ein Vermittlungs Server erforderlich, um Signalisierungen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway zu übersetzen, und ein PSTN-Gateway, um Signalisierungs-und Medien Verbindungen zwischen dem Vermittlungsserver und dem PSTN-Gateway zu übersetzen. . Für Einwahlkonferenzen müssen Sie mindestens einen Vermittlungs Server und mindestens eine der folgenden Aktionen bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)
    
  > [!NOTE]
  > Wenn Sie auch Enterprise-VoIP bereitstellen, sind Vermittlungs Server und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens einen Vermittlungs Server und mindestens ein PSTN-Gateway, IP-PBX oder SBC für Einwahlkonferenzen bereitstellen. 
  
- **Dateispeicher.** Der Dateispeicher wird für Audiodateien mit aufgezeichneten Namen verwendet. Er ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.
    
- **Benutzerspeicher.** Der Benutzerspeicher dient zum Speichern von Skype for Business Server-Pins für Benutzer. Für PINs wird ein Hashalgorithmus verwendet. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.
    
- **Office Web Apps-Server.** Um Webkonferenzfunktionen verwenden zu können, müssen Administratoren Office Web Apps Server installieren und Skype for Business Server für die Kommunikation mit Office Web Apps Server konfigurieren.
    
## <a name="conferencing-policies"></a>Konferenzrichtlinien

Wenn Sie die Richtlinien Ihrer Organisation erzwingen und die Bandbreitennutzung steuern möchten, können Sie Richtlinien für die Besprechungstypen festlegen, die von Benutzern organisiert werden können. Sie können eine Vielzahl von Konferenzrichtlinien definieren und diese einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Details zum Festlegen von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Details zur Bandbreitenverwaltung finden Sie unter [Planen der Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Unterstützung für große Besprechungen

Die Größe von Besprechungen, die von Skype for Business Server unterstützt werden können, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden:
  
- In einem gemeinsamen Pool kann Skype for Business Server Besprechungen mit bis zu 250 Benutzern hosten. Bei einem freigegebenen Pool handelt es sich um einen Pool, in dem alle Skype for Business Server-Arbeitsauslastungen, einschließlich Instant Messaging (im) und Anwesenheit, Konferenz und Enterprise-VoIP, gehostet werden. 
    
- In einem dedizierten Pool kann Skype for Business Server Besprechungen mit bis zu 1000 Teilnehmern mithilfe von Web-und Audio/Video-Konferenzen (a/V) unterstützen, einschließlich der Freigabe von PowerPoint-Präsentationen. Hierzu muss ein dedizierter Pool konfiguriert werden, der große Besprechungen unterstützt und so verwaltet wird, dass er das Hosten einer einzigen großen Besprechung sicherstellt. 
    
Weitere Informationen zum Verwalten großer Besprechungen finden Sie unter [Planen großer Besprechungen in Skype for Business Server](large-meetings.md).
  
Wenn in Ihrer Organisation größere Besprechungsfunktionen erforderlich sind, sollten Sie eine Hybridumgebung implementieren, die Skype-Live Konferenz, einen Onlinedienst, der Teil von Office 365 ist, nutzt. Skype-Livekonferenz ermöglicht Benutzern, Besprechungen von bis zu 10.000 Teilnehmern zu hosten und an ein ebenso großes Online-Publikum zu übertragen. Für die Nutzung von Skype-Livekonferenz muss Skype for Business Server bereits in einer Hybridumgebung mit einem Office 365-Produktionsmandanten konfiguriert sein. Als Grundvoraussetzung muss bei allen Benutzern ein Online-Mandant eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die die Vorteile von Skype-Livekonferenz nutzen kann, finden Sie weitere Informationen unter [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md)
  
## <a name="determine-your-organizations-needs"></a>Festlegen der Anforderungen Ihres Unternehmens

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die folgende Liste führt Sie durch den Konferenz Planungsprozess, um zu ermitteln, welche Features von Konferenzen Sie basierend auf den Anforderungen Ihrer Organisation bereitstellen sollten.
  
> [!NOTE]
> Wenn Sie die Konferenzfunktion bei der Bereitstellung aktivieren, werden auch die Web- und die A/V-Konferenzfunktionen automatisch freigeschaltet. Sie können allerdings bestimmte Funktionen deaktivieren, indem Sie, wie zuvor in diesem Kapitel beschrieben, Konferenzrichtlinien aufstellen. 
  
- **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn ja, müssen Sie die Konferenzfunktionen mithilfe des Planungstools oder des Topologie-Generators für Ihren Front-End-Pool freischalten. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt. Skype for Business Server bietet einen Drosselungsmechanismus zur Steuerung jeder Anwendungsfreigabesitzung. In der Standardeinstellung sind für jede Sitzung 1,5 KB/s festgelegt. Wenn Sie die Anwendungsfreigabe nicht aktivieren möchten, Sie jedoch die Zusammenarbeit mit Dokumenten verwenden möchten, können Sie Konferenzen aktivieren und Konferenzrichtlinien verwenden, um die Anwendungsfreigabe zu deaktivieren. Details zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Um Benutzern das Freigeben von PowerPoint-Präsentationen zu ermöglichen, müssen Sie den Office Web Apps-Server konfigurieren. Weitere Informationen zum Konfigurieren von Office Web Apps Server finden Sie unter [Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Möchten Sie Audio- und Videokonferenzen aktivieren?**
    
    Wenn ja, müssen Sie die Konferenzfunktionen mithilfe des Planungstools oder des Topologie-Generators für Ihren Front-End-Pool freischalten. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Für Audio- und Videokonferenzen ist eine höhere Netzwerkbandbreite erforderlich als für Webkonferenzen (diese umfassen Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie Audio- und Videokonferenzen nicht aktivieren, jedoch die Funktion für Webkonferenzen bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und A/V-Konferenzen mithilfe von Konferenzrichtlinien deaktivieren.
    
    Wenn Sie Audiokonferenzen, jedoch keine Videokonferenzen zulassen möchten, können Sie die A/V-Konferenzfunktion aktivieren und Videokonferenzen mithilfe von Konferenzrichtlinien verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen. 
    
    Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Enterprise Voice wird für A/V-Konferenzen nicht benötigt. Wenn Sie A/V-Konferenzen aktivieren, können Benutzer ihren Konferenzen Audiofunktionen hinzufügen, falls sie über entsprechende Geräte verfügen. Dies gilt auch bei Verwendung eines Nebenstellensystems als Telefonlösung. 
  
- **Möchten Sie Benutzern die Teilnahme am Audioteil von Konferenzen ermöglichen, wenn Sie ein PSTN-Telefon verwenden?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.
    
    Einwahlkonferenzen sind ein optionales Feature, das Sie bei der Bereitstellung von Skype for Business Server-Konferenzen konfigurieren können. Wenngleich Einwahlkonferenzen einige Komponenten von Enterprise Voice verwenden, ist die Bereitstellung von Enterprise Voice nicht erforderlich, um Einwahlkonferenzen bereitzustellen. Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Weitere Informationen zum Konfigurieren von Einwahlkonferenzen für Enterprise-und anonyme Benutzer finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) und [Konfigurieren von Einwahlkonferenzen in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Möchten Sie externen Benutzern mit Skype for Business-Clients erlauben, an einer Konferenz teilzunehmen?**
    
    Indem Sie externe Teilnahme an Besprechungen zulassen, maximieren Sie Ihre Investition in Skype for Business Server. Folgende Personenkreise können als externe Benutzer eingestuft werden:
    
  - **Remotebenutzer.** Die eigenen Benutzer Ihrer Organisation, wenn diese außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere Skype for Business Server-Geräte verwenden.
    
  - **Federated-Benutzer.** Benutzer von Unternehmen, mit denen Sie zusammenarbeiten, die auch Skype for Business Server ausführen. Damit Ihre Benutzer problemlos Kontakt zu diesen Benutzern aufnehmen können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.
    
  - **Anonyme Benutzer.** Alle anderen externen Benutzer, die von Ihren Benutzern zur Teilnahme an bestimmten Konferenzen eingeladen werden. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.
    
    Wenn Sie externe Benutzer zulassen möchten, müssen Sie Edgeserver bereitstellen. Wenn Sie Edgeserver bereitstellen, können Sie zudem Partnerverbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – einrichten, sodass Benutzer dieser Organisationen einfacher mit Ihren Benutzern zusammenarbeiten können.
    
    Ausführliche Informationen zur Bereitstellung von Edgeservern finden Sie unter „Planen für Edgeserver“ und „Bereitstellen von Edgeserver“. Details zum Aktivieren von externem Zugriff für Office Web Apps Server finden Sie unter [Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Möchten Sie die Clients steuern, die an den Skype for Business Server-Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal, wenn ein Benutzer auf einen Link klickt, um an einer geplanten Besprechung teilzunehmen, erkennt Skype for Business Server, ob ein Client bereits auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt mit Links zu alternativen Clients wird geöffnet. Die Seite "Besprechungsteilnahme" enthält immer die Option zur Verwendung von Skype for Business Web App. Ferner können Sie entscheiden, ob Links für Teilnehmer und frühere Versionen von Communicator eingeschlossen werden sollen. 
    

