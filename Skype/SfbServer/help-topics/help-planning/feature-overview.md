---
title: Skype for Business Server Featureübersicht –Planungstool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Informationen zum Planungstool Skype for Business Server Featureübersicht.
ms.openlocfilehash: ac759dab4000ebdbe969b2d7436cbb46c408dc38
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848878"
---
# <a name="skype-for-business-server-feature-overview-planning-tool"></a>Skype for Business Server Featureübersicht –Planungstool
 
Skype for Business Server 2015-Planungstool
  
Sie können die Seite **"Zentrale Standorte"** des Planungstools verwenden, um die Skype for Business Server Bereitstellung zu entwerfen. Sie können zwei entweder eine zentrale oder eine verteilte Bereitstellung erstellen. Eine zentrale Bereitstellung verfügt nur über einen zentralen Standort, an dem alle Skype for Business Benutzer in Ihrer Organisation gespeichert sind. Eine verteilte Bereitstellung verfügt über mehr als einen zentralen Standort. Wenn Sie Skype for Business Server an mehreren zentralen Standorten bereitstellen, geben Sie die Anzahl der Benutzer an jedem zentralen Standort im Planungstool ein.
  
Um die Definition des zentralen Standorts abzuschließen, müssen Sie zuerst die folgenden Informationen angeben:
  
- **Websitename** Geben Sie den Namen des zentralen Standorts ein.
    
- **Anzahl der Benutzer** Geben Sie die Anzahl der Benutzer ein, einschließlich der Benutzer an Zweigstellen, die am zentralen Standort verwaltet werden.
    
- **In der Cloud verwalteten Benutzer** Geben Sie die Anzahl der Benutzer ein, die von Skype for Business Online auf dem zentralen Standort verwaltet werden.
    
## <a name="ui-elements"></a>UI-Elemente

Die verbleibenden Elemente wurden entweder mit den Antworten ausgefüllt, die Sie auf die im **Assistenten Erste Schritte** gestellten Fragen bereitgestellt haben, oder, wenn Sie den Assistenten übersprungen haben, automatisch vom Planungstool ausgefüllt.
  
### <a name="online-collaboration"></a>Onlinezusammenarbeit

 **Die Onlinezusammenarbeit** enthält die folgenden Optionen:
  
- **Chat und Anwesenheit**
    
    Chatnachrichten ermöglichen Benutzern die Kommunikation miteinander in Echtzeit auf ihren Computern mithilfe von textbasierten Nachrichten. Es werden sowohl Sofortnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Anwesenheit stellt Benutzern Informationen über den Status anderer Personen im Netzwerk bereit. Der Anwesenheitsstatus eines Benutzers stellt Informationen bereit, mit denen andere personen ermitteln können, ob der Benutzer online ist und wie er am besten kontaktiert werden kann. Beispielsweise wird ein Benutzer, der sich in einer Besprechung befindet, am besten per E-Mail kontaktiert.
    
- **Audio- und Videokonferenzen**
    
    Audio-/Videokonferenzen (A/V) ermöglichen Audio- und Videokonferenzen in Echtzeit.
    
- **Einwahlkonferenzen**
    
    Einwahlkonferenzen ermöglichen Benutzern den Beitritt zu einem A/V über ein Telefon im PsTN. Einwahlkonferenzen erfordern die Bereitstellung der Konferenzzentrale- und Konferenzankündigung-Dienstanwendungen.
    
- **Webkonferenzen**
    
    Mithilfe von Webkonferenzen können Unternehmensbenutzer innerhalb und außerhalb der Firewall Echtzeitkonferenzen erstellen und daran teilnehmen, die auf Ihren internen Servern gehostet werden.
    
- **Beständiger Chat**
    
    Der beständige Chat ermöglicht es mehreren Benutzern, an Unterhaltungen teilzunehmen, in denen sie Inhalte zu bestimmten Themen veröffentlichen und darauf zugreifen, einschließlich Text, Links und Dateien. Benutzer können zwar während einer Sitzung in Echtzeit kommunizieren, der Inhalt der einzelnen Sitzungen kann jedoch dauerhaft sein, was bedeutet, dass er auch nach Beendigung einer Sitzung weiterhin verfügbar ist.
    
