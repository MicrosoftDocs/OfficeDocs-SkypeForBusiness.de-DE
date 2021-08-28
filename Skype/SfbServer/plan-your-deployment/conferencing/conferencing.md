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
ms.localizationpriority: medium
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über Die Funktionen und Funktionen von Konferenzen in Skype for Business Server zu erfahren.'
ms.openlocfilehash: 90200648c8e370bd0e59f0b6759717cd706b683d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628587"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planen von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über konferenzfeatures und -funktionen in Skype for Business Server zu erfahren.
  
Mithilfe von Konferenzen in Skype for Business Server können Sichten und Online-Konferenzen mit ihrem Skype for Business-Client abhalten, anstatt dass sich alle im selben Raum treffen. Besprechungsteilnehmer können mit ihrem Skype for Business Client eine Verbindung zu einer Besprechung herstellen, um eine vollständige Audio- und Videoerfahrung zu erhalten, oder sich per Telefon in eine Konferenz einwählen. Konferenzen unterstützen auch Chat, Desktop- und Anwendungsfreigabe sowie interaktive Whiteboards.
  
Dieses Thema umfasst die folgenden Abschnitte:
  
- Konferenzfunktionen und -funktionen
    
- Konferenzkomponenten
    
- Konferenzrichtlinien
    
- Unterstützung für große Besprechungen
    
- Ermitteln der Anforderungen Ihrer Organisation
    
## <a name="conferencing-features-and-capabilities"></a>Konferenzfunktionen und -funktionen

In Skype for Business Server stehen vier Arten von Konferenzen zur Verfügung: Webkonferenzen, Audio- und Videokonferenzen (A/V), Einwahlkonferenzen und Chatkonferenzen. 
  
Sie können je nach Ihren Anforderungen alle Konferenztypen aktivieren oder nur einen Typ verwenden. Sie können beispielsweise alle Typen aktivieren, einschließlich Einwahlkonferenzen, damit Benutzer, die nicht an einer Konferenz mit einem Skype for Business-Client teilnehmen können, sich über ein Telefon an der Besprechungsaudio anmelden und daran teilnehmen können. Wenn Sie Skype for Business Server bereitstellen, werden die Chatkonferenzfunktionen automatisch bereitgestellt. Sie geben mithilfe des Topologie-Generators an, ob Web-, A/V- und Einwahlkonferenzen bereitgestellt werden sollen. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md) 
  
In den folgenden Unterabschnitten werden die Features und Funktionen der einzelnen Konferenztypen beschrieben.
  
### <a name="web-conferencing"></a>Webkonferenzen

Webkonferenzen ermöglichen Besprechungsteilnehmern die Zusammenarbeit an Dokumenten, die während der Besprechung freigegeben wurden, und dem Besprechungsreferenten das Freigeben von Anwendungen über den Skype for Business-Client. Webkonferenzen bieten die folgenden Features: 
  
- **Whiteboard und Anmerkungen.** Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Das Whiteboardfeature verbessert die Zusammenarbeit, da alle Besprechungsteilnehmer Ideen diskutieren und entwickeln können, Notizen machen können usw.
    
- **Polling.** Das Abfragefeature verbessert die Zusammenarbeit, indem referenten schnell die Einstellungen der Teilnehmer ermitteln können. In Onlinebesprechungen und -unterhaltungen können Referenten über Abrufe anonyme Antworten von Teilnehmern einholen. Alle Referenten können die Ergebnisse sehen und sie für alle Teilnehmer ausblenden oder anzeigen.
    
- **Anwendungsfreigabe und Desktopfreigabe.** Während einer Konferenz kann der Besprechungsreferent den gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Abgesehen davon, dass nur der Inhalt angezeigt wird, können andere Teilnehmer an der Konferenz die Steuerung des Bildschirms des Referenten anfordern und mit der Berechtigung mit dem Inhalt interagieren (einschließlich Bildlauf und Bearbeitung). Besprechungsteilnehmer können auch als Referenten übernehmen und mit der Freigabe von Inhalten während der Besprechung beginnen.
    
