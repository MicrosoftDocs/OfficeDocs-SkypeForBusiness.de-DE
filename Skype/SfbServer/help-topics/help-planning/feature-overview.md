---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Skype for Business Server 2015 – Planungstool
ms.openlocfilehash: f04935f7dc4d27883e40b388051b9affa4ec30e9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219786"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Skype for Business Server 2015 – Planungstool
  
Die Seite **Zentralen Standorten** mit dem Planungstool können Sie um die Skype für Business Server-Bereitstellung zu entwerfen. Sie können entweder eine zentralisierte oder eine verteilte Bereitstellung erstellen. Eine zentrale Bereitstellung verfügt nur über einen zentralen Standort, die alle Skype für Unternehmensbenutzer in Ihrer Organisation befinden. Bei einer verteilten Bereitstellung sind mehrere zentrale Standorte vorhanden. Wenn Sie Skype für Business Server an mehreren zentralen Standorten bereitstellen, können Sie die Anzahl der Benutzer bei jeder zentrale Standort im Planungstool eingeben.
  
Um die Definition des zentralen Standorts fertigzustellen, müssen Sie zunächst folgende Informationen bereitstellen:
  
- **Websitename** Geben Sie den Namen des zentralen Standorts ein.
    
- **Anzahl der Nutzer** Geben Sie die Anzahl der Nutzer ein, einschließlich der Nutzer an Zweigstellen, die an den zentralen Standort verschoben werden.
    
- **Cloud Benutzer verwaltet** Geben Sie die Anzahl der Benutzer, die verwaltet werden am zentralen Standort aus Skype für Business Online.
    
## <a name="ui-elements"></a>UI-Elemente

Die übrigen Element wurden mit den Antworten ausgefüllt, die Sie zu den Fragen im Assistenten für **erste Schritte** angegeben haben. Wenn Sie diesen Assistenten übersprungen haben, werden die Elemente automatisch vom Planungstool ausgefüllt.
  
### <a name="online-collaboration"></a>Onlinezusammenarbeit

 **Onlinezusammenarbeit** enthält folgende Optionen:
  
- **Chat und Anwesenheit**
    
    Der Chat ermöglicht Nutzern die Kommunikation in Echtzeit auf ihren Computern über textbasierte Nachrichten. Sowohl Chatsitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern werden unterstützt. Die Anwesenheitsfunktion liefert Nutzern Informationen zum Status anderer Nutzer im Netzwerk. Anwesenheitsstatus eines Benutzers liefert Informationen, deren Hilfe andere Benutzer zu bestimmen, ob der Benutzer online ist und wie Sie am besten den Benutzer zu kontaktieren. Ein Nutzer, der sich in einer Besprechung befindet, wird beispielsweise am besten per E-Mail kontaktiert.
    
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
    
    Skype für Business Server 2015 führt einen voll integrierte XMPP-Proxy (auf dem Edge-Servern bereitgestellt) und einem XMPP-Gateway auf Front-End-Servern bereitgestellt. Sie können bereitstellen, hinzufügen und Konfigurieren des XMPP-Proxys und XMPP-Gateway ansetzt, kann Ihre Skype für Business Server 2015 Benutzer Kontakte von XMPP-basierten Partnern für instant messaging (IM) und Anwesenheit hinzufügen.
    
- **Mobilität**
    
    Wenn Sie die Skype für Business Server 2015 Mobility Service bereitstellen, können Benutzer unterstützte Apple iOS, Android, Windows Phone oder mobilen Nokia-Geräten solche Aktivitäten als senden und Empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen von Anwesenheitsinformationen ausführen verwenden.
    
- **W15 Exchange-Postfach**
    
    Skype für Business Server 2015 können Sie Voicemail-Nachrichten in Exchange Unified Messaging (UM) gespeichert haben. Diese Voicemailnachrichten werden dann als e-Mail-Nachrichten in die Posteingänge der Benutzer angezeigt.
    
### <a name="voice"></a>VoIP

 **VoIP** enthält folgende Optionen:
  
- **Enterprise-VoIP**
    
    Enterprise-VoIP ist Microsofts softwarebasiertes VoIP-Lösung. Enterprise-VoIP kann Benutzer Skype für Unternehmen verwenden, um einen Anruf von ihrem Computer zu tätigen.
    
- **Exchange Unified Messaging**
    
    Exchange Unified Messaging (UM) kombiniert Voicemail und e-Mail in einer einzigen Messaginginfrastruktur. Skype für Business Server 2015 verwendet Exchange UM-Mailboxansage, Teilnehmerzugriff, anrufbenachrichtigungen und automatische Telefonzentrale bereitzustellen. Wenn Sie diese Dienste verwenden, müssen Sie Exchange UM und Skype für Business Server in einer freigegebenen Active Directory-Topologie zu integrieren.
    
### <a name="additional-deployment-options"></a>Weitere Bereitstellungsoptionen

 **Weitere Bereitstellungsoptionen** enthält folgende Optionen:
  
