---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Skype for Business Server 2015 – Planungstool
ms.openlocfilehash: fddf71cef6dc54045c657ca466137b4adb650d9d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274177"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Skype for Business Server 2015 – Planungstool
  
Sie können die Seite " **zentrale Websites** " des Planungstools verwenden, um die Bereitstellung von Skype for Business Server zu entwerfen. Sie können entweder eine zentralisierte oder eine verteilte Bereitstellung erstellen. Eine zentralisierte Bereitstellung hat nur einen zentralen Standort, in dem alle Skype for Business-Benutzer in Ihrer Organisation zu Hause sind. Bei einer verteilten Bereitstellung sind mehrere zentrale Standorte vorhanden. Wenn Sie Skype for Business Server an mehreren zentralen Standorten bereitstellen, geben Sie die Anzahl der Benutzer an jedem zentralen Standort im Planungs Tool ein.
  
Um die Definition des zentralen Standorts fertigzustellen, müssen Sie zunächst folgende Informationen bereitstellen:
  
- **Websitename** Geben Sie den Namen des zentralen Standorts ein.
    
- **Anzahl der Nutzer** Geben Sie die Anzahl der Nutzer ein, einschließlich der Nutzer an Zweigstellen, die an den zentralen Standort verschoben werden.
    
- In der Cloud vernetzte **Benutzer** Geben Sie in Skype for Business Online die Anzahl der Benutzer ein, die sich in der zentralen Website befinden.
    
> [!NOTE]
> Dieses Tool wird für Skype for Business Server 2019 nicht aktualisiert.

## <a name="ui-elements"></a>UI-Elemente

Die übrigen Element wurden mit den Antworten ausgefüllt, die Sie zu den Fragen im Assistenten für **erste Schritte** angegeben haben. Wenn Sie diesen Assistenten übersprungen haben, werden die Elemente automatisch vom Planungstool ausgefüllt.
  
### <a name="online-collaboration"></a>Onlinezusammenarbeit

 **Onlinezusammenarbeit** enthält folgende Optionen:
  
- **Chat und Anwesenheit**
    
    Der Chat ermöglicht Nutzern die Kommunikation in Echtzeit auf ihren Computern über textbasierte Nachrichten. Sowohl Chatsitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern werden unterstützt. Die Anwesenheitsfunktion liefert Nutzern Informationen zum Status anderer Nutzer im Netzwerk. Der Anwesenheitsstatus eines Benutzers bietet Informationen, mit denen andere Personen ermitteln können, ob der Benutzer online ist, und wie Sie den Benutzer am besten kontaktieren können. Ein Nutzer, der sich in einer Besprechung befindet, wird beispielsweise am besten per E-Mail kontaktiert.
    
- **Audio- und Videokonferenzen**
    
    Audio-/Video (A/V)-Konferenzen ermöglichen Audio- und Videokonferenzen in Echtzeit.
    
- **Einwahlkonferenzen**
    
    Einwahlkonferenzen ermöglichen Benutzern die Teilnahme an einer A/V-Konferenz mit einem Festnetztelefon. Einwahlkonferenzen erfordern die Bereitstellung der Konferenztelefonzentrale und des Konferenzankündigungsdiensts.
    
- **Webkonferenzen**
    
    Webkonferenzen ermöglichen Enterprise-Benutzern innerhalb und außerhalb der Firewall das Erstellen von und Teilnehmen an Konferenzen in Echtzeit, die auf Ihren internen Servern gehostet sind.
    
- **Beständiger Chat**
    
    Mit dem beständigen Chat können sich mehrere Benutzer in Chatrooms an Unterhaltungen beteiligen, in denen sie Inhalte zu bestimmten Themen veröffentlichen und darauf zugreifen, einschließlich Text, Links und Dateien. Benutzer können zwar während einer Sitzung in Echtzeit kommunizieren, der Inhalt der einzelnen Sitzungen ist jedoch dauerhaft, was bedeutet, dass er auch nach Beendigung einer Sitzung weiterhin verfügbar ist.
    