- **PowerPoint Teilens.** Ermöglicht Benutzern das Freigeben PowerPoint Präsentationen in der Besprechung über einen Office Web Apps-Server, der Folgendes ermöglicht:
    
  - Anzeigen in hoher Auflösung und Unterstützung für PowerPoint Funktionen, z. B. Animationen, Folienübergänge und eingebettetes Video.
    
  - Mobile Geräte können auf diese Präsentationen zugreifen.
    
  - Benutzer mit den entsprechenden Berechtigungen können unabhängig von der Präsentation selbst einen Bildlauf durch eine PowerPoint Präsentation durchführen. Während Ken beispielsweise seine Bildschirmpräsentation präsentiert, kann Heidi jede gewünschte Folie betrachten, ohne kens Präsentation zu beeinträchtigen.
    
### <a name="audio-and-video-conferencing"></a>Audio- und Videokonferenzen

Audio- und Videokonferenzen ermöglichen Audio und Video in der Besprechung. Mit Audio können Die Teilnehmer miteinander sprechen, als bef?nen sie sich im selben Raum befinden. Video ermöglicht die Videoanzeige im Skype for Business-Client aller Teilnehmer oder Referenten, die an der Besprechung teilnehmen, mit einer Web-Cam oder einem Konferenzgerät, das Video unterstützt.
  
 Skype for Business Server bietet verschiedene Features, die Benutzer zum Konfigurieren der Audiokonferenzumgebung für den Benutzer verwenden können, einschließlich der folgenden:
  
- **Zielgruppe stummschalten.** Der Referent kann diese Einstellung verwenden, um alle Audioteilnehmer in der Konferenz stumm zu schalten und die Konferenz in einen Zustand zu versetzen, in dem Nicht-Referenten die Stummschaltung selbst nicht aufheben können.
    
- **Ankündigungen beim Ein- und Verlassen von Konferenzen.** Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten diese Einstellung verwenden, um Ansagen zum Ein- und Ausschalten zu aktivieren oder zu beenden, um Ablenkungen während der Konferenz zu minimieren.
    
- **Hinzufügen eines Benutzers durch Ausgehende Anrufe.** Referenten und Teilnehmer, denen die Berechtigung erteilt wurde, können pstn-Nummern zu den Konferenzen hinzufügen und die Konferenz-Auswahl für diese Nummern durchführen lassen.
    
  Skype for Business Server bietet verschiedene Features, mit denen Benutzer die Videokonferenzumgebung für den Benutzer konfigurieren können, einschließlich der folgenden:
  
- **Katalogansicht.** In Videokonferenzen mit mehr als zwei Personen sehen Benutzer automatisch jeden in der Konferenz. Wenn die Konferenz mehr als fünf Teilnehmer hat, wird das Video der aktivsten Teilnehmer in der obersten Zeile angezeigt, und nur das Foto wird für die anderen Teilnehmer angezeigt. Video mit mehreren Teilnehmern ist standardmäßig aktiviert.
    
- **Panoramavideo.** Wenn ein RoundTable-Videokonferenzgerät im Konferenzraum installiert ist, bietet dieses Feature eine vollständige 360-Grad-Ansicht des Konferenzraums. Der Panoramavideostreifen ist nur für RoundTable-Geräte verfügbar.
    
- **Nur-Referenten-Videomodus.** Referenten können die Besprechung so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dies verhindert Ablenkungen bei großen Besprechungen, wenn mehrere Videostreams verfügbar sind und verschiedene Quellen gesperrt werden. Dieser Modus gilt auch für Videos, die von RoundTable-Geräten aufgenommen und bereitgestellt werden.
    
- **Video-Blickpunkt.** Referenten können die Besprechung so konfigurieren, dass nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, von den anderen Teilnehmern der Konferenz angezeigt wird. Dieser Modus gilt auch für Videos, die von RoundTable-Geräten für Panoramavideos aufgenommen und bereitgestellt werden.
    
### <a name="dial-in-conferencing"></a>Einwahlkonferenz

Einwahlkonferenzen ermöglichen Es Besprechungsteilnehmern, am Audioteil einer Besprechung teilzunehmen, indem sie sich von einem Telefon aus in die Besprechung einwählen. Einwahlkonferenzen sind ein Teil von Audiokonferenzen und erfordern zusätzliche Konfiguration. Weitere Informationen zu Einwahlkonferenzen finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](dial-in-conferencing.md) und Konfigurieren von [Einwahlkonferenzen in Skype for Business Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md) 
  