### <a name="users"></a>Benutzer

 **Benutzer** enthalten die folgenden Optionen:
  
- **Interne Organisation**
    
- **Partnerverbund mit anderen Organisationen**
    
- **Partnerverbund mit früheren Versionen**
    
- **Partnerverbund mit öffentlichen Chatdienstanbietern** Ermöglicht Benutzern in Ihrer Organisation die Kommunikation mit öffentlichen Instant Messaging-Dienstanbietern wie MSN, Yahoo! und AOL. Zum Einrichten eines Partnerverbunds mit öffentlichen Chatnetzwerken ist eine separate Lizenz erforderlich.
    
- **Partnerverbund mit XMPP-basiertem Dienstanbieter**
    
    Skype for Business Server 2015 führt einen vollständig integrierten XMPP-Proxy (bereitgestellt auf den Edgeservern) und ein XMPP-Gateway ein, das auf Ihren Front-End-Servern bereitgestellt wird. Sie können das Hinzufügen und Konfigurieren des XMPP-Proxys und des XMPP-Gateways bereitstellen, damit Ihre Skype for Business Server 2015-Benutzer Kontakte von XMPP-basierten Partnern für Chatnachrichten und Anwesenheitsinformationen hinzufügen können.
    
- **Mobilität**
    
    Wenn Sie den Skype for Business Server 2015 Mobility Service bereitstellen, können Benutzer unterstützte mobile Geräte von Apple iOS, Android, Windows Phone oder Nokia verwenden, um Aktivitäten wie das Senden und Empfangen von Chatnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen auszuführen.
    
- **W15 Exchange-Postfach**
    
    Skype for Business Server 2015 können Sie Voicemailnachrichten in Exchange Unified Messaging (UM) speichern. Diese Voicemailnachrichten werden dann als E-Mail-Nachrichten in den Postfächern Ihrer Benutzer angezeigt.
    
### <a name="voice"></a>VoIP

 **Voice** enthält die folgenden Optionen:
  
- **Enterprise-VoIP**
    
    Enterprise VoIP-Lösung ist die softwaregestützte VoIP-Lösung von Microsft. mit Enterprise Voice können Benutzer Skype for Business verwenden, um einen Telefonanruf von ihrem Computer aus zu tätigen.
    
- **Exchange Unified Messaging**
    
    Exchange Unified Messaging (UM) kombiniert Voicemail und E-Mail in einer einzigen Messaginginfrastruktur. Skype for Business Server 2015 verwendet Exchange UM, um Anrufbeantwortung, Abonnentenzugriff, Anrufbenachrichtigung und automatische Telefonzentralendienste bereitzustellen. Wenn Sie diese Dienste verwenden, müssen Sie Exchange UM und Skype for Business Server in eine freigegebene Active Directory-Topologie integrieren.
    
### <a name="additional-deployment-options"></a>Zusätzliche Bereitstellungsoptionen

 **Zusätzliche Bereitstellungsoptionen** enthalten die folgenden Optionen:
  
- **Hochverfügbarkeit**
    
    Hohe Verfügbarkeit ermöglicht Standbyserver für Failoverunterstützung.
    
- **Notfallwiederherstellung**
    
    Notfallwiederherstellungsmaßnahmen ermöglichen es Ihnen, Front-End-Pools in zwei Rechenzentren zu koppeln.
    
- **Überwachen**
    
    Die Überwachung erfasst Anrufdetaildatensätze im Zusammenhang mit Kommunikationssitzungen. Außerdem werden Metriken aus Audio- und Videositzungen an den Teilnehmerendpunkten erfasst. Monitoring Server bietet Nutzungsstatistiken, Trends und Statistiken zur Medienqualität.
    
- **Archivierung**
    
    Die Archivierung speichert Chatunterhaltungen und Konferenzen.
    
- **Exchange Archivierungsintegration**
    
    Wenn Sie Benutzer haben, die Exchange 2013 verwaltet werden und ihre Postfächer in In-Place Haltebereich versetzt wurden, können Sie die Option auswählen, Skype for Business Server 2015-Speicher in Exchange Speicher zu integrieren.
    
