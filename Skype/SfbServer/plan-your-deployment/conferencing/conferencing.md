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
description: 'Zusammenfassung: in diesem Thema erfahren Sie mehr über Konferenzfeatures und Funktionen in Skype for Business Server.'
ms.openlocfilehash: feaa3dbbe3d05b09e3490ef160ceb21816ae7d5e
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780424"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planen von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über Konferenzfeatures und Funktionen in Skype for Business Server.
  
Konferenzen in Skype for Business Server ermöglichen es Benutzern, Konferenzen online mit Ihrem Skype for Business-Client zu treffen und zu halten, anstatt sich alle im selben Raum zu versammeln. Besprechungsteilnehmer können mit Ihrem Skype for Business-Client eine Verbindung zu einer Besprechung herstellen, um eine vollständige Audio-und Video Umgebung zu erhalten oder sich über ein Telefon in eine Konferenz einzuwählen. Konferenzen unterstützen auch Chatnachrichten, Desktop-und Anwendungsfreigabe und interaktive White Boards.
  
Dieses Thema enthält die folgenden Abschnitte:
  
- Konferenzfeatures und-Funktionen
    
- Konferenzkomponenten
    
- Konferenzrichtlinien
    
- Unterstützung für große Besprechungen
    
- Bestimmen der Anforderungen Ihrer Organisation
    
## <a name="conferencing-features-and-capabilities"></a>Konferenzfeatures und-Funktionen

In Skype for Business Server stehen vier Konferenztypen zur Verfügung: Webkonferenz-, Audio-und Videokonferenzen (A/V), Einwahlkonferenzen und Chat Konferenzen (Sofortnachrichten). 
  
