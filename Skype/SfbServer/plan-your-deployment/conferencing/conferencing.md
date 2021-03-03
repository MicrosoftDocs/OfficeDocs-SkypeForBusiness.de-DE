---
title: Planen von Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Konferenzfunktionen und -funktionen in Skype for Business Server zu erfahren.'
ms.openlocfilehash: 187da0c45724140295ba28285a33d8d57d422e4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814055"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planen von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Konferenzfunktionen und -funktionen in Skype for Business Server zu erfahren.
  
Mit Konferenzen in Skype for Business Server können Benutzer sich online mit ihrem Skype for Business-Client treffen und konferenzen halten, anstatt sich im gleichen Raum zu treffen. Besprechungsteilnehmer können mit ihrem Skype for Business-Client eine Verbindung mit einer Besprechung herstellen, um eine vollständige Audio- und Videoerfahrung zu erhalten, oder sich über ein Telefon in eine Konferenz einwählen. Konferenzen unterstützen auch Chat, Desktop- und Anwendungsfreigabe sowie interaktive Whiteboards.
  
Dieses Thema enthält die folgenden Abschnitte:
  
- Konferenzfeatures und -funktionen
    
- Konferenzkomponenten
    
- Konferenzrichtlinien
    
- Unterstützung für große Besprechungen
    
- Bestimmen der Anforderungen Ihrer Organisation
    
## <a name="conferencing-features-and-capabilities"></a>Konferenzfeatures und -funktionen

In Skype for Business Server stehen vier Arten von Konferenzen zur Verfügung: Webkonferenzen, Audio- und Videokonferenzen (A/V), Einwahlkonferenzen und Chatkonferenzen. 
  
Sie können je nach Ihren Anforderungen alle Konferenztypen aktivieren oder nur einen Typ verwenden. Sie können beispielsweise alle Typen, einschließlich Einwahlkonferenzen, aktivieren, damit Benutzer, die nicht an einer Konferenz mit einem Skype for Business-Client teilnehmen können, sich über ein Telefon einwählen und an den Audiokonferenzen teilnehmen können. Wenn Sie Skype for Business Server bereitstellen, werden die Funktionen für Chatkonferenzen automatisch bereitgestellt. Geben Sie mithilfe des Topologie-Generators an, ob Web-, A/V- und Einwahlkonferenzen bereitgestellt werden. Weitere Informationen finden Sie unter ["Bereitstellen von Konferenzen in Skype for Business Server".](../../deploy/deploy-conferencing/deploy-conferencing.md) 
  
In den folgenden Unterabschnitten werden die Features und Funktionen der einzelnen Konferenztypen beschrieben.
  
### <a name="web-conferencing"></a>Webkonferenzen

Webkonferenzen ermöglichen Besprechungsteilnehmern die Zusammenarbeit an Dokumenten, die während der Besprechung freigegeben wurden, und für den Besprechungssprecher das Freigeben von Anwendungen über den Skype for Business-Client. Webkonferenzen bieten die folgenden Funktionen: 
  
- **Whiteboard und Anmerkungen.** Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Das Whiteboardfeature verbessert die Zusammenarbeit, da alle Besprechungsteilnehmer Ideen diskutieren und entwickeln können, Notizen machen können usw.
    
- **Abruf.** Das Abruffeature verbessert die Zusammenarbeit, indem Sprecher die Einstellungen der Teilnehmer schnell ermitteln können. In Onlinebesprechungen und -unterhaltungen können Referenten über Abrufe anonyme Antworten von Teilnehmern einholen. Alle Referenten können die Ergebnisse sehen und sie für alle Teilnehmer ausblenden oder anzeigen.
    
- **Anwendungsfreigabe und Desktopfreigabe.** Während einer Konferenz kann der Besprechungs presenter den gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Neben dem einfachen Anzeigen der Inhalte können andere Konferenzteilnehmer die Steuerung des Bildschirms des Presenters anfordern und mit Erlaubnis mit dem Inhalt interagieren (einschließlich Bildlauf und Bearbeitung). Besprechungsteilnehmer können auch als Moderator übernehmen und mit der Freigabe von Inhalten während der Besprechung beginnen.
    
