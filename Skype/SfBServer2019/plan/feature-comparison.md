---
title: Vergleich von Desktop-Client-Features für Skype for Business Server 2019
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Zusammenfassung: Skype for Business Server 2019 oder Skype for Business Online-Administratoren können diese Tabellen verwenden, um zu verstehen, welche Features für welche Clients unterstützt werden.'
ms.openlocfilehash: 351158dde052039ad60e796fb528af48e923dfd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812603"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Vergleich von Desktop-Client-Features für Skype for Business Server 2019

**Zusammenfassung:** Skype for Business Server 2019 oder Skype for Business Online-Administratoren können diese Tabellen verwenden, um zu verstehen, welche Features für welche Clients unterstützt werden.

 Überprüfen Sie vor der Bereitstellung oder dem Upgrade auf Skype for Business Server, welche Clients bereits in Ihrer Organisation verwendet werden. Ermitteln Sie anhand der folgenden Tabellen die Auswirkungen der unterstützten Funktionen auf diese Clients. Dann können Sie den Benutzern die Änderungen vermitteln sowie das Tempo des Rollouts bestimmen und die Vorteile des Upgrades auf den neuesten Client in vollem Umfang verstehen.

Einige der in Skype for Business Server 2019 verfügbaren Funktionen stehen in Skype for Business Online nicht zur Verfügung. Einzelheiten finden Sie unter [Einschränkungen für Online-oder Hybrid Benutzerkonten](feature-comparison.md#Online-Hybrid) . Skype for Business Online-Administratoren finden unter [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) Informationen zu den verschiedenen verfügbaren Plänen.

In den folgenden Tabellen sind die Features aufgeführt, die für jeden Client verfügbar sind, der mit Skype for Business Server 2019 oder Skype for Business Online funktioniert. Siehe[Vergleich der Funktionen von Mobile Clients für Skype for Business](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) für einen Vergleich der Funktionen für Smartphones und Tablet-Clients. Die Clientzugriffslizenz oder Benutzerabonnementlizenz, die Ihre Organisation erwirbt, hat auch Auswirkungen darauf, welche Funktionen Ihren Benutzern zur Verfügung stehen. Ob Sie den Client mit vollem Funktionsumfang oder den Standardclient für Benutzer bereitstellen, hängt von der Lizenz oder dem Plan ab, den Ihre Organisation erwirbt. Weitere Informationen finden Sie unter [Leitfaden zur Lizenzierung](https://products.office.com/en-us/skype-for-business/it-pros).

> [!IMPORTANT]
> Skype for Business Server 2019 und Skype for Business Online unterstützen die folgenden zuvor veröffentlichten Clients: lync 2013, Skype for Business 2015 und Skype for Business 2016 sowie den Skype for Business 2019-Client. Informationen zu diesen Clients, wenn Sie mit anderen Servern verwendet werden, finden Sie in den [Client Vergleichstabellen für lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) und [Vergleich der Desktop Client-Features für Skype for Business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> Der Skype for Business-Web-App Browser-Client und die Skype Meetings App Windows 10 App bieten nur [Unterstützung für Besprechungen](feature-comparison.md#BKMK_Conferencing). Weitere Informationen zu diesen Clients finden Sie unter [Plan for Meetings clients (Web App and Meetings App)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md).

## <a name="enhanced-presence-support"></a>Unterstützung für erweiterte Anwesenheitsinformationen
<a name="BKMK_EnhancedPresence"> </a>

Diese Tabelle enthält die erweiterten Anwesenheitsfunktionen, die über die einfache Angabe hinausgehen, ob Benutzer online, offline, beschäftigt usw. sind. 


| Feature/Funktion                                                                                  | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Status veröffentlichen                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Status anzeigen                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Statushinweise und Abwesenheitsnotizen anzeigen                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Benutzerdefinierten Standort hinzufügen                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Eigene Notiz hinzufügen                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Verwenden eines Fotos von einer beliebigen öffentlichen Site für „Mein Bild“  <br/> (nicht in Skype for Business Online verfügbar) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776; Unterstützt nicht das Veröffentlichen des Status auf der Grundlage von Kalenderinformationen (frei/gebucht).

## <a name="contacts-and-contact-groups-support"></a>Unterstützung von Kontakten und Kontaktgruppen
<a name="BKMK_Contacts"> </a>

Diese Tabelle enthält die Funktionen im Zusammenhang mit der Verwaltung von Chatkontakten und Kontakten mit Anwesenheitsfunktionen. 


| Feature/Funktion                                                                            | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Bereits ausgefüllte Kontaktliste                                                                   | &#x2714;                                      |                           |                  |
| Kontaktliste anzeigen und ändern                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Private Beziehungen steuern                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Unternehmensadressbuch durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Microsoft Outlook-Kontakte durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kontaktgruppen verwalten                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Verteilergruppen und Office 365-Gruppen erweitern                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Nach Reaktionsgruppen suchen  <br/> (nicht in Skype for Business Online verfügbar)                | &#x2714;                                      |                           | &#x2714;         |
| Gruppe „Letzte Kontakte“ anzeigen                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Gruppe „Aktuelle Unterhaltungen“ anzeigen                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Alternative Kontaktansichten anzeigen (z. B. Kachelansicht)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kontakte nach „Gruppe“, „Beziehung“ oder „Neu“ sortieren (Personen, die Sie zu ihrer „Kontaktliste“ hinzugefügt haben) | &#x2714;                                      |                           | &#x2714;         |
| Kontakte nach Status (Verfügbarkeit) sortieren                                                        | &#x2714;                                      |                           | &#x2714;         |
| Exchange-Kontakte suchen und hinzufügen                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Chatunterstützung
<a name="BKMK_IMSupport"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Chatunterstützung.

|Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Chatnachricht oder E-Mail an Kontakt initiieren  |&#x2714;|&#x2714;|&#x2714;|  
|In einem einzelnen Fenster mit Registerkarten zwischen mehreren Chats navigieren bzw. mehrere Unterhaltungen verfolgen   |&#x2714;|&#x2714;|&#x2714;| 
|Chatnachrichtenunterhaltungen in Outlook protokollieren  |&#x2714;|&#x2714;, wenn der serverseitige Konversations Verlauf aktiviert ist   |&#x2714;|   
|Überprüfen der Rechtschreibung |&#x2714;|&#x2714;||   
|Qualifikationssuche (mit SharePoint Server Integration)  <br/> (Für die Qualifikationssuche sind lokale Bereitstellungen von Skype for Business Server und SharePoint 2013 erforderlich.)  |&#x2714;||&#x2714;|
|Integration des beständigen Chats (Gruppenchats)  <br/> (nicht für Skype for Business Online verfügbar)|&#x2714;||&#x2714;|  
|Beständigen Chatroom mit einem Klick zu einer Skype for Business-Besprechung eskalieren  <br/> (nicht für Skype for Business Online verfügbar) |&#x2714;||&#x2714;| 
|Inlinebilder vom Absender und Empfänger im Chatfenster |&#x2714;||&#x2714;| 
|Empfangen von Freihandnachrichten |&#x2714;||&#x2714;| 
|„Hohe Priorität“ für Chatnachrichten festlegen |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Unterstützung für Besprechungen
<a name="BKMK_Conferencing"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für Besprechungen.

> [!NOTE]
>  Die Besprechungsfunktionen von Skype for Business sind in Skype for Business Online Standalone-Plan 1 nicht verfügbar.  Plan 1 wird [zurückgezogen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

In Skype-zu-Skype-Sitzungen können Benutzer mit Skype for Business Online-Plan 1 an Desktopfreigabe- und Anwendungsfreigabesitzungen teilnehmen, wenn sie von anderen Benutzern dazu eingeladen werden, die über Zugriff auf Freigabefunktionen verfügen.
Details hierzu finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx). 

|Feature/Funktion | Skype for Business 2016-Client | Skype for Business unter Mac | Skype for Business-Web-App | Skype for Business 2015-Client | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Computeraudiofunktionen hinzufügen  |&#x2714;|&#x2714;|&#x2714;(erfordert Plug-In)  |&#x2714;|&#x2714;| 
|Video hinzufügen |&#x2714;|&#x2714;|&#x2714;(erfordert Plug-In) |&#x2714;|&#x2714;| 
|Video mit mehreren Teilnehmern ansehen (Katalogansicht)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung    |&#x2714;|&#x2714;|Nur #a0 Ansicht   ||| 
|Steuerelemente für Referenten in Besprechungen verwenden |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Auf detaillierte Besprechungsliste zugreifen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|An Chatnachrichten mit mehreren Teilnehmern teilnehmen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Desktop freigeben (sofern aktiviert)  |&#x2714;|&#x2714; &#x2776; |&#x2714;&#x2776; (erfordert Plug-in) |&#x2714;| &#x2714;|
|Programm freigeben (sofern aktiviert) |&#x2714;|Nur Ansicht   |&#x2714;(erfordert Plug-In)  |&#x2714;|&#x2714;|   
|Anonyme Teilnehmer hinzufügen (sofern aktiviert) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahl Audio-Besprechungen #a0|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Eine Besprechung mit „Jetzt besprechen“ einleiten|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Microsoft PowerPoint-Dateien hinzufügen und vorführen |&#x2714;| &#x2778; Anmerkungen sind nicht verfügbar   |&#x2714;|&#x2714;|&#x2714;| 
|In Microsoft PowerPoint-Dateien navigieren |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|OneNote-Besprechungsnotizen hinzufügen und bearbeiten  |&#x2714;||Nur bearbeiten (nicht hinzufügen)  |&#x2714;|&#x2714;|
|Whiteboard verwenden |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Abstimmungen durchführen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Dateien hochladen, um sie für andere Personen freizugeben |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen |Outlook oder Skype for Business Web Scheduler  |Outlook oder Skype for Business Web Scheduler |Skype for Business Web Scheduler |Outlook oder Skype for Business Web Scheduler   |Outlook oder Lync Web Scheduler |  
|Q&amp;A-Manager |&#x2714;|||||
|Teilnehmervideo deaktivieren |&#x2714;||&#x2714;|||
|Besprechungschat deaktivieren |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer stummschalten |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Alle zu Teilnehmern machen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Skype Meeting Broadcast erstellen |&#x2714;|||||
|Stellvertretung kann Besprechungen im Namen des Delegierenden planen |&#x2714;|&#x2714;|&#x2714;|||
|Stellvertretungen zwischen Skype for Business und Outlook synchronisieren |&#x2714;||&#x2714;|&#x2714;|| 
|Videospotlight festlegen (Video sperren) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Steuerung der Bildschirmübertragung übergeben/übernehmen  |&#x2714;||&#x2714;|||

 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business auf den Mac, Lync für Mac 2011- oder Communicator für Mac 2011-Benutzern freigegeben wurden. Skype for Business auf den Mac, Lync für Mac 2011- und Communicator für Mac 2011-Benutzer können keine Desktops steuern, die von Windows-Benutzer freigegeben wurden. Dies funktioniert auch nicht für Skype for Business-Web-App auf Max OSX.

 &#x2777; für Skype for Business Online erfordert dieses Feature Microsoft-PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.

 &#x2778; Der Lync für Mac 2011-Client kann Microsoft Office 2013 PowerPoint-Präsentationen nicht anzeigen, wenn sie in einer Konferenz von der Skype for Business-Web-App freigegeben wurden.

&#x2779; für Skype for Business 2016-apps müssen Sie Klick-und-Los, Build 16.0.4227 oder höher verwenden.

&#x2780; für Skype for Business 2015-apps müssen Sie über das September-Update, Build 15.0.4747 oder höher verfügen.

## <a name="voice-telephony-support"></a>Unterstützung für VoIP (Telefonie)
<a name="BKMK_Telephony"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für VoIP-Dienste.

> [!NOTE]
> Skype for Business VoIP (Telefonie)-Funktionen sind auf bestimmte Skype for Business Online-Abonnementpläne beschränkt. Details hierzu finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx). 

 | Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----| 
|Anruf initiieren |&#x2714;|&#x2714;|&#x2714;|
|Kontakt durch Mausklick anrufen |&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten |&#x2714;|&#x2714;|&#x2714;|  
|Anrufweiterleitung verwalten |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Einstellungen für Teamanruf verwalten |&#x2714;||&#x2714; &#x2776; |
|Stellvertretungen verwalten |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Anruf an eine Reaktionsgruppe initiieren|&#x2714;||&#x2714; &#x2776; |
|Unterstützung für Notrufe (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Chatbenachrichtigung an SIP-URIs für E-911-Anrufe |&#x2714;|&#x2714;|&#x2714;|
|Chatbenachrichtigung an Verteilerliste für E-911-Anrufe|&#x2714;|&#x2714;|&#x2714;|
|Mit Voicemail verbinden, Begrüßung einrichten oder ändern |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Benachrichtigung über verpasste Anrufe |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anruf parken |&#x2714;||&#x2714; &#x2776; |
|Gruppenanrufannahme |&#x2714;||&#x2714; &#x2776; |
|Standortbasiertes Routing |&#x2714;|&#x2714;|&#x2714;| 
|Reaktionsgruppe/Teamanrufgruppe verwalten |&#x2714;||&#x2714;|

 &#x2776; Dieses Feature ist nicht in Skype for Business Online verfügbar.

## <a name="external-users-support"></a>Unterstützung externer Benutzer
<a name="BKMK_ExternalUsers"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für externe Benutzer, die im PSTN verwaltet werden.


|Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Chatnachricht mit öffentlichem Kontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Chatnachricht mit Partnerkontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Anrufe mit zwei oder mehr Teilnehmern mit externen Benutzern durchführen  <br/> (nicht in Skype for Business Online verfügbar)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Aufzeichnungsunterstützung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für das Aufzeichnen von Besprechungen.

| Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client |   
|:-----|:-----|:-----|:-----|  
|Aufzeichnung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten auf Clientseite |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen auf Clientseite| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Auswählen der bevorzugten Auflösung für die Aufzeichnung  |&#x2714;||&#x2714;|

 &#x2776;  Die Aufzeichnungsfunktion ist in bestimmten Skype for Business Online Standalone-Plänen nicht verfügbar. Die Aufzeichnung erfordern die vollständigen Skype for Business-Clientberechtigungen.

 &#x2777; Die Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen ist in Skype for Business Online nicht verfügbar.

## <a name="modern-authentication"></a>Moderne Authentifizierung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Funktionen, die Unterstützung für moderne Authentifizierung erfordern. 

Moderne Authentifizierung erfordert außerdem eine Topologie, die in[Skype for Business-Topologien, die von Moderner Authentifizierung unterstützt werden ](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md)beschrieben wird.


 | Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Moderne Authentifizierung |&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung |&#x2714; (Nur in eine Domäne eingebundene Geräte) |&#x2714;|&#x2714; (Nur in eine Domäne eingebundene Geräte)  |
|Kerberos-Authentifizierung |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Unterstützung für Archivierung, Konformität und Protokollierung
<a name="BKMK_Archiving"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für Archivierungs- und Protokollierungsfunktionen.


 | Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business unter Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Archivierung von Chats im Outlook-Ordner „Aufgezeichnete Unterhaltungen“|&#x2714; &#x2776; |&#x2714;, wenn der serverseitige Konversations Verlauf aktiviert ist  |&#x2714; &#x2776; | 
|Archivierung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten auf Clientseite  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Client seitige Archivierung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen (nicht verfügbar in Skype for Business Online)  |&#x2714;||&#x2714;|
|Zugriff auf Anmeldeprotokolle vom Skype for Business-Symbol in der Taskleiste |&#x2714;||&#x2714;|

 &#x2776;  Für Skype for Business Online-Benutzer erfordert diese Funktion Exchange Online. Sie wird über das „In-Situ-Speicher“-Attribut des Exchange-Postfachs des Benutzers gesteuert.

## <a name="client-limitations"></a>Einschränkungen der Clients
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Einschränkungen des Standardclients
<a name="Full-Basic"> </a>

Die folgenden Funktionen sind bei Verwendung des Clients mit vollem Funktionsumfang verfügbar, bei Verwendung des Standardclients jedoch nicht: 

- Einstellungen für Teamanruf verwalten

- Stellvertretungen verwalten

- Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario)

- Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde

- Hohes Anrufaufkommen verwalten

- Anruf an eine Reaktionsgruppe initiieren

- Anruf parken

- Begrüßung ändern

- Gruppenanrufannahme

### <a name="online-or-hybrid-user-account-limitations"></a>Einschränkungen für Onlinebenutzerkonten oder hybride Benutzerkonten
<a name="Online-Hybrid"> </a>

Benutzerkonten können entweder online oder lokal vorhanden sein, und das wirkt sich auf die Features aus, die diesem Benutzer zur Verfügung stehen. Benutzer mit Konten auf Skype for Business Online haben auch mit dem Client mit vollem Funktionsumfang keinen Zugriff auf die folgenden Features: 

- Erweiterte Anwesenheit: Foto von einer beliebigen öffentlichen Site für „Mein Bild“ verwenden

- Kontakte: Nach Reaktionsgruppen suchen

- Chatunterstützung: Integration des beständigen Chats (Gruppen-Chats)

- Chatunterstützung: Beständigen Chatroom mit einem Klick zu einer Skype for Business-Besprechung eskalieren

- Externe Benutzer: Anrufe mit zwei oder mehr Teilnehmern mit externen Benutzern durchführen

## <a name="see-also"></a>Siehe auch
<a name="Types"> </a>

[Plan für Clients und Geräte](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Letzte Updates für Skype for Business-Versionen, die Windows Installer (MSI) verwenden](../../SfbServer/sfb-client-updates.md)