- **Hohe Verfügbarkeit**
    
    Die hohe Verfügbarkeit ermöglicht Standbyserver für die Failoverunterstützung.
    
- **Notfallwiederherstellung**
    
    Disaster Recovery Maßnahmen können Sie Paar Front-End-Pools befindet sich in zwei Rechenzentren.
    
- **Überwachen**
    
    Mit der Überwachung werden Anrufdetaildatensätze zu Kommunikationssitzungen erfasst. Zudem werden Metriken aus Audio- und Videositzungen von den Teilnehmerendpunkten gesammelt. Monitoring Server bietet Nutzungsstatistiken, Trends und Media Quality Statistik.
    
- **Archiving**
    
    Mit der Archivierung werden Chatunterhaltungen und Konferenzen gespeichert.
    
- **Exchange-Archivierungsintegration**
    
    Wenn Sie Benutzer, die sich auf Exchange 2013 befinden und ihren Postfächern zu Compliance-Archiv platzieren wurde haben, können Sie die Option zum Integrieren von Skype für Business Server 2015 Storage mit Exchange auswählen.
    
- **IPv4**
    
    Bei IPv4-Adressen handelt es sich um 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen. Aufgrund der steigenden Anzahl an Geräten weltweit stehen keine IPv4-Adressen mehr zur Verfügung. Daher werden von vielen neuen Geräten IPv6-Adressen verwendet.
    
- **IPv6**
    
    IPv6-Adressen haben die gleiche Funktion wie IPv4-Adressen (und bieten einige zusätzliche Features), anstelle von lediglich 32 Bit werden von IPv6-Adressen jedoch 128 Bit verwendet. Dadurch steht nicht nur ein neuer Satz, sondern auch eine größere Anzahl an Adressen zur Verfügung.
    
- **Geräteaktualisierungswebdienst**
    
    Der Geräteupdate-Webdienst bietet eine automatisierte Möglichkeit zur Aktualisierung von alle Geräten, beispielsweise Skype für Business für Windows Phone, die außerhalb Ihrer Organisation bereitgestellt werden.
    
### <a name="server-applications"></a>Serveranwendungen

 **Serveranwendungen** enthält folgende Optionen:
  
- **Reaktionsgruppe**
    
    Die Anwendung "Reaktionsgruppe" automatisch beantwortet und verteilt Anrufe an einen verfügbaren Helpdesk-Agent.
    
- **Ankündigung**
    
    Wenn Sie Enterprise-VoIP bereitstellen möchten, möchten Sie möglicherweise mehr konfigurieren wie Telefonanrufe behandelt werden, wenn die gewählte Nummer gültig, aber nicht in einen gemeinsamen Benutzerbereich zugeordnet ist. Administratoren können den Ankündigungsdienst so konfigurieren, dass diese Anrufe an ein vorab festgelegtes Ziel (Rufnummer, SIP-URI) übergeben werden, oder eine Audioansage wiedergegeben wird oder beides. Die Verwendung des Ankündigungsdiensts verhindert Situationen, in denen sich ein Anrufer verwählt und ein Besetztzeichen hört oder der SIP-Client eine Fehlermeldung empfängt. Die Ankündigungsdienstfunktion ist ein gängiges Feature bei Nebenstellenanlagen. 
    
- **Parken von Anrufen**
    
    Parken Anwendung ermöglicht ein Enterprise-VoIP-Benutzer einen Anruf platziert auf halten von einem Telefon, und klicken Sie dann den Anruf von einem anderen Telefon empfangen, ohne zu binden Ressourcen auf dem Telefon, das den Anruf empfangen hat. Anwendung zum Parken von Anrufen ist nützlich, wenn ein Benutzer benötigt, um einen Anruf weiterleiten, aber der jeweiligen Empfänger unbekannt ist. 
    
- **Konferenztelefonzentrale**
    
    Die Anwendung Konferenzzentrale bietet Funktionen für Audiokonferenzen, ohne den Dienst, der einen Drittanbieter-Audiokonferenzen Telefonbenutzer.
    
- **Konferenzankündigung**
    
    Konferenzankündigungsdienst, dass die Anwendung Töne erzeugt, die signalisieren, wenn Benutzer eingeben oder diese verlassen einer Konferenz als auch Benachrichtigungen zu Telefonbenutzer beim stumm geschaltet oder dies wieder aufgehoben wird.
    
- **Anrufsteuerung**
    
    Die Anrufsteuerung (Call Admission Control, CAC) – auch als "Bandbreitenverwaltung" bezeichnet – sorgt dafür, dafür, ein negatives Benutzererlebnis in überlasteten Netzwerken zu verhindern, indem basierend auf der verfügbaren Netzwerkbandbreite festgelegt wird, ob Echtzeitkommunikationssitzungen (z. B. Sprach- oder Videoanrufe) hergestellt werden können. 
    
    > [!NOTE]
    > Die Anrufsteuerung steuert nur den Echtzeitdatenverkehr nur und hat keinen Einfluss auf anderen Datenverkehr. 
  
    Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.
    