- **PowerPoint-Freigabe.** Ermöglicht Benutzern das Freigeben von PowerPoint-Präsentationen in der Besprechung über einen Office Web Apps-Server, was:
    
  - Hochauflösende Displays und Unterstützung für PowerPoint-Funktionen, z. B. Animationen, Folienübergänge und eingebettetes Video.
    
  - Mobile Geräte können auf diese Präsentationen zugreifen.
    
  - Benutzer mit den entsprechenden Berechtigungen können unabhängig von der Präsentation selbst einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während Ken beispielsweise seine Bildschirmpräsentation präsentiert, kann Heidi jede Folie betrachten, die sie möchte, ohne sich auf Kens Präsentation zu beeinträchtigen.
    
### <a name="audio-and-video-conferencing"></a>Audio- und Videokonferenzen

Audio- und Videokonferenzen ermöglichen audio- und video in der Besprechung. Audio ermöglicht teilnehmern, miteinander zu sprechen, als besennen sie sich im gleichen Raum. Video ermöglicht die Videoanzeige im Skype for Business-Client aller Teilnehmer oder Moderatoren, die der Besprechung mit einer Webkamera oder einem Konferenzgerät beitreten, das Video unterstützt.
  
 Skype for Business Server bietet mehrere Funktionen, die Benutzer zum Konfigurieren der Audiokonferenzerfahrung für den Benutzer verwenden können, einschließlich der folgenden:
  
- **Zielgruppe stummschalten.** Der Moderator kann diese Einstellung verwenden, um alle Audioteilnehmer der Konferenz stummschalten und die Konferenz in einen Zustand zu setzen, in dem sich Nicht- Presenter nicht selbst stummschalten können.
    
- **Ein-/Austrittsansagen für Konferenzen.** Wenn Sie Einwahlkonferenzen aktiviert haben, können Sprecher diese Einstellung verwenden, um Ansagen für ein- und auszuschalten, um Ablenkungen während einer Konferenz zu minimieren.
    
- **Hinzufügen eines Benutzers durch Auswählen.** Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.
    
  Skype for Business Server bietet mehrere Funktionen, die Benutzer zum Konfigurieren der Videokonferenzerfahrung für den Benutzer verwenden können, einschließlich der folgenden:
  
- **Katalogansicht.** In Videokonferenzen mit mehr als zwei Personen sehen Benutzer automatisch alle Personen in der Konferenz. Wenn die Konferenz mehr als fünf Teilnehmer hat, wird das Video der aktivsten Teilnehmer in der obersten Zeile angezeigt, und nur das Foto wird für die anderen Teilnehmer angezeigt. Video mit mehrerenPartys ist standardmäßig aktiviert.
    
- **Panoramavideo.** Wenn ein RoundTable-Videokonferenzgerät im Konferenzraum installiert ist, bietet dieses Feature eine vollständige 360-Grad-Ansicht des Konferenzraums. Der Panoramavideostreifen ist nur auf RoundTable-Geräten verfügbar.
    
- **Nur Presenter-Videomodus.** Presenters can configure the meeting so that only the video from the presenter is shown. Dies verhindert Ablenkungen bei großen Besprechungen, wenn mehrere Videostreams verfügbar sind, und sperrt unterschiedliche Quellen. Dieser Modus gilt auch für Videos, die von RoundTable-Geräten aufgenommen und bereitgestellt werden.
    
- **Video-Spotlight.** Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference. Dieser Modus gilt auch für Videos, die von RoundTable-Geräten für Panoramavideos aufgenommen und bereitgestellt werden.
    
### <a name="dial-in-conferencing"></a>Einwahlkonferenz

Einwahlkonferenzen ermöglichen Besprechungsteilnehmern die Teilnahme am Audioteil einer Besprechung, indem sie sich über ein Telefon bei der Besprechung einwählen. Einwahlkonferenzen sind ein Teil von Audiokonferenzen und erfordern zusätzliche Konfiguration. Weitere Informationen zu Einwahlkonferenzen finden Sie unter "Planen von Einwahlkonferenzen [in Skype for Business Server"](dial-in-conferencing.md) und "Konfigurieren von Einwahlkonferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/dial-in-conferencing.md) 
  
### <a name="instant-messaging-conferencing"></a>Chatkonferenzen

Chatkonferenzen ermöglichen mehr als zwei Parteien die Kommunikation in einer einzelnen Chatsitzung. Weitere Informationen zu Chatkonferenzen finden Sie unter "Planen von Chat [und Anwesenheit in Skype for Business Server".](../../plan-your-deployment/instant-messaging-and-presence.md)
  
## <a name="conferencing-components"></a>Konferenzkomponenten