- **IPv4**
    
    IPv4-Adressen sind 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen. Aufgrund der zunehmenden Anzahl von Geräten weltweit sind die verfügbaren IPv4-Adressen abgelaufen. Aus diesem Grund werden viele neue Geräte auf die Verwendung von IPv6-Adressen umgezogen.
    
- **IPv6**
    
    IPv6-Adressen führen die gleiche Funktion wie IPv4-Adressen aus (mit einigen zusätzlichen Features), aber anstatt nur 32-Bit-Adressen verwenden IPv6-Adressen 128-Bit. Dies bietet nicht nur eine neue Gruppe von Adressen, sondern auch eine viel größere Anzahl von Adressen.
    
- **Geräteaktualisierungs-Webdienst**
    
    Der Device Update-Webdienst bietet eine automatisierte Möglichkeit zum Aktualisieren aller Geräte, z. B. Skype for Business für Windows Phone, die außerhalb Ihrer Organisation bereitgestellt werden.
    
### <a name="server-applications"></a>Serveranwendungen

 **Serveranwendungen** enthalten die folgenden Optionen:
  
- **Reaktionsgruppe**
    
    Die Reaktionsgruppenanwendung beantwortet und verteilt Anrufe automatisch an einen verfügbaren Helpdesk-Agent.
    
- **Ankündigung**
    
    Wenn Sie beabsichtigen, Enterprise-VoIP bereitzustellen, möchten Sie möglicherweise konfigurieren können, wie Telefonanrufe verarbeitet werden, wenn die gewählte Nummer gültig ist, aber keinem gemeinsamen Benutzerbereich zugewiesen ist. Administratoren können den Ankündigungsdienst so konfigurieren, dass diese Anrufe an ein vordefiniertes Ziel (Telefonnummer oder SIP-URI) übertragen oder eine Audioankündigung oder beides wiedergeben. Durch die Verwendung des Ankündigungsdiensts wird die Situation vermieden, in der ein Anrufer fehlgeleitet und einen besetzten Ton hört oder der SIP-Client eine Fehlermeldung empfängt. Die Funktion des Ankündigungsdiensts ist ein typisches PBX-Feature. 
    
- **Parken von Anrufen**
    
    Die Anwendung zum Parken von Anrufen ermöglicht es einem Enterprise-VoIP Benutzer, einen Anruf von einem Telefon aus zu sperren und dann den Anruf von einem anderen Telefon zu empfangen, ohne Ressourcen auf dem Telefon zu binden, das den Anruf empfangen hat. Die Anwendung zum Parken von Anrufen ist nützlich, wenn ein Benutzer einen Anruf übertragen muss, der empfängerspezifische Empfänger jedoch unbekannt ist. 
    
- **Konferenzzentrale**
    
    Konferenzzentralenanwendung bietet Telefonbenutzern Ohne den Dienst eines Drittanbieters für Audiokonferenzen Audiokonferenzfunktionen.
    
- **Konferenzankündigung**
    
    Konferenzankündigungsanwendung erzeugt Töne, die signalisieren, wenn Benutzer eine Konferenz betreten oder verlassen, sowie Benachrichtigungen an Telefonbenutzer, wenn sie stumm oder unveränderlich sind.
    
- **Anrufsteuerung**
    
    Die Anrufsteuerung (Call Admission Control, CAC), auch bekannt als WAN-Bandbreitenverwaltung, trägt dazu bei, eine schlechte Qualität der Benutzererfahrung für Benutzer in überlasteten Netzwerken zu verhindern, indem basierend auf der verfügbaren Bandbreite ermittelt wird, ob zugelassen und neue Echtzeitkommunikationssitzungen eingerichtet werden sollen. 
    
    > [!NOTE]
    > Die Anrufsteuerung steuert nur Echtzeitdatenverkehr und hat keinen Einfluss auf den Datenverkehr. 
  
    Wenn eine neue VoIP- oder Videositzung die Bandbreiteneinschränkungen überschreitet, die Sie in einem WAN zugewiesen haben, wird die Sitzung entweder blockiert oder (nur für Telefonanrufe) an das Festnetz umgeleitet.
    

