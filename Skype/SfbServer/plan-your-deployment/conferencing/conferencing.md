---
title: Planen von Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zu Live Meeting-Features und Funktionen in Skype für Business Server erhalten.'
ms.openlocfilehash: cefd631f1750d7eaa4404a2fe2ffa8aa91675824
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899435"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planen von Konferenzen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zu Live Meeting-Features und Funktionen in Skype für Business Server erhalten.
  
Konferenzen in Skype für Business Server ermöglicht Benutzern das erfüllen und Konferenzen online mit ihren Skype für Business Client anstelle von jeder zusammen im selben Raum abrufen. Teilnehmer kann eine Verbindung mit einer Besprechung mit ihren Skype für Business-Client für eine vollständige Audio- und Videoerlebnis, oder zu einer Konferenz mit einem Telefon einwählen. Die Konferenzen unterstützen außerdem Funktionen wie Chat, Desktop- und Anwendungsfreigabe sowie interaktive Whiteboards.
  
Dieses Thema enthält die folgenden Abschnitte:
  
- Konferenzfunktionen und -optionen
    
- Konferenzkomponenten
    
- Konferenzrichtlinien
    
- Unterstützung für große Besprechungen
    
- Festlegen der Anforderungen Ihres Unternehmens
    
## <a name="conferencing-features-and-capabilities"></a>Konferenzfunktionen und -optionen

Es stehen vier Typen von Konferenzen in Skype für Business Server: Webkonferenzen, Audio und Video (A / V) Konferenz-, einwahlkonferenzen und Konferenzen Sofortnachrichten (IM). 
  
Ganz nach Ihren Bedürfnissen können Sie entweder alle Konferenzarten aktivieren oder nur einen einzigen Typen nutzen. Beispielsweise können Sie alle Typen, einschließlich einwahlkonferenzen, um Benutzern zu ermöglichen, die nicht in der Lage zur Teilnahme an einer Konferenz mit einer Skype Business Client sind in aufrufen und teilnehmen an den Audiodaten der Besprechung über ein Telefon aktivieren. Wenn Sie Skype für Business Server bereitstellen, sind Instant Messaging-Konferenzfunktionen automatisch bereitgestellt. Sie angeben, ob zum Bereitstellen von Web, A / V und einwahlkonferenzen mit dem Topologie-Generator. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype für Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
In den folgenden Unterabschnitten werden die Funktionen und Optionen der einzelnen Konferenzarten beschrieben.
  
### <a name="web-conferencing"></a>Webkonferenzen

Webkonferenzen kann Besprechungsteilnehmer während der Besprechung und für den Referenten Besprechung Freigeben von Anwendungen durch die Skype für Business Client freigegebene Dokumente zu bearbeiten. Webkonferenzen bieten die folgenden Funktionen: 
  
- **Whiteboard und Anmerkungen.** Ein Whiteboard ist ein leerer Zeichenbereich, der im Rahmen einer Zusammenarbeit eingesetzt wird und auf dem Text, Zeichnungen, und Bilder verwendet werden können. Anmerkungen auf Whiteboards sind für alle Teilnehmer der Besprechung sichtbar. Die Whiteboard-Funktion verbessert die Zusammenarbeit, indem Besprechungsteilnehmer die Möglichkeit erhalten, Ideen zu diskutieren, ein Brainstorming durchzuführen, Notizen zu machen, usw.
    
- **Abrufen.** Die Features kann die Zusammenarbeit verbessert werden, da Referenten schnell die vorstellungen der Teilnehmer ermitteln. Referenten können während onlinebesprechungen und Unterhaltungen Abruf verwenden, um von den Teilnehmern anonym Antworten zu erfassen. Alle Referenten können die Ergebnisse angezeigt und können die Ergebnisse ein- und Ausblenden werden an alle Teilnehmer.
    
- **Anwendungs- und Desktopfreigabe.** Während einer Konferenz kann der Vortragende ihren gesamten Desktop, eine einzelne Anwendung oder einzelnen Überwachungsobjekte in einer Umgebung mit mehreren Bildschirmen freigeben. Andere Teilnehmer der Konferenz können nicht nur die Inhalte sehen, sondern auch die Kontrolle über Ihren Bildschirm anfordern und mit Ihrer Erlaubnis mit den Inhalten interagieren (einschließlich Bildlauf und Bearbeitung). Teilnehmer können außerdem als Referenten die Kontrolle übernehmen und während der Besprechung Inhalte freigeben.
    