Zu den Komponenten, die Konferenzfeatures unterstützen, gehören die folgenden:
  
- **Anwendungsdienst.** Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications (UC)-Anwendungen. Einwahlkonferenzen verwenden zwei UC-Anwendungen, für die der Anwendungsdienst erforderlich ist: Die Konferenztelefonankündigung und die Konferenzankündigung. Der Anwendungsdienst wird standardmäßig auf jedem Front-End-Server in einem Front-End-Pool installiert und aktiviert. Es wird auch auf jedem Standard Edition-Server installiert, um Einwahlkonferenzen zu aktivieren und zu konfigurieren.
    
- **Konferenz attendant-Anwendung.** Die Konferenztelefonanrufanwendung ist eine Unified Communications-Anwendung, die Festnetzanrufe (Public Switched Telephone Network, PSTN) akzeptiert, Ansforderungen wieder gibt und an einer A/V-Konferenz teilnimmt. Die Konferenztelefonanrufanwendung wird standardmäßig installiert und aktiviert, wenn Sie Einwahlkonferenzen aktivieren.
    
- **Konferenzankündigungsanwendung.** Die Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung, die Töne und Eingabeaufforderungen für Teilnehmer im öffentlichen Telefonnetz bei bestimmten Aktionen wiedergibt, z. B. wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, Teilnehmer stummgeschaltet oder stummgeschaltet werden, jemand in die Konferenzlobby wechselt oder die Konferenz gesperrt oder entsperrt ist. Die Konferenzankündigungsanwendung unterstützt auch Dual-Tone Multi-Frequency (DTMF)-Befehle über die Telefontaste. Die Konferenzankündigungsanwendung wird automatisch installiert und standardmäßig aktiviert, wenn Sie Einwahlkonferenzen aktivieren.
    
- **Seite "Einstellungen für Einwahlkonferenzen".** Auf der Seite "Einstellungen für Einwahlkonferenzen" werden Einwahlnummern für Konferenzen mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und In-Conference-DTMF-Steuerelementen angezeigt und die Verwaltung der persönlichen Identifikationsnummer (PIN) und zugewiesener Konferenzinformationen unterstützt. Die Seite "Einstellungen für Einwahlkonferenzen" wird automatisch als Teil der Webdienste installiert.
    
