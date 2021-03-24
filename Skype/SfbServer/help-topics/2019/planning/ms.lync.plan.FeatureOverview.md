---
title: Featureübersicht (Planungstool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server Planning Tool
ms.openlocfilehash: 4084d263a693a064e06a814d2fab4542ca3142c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093323"
---
# <a name="feature-overview-planning-tool"></a>Featureübersicht (Planungstool)
 
Skype for Business Server Planning Tool
  
Sie können die Seite **Zentrale Websites des** Planungstools verwenden, um die Skype for Business Server-Bereitstellung zu entwerfen. Sie können zwei entweder eine zentrale oder eine verteilte Bereitstellung erstellen. Eine zentrale Bereitstellung verfügt nur über einen zentralen Standort, an dem alle Skype for Business-Benutzer in Ihrer Organisation vorhanden sind. Eine verteilte Bereitstellung verfügt über mehr als einen zentralen Standort. Wenn Sie Skype for Business Server an mehreren zentralen Standorten bereitstellen, geben Sie die Anzahl der Benutzer an jedem zentralen Standort im Planungstool ein.
  
Zum Abschließen der Definition des zentralen Standorts müssen Sie zunächst die folgenden Informationen bereitstellen:
  
- **Websitename** Geben Sie den Namen des zentralen Standorts ein.
    
- **Anzahl der Benutzer** Geben Sie die Anzahl der Benutzer ein, einschließlich der Benutzer an Zweigstellenstandorten, die am zentralen Standort vorhanden sind.
    
- **Cloud Homed Users** Geben Sie die Anzahl der Benutzer ein, die über Skype for Business Online an der zentralen Website vorhanden sind.
    
## <a name="ui-elements"></a>Benutzeroberflächenelemente

Die verbleibenden Elemente wurden entweder mit den Antworten gefüllt, die Sie auf die Fragen im Assistenten für erste Schritte gestellt haben, oder, wenn Sie den Assistenten übersprungen haben, automatisch vom Planungstool aufgefüllt. 
  
### <a name="online-collaboration"></a>Onlinezusammenarbeit

 **Die Onlinezusammenarbeit** enthält die folgenden Optionen:
  
- **Im-Und-Anwesenheit**
    
    Instant Messaging (Instant Messaging, Chat) ermöglicht Es Benutzern, mithilfe textbasierter Nachrichten auf ihren Computern in Echtzeit miteinander zu kommunizieren. Es werden sowohl Sofortnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Anwesenheit stellt Benutzern Informationen über den Status anderer Benutzer im Netzwerk zur Verfügung. Der Anwesenheitsstatus eines Benutzers enthält Informationen, mit deren Hilfe andere Personen feststellen können, ob der Benutzer online ist und wie sie den Benutzer am besten kontaktieren können. Beispielsweise wird ein Benutzer, der sich in einer Besprechung befindet, am besten per E-Mail kontaktiert.
    
- **Audio- und Videokonferenzen**
    
    Audio-/Videokonferenzen (A/V) ermöglichen Audio- und Videokonferenzen in Echtzeit.
    
- **Einwahlkonferenzen**
    
    Mit Einwahlkonferenzen können Benutzer über ein Telefon im PSTN an einem A/V teilnehmen. Für Einwahlkonferenzen müssen Sie die Anwendungen Konferenz attendant und Conferencing Announcement Service bereitstellen.
    
- **Webkonferenzen**
    
    Webkonferenzen ermöglichen Unternehmensbenutzern innerhalb und außerhalb der Firewall das Erstellen und Teilnehmen an Echtzeitkonferenzen, die auf Ihren internen Servern gehostet werden.
    
- **Beständiger Chat**
    
    Beständigen Chat ermöglicht es mehreren Benutzern, an Unterhaltungen teilzunehmen, in denen sie Inhalte zu bestimmten Themen veröffentlichen und darauf zugreifen, einschließlich Text, Links und Dateien. Benutzer können zwar während einer Sitzung in Echtzeit kommunizieren, der Inhalt der einzelnen Sitzungen kann jedoch dauerhaft sein, was bedeutet, dass er auch nach Beendigung einer Sitzung weiterhin verfügbar ist.

    > [!NOTE] 
    > Beständigen Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden.
    
### <a name="users"></a>Benutzer

 **Benutzer** enthält die folgenden Optionen:
  
- **Interne Organisation**
    
- **Verbund mit anderen Organisationen**
    
- **Verbund mit früheren Versionen**
    
- **Verbund mit öffentlichen Anbieter für Imitationsdienste** Ermöglicht Benutzern in Ihrer Organisation die Kommunikation mit öffentlichen Instant Messaging-Dienstanbietern wie MSN, Yahoo! und AOL. Zum Einrichten eines Verbunds mit öffentlichen Chatnetzwerken ist eine separate Lizenz erforderlich.
    
- **Verbund mit XMPP-basiertem Dienstanbieter**
    
    Skype for Business Server 2015 hat einen vollständig integrierten XMPP-Proxy (auf den Edgeservern bereitgestellt) und ein XMPP-Gateway eingeführt, das auf Ihren Front-End-Servern bereitgestellt wird. Sie können das Hinzufügen und Konfigurieren des XMPP-Proxys bereitstellen, und mit dem XMPP-Gateway können Ihre Skype for Business Server-Benutzer Kontakte von XMPP-basierten Partnern für Chat und Anwesenheit hinzufügen.
    
- **Mobilität**
    
    Wenn Sie den Skype for Business Server Mobility Service bereitstellen, können Benutzer unterstützte mobile Apple iOS-, Android-, Windows Phone- oder Nokia-Geräte verwenden, um Aktivitäten wie das Senden und Empfangen von Chatnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheit durchzuführen.
    
- **W15 Exchange-Postfach**
    
    Mit Skype for Business Server können Sie Voicemailnachrichten in Exchange Unified Messaging (UM) speichern. Diese Voicemailnachrichten werden dann als E-Mail-Nachrichten in den Posteingangen Ihrer Benutzer angezeigt.

    > [!NOTE]
    > Exchange Unified Messaging, wie zuvor bekannt, ist in Exchange 2019 nicht mehr verfügbar, Sie können jedoch weiterhin das Telefonsystem verwenden, um Voicemailnachrichten zu erfassen und die Aufzeichnung dann im Exchange-Postfach eines Benutzers zu be lassen. Weitere [Informationen finden Sie unter Plan Cloud Voicemail service.](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)
    
### <a name="voice"></a>VoIP

 **Voice** enthält die folgenden Optionen:
  
- **Enterprise-VoIP**
    
    Enterprise-VoIP ist die softwarebetriebene VoIP-Lösung von Microsft. Mithilfe von Unternehmensstimmen können Benutzer Skype for Business verwenden, um einen Telefonanruf von ihrem Computer aus zu führen.
    
- **Exchange Unified Messaging**
    
    Exchange Unified Messaging (UM) kombiniert Voicemail und E-Mail in einer einzigen Messaginginfrastruktur. Skype for Business Server 2015 verwendet Exchange UM, um Anrufbeantwortung, Teilnehmerzugriff, Anrufbenachrichtigungen und Dienste für automatische Telefonkonferenzen zur Verfügung zu stellen. Wenn Sie diese Dienste verwenden, müssen Sie Exchange UM und Skype for Business Server in eine freigegebene Active Directory-Topologie integrieren.

    > [!NOTE]
    > Exchange Unified Messaging, wie zuvor bekannt, ist in Exchange 2019 nicht mehr verfügbar, Sie können jedoch weiterhin das Telefonsystem verwenden, um Voicemailnachrichten zu erfassen und die Aufzeichnung dann im Exchange-Postfach eines Benutzers zu be lassen. Weitere [Informationen finden Sie unter Plan Cloud Voicemail service.](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)
    
### <a name="additional-deployment-options"></a>Zusätzliche Bereitstellungsoptionen

 **Zusätzliche Bereitstellungsoptionen** enthalten die folgenden Optionen:
  
- **Hochverfügbarkeit**
    
    Hohe Verfügbarkeit ermöglicht Standbyservern die Failoverunterstützung.
    
- **Notfallwiederherstellung**
    
    Mit Notfallwiederherstellungsmaßnahmen können Sie Front-End-Pools in zwei Rechenzentren koppeln.
    
- **Überwachen**
    
    Die Überwachung erfasst Anrufdetaildatensätze im Zusammenhang mit Kommunikationssitzungen. Außerdem werden Metriken von Audio- und Videositzungen an den Endpunkten der Teilnehmer erfasst. Monitoring Server bietet Verwendungsstatistiken, Trends und Medienqualitätsstatistiken.
    
- **Archivierung**
    
    In der Archivierung werden Chatunterhaltungen und Konferenzen speichert.
    
- **Exchange-Archivierungsintegration**
    
    Wenn Sie Benutzer haben, die in Exchange gespeichert sind und deren Postfächer in den In-Place-Speicher verschoben wurden, können Sie die Option zum Integrieren des Skype for Business Server-Speichers in den Exchange-Speicher auswählen.
    
- **IPv4**
    
    IPv4-Adressen sind 32-Bit-Adressen, mit denen ein Computer über das Internet kommunizieren kann. Aufgrund der zunehmenden Anzahl von Geräten weltweit sind die verfügbaren IPv4-Adressen nicht mehr verfügbar. Aus diesem Grund werden viele neue Geräte zu IPv6-Adressen um.
    
- **IPv6**
    
    IPv6-Adressen erfüllen die gleiche Funktion wie IPv4-Adressen (mit einigen zusätzlichen Features), aber statt nur 32 Bit verwenden IPv6-Adressen 128-Bit. Dies bietet nicht nur einen neuen Satz von Adressen, sondern auch eine viel größere Anzahl von Adressen.
    
- **Geräteaktualisierungs-Webdienst**
    
    Der Geräteupdatewebdienst bietet eine automatisierte Möglichkeit zum Aktualisieren aller Geräte, z. B. Skype for Business for Windows Phone, die außerhalb Ihrer Organisation bereitgestellt werden.
    
### <a name="server-applications"></a>Serveranwendungen

 **Serveranwendungen** enthält die folgenden Optionen:
  
- **Reaktionsgruppe**
    
    Die Reaktionsgruppe-Anwendung beantwortet und verteilt Anrufe automatisch an einen verfügbaren Helpdesk-Agent.
    
- **Ankündigung**
    
    Wenn Sie planen, Enterprise-VoIP bereitstellen, können Sie möglicherweise konfigurieren, wie Telefonanrufe verarbeitet werden, wenn die gewählte Nummer gültig ist, aber keinem gemeinsamen Benutzerbereich zugewiesen ist. Administratoren können den Ansagedienst so konfigurieren, dass diese Anrufe an ein vordefiniertes Ziel (Telefonnummer oder SIP-URI) übertragen oder eine Audioansage oder beides abspielen. Die Verwendung des Ansagediensts verhindert, dass ein Anrufer einen besetzten Ton angibt und hört oder der SIP-Client eine Fehlermeldung empfängt. Die Funktion des Ankündigungsdiensts ist ein typisches PbX-Feature. 
    
- **Parken von Anrufen**
    
    Die Anwendung zum Parken von Anrufen ermöglicht einem Enterprise-VoIP, einen Anruf von einem Telefon aus zu halten und dann den Anruf von einem anderen Telefon zu empfangen, ohne Ressourcen auf dem Telefon zu binden, das den Anruf empfangen hat. Die Anwendung zum Parken von Anrufen ist nützlich, wenn ein Benutzer einen Anruf übertragen muss, der spezifische Empfänger jedoch unbekannt ist. 
    
- **Konferenz attendant**
    
    Die Konferenztelefonanwendung bietet Audiokonferenzfunktionen für Telefonbenutzer ohne den Dienst eines Drittanbieters für Audiokonferenzen.
    
- **Ankündigung von Konferenzen**
    
    Die Konferenzansageanwendung erzeugt Töne, die signalisieren, wenn Benutzer eine Konferenz betreten oder verlassen, sowie Benachrichtigungen an Telefonbenutzer, wenn sie stummgeschaltet oder unveränderlich sind.
    
- **Anrufsteuerung**
    
    Die Anrufsteuerung (Call Admission Control, ANRUFSTEUERUNG), auch bekannt als WAN-Bandbreitenverwaltung, trägt dazu bei, eine schlechte Qualität der Benutzererfahrung in überlasteten Netzwerken zu verhindern, indem basierend auf der verfügbaren Bandbreite ermittelt wird, ob zulässige und neue Echtzeitkommunikationssitzungen eingerichtet werden sollen. 
    
    > [!NOTE]
    > Die Cac steuert nur den Echtzeitdatenverkehr und wirkt sich nicht auf den Datenverkehr aus. 
  
    Wenn eine neue Sprach- oder Videositzung die Bandbreitenbeschränkungen überschreitet, die Sie für ein WAN zugewiesen haben, wird die Sitzung entweder blockiert oder (nur für Telefonanrufe) an das PSTN umgeleitet.