### <a name="users"></a>Nutzer

 **Nutzer** enthält folgende Optionen:
  
- **Interne Organisation**
    
- **Partnerverbund mit anderen Organisationen**
    
- **Partnerverbund mit vorherigen Versionen**
    
- **Partnerverbund mit öffentlichen Chatserviceanbietern** Ermöglicht Nutzern in Ihrer Organisation das Herstellen einer Verbindung mit öffentlichen Chatserviceanbietern wie MSN, Yahoo! und AOL. Zum Einrichten eines Partnerverbunds mit öffentlichen Chatserviceanbietern ist eine separate Lizenz erforderlich.
    
- **Partnerverbund mit XMOO-basierten Dienstanbietern**
    
    Skype for Business Server 2015 führt einen vollständig integrierten XMPP-Proxy (auf den Edge-Servern bereitgestellt) und ein XMPP-Gateway ein, das auf Ihren Front-End-Servern bereitgestellt wird. Sie können das Hinzufügen und Konfigurieren des XMPP-Proxys und das XMPP-Gateway bereitstellen, damit Ihre Skype for Business Server 2015-Benutzer Kontakte von XMPP-basierten Partnern für Chats und Anwesenheitsinformationen hinzufügen können.

> [!NOTE]
> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    
- **Mobilität**
    
    Wenn Sie den Skype for Business Server 2015-Mobilitätsdienst bereitstellen, können Benutzer unterstützte Apple IOS-, Android-, Windows Phone-oder Nokia Mobile-Geräte verwenden, um solche Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsfunktionen auszuführen.
    
- **W15 Exchange-Postfach**
    
    Mit Skype for Business Server 2015 können Sie Voicemail-Nachrichten in Exchange Unified Messaging (um) speichern. Diese Sprachnachrichten werden dann als e-Mail-Nachrichten in den Posteingängen Ihrer Benutzer angezeigt.
    
### <a name="voice"></a>VoIP

 **VoIP** enthält folgende Optionen:
  
- **Enterprise-VoIP**
    
    Enterprise-VoIP ist die Software-VoIP-Lösung von Microsft. Enterprise-VoIP ermöglicht Benutzern die Verwendung von Skype for Business, um einen Telefonanruf von Ihrem Computer aus zu tätigen.
    
- **Exchange Unified Messaging**
    
    Exchange Unified Messaging (um) kombiniert Voicemail und e-Mail-Nachrichten in einer einzelnen Messaging Infrastruktur. Skype for Business Server 2015 verwendet Exchange um, um die Anrufannahme, den Teilnehmerzugriff, die Anrufbenachrichtigung und die automatischen Telefonzentralendienste bereitzustellen. Wenn Sie diese Dienste verwenden, müssen Sie Exchange um-und Skype for Business Server in eine freigegebene Active Directory-Topologie integrieren.
    
### <a name="additional-deployment-options"></a>Weitere Bereitstellungsoptionen

 **Weitere Bereitstellungsoptionen** enthält folgende Optionen:
  
- **Hohe Verfügbarkeit**
    
    Die hohe Verfügbarkeit ermöglicht Standbyserver für die Failoverunterstützung.
    
- **Notfallwiederherstellung**
    
    Durch Disaster Recovery-Maßnahmen können Sie Front-End-Pools in zwei Rechenzentren koppeln.
    
- **Überwachen**
    
    Mit der Überwachung werden Anrufdetaildatensätze zu Kommunikationssitzungen erfasst. Zudem werden Metriken aus Audio- und Videositzungen von den Teilnehmerendpunkten gesammelt. Der Monitoring Server bietet Nutzungsstatistiken, Trends und Statistiken zur Medienqualität.
    
- **Archiving**
    
    Mit der Archivierung werden Chatunterhaltungen und Konferenzen gespeichert.
    
- **Exchange-Archivierungsintegration**
    
    Wenn Sie über Benutzer verfügen, die sich in Exchange 2013 befinden und deren Postfächer in der Warteschleife platziert wurden, können Sie die Option zum Integrieren von Skype for Business Server 2015-Speicher mit Exchange-Speicher auswählen.
    