- **Vermittlungsserver und PSTN-Gateway.** Einwahlkonferenzen erfordern einen Vermittlungsserver zum Übersetzen von Signalen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway sowie ein PSTN-Gateway zum Übersetzen von Signalen und Medien zwischen dem Vermittlungsserver und dem PSTN-Gateway. Für Einwahlkonferenzen müssen Sie mindestens einen Vermittlungsserver und mindestens einen der folgenden Server bereitstellen:
    
  - PSTN-Gateway
    
  - IP-PBX
    
  - Session Border Controller (SBC) (für einen Internettelefoniedienstanbieter, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
  > [!NOTE]
  > Wenn Sie auch Enterprise-VoIP, sind Vermittlungsserver und PSTN-Gateways Teil Enterprise-VoIP Bereitstellung. Wenn Sie keine Enterprise-VoIP, müssen Sie mindestens einen Vermittlungsserver und mindestens ein PSTN-Gateway, eine IP-PBX-Anlage oder einen SBC für Einwahlkonferenzen bereitstellen. 
  
- **Dateispeicher.** Der Dateispeicher wird für Audiodateien mit aufgezeichneten Namen verwendet. Der Dateispeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.
    
- **Benutzerspeicher.** Der Benutzerspeicher wird zum Speichern von Skype for Business Server-PINs verwendet. PINs werden mit Hashing verwendet. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.
    
- **Office Web Apps Server.** Um Webkonferenzfunktionen nutzen zu können, müssen Administratoren Office Web Apps Server installieren und Skype for Business Server für die Kommunikation mit Office Web Apps Server konfigurieren.
    
## <a name="conferencing-policies"></a>Konferenzrichtlinien

Um die Richtlinien Ihrer Organisation zu erzwingen und die Bandbreitennutzung zu steuern, können Sie Richtlinien für die Arten von Besprechungen festlegen, die Benutzer organisieren können. Sie können eine Vielzahl von Konferenzrichtlinien definieren und sie einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Weitere Informationen zum Festlegen von Konferenzrichtlinien finden Sie unter "Verwalten von [Konferenzrichtlinien in Skype for Business Server".](../../manage/conferencing/conferencing-policies.md) Weitere Informationen zur Bandbreitenverwaltung finden Sie unter ["Planen der Anrufsteuerung in Skype for Business Server".](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
## <a name="support-for-large-meetings"></a>Unterstützung für große Besprechungen

Die Größe von Besprechungen, die Skype for Business Server unterstützen kann, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden:
  
- In einem freigegebenen Pool kann Skype for Business Server Besprechungen mit bis zu 250 Benutzern hosten. Ein freigegebener Pool ist ein Pool, der alle Skype for Business Server-Workloads hostet, einschließlich Sofortnachrichten und Anwesenheit, Konferenzen und Enterprise-VoIP. 
    
- In einem dedizierten Pool kann Skype for Business Server Besprechungen mit bis zu 1.000 Teilnehmern mithilfe von Web- und Audio-/Videokonferenzen (A/V) unterstützen, einschließlich der Freigabe von PowerPoint-Präsentationen. Für diese Unterstützung ist ein dedizierter Pool erforderlich, der für die Unterstützung großer Besprechungen konfiguriert und so verwaltet wird, dass immer nur eine große Besprechung gleichzeitig verwaltet wird. 
    
Weitere Informationen zum Verwalten großer Besprechungen finden Sie unter ["Planen großer Besprechungen in Skype for Business Server".](large-meetings.md)
  
Wenn Ihre Organisation größere Besprechungsfunktionen benötigt, sollten Sie die Implementierung einer Hybridumgebung in Betracht ziehen, die die Vorteile von Skype Meeting Broadcast nutzt, einem Onlinedienst, der Bestandteil von Microsoft 365 und Office 365 ist. Skype Meeting Broadcast ermöglicht Benutzern das Hosten und Übertragen von Besprechungen an ein großes Onlinepublikum mit bis zu 10.000 Teilnehmern. Für die Verwendung von Skype Meeting Broadcast muss Skype for Business Server bereits in einer Hybrideinrichtung mit einer Microsoft 365- oder Office 365-Produktionsorganisation konfiguriert sein. Für alle Benutzer muss ein Online mandant als Voraussetzung eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die die Vorteile von Skype Meeting Broadcast nutzen kann, lesen Sie die Informationen unter "Konfigurieren Ihrer lokalen Bereitstellung für [Skype Meeting Broadcast".](../../deploy/configure-skype-meeting-broadcast.md)
  
## <a name="determine-your-organizations-needs"></a>Ermitteln der Anforderungen Ihrer Organisation

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die folgende Liste führt Sie durch den Konferenzplanungsprozess, um basierend auf den Anforderungen Ihrer Organisation zu bestimmen, welche Konferenzfunktionen Sie bereitstellen sollten.
  
> [!NOTE]
> Wenn Sie Konferenzen bei der Bereitstellung aktivieren, aktivieren Sie automatisch sowohl Web- als auch A/V-Konferenzen. Sie können jedoch bestimmte Features deaktivieren, indem Sie Konferenzrichtlinien konfigurieren, wie zuvor in diesem Thema beschrieben. 
  