- **Power Point-Freigabe.** Benutzer können PowerPoint-Präsentationen in der Besprechung über einen Office Web App-Server freigeben. Daraus ergeben sich folgende Möglichkeiten:
    
  - Hochauflösende Displays und Unterstützung von PowerPoint-Funktionen wie Animationen, Folienübergänge und eingebettete Videos.
    
  - Mobile Geräte erhalten Zugriff auf diese Präsentationen.
    
  - Benutzer mit entsprechenden Berechtigungen können unabhängig von der Präsentation einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während Klaus beispielsweise seine Bildschirmpräsentation ablaufen lässt, kann Helga sich eine beliebige Folie ansehen, ohne Klaus Präsentation zu beeinträchtigen.
    
### <a name="audio-and-video-conferencing"></a>Audio- und Videokonferenzen

Mit der AV-Konferenzfunktion können in der Besprechung Audio- und Videodaten übertragen werden. Über den Audioteil können die Attendants miteinander sprechen, als befänden sie sich in demselben Raum. Video ermöglicht Grafikmodus in der Skype für Business-Client der Teilnehmer und Referenten, die mit einem Web Cam oder für Konferenzen Gerät an der Besprechung teilnehmen, die Video unterstützt.
  
 Skype für Business Server bietet verschiedene Features, die Benutzer verwenden können, so konfigurieren Sie die Audiokonferenz erleben Sie die für den Benutzer, einschließlich der folgenden:
  
- **Stummschaltung der Teilnehmer.** Der Referent kann mit dieser Einstellung alle Audioteilnehmer der Konferenz stummschalten und die Konferenz so in einen Modus versetzen, in dem die Teilnehmer die Stummschaltung nicht selbst aufheben können.
    
- **Konferenzen Entry/Exit Ankündigungen.** Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten über diese Einstellung Ansagen beim Beitreten und Verlassen ein- oder ausschalten, um Ablenkungen während der Konferenz zu vermeiden.
    
- **Hinzufügen eines Benutzers durch Telefonverbindung.** Referenten und Teilnehmer, die Berechtigung erteilt wurden können PSTN-Nummern zu Konferenzen hinzufügen und auf diese Nummern Dial-Out-Konferenz.
    
  Skype für Business Server bietet verschiedene Features, die Benutzer verwenden können, so konfigurieren Sie die Videokonferenzen für den Benutzer, einschließlich der folgenden auftreten:
  
- **Katalogansicht.** In Videokonferenzen, an denen mehr als zwei Personen teilnehmen, sehen die Benutzer automatisch alle Teilnehmer der Konferenz. Wenn die Konferenz mehr als fünf Teilnehmer hat, werden in der ersten Zeile die Videos der aktivsten Teilnehmer angezeigt und für die übrigen Teilnehmer Fotos. Die Videoaushandlung ist standardmäßig aktiviert.
    
- **Panoramavideo.** Wenn im Konferenzraum ein Round Table-Videokonferenzgerät installiert ist, bietet diese Funktion eine vollständige 360-Grad-Ansicht des Konferenzraums. Panoramavideo ist nur mit Round Table verfügbar.
    
- **Modus nur referentenvideo.** Referenten können Besprechungen so konfigurieren, dass nur das Video des Referenten angezeigt wird. Dies verhindert bei großen Besprechungen Ablenkungen, wenn mehrere Videostreams verfügbar und mit verschiedenen Quellen verbunden sind. Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräte aufgenommen und bereitgestellt werden.
    
- **Videospotlight.** Referenten können die Besprechung so konfigurieren, dass die Teilnehmer der Konferenz nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, sehen. Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräten aufgenommen und bereitgestellt werden.
    
### <a name="dial-in-conferencing"></a>Einwahlkonferenzen