- **IPv4**
    
    Bei IPv4-Adressen handelt es sich um 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen. Aufgrund der steigenden Anzahl an Geräten weltweit stehen keine IPv4-Adressen mehr zur Verfügung. Daher werden von vielen neuen Geräten IPv6-Adressen verwendet.
    
- **IPv6**
    
    IPv6-Adressen haben die gleiche Funktion wie IPv4-Adressen (und bieten einige zusätzliche Features), anstelle von lediglich 32 Bit werden von IPv6-Adressen jedoch 128 Bit verwendet. Dadurch steht nicht nur ein neuer Satz, sondern auch eine größere Anzahl an Adressen zur Verfügung.
    
- **Geräteaktualisierungswebdienst**
    
    Der Geräteupdate-Webdienst bietet eine automatisierte Möglichkeit, alle Geräte wie Skype for Business für Windows Phone zu aktualisieren, die außerhalb Ihrer Organisation bereitgestellt werden.
    
### <a name="server-applications"></a>Serveranwendungen

 **Serveranwendungen** enthält folgende Optionen:
  
- **Reaktionsgruppe**
    
    Die Antwortgruppen Anwendung beantwortet und verteilt Anrufe automatisch an einen verfügbaren Helpdesk-Agenten.
    
- **Ankündigung**
    
    Wenn Sie Enterprise-VoIP bereitstellen möchten, sollten Sie in der Lage sein, die Art und Weise zu konfigurieren, wie Telefonanrufe gehandhabt werden, wenn die gewählte Nummer gültig, aber keinem Benutzer-gemeinsamen Bereich zugewiesen ist. Administratoren können den Ankündigungsdienst so konfigurieren, dass diese Anrufe an ein vorab festgelegtes Ziel (Rufnummer, SIP-URI) übergeben werden, oder eine Audioansage wiedergegeben wird oder beides. Die Verwendung des Ankündigungsdiensts verhindert Situationen, in denen sich ein Anrufer verwählt und ein Besetztzeichen hört oder der SIP-Client eine Fehlermeldung empfängt. Die Ankündigungsdienstfunktion ist ein gängiges Feature bei Nebenstellenanlagen. 
    
- **Parken von Anrufen**
    
    Die Anwendung "Anruf parken" ermöglicht es einem Enterprise-VoIP-Benutzer, einen Anruf von einem Telefon aus zu halten, und dann den Anruf von einem anderen Telefon zu empfangen, ohne Ressourcen auf dem Telefon zu binden, das den Anruf erhalten hat. Die Anwendung für den Parken von anrufen ist nützlich, wenn ein Benutzer einen Anruf übertragen muss, der Empfänger aber unbekannt ist. 
    
- **Konferenztelefonzentrale**
    
    Die Conferencing Attendant-Anwendung bietet Audiokonferenzfunktionen für Telefonbenutzer ohne den Dienst eines Drittanbieters für Audiokonferenzen.
    
- **Konferenzankündigung**
    
    Die APP für Konferenz Ankündigungen erzeugt Töne, die signalisieren, wenn Benutzer eine Konferenz betreten oder belegen, sowie Benachrichtigungen an Telefonbenutzer, wenn Sie stumm geschaltet oder stumm geschaltet sind.
    
- **Anrufsteuerung**
    
    Die Anrufsteuerung (Call Admission Control, CAC) – auch als "Bandbreitenverwaltung" bezeichnet – sorgt dafür, dafür, ein negatives Benutzererlebnis in überlasteten Netzwerken zu verhindern, indem basierend auf der verfügbaren Netzwerkbandbreite festgelegt wird, ob Echtzeitkommunikationssitzungen (z. B. Sprach- oder Videoanrufe) hergestellt werden können. 
    
    > [!NOTE]
    > Die Anrufsteuerung steuert nur den Echtzeitdatenverkehr nur und hat keinen Einfluss auf anderen Datenverkehr. 
  
    Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.
    