- **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn ja, müssen Sie die Konferenzen für Ihren Front-End-Pool mithilfe des Planungstools oder des Topologie-Generators aktivieren. Weitere Informationen finden Sie unter ["Bereitstellen von Konferenzen in Skype for Business Server".](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    Für die Anwendungsfreigabe ist eine höhere Netzwerkbandbreite erforderlich als für die Dokumentzusammenarbeit. Skype for Business Server bietet einen Einschränkungsmechanismus zum Steuern jeder Anwendungsfreigabesitzung. In der Standardeinstellung ist für jede Sitzung 1,5 KB/s festgelegt. Wenn Sie die Anwendungsfreigabe nicht aktivieren, aber die Zusammenarbeit an Dokumenten wünschen, können Sie die Konferenz- und Konferenzrichtlinien aktivieren, um die Anwendungsfreigabe zu deaktivieren. Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter "Verwalten von [Konferenzrichtlinien in Skype for Business Server".](../../manage/conferencing/conferencing-policies.md)
    
    Um Benutzern die Freigabe von PowerPoint-Präsentationen zu ermöglichen, müssen Sie Office Web Apps Server konfigurieren. Weitere Informationen zum Konfigurieren von Office Web Apps Server finden Sie unter "Konfigurieren der Integration [mit Office Web Apps Server in Skype for Business Server".](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **Möchten Sie Audio- und Videokonferenzen aktivieren?**
    
    Wenn ja, müssen Sie die Konferenzen für Ihren Front-End-Pool mithilfe des Planungstools oder des Topologie-Generators aktivieren. Weitere Informationen finden Sie unter ["Bereitstellen von Konferenzen in Skype for Business Server".](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    Audio- und Videokonferenzen erfordern und verwenden mehr Netzwerkbandbreite als Webkonferenzen (einschließlich Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie Audio- und Videokonferenzen nicht aktivieren, aber Webkonferenzen aktivieren möchten, können Sie Konferenzen aktivieren und A/V-Konferenzen mithilfe von Konferenzrichtlinien deaktivieren.
    
    Wenn Sie Audiokonferenzen, aber keine Videokonferenzen aktivieren möchten, können Sie A/V-Konferenzen aktivieren und Konferenzrichtlinien verwenden, um Videokonferenzen zu verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen. 
    
    Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter "Verwalten von [Konferenzrichtlinien in Skype for Business Server".](../../manage/conferencing/conferencing-policies.md)
    
    > [!NOTE]
    > Enterprise-VoIP ist für die Verwendung von A/V-Konferenzen nicht erforderlich. Wenn Sie A/V-Konferenzen aktivieren, können Ihre Benutzer audio zu ihren Konferenzen hinzufügen, wenn sie über Audiogeräte verfügen, auch wenn Sie eine Nebenstellenanlage für Ihre Telefonlösung verwenden. 
  
- **Sollen Benutzer bei Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen können?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.
    
    Einwahlkonferenzen sind eine optionale Funktion, die Sie bei der Bereitstellung von Skype for Business Server-Konferenzen konfigurieren können. Obwohl für Einwahlkonferenzen einige der komponenten verwendet werden, die Enterprise-VoIP verwendet, können Sie Einwahlkonferenzen auch dann bereitstellen, wenn Sie keine Enterprise-VoIP. Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Weitere Informationen zum Konfigurieren von Einwahlkonferenzen für Unternehmensbenutzer und anonyme Benutzer finden Sie unter "Bereitstellen von Konferenzen [in Skype for Business Server"](../../deploy/deploy-conferencing/deploy-conferencing.md) und "Konfigurieren von Einwahlkonferenzen in Skype for Business [Server".](../../deploy/deploy-conferencing/dial-in-conferencing.md)
    
- **Möchten Sie externen Benutzern mit Skype for Business-Clients die Teilnahme an Konferenzen ermöglichen?**
    
    Indem Sie die externe Teilnahme an Besprechungen zulassen, maximieren Sie Ihre Investition in Skype for Business Server. Externe Benutzer können Folgendes umfassen:
    
  - **Remotebenutzer.** Die eigenen Benutzer Ihrer Organisation, wenn sie außerhalb Ihrer Firewalls arbeiten und laptops oder andere Skype for Business Server-Geräte verwenden.
    
  - **Verbundbenutzer.** Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten, die auch Skype for Business Server ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.
    
  - **Anonyme Benutzer.** Alle anderen externen Benutzer, die von Ihren Benutzern zur Teilnahme an bestimmten Konferenzen eingeladen werden. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.
    
    Wenn Sie externe Benutzer zulassen möchten, müssen Sie Edgeserver bereitstellen. Darüber hinaus können Sie mit bereitgestellten Edgeservern Verbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – erstellen, und Benutzer aus diesen Organisationen können einfacher mit Ihren Benutzern zusammenarbeiten.
    
    Weitere Informationen zum Bereitstellen von Edgeservern finden Sie unter "Planen von Edgeservern und Bereitstellen von Edgeservern". Weitere Informationen zum Aktivieren des externen Zugriffs für Office Web Apps Server finden Sie unter "Konfigurieren der Integration [mit Office Web Apps Server in Skype for Business Server".](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **Möchten Sie die Clients steuern, die an Skype for Business Server-Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal, wenn ein Benutzer auf einen Link klickt, um an einer geplanten Besprechung teil zu nehmen, erkennt Skype for Business Server, ob bereits ein Client auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt wird geöffnet, auf der Links für alternative Clients angezeigt werden. Die Seite für den Besprechungs beitritt enthält immer die Option zur Verwendung von Skype for Business Web App. Zusätzlich zu dieser Option können Sie festlegen, ob Links für Attendee und frühere Versionen von Communicator. 
    