### <a name="instant-messaging-conferencing"></a>Chatkonferenzen

Chatkonferenzen ermöglichen mehr als zwei Parteien die Kommunikation in einer einzigen Chatsitzung. Ausführliche Informationen zu Chatkonferenzen finden Sie unter [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Konferenzkomponenten

Zu den Komponenten, die Konferenzfunktionen unterstützen, gehören folgende:
  
- **Anwendungsdienst.** Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications(UC)-Anwendungen. Einwahlkonferenzen verwenden zwei UC-Anwendungen, die den Anwendungsdienst erfordern: Konferenzzentrale und Konferenzankündigung. Der Anwendungsdienst wird standardmäßig auf jedem Front-End-Server in einem Front-End-Pool installiert und aktiviert. Es wird auch auf jedem Standard Edition Server installiert, um Einwahlkonferenzen zu aktivieren und zu konfigurieren.
    
- **Konferenzzentralenanwendung.** Die Konferenzzentralenanwendung ist eine Unified Communications-Anwendung, die PSTN-Anrufe (Public Switched Telephone Network) akzeptiert, Eingabeaufforderungen wiedergibt und die Anrufe an einer A/V-Konferenz teilnimmt. Die Konferenzzentralenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Einwahlkonferenzen aktivieren.
    
- **Konferenzankündigungsanwendung.** Die Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung, die Töne und Eingabeaufforderungen an PSTN-Teilnehmer bei bestimmten Aktionen abgibt, z. B. wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, die Teilnehmer stummgeschaltet oder unveränderlich sind, jemand in den Konferenzlobby eintritt oder die Konferenz gesperrt oder entsperrt ist. Konferenzankündigungsanwendung unterstützt auch DTMF-Befehle (Dual-Tone Multi-Frequency) über die Wähltastatur des Telefons. Die Konferenzankündigungsanwendung wird automatisch installiert und standardmäßig aktiviert, wenn Sie Einwahlkonferenzen aktivieren.
    
- **Einwahlkonferenzen Einstellungen Seite.** Auf der Seite "Einwahlkonferenzen Einstellungen" werden Einwahlnummern für Konferenzen mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in Konferenzen angezeigt und die Verwaltung der persönlichen Identifikationsnummer (PIN) und der zugewiesenen Konferenzinformationen unterstützt. Die Seite "Einwahlkonferenzen Einstellungen" wird automatisch als Teil der Webdienste installiert.
    
- **Vermittlungsserver und PSTN-Gateway.** Einwahlkonferenzen erfordern, dass ein Vermittlungsserver Die Signalisierung (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway übersetzt, und ein PSTN-Gateway zum Übersetzen von Signalen und Medien zwischen dem Vermittlungsserver und dem PSTN-Gateway. Für Einwahlkonferenzen müssen Sie mindestens einen Vermittlungsserver und mindestens einen der folgenden Optionen bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Internettelefoniedienstanbieter, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
  > [!NOTE]
  > Wenn Sie auch Enterprise-VoIP bereitstellen, sind Vermittlungsserver und PSTN-Gateways Teil der Enterprise-VoIP Bereitstellung. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens einen Vermittlungsserver und mindestens ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen SBC für Einwahlkonferenzen bereitstellen. 
  
- **Dateispeicher.** Der Dateispeicher wird für Audiodateien mit aufgezeichnetem Namen verwendet. Datei Store ist eine Standardkomponente in jeder Enterprise Edition oder Standard Edition Bereitstellung.
    
- **Benutzerspeicher.** Der Benutzerspeicher wird verwendet, um Benutzer-Skype for Business Server PINs zu speichern. PINs werden mit Hashing versehen. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition oder Standard Edition Bereitstellung.
    
- **Office Web Apps Server.** Um Webkonferenzfunktionen verwenden zu können, müssen Administratoren Office Web Apps-Server installieren und Skype for Business Server für die Kommunikation mit Office Web Apps Server konfigurieren.
    
## <a name="conferencing-policies"></a>Konferenzrichtlinien

Um die Richtlinien Ihrer Organisation durchzusetzen und die Bandbreitennutzung zu steuern, können Sie Richtlinien für die Arten von Besprechungen festlegen, die Benutzer organisieren können. Sie können eine Vielzahl von Konferenzrichtlinien definieren und sie einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Ausführliche Informationen zum Festlegen von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server.](../../manage/conferencing/conferencing-policies.md) Ausführliche Informationen zur Bandbreitenverwaltung finden Sie unter [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Unterstützung für große Besprechungen

Die Größe von Besprechungen, die Skype for Business Server unterstützen können, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden:
  
- In einem freigegebenen Pool können Skype for Business Server Besprechungen mit bis zu 250 Benutzern hosten. Ein freigegebener Pool ist ein Pool, der alle Skype for Business Server Workloads hostet, einschließlich Chatnachrichten und Anwesenheitsinformationen, Konferenzen und Enterprise-VoIP. 
    
- In einem dedizierten Pool können Skype for Business Server Besprechungen mit bis zu 1.000 Teilnehmern über Web- und Audio-/Videokonferenzen (A/V) unterstützen, einschließlich der Freigabe PowerPoint Präsentationen. Für diese Unterstützung ist ein dedizierter Pool erforderlich, der für die Unterstützung großer Besprechungen konfiguriert und so verwaltet wird, dass nur eine einzelne große Besprechung gleichzeitig gehostet wird. 
    
Weitere Informationen zum Verwalten großer Besprechungen finden Sie unter [Planen großer Besprechungen in Skype for Business Server.](large-meetings.md)
  
Wenn Ihre Organisation größere Besprechungsfunktionen erfordert, sollten Sie erwägen, eine Hybridumgebung zu implementieren, die Skype-Besprechung Broadcast nutzt, einen Onlinedienst, der Teil Microsoft 365 und Office 365 ist. Skype-Besprechung Broadcast ermöglicht Benutzern das Hosten und Übertragen von Besprechungen an ein großes Onlinepublikum von bis zu 10.000 Teilnehmern. Die Verwendung von Skype-Besprechung Broadcast erfordert, dass Skype for Business Server bereits in einem Hybridsetup mit einer Produktions-Microsoft 365 oder Office 365 Organisation konfiguriert werden. Für alle Benutzer muss ein Onlinemandant als Voraussetzung eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die Skype-Besprechung Broadcast nutzen kann, lesen [Sie "Konfigurieren Ihrer lokalen Bereitstellung für Skype-Besprechung Broadcast".](../../deploy/configure-skype-meeting-broadcast.md)
  
## <a name="determine-your-organizations-needs"></a>Ermitteln der Anforderungen Ihrer Organisation

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die folgende Liste führt Sie durch den Konferenzplanungsprozess, um zu bestimmen, welche Funktionen von Konferenzen Sie basierend auf den Anforderungen Ihrer Organisation bereitstellen sollten.
  
> [!NOTE]
> Wenn Sie Konferenzen bei der Bereitstellung aktivieren, aktivieren Sie automatisch sowohl Web- als auch A/V-Konferenzen. Sie können jedoch bestimmte Features deaktivieren, indem Sie Konferenzrichtlinien wie zuvor in diesem Thema beschrieben konfigurieren. 
  
- **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn ja, müssen Sie die Konferenzfunktion für Ihren Front-End-Pool mithilfe des Planungstool oder mithilfe des Topologie-Generators aktivieren. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    Für die Anwendungsfreigabe ist eine höhere Netzwerkbandbreite erforderlich als für die Dokumentzusammenarbeit. Skype for Business Server bietet einen Einschränkungsmechanismus, um jede Anwendungsfreigabesitzung zu steuern. In der Standardeinstellung ist für jede Sitzung 1,5 KB/s festgelegt. Wenn Sie die Anwendungsfreigabe nicht aktivieren möchten, aber die Dokumentzusammenarbeit möchten, können Sie Konferenzen aktivieren und die Anwendungsfreigabe mithilfe von Konferenzrichtlinien deaktivieren. Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
    
    Damit Benutzer PowerPoint Präsentationen freigeben können, müssen Sie Office Web Apps-Server konfigurieren. Ausführliche Informationen zum Konfigurieren Office Web Apps-Servers finden Sie unter Konfigurieren der [Integration mit Office Web Apps Server in Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **Möchten Sie Audio- und Videokonferenzen aktivieren?**
    
    Wenn ja, müssen Sie die Konferenzfunktion für Ihren Front-End-Pool mithilfe des Planungstool oder mithilfe des Topologie-Generators aktivieren. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    Audio- und Videokonferenzen erfordern und nutzen mehr Netzwerkbandbreite als Webkonferenzen (einschließlich Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie Audio- und Videokonferenzen nicht aktivieren möchten, aber Webkonferenzen aktivieren möchten, können Sie Konferenzen aktivieren und Konferenzrichtlinien verwenden, um A/V-Konferenzen zu deaktivieren.
    
    Wenn Sie Audiokonferenzen, aber keine Videokonferenzen aktivieren möchten, können Sie A/V-Konferenzen aktivieren und Konferenzrichtlinien verwenden, um Videokonferenzen zu verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen. 
    
    Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
    
    > [!NOTE]
    > Enterprise-VoIP ist für die Verwendung von A/V-Konferenzen nicht erforderlich. Wenn Sie A/V-Konferenzen aktivieren, können Ihre Benutzer ihren Konferenzen Audio hinzufügen, wenn sie über Audiogeräte verfügen, auch wenn Sie eine Nebenstellenanlage für Ihre Telefonlösung verwenden. 
  
- **Sollen Benutzer bei Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen können?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.
    
    Einwahlkonferenzen sind ein optionales Feature, das Sie bei der Bereitstellung Skype for Business Server Konferenzen konfigurieren können. Obwohl Einwahlkonferenzen einige der gleichen Komponenten verwenden, die Enterprise-VoIP verwendet, können Sie Einwahlkonferenzen auch dann bereitstellen, wenn Sie Enterprise-VoIP nicht bereitstellen. Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Weitere Informationen zum Konfigurieren von Einwahlkonferenzen für Unternehmensbenutzer und anonyme Benutzer finden Sie unter [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) und Konfigurieren von [Einwahlkonferenzen in Skype for Business Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)
    
- **Möchten Sie externen Benutzern mit Skype for Business Clients die Teilnahme an Konferenzen ermöglichen?**
    
    Indem Sie die externe Teilnahme an Besprechungen zulassen, maximieren Sie Ihre Investition in Skype for Business Server. Externe Benutzer können Folgendes umfassen:
    
  - **Remotebenutzer.** Die eigenen Benutzer Ihrer Organisation, wenn sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere Skype for Business Server Geräte verwenden.
    
  - **Verbundbenutzer.** Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten, die auch Skype for Business Server ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.
    
  - **Anonyme Benutzer.** Alle anderen externen Benutzer, die von Ihren Benutzern zur Teilnahme an bestimmten Konferenzen eingeladen werden. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.
    
    Wenn Sie externe Benutzer zulassen möchten, müssen Sie Edgeserver bereitstellen. Darüber hinaus können Sie mit bereitgestellten Edgeservern Verbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – erstellen, und Benutzer aus diesen Organisationen können einfacher mit Ihren Benutzern zusammenarbeiten.
    
    Ausführliche Informationen zum Bereitstellen von Edgeservern finden Sie unter "Planen von Edgeservern und Bereitstellen von Edgeservern". Ausführliche Informationen zum Aktivieren des externen Zugriffs für Office Web Apps Server finden Sie unter Konfigurieren der [Integration mit Office Web Apps Server in Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **Möchten Sie die Clients steuern, die an Skype for Business Server Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal, wenn ein Benutzer auf einen Link klickt, um an einer geplanten Besprechung teilzunehmen, erkennt Skype for Business Server, ob ein Client bereits auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt wird geöffnet, auf der Links für alternative Clients angezeigt werden. Die Besprechungsbeitrittsseite enthält immer die Option, Skype for Business-Web-App zu verwenden. Zusätzlich zu dieser Option können Sie festlegen, ob Links für Teilnehmer und frühere Versionen von Communicator eingeschlossen werden sollen. 
    