Einwahlkonferenzen kann Teilnehmer an der Audiokomponente einer Besprechung beitreten, indem Sie die Besprechung einwählen, über ein Telefon. Einwahlkonferenzen sind ein Unterbereich der Audiokonferenzen und müssen zusätzlich konfiguriert werden. Weitere Informationen zu einwahlkonferenzen finden Sie unter [Planen von einwahlkonferenzen in Skype für Business Server](dial-in-conferencing.md) und [Configure einwahlkonferenzen in Skype für Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Chatkonferenzen

Über die Chatkonferenzfunktion können mehr als zwei Parteien in einer einzigen Sofortnachrichtensitzung miteinander kommunizieren. Ausführliche Informationen zu Instant Messaging-Konferenzen finden Sie unter [Planen von instant messaging und Anwesenheit in Skype für Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Konferenzkomponenten

Zu den Komponenten, die für die Unterstützung der Konferenzfunktionen erforderlich sind, gehören:
  
- **Anwendungsdienst.** Der Anwendungsdienst bietet eine Plattform zum Bereitstellen, Hosten und Verwalten von Unified Communications-Anwendungen (UC). Bei Einwahlkonferenzen werden zwei UC-Anwendungen verwendet, die den Anwendungsdienst benötigen: Die Konferenzzentrale und die Konferenzankündigungsanwendung. Der Webanwendungsdienst wird installiert und aktiviert standardmäßig auf jedem Front-End-Server in einem Front-End-Pool. Darüber hinaus wird er auf jedem Standard Edition-Server installiert, um Einwahlkonferenzen zu aktivieren und zu konfigurieren.
    
- **Die Konferenzzentrale.** Die Anwendung „Konferenzzentrale“ ist eine Unified Communications-Anwendung, die Festnetzanrufe annimmt, Ansagen wiedergibt und Anrufe mit einer A/V-Konferenz verbindet. Sie wird standardmäßig installiert und aktiviert, wenn Sie die Option für Einwahlkonferenzen aktivieren.
    
- **Konferenzankündigungsanwendung.** Die Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung zur Wiedergabe von Signaltönen und Ansagen für Festnetzteilnehmer bei bestimmten Aktionen (z. B. wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, Teilnehmer stumm geschaltet werden oder die Stummschaltung aufgehoben wird, Benutzer in der Lobby platziert werden oder wenn die Konferenz gesperrt bzw. entsperrt wird). Die Konferenzankündigungsanwendung unterstützt zudem DTMF-Befehle (Dual-Tone Multifrequency, Tonwahlverfahren) über die Telefontastatur. Die Konferenzankündigungsanwendung wird standardmäßig automatisch installiert und aktiviert, wenn Sie die Option für Einwahlkonferenzen aktivieren.
    
- **Die Einrichtungsseite für Einwahlkonferenzen.** Auf der Einrichtungsseite für Einwahlkonferenzen werden die Konferenzeinwahlnummern mit den verfügbaren Sprachen, zugewiesenen Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und die in einer Konferenz verfügbaren DTMF-Steuerelemente angezeigt. Darüber hinaus können Benutzer auf dieser Seite ihre persönliche Identifikationsnummer (PIN) sowie zugewiesene Konferenzinformationen verwalten. Die Einrichtungsseite für Einwahlkonferenzen wird automatisch als Teil der Web Services installiert.
    
- **Vermittlungsserver und PSTN-Gateway.** Einwahlkonferenzen erfordert einen Vermittlungsserver zu übersetzen Signale (und Medien in einigen Konfigurationen) zwischen Skype für Business Server und dem PSTN-Gateway und ein PSTN-Gateway Signale und Medien zwischen dem Vermittlungsserver und PSTN-Gateway übersetzen . Für einwahlkonferenzen müssen Sie mindestens einen Vermittlungsserver und mindestens eine der folgenden bereitstellen:
    
  - PSTN-Gateway
    
  - IP-Nebenstellenanlage
    
  - Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)
    
  > [!NOTE]
  > Wenn Sie außerdem Enterprise-VoIP bereitstellen, sind Vermittlungsserver und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens einen Vermittlungsserver und mindestens eine PSTN-Gateways, IP-Nebenstellenanlage oder SBC für einwahlkonferenzen bereitstellen. 
  
- **Dateispeicher.** Der Dateispeicher wird für Audiodateien mit aufgezeichneten Namen verwendet. Er ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.
    
- **Benutzerspeicher.** Benutzerspeicher wird verwendet, um Benutzer Skype für Business Server PINs zu speichern. Für PINs wird ein Hashalgorithmus verwendet. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.
    
- **Office Web Apps-Server.** Um die Webkonferenzfunktionen benötigt verwenden, müssen Administratoren Office Web Apps Server installieren, und konfigurieren sie Skype für Business Server mit Office Web Apps-Server kommunizieren.
    
## <a name="conferencing-policies"></a>Konferenzrichtlinien

Zum Erzwingen der Richtlinien und Steuern der Bandbreite-Verwendung Ihrer Organisation können Sie Richtlinien für die Arten von Besprechungen festlegen, die Benutzern das organisieren können. Sie können eine Vielzahl von Konferenzrichtlinien definieren und diese einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Weitere Informationen zum Festlegen von konferenzrichtlinien finden Sie unter [Manage Conferencing Policies in Skype für Business Server](../../manage/conferencing/conferencing-policies.md). Ausführliche Informationen zur bandbreitenverwaltung von finden Sie unter [Planen für die anrufsteuerung in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Unterstützung für große Besprechungen

Die Größe von Besprechungen, die unterstützt Skype für Business Server hängt davon ab, ob Konferenzen in einem Pool gemeinsam genutzte oder dedizierte gehostet wird:
  
- Skype für Business Server, auf einem freigegebenen Pool kann Besprechungen mit bis zu 250 Benutzern hosten. Ein freigegebener Pool ist ein Pool aus, der alle Skype für Business Server Arbeitslasten, einschließlich Sofortnachrichten (IM) und Anwesenheitsinformationen, Konferenzen und Enterprise-VoIP hostet. 
    
- Auf einem dedizierten Pool, Skype für Business Server unterstützen Besprechungen mit bis zu 1000 Teilnehmern mit Web und Audio/Video (A / V) Konferenzen, einschließlich der Freigabe von PowerPoint-Präsentationen. Hierzu muss ein dedizierter Pool konfiguriert werden, der große Besprechungen unterstützt und so verwaltet wird, dass er das Hosten einer einzigen großen Besprechung sicherstellt. 
    
Weitere Informationen zum Verwalten von großen Besprechungen finden Sie unter [Planen von großen Besprechungen in Skype für Business Server](large-meetings.md).
  
Wenn Ihre Organisation größere Besprechung Funktionen erforderlich sind, sollten Sie erwägen, implementieren eine hybridumgebung, die ein Onlinedienst Skype Besprechung übertragen nutzt, die Teil von Office 365 ist. Skype-Livekonferenz ermöglicht Benutzern, Besprechungen von bis zu 10.000 Teilnehmern zu hosten und an ein ebenso großes Online-Publikum zu übertragen. Für die Nutzung von Skype-Livekonferenz muss Skype for Business Server bereits in einer Hybridumgebung mit einem Office 365-Produktionsmandanten konfiguriert sein. Als Grundvoraussetzung muss bei allen Benutzern ein Online-Mandant eingerichtet sein. Wenn Sie an der Bereitstellung einer Hybridlösung interessiert sind, die die Vorteile von Skype-Livekonferenz nutzen kann, finden Sie weitere Informationen unter [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md)
  
## <a name="determine-your-organizations-needs"></a>Festlegen der Anforderungen Ihres Unternehmens

Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. In der folgenden Liste werden Sie bei der Planung der Vorgang, um zu bestimmen, welche Features von Live Meeting Sie bereitstellen sollten, basierend auf den Anforderungen der Organisation.
  
> [!NOTE]
> Wenn Sie die Konferenzfunktion bei der Bereitstellung aktivieren, werden auch die Web- und die A/V-Konferenzfunktionen automatisch freigeschaltet. Sie können allerdings bestimmte Funktionen deaktivieren, indem Sie, wie zuvor in diesem Kapitel beschrieben, Konferenzrichtlinien aufstellen. 
  
- **Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**
    
    Wenn ja, müssen Sie die Konferenzfunktionen mithilfe des Planungstools oder des Topologie-Generators für Ihren Front-End-Pool freischalten. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype für Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt. Skype für Business Server bietet einen Drosselung Mechanismus für jede Anwendung einer freigabesitzung steuern. In der Standardeinstellung sind für jede Sitzung 1,5 KB/s festgelegt. Wenn Sie nicht die Anwendungsfreigabe aktivieren möchten, aber Sie, dass Zusammenarbeit an Dokumenten möchten, können Sie Konferenzfunktionen aktivieren und Verwenden von konferenzrichtlinien auf Anwendungsfreigabe deaktivieren. Ausführliche Informationen zum Konfigurieren von konferenzrichtlinien finden Sie unter [konferenzrichtlinien in Skype für Business Server verwalten](../../manage/conferencing/conferencing-policies.md).
    
    Um Benutzern das Freigeben von PowerPoint-Präsentationen zu ermöglichen, müssen Sie den Office Web Apps-Server konfigurieren. Ausführliche Informationen zum Konfigurieren von Office Web Apps Server finden Sie unter [Integration mit Office Web Apps Server in Skype für Business Server konfigurieren](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Möchten Sie Audio- und Videokonferenzen aktivieren?**
    
    Wenn ja, müssen Sie die Konferenzfunktionen mithilfe des Planungstools oder des Topologie-Generators für Ihren Front-End-Pool freischalten. Weitere Informationen finden Sie unter [Bereitstellen von Konferenzen in Skype für Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Für Audio- und Videokonferenzen ist eine höhere Netzwerkbandbreite erforderlich als für Webkonferenzen (diese umfassen Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie Audio- und Videokonferenzen nicht aktivieren, jedoch die Funktion für Webkonferenzen bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und A/V-Konferenzen mithilfe von Konferenzrichtlinien deaktivieren.
    
    Wenn Sie Audiokonferenzen, jedoch keine Videokonferenzen zulassen möchten, können Sie die A/V-Konferenzfunktion aktivieren und Videokonferenzen mithilfe von Konferenzrichtlinien verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen. 
    
    Weitere Informationen zum Konfigurieren von konferenzrichtlinien finden Sie unter [Manage Conferencing Policies in Skype für Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Enterprise Voice wird für A/V-Konferenzen nicht benötigt. Wenn Sie A/V-Konferenzen aktivieren, können Benutzer ihren Konferenzen Audiofunktionen hinzufügen, falls sie über entsprechende Geräte verfügen. Dies gilt auch bei Verwendung eines Nebenstellensystems als Telefonlösung. 
  
- **Möchten Sie die Benutzer den Audioteil von Konferenzen teilnehmen, wenn Sie ein PSTN-Telefon verwenden können?**
    
    Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.
    
    Einwahlkonferenzen ist eine optionale Funktion, die Sie bei der Bereitstellung von Skype für Konferenzen Business Server konfigurieren können. Wenngleich Einwahlkonferenzen einige Komponenten von Enterprise Voice verwenden, ist die Bereitstellung von Enterprise Voice nicht erforderlich, um Einwahlkonferenzen bereitzustellen. Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Weitere Informationen zum Konfigurieren von einwahlkonferenzen für anonyme Benutzer und Unternehmen finden Sie unter [Bereitstellen von Konferenzen in Skype für Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) und [Configure einwahlkonferenzen in Skype für Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Möchten Sie externen Benutzern mit Skype for Business-Clients erlauben, an einer Konferenz teilzunehmen?**
    
    Durch Zulassen der externen Teilnahme an Besprechungen, Maximieren Sie Ihre Investitionen in Skype für Business Server. Folgende Personenkreise können als externe Benutzer eingestuft werden:
    
  - **Remotebenutzer.** Die organisationseigenen Benutzer, wenn außerhalb der Organisationsfirewalls arbeiten und Laptops oder andere Skype für Business Server-Geräte verwenden.
    
  - **Verbundbenutzer.** Benutzer von Unternehmen, mit denen Sie arbeiten, die auch Skype für Business Server ausführen. Damit Ihre Benutzer problemlos Kontakt zu diesen Benutzern aufnehmen können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.
    
  - **Anonyme Benutzer.** Alle anderen externen Benutzer, die von Ihren Benutzern zur Teilnahme an bestimmten Konferenzen eingeladen werden. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.
    
    Wenn Sie externen Benutzern ermöglichen möchten, müssen Sie die Edge-Server bereitstellen. Wenn Sie Edgeserver bereitstellen, können Sie zudem Partnerverbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – einrichten, sodass Benutzer dieser Organisationen einfacher mit Ihren Benutzern zusammenarbeiten können.
    
    Ausführliche Informationen zur Bereitstellung von Edgeservern finden Sie unter „Planen für Edgeserver“ und „Bereitstellen von Edgeserver“. Weitere Informationen zum Festlegen des externen Zugriffs für Office Web Apps Server finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server in Skype für Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Möchten Sie die Clients kontrollieren, die Skype für Business Server-Besprechungen teilnehmen können?**
    
    Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen. Jedes Mal erkennt ein Benutzer auf einen Link zum Teilnehmen an einer geplanten Besprechung klickt, Skype für Business Server, ob ein Client bereits auf dem Computer installiert ist. Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt mit Links zu alternativen Clients wird geöffnet. Der Besprechung teilnehmen Seite enthält immer die Option Skype für Web-Geschäfts-App verwenden. Ferner können Sie entscheiden, ob Links für Teilnehmer und frühere Versionen von Communicator eingeschlossen werden sollen. 
    