Sie können auswählen, ob alle Konferenztypen aktiviert werden sollen, oder Sie können je nach Bedarf nur einen Typ verwenden. Sie können beispielsweise alle Typen, einschließlich Einwahlkonferenzen, aktivieren, um Benutzern, die nicht in der Lage sind, an einer Konferenz teilzunehmen, einen Skype for Business-Client zu ermöglichen, sich über ein Telefon anzumelden und an der Audiokonferenz teilzunehmen. Wenn Sie Skype for Business Server bereitstellen, werden Chat Konferenzfunktionen automatisch bereitgestellt; Sie können mithilfe des Topologie-Generators angeben, ob Sie die Webparts, A/V-und Einwahlkonferenzen bereitstellen möchten. Weitere Informationen finden Sie unter [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
In den folgenden Unterabschnitten werden die Features und Funktionen der einzelnen Konferenztypen beschrieben.
  
### <a name="web-conferencing"></a>Webkonferenzen

Mit Webkonferenzen können Besprechungsteilnehmer an Dokumenten zusammenarbeiten, die während der Besprechung freigegeben wurden, und für den besprechungsreferenten, um Anwendungen über den Skype for Business-Client freizugeben. Webkonferenzen bieten die folgenden Features: 
  
- **Whiteboard und Anmerkungen.** Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Das Whiteboardfeature verbessert die Zusammenarbeit, da alle Besprechungsteilnehmer Ideen diskutieren und entwickeln können, Notizen machen können usw.
    
- **Abruf.** Das Polling-Feature verbessert die Zusammenarbeit, indem Referenten die Einstellungen der Teilnehmer schnell bestimmen können. In Onlinebesprechungen und -unterhaltungen können Referenten über Abrufe anonyme Antworten von Teilnehmern einholen. Alle Referenten können die Ergebnisse sehen und sie für alle Teilnehmer ausblenden oder anzeigen.
    
- **Anwendungsfreigabe und Desktop Freigabe.** Während einer Konferenz kann der Besprechungs Referent den gesamten Desktop, eine einzelne Anwendung oder einzelne Monitore in einer Umgebung mit mehreren Monitoren freigeben. Neben dem Anzeigen des Inhalts können andere Teilnehmer an der Konferenz die Steuerung des Bildschirms des Referenten anfordern und mit der Berechtigung mit dem Inhalt interagieren (einschließlich Scrollen und bearbeiten). Besprechungsteilnehmer können auch als Referenten übernehmen und die Freigabe von Inhalten während der Besprechung starten.
    
- **PowerPoint-Freigabe.** Ermöglicht Benutzern das Freigeben von PowerPoint-Präsentationen in der Besprechung über einen Office-webapps-Server, was Folgendes ermöglicht:
    
  - Hochauflösende Displays und Unterstützung für PowerPoint-Funktionen wie Animationen, Folienübergänge und eingebettete Videos.
    
  - Mobile Geräte können auf diese Präsentationen zugreifen.
    
  - Benutzer mit den entsprechenden Berechtigungen können unabhängig von der Präsentation selbst einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während Ken beispielsweise seine Bildschirmpräsentation präsentiert, kann Heidi jede beliebige Folie anzeigen, ohne die Darstellung von Ken zu beeinflussen.
    
### <a name="audio-and-video-conferencing"></a>Audio-und Videokonferenzen

Audio-und Videokonferenzen ermöglichen Audio-und Videokonferenzen in der Besprechung. Mit Audio können Teilnehmer miteinander kommunizieren, als wären Sie im selben Raum. Video zeigt die Videoanzeige im Skype for Business-Client aller Teilnehmer oder Referenten an, die an der Besprechung teilnehmen, mit einer Webcam oder einem Konferenzgerät, das Video unterstützt.
  
 Skype for Business Server bietet verschiedene Features, mit denen Benutzer die Audiokonferenz für den Benutzer konfigurieren können, einschließlich der folgenden:
  
- **Benutzergruppe stumm.** Der Referent kann diese Einstellung verwenden, um alle Audioteiler in der Konferenz stummzuschalten und die Konferenz in einen Zustand zu versetzen, in dem nicht-Referenten sich selbst nicht entmuten können.
    
- **Konferenz Eintrag/Exit-Ankündigungen.** Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten diese Einstellung verwenden, um die Eingabe-und Beendigungs Ankündigungen zu aktivieren oder zu deaktivieren, um Ablenkungen während einer Konferenz zu minimieren.
    
- **Hinzufügen eines Benutzers, indem Sie sich auswählen.** Referenten und Teilnehmer, denen die Berechtigung erteilt wurde, können PSTN-Nummern zu den Konferenzen hinzufügen und die Konferenz für diese Nummern wählen.
    
  Skype for Business Server bietet verschiedene Features, mit denen Benutzer die Videokonferenzumgebung für den Benutzer konfigurieren können, einschließlich der folgenden:
  
- **Galerieansicht.** Bei Videokonferenzen mit mehr als zwei Personen sehen die Benutzer automatisch alle Mitglieder der Konferenz. Wenn die Konferenz über mehr als fünf Teilnehmer verfügt, wird das Video der aktivsten Teilnehmer in der obersten Zeile angezeigt, und für die anderen Teilnehmer wird nur das Foto angezeigt. Video mit mehreren Teilern ist standardmäßig aktiviert.
    
- **Panorama Video.** Wenn ein RoundTable-Videokonferenz Gerät im Konferenzraum installiert ist, bietet dieses Feature eine vollständige 360 Grad Ansicht des Konferenzraums. Der Panorama-Video Strip ist nur für RoundTable-Geräte verfügbar.
    
- **Videomodus für Referenten.** Referenten können die Besprechung so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dadurch werden Ablenkungen in großen Besprechungen verhindert, wenn mehrere Videostreams verfügbar sind und verschiedene Quellen gesperrt werden. Dieser Modus gilt auch für von RoundTable-Geräten erfasste und bereitgestellte Videos.
    
- **Video Spotlight.** Referenten können die Besprechung so konfigurieren, dass nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, von den anderen Teilnehmern in der Konferenz angezeigt wird. Dieser Modus gilt auch für Videos, die von RoundTable-Geräten für Panorama Video erfasst und bereitgestellt werden.
    
### <a name="dial-in-conferencing"></a>Einwahlkonferenz

Mit Einwahlkonferenzen können Besprechungsteilnehmer am Audioteil einer Besprechung teilnehmen, indem Sie sich über ein Telefon in die Besprechung einwählen. Einwahlkonferenzen sind ein Teil von Audiokonferenzen und erfordern zusätzliche Konfiguration. Weitere Informationen zu Einwahlkonferenzen finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](dial-in-conferencing.md) und Konfigurieren von [Einwahlkonferenzen in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Instant Messaging-Konferenzen

Chat Konferenzen (Instant Messaging) ermöglichen es mehr als zwei Parteien, in einer einzelnen Chatsitzung zu kommunizieren. Ausführliche Informationen zu Chat Konferenzen finden Sie unter [Plan for Instant Messaging and Presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Konferenzkomponenten

Zu den Komponenten, die Konferenzfunktionen unterstützen, gehören folgende:
  
- **Anwendungsdienst.** Das Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von UC-Anwendungen (Unified Communications). Bei Einwahlkonferenzen werden zwei UC-Anwendungen verwendet, für die die Anwendungsdienst erforderlich ist: Konferenzzentrale und Konferenz Ansage. Die Anwendungsdienst ist auf jeder Front-End-Server in einem Front-End-Pool installiert und wird standardmäßig aktiviert. Sie wird auch auf jeder Standard Edition-Server installiert, um Einwahlkonferenzen zu aktivieren und zu konfigurieren.
    
- **Konferenzzentrale.** Bei der Konferenzzentrale handelt es sich um eine Unified Communications-Anwendung, die PSTN-Anrufe (Public Switched Telephone Network) akzeptiert, Ansagen abgibt und die Anrufe an eine a/V-Konferenz anschließt. Das Konferenzzentrale wird standardmäßig installiert und aktiviert, wenn Sie Einwahlkonferenzen aktivieren.
    
- **Konferenzankündigungsanwendung.** Das Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung, die für bestimmte Aktionen Töne und Ansagen an PSTN-Teilnehmer abgibt, beispielsweise wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, die Teilnehmer stumm geschaltet oder stumm geschaltet werden, jemand in die Konferenz Lobby wechselt oder die Konferenz gesperrt oder entsperrt ist. Konferenzankündigungsanwendung unterstützt auch DTMF-Befehle (Dual-Tone Multi-Frequency) über die Telefontastatur. Das Konferenzankündigungsanwendung wird automatisch installiert und standardmäßig aktiviert, wenn Sie Einwahlkonferenzen aktivieren.
    
- **Seite "Einstellungen für Einwahlkonferenzen".** Das Seite "Einstellungen für Einwahlkonferenzen" zeigt Konferenzeinwahl Nummern mit den verfügbaren Sprachen an, zugewiesene Konferenz Informationen (also für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung von persönlicher Identifikationsnummer (PIN) und zugewiesener Konferenz Informationen. Das Seite "Einstellungen für Einwahlkonferenzen" wird automatisch als Teil von Webdienste installiert.
    
- **Vermittlungsserver und PSTN-Gateway.** Einwahlkonferenzen erfordern eine Vermittlungsserver zum Übersetzen von Signalen (und Medien in einigen Konfigurationen) zwischen Skype for Business Server und dem PSTN-Gateway sowie ein PSTN-Gateway zum Übersetzen von Signal-und Mediendaten zwischen der Vermittlungsserver und dem PSTN-Gateway. Bei Einwahlkonferenzen müssen Sie mindestens eine Vermittlungsserver und mindestens eine der folgenden bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Internet Telefonie-Dienstanbieter, zu dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
  > [!NOTE]
  > Wenn Sie auch Enterprise-VoIP bereitstellen, sind Vermittlungsserver-und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens eine Vermittlungsserver und mindestens ein PSTN-Gateway, eine IP-PBX-Anlage oder einen SBC für Einwahlkonferenzen bereitstellen. 
  
- **Dateispeicher.** Dateispeicher wird für aufgezeichnete Namen-Audiodateien verwendet. Dateispeicher ist eine Standardkomponente in jeder Enterprise Edition-oder Standard Edition-Bereitstellung.
    
- **Benutzerspeicher.** Der Benutzerspeicher dient zum Speichern von Benutzer Skype for Business Server Pins. Pins werden gehasht. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition-oder Standard Edition-Bereitstellung.
    
- **Office Web Apps Server.** Um Webkonferenzfunktionen nutzen zu können, müssen Administratoren Office-webapps Server installieren und Skype for Business Server für die Kommunikation mit Office webapps Server konfigurieren.
    
## <a name="conferencing-policies"></a>Konferenzrichtlinien

Um die Richtlinien Ihrer Organisation durchzusetzen und die Bandbreitennutzung zu steuern, können Sie Richtlinien für die Besprechungstypen festlegen, die Benutzer organisieren können. Sie können eine Vielzahl von Konferenzrichtlinien definieren und Sie einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Ausführliche Informationen zum Festlegen von Konferenzrichtlinien finden Sie unter [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Ausführliche Informationen zur Bandbreitenverwaltung finden Sie unter [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Unterstützung für große Besprechungen

Die Größe der Besprechungen, die Skype for Business Server unterstützenkann, hängt davon ab, ob Konferenzen in einem freigegebenen oder dedizierten Pool gehostet werden:
  
- In einem gemeinsamen Pool können Skype for Business Server Besprechungen mit bis zu 250 Benutzern hosten. Ein freigegebener Pool ist ein Pool, der alle Skype for Business Server Arbeitslasten wie Instant Messaging (Sofortnachrichten) und Anwesenheit, Konferenzen und Enterprise-VoIP hostet. 
    
- In einem dedizierten Pool können Skype for Business Server Besprechungen mit bis zu 1000 Teilnehmern mithilfe von Netz-und Audio/Video-Konferenzen (a/V) unterstützen, einschließlich der Freigabe von PowerPoint-Präsentationen. Diese Unterstützung erfordert einen dedizierten Pool, der für die Unterstützung großer Besprechungen konfiguriert und so verwaltet wird, dass gleichzeitig nur eine einzige große Besprechung gehostet wird. 
    
Weitere Informationen zum Verwalten von großen Besprechungen finden Sie unter [Plan for Large Meetings in Skype for Business Server](large-meetings.md).
  
Wenn Ihre Organisation größere Besprechungsfunktionen erfordert, sollten Sie die Implementierung einer Hybridumgebung in Betracht ziehen, die Skype-Live Konferenz, einen Onlinedienst, der Teil Office 365 ist, nutzt. Skype-Live Konferenz ermöglicht Benutzern das Hosten und übertragen von Besprechungen mit großen Online-Zielgruppen von bis zu 10.000 Teilnehmern. Die Verwendung von Skype-Live Konferenz erfordert, dass Skype for Business Server bereits in einem Hybrid-Setup mit einer Produktions Office 365 Organisation konfiguriert werden. Für alle Benutzer muss ein Online Mandant als Voraussetzung eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die Skype-Live Konferenz nutzen kann, finden Sie weitere Informationen unter [configure your on-premises Deployment for Skype Live Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Bestimmen der Anforderungen Ihrer Organisation

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die folgende Liste führt Sie durch den Konferenz Planungsprozess, um zu ermitteln, welche Features von Konferenzen Sie basierend auf den Anforderungen Ihrer Organisation bereitstellen sollten.
  
> [!NOTE]
> Wenn Sie Konferenzen bei der Bereitstellung aktivieren, aktivieren Sie automatisch sowohl eine Webkonferenz als auch A/V-Konferenzen. Sie können jedoch bestimmte Features deaktivieren, indem Sie wie zuvor in diesem Thema beschrieben Konferenzrichtlinien konfigurieren. 
  
- **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn dies der Fall ist, müssen Sie die Konferenz für Ihre Front-End-Pool mithilfe des Planungstools oder mithilfe des Topologie-Generators aktivieren. Weitere Informationen finden Sie unter [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Für die Anwendungsfreigabe ist eine höhere Netzwerkbandbreite erforderlich als für die Dokumentzusammenarbeit. Skype for Business Server stellt einen Einschränkungsmechanismus zum Steuern der einzelnen Anwendungsfreigabesitzungen bereit. In der Standardeinstellung ist für jede Sitzung 1,5 KB/s festgelegt. Wenn Sie die Anwendungsfreigabe nicht aktivieren möchten, aber die Zusammenarbeit mit Dokumenten wünschen, können Sie die Konferenzfunktionen aktivieren und Konferenzrichtlinien verwenden, um die Anwendungsfreigabe zu deaktivieren. Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Um Benutzern die Freigabe von PowerPoint-Präsentationen zu ermöglichen, müssen Sie Office-webapps-Server konfigurieren. Ausführliche Informationen zum Konfigurieren von Office-webapps Server finden Sie unter [configure Integration with Office webapps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Möchten Sie Audio-und Videokonferenzen aktivieren?**
    
    Wenn dies der Fall ist, müssen Sie die Konferenz für Ihre Front-End-Pool mithilfe des Planungstools oder mithilfe des Topologie-Generators aktivieren. Weitere Informationen finden Sie unter [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Audio-und Videokonferenzen erfordern und verwenden mehr Netzwerkbandbreite als Webkonferenzen (einschließlich der Zusammenarbeit von Dokumenten und der Anwendungsfreigabe). Wenn Sie keine Audio-und Videokonferenzen aktivieren möchten, aber Webkonferenzen aktivieren möchten, können Sie Konferenzen aktivieren und Konferenzrichtlinien verwenden, um A/V-Konferenzen zu deaktivieren.
    
    Wenn Sie Audiokonferenzen, aber keine Videokonferenzen aktivieren möchten, können Sie A/V-Konferenzen aktivieren und Konferenzrichtlinien verwenden, um Videokonferenzen zu verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen. 
    
    Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Enterprise-VoIP ist für die Verwendung von A/V-Konferenzen nicht erforderlich. Wenn Sie a/V-Konferenzen aktivieren, können Ihre Benutzer Ihrer Konferenzen Audiodaten hinzufügen, wenn Sie über Audiogeräte verfügen, selbst wenn Sie eine Nebenstellenanlage für Ihre Telefonlösung verwenden. 
  
- **Sollen Benutzer bei Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen können?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.
    
    Einwahlkonferenzen sind ein optionales Feature, das Sie bei der Bereitstellung von Skype for Business Server Konferenzen konfigurieren können. Bei Einwahlkonferenzen werden zwar einige der Komponenten verwendet, die Enterprise-VoIP verwendet, aber Sie können Einwahlkonferenzen auch dann bereitstellen, wenn Sie Enterprise-VoIP nicht bereitstellen. Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Weitere Informationen zum Konfigurieren von Einwahlkonferenzen für Unternehmen und anonyme Benutzer finden Sie unter [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) und [configure Dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Möchten Sie, dass externe Benutzer mit Skype for Business Clients an Konferenzen teilnehmen können?**
    
    Indem Sie externe Teilnahme an Besprechungen ermöglichen, maximieren Sie Ihre Investitionen in Skype for Business Server. Externe Benutzer können Folgendes umfassen:
    
  - **Remote Benutzer.** Die eigenen Benutzer Ihrer Organisation, wenn Sie außerhalb Ihrer Firewalls arbeiten und ihre Laptops oder andere Skype for Business Server Geräte verwenden.
    
  - **Verbundbenutzer.** Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten und die auch Skype for Business Server ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.
    
  - **Anonyme Benutzer.** Alle anderen externen Benutzer, die von Ihren Benutzern zur Teilnahme an bestimmten Konferenzen eingeladen werden. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.
    
    Wenn Sie externe Benutzer zulassen möchten, müssen Sie Edgeserver bereitstellen. Außerdem können Sie mit bereitgestellten Edge-Servern Verbundbeziehungen mit anderen Organisationen (beispielsweise Ihren Kunden oder Lieferanten) erstellen, und Benutzer aus diesen Organisationen können mit ihren Benutzern leichter zusammenarbeiten.
    
    Ausführliche Informationen zum Bereitstellen von Edgeserver finden Sie unter Planen von Edge-Servern und Bereitstellen von Edge-Servern. Ausführliche Informationen zum Aktivieren von externem Zugriff für Office-webapps Server finden Sie unter [configure Integration with Office webapps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Möchten Sie die Clients steuern, die an Skype for Business Server Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal, wenn ein Benutzer auf einen Link klickt, um einer geplanten Besprechung beizutreten, erkennt Skype for Business Server, ob ein Client bereits auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt wird geöffnet, auf der Links für alternative Clients angezeigt werden. Die Seite für den besprechungsbeitritt enthält immer die Option zum verwenden Skype for Business-Webanwendung. Zusätzlich zu dieser Option können Sie entscheiden, ob Sie Links für Teilnehmer und frühere Versionen von Communicator einschließen möchten. 
    

