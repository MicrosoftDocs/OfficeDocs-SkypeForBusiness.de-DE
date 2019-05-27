---
title: Vergleich von Desktop-Client-Features für Skype for Business Server 2019
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Zusammenfassung: Skype for Business Server 2019 oder Skype for Business Online-Administratoren können diese Tabellen verwenden, um zu verstehen, welche Features für welche Clients unterstützt werden.'
ms.openlocfilehash: e26c5020f780542a890b9016057171c59a3eee32
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280570"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Vergleich von Desktop-Client-Features für Skype for Business Server 2019

**Zusammenfassung:** Skype for Business Server 2019 oder Skype for Business Online-Administratoren können diese Tabellen verwenden, um zu verstehen, welche Features für welche Clients unterstützt werden.

 Überprüfen Sie vor der Bereitstellung oder dem Upgrade auf Skype for Business Server, welche Clients bereits in Ihrer Organisation verwendet werden. Verwenden Sie die nachstehenden Tabellen, um zu verstehen, wie sich die Funktionsunterstützung auf diese Clients auswirkt. Dann können Sie den Benutzern die Änderungen vermitteln sowie das Tempo des Rollouts bestimmen und die Vorteile des Upgrades auf den neuesten Client in vollem Umfang verstehen.

Einige der in Skype for Business Server 2019 verfügbaren Funktionen stehen in Skype for Business Online nicht zur Verfügung. Einzelheiten finden Sie unter [Einschränkungen für Online-oder Hybrid Benutzerkonten](feature-comparison.md#Online-Hybrid) . Skype for Business Online-Administratoren möchten möglicherweise auf die [Beschreibung des Skype for Business Online-Diensts](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) verweisen, um Informationen zu den unterschiedlichen Plänen zu erhalten, die Ihnen zur Verfügung stehen.

In den folgenden Tabellen sind die Features aufgeführt, die für jeden Client verfügbar sind, der mit Skype for Business Server 2019 oder Skype for Business Online funktioniert. Möglicherweise möchten Sie auch den [Vergleich der Features für mobile Clients für Skype for Business](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) für Smartphone-und Tablet-Client-Feature-Vergleiche besprechen. Die Client Zugriffslizenz oder die Benutzerabonnementlizenz, die Ihre Organisation kauft, wirkt sich auch auf die für die Benutzer verfügbaren Features aus. Ob Sie den vollständigen oder einfachen Client für Benutzer bereitstellen, hängt von der Lizenz oder dem Plan ab, den Ihre Organisation zum Kauf auswählt. Weitere Informationen finden Sie im [Lizenzierungs Handbuch](https://products.office.com/en-us/skype-for-business/it-pros) .

> [!IMPORTANT]
> Skype for Business Server 2019 und Skype for Business Online unterstützen die folgenden zuvor veröffentlichten Clients: lync 2013, Skype for Business 2015 und Skype for Business 2016 sowie den Skype for Business 2019-Client. Informationen zu diesen Clients, wenn Sie mit anderen Servern verwendet werden, finden Sie in den [Client Vergleichstabellen für lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) und [Vergleich der Desktop Client-Features für Skype for Business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> Der Skype for Business Web App-Browser-Client und die APP für die Windows 10-App für Skype-Besprechungen bieten nur [Unterstützung](feature-comparison.md#BKMK_Conferencing)für Besprechungen. Weitere Informationen zu diesen Clients finden Sie unter [Plan for Meetings clients (Web App and Meetings App)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md).

## <a name="enhanced-presence-support"></a>Unterstützung für erweiterte Anwesenheitsinformationen
<a name="BKMK_EnhancedPresence"> </a>

Diese Tabelle enthält die erweiterten Anwesenheitsfunktionen, die über die einfache Angabe hinausgehen, ob Benutzer online, offline, beschäftigt usw. sind. 


| Feature/Funktion                                                                                  | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Status veröffentlichen                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Status anzeigen                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Statushinweise und Abwesenheitsnotizen anzeigen                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Benutzerdefinierten Standort hinzufügen                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Benutzerdefinierte Notiz hinzufügen                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Verwenden eines Fotos von einer beliebigen öffentlichen Site für „Mein Bild“  <br/> (nicht verfügbar in Skype for Business Online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776;  Unterstützt den Veröffentlichungsstatus nicht basierend auf den Frei/Gebucht-Informationen des Kalenders.

## <a name="contacts-and-contact-groups-support"></a>Unterstützung für Kontakte und Kontaktgruppen
<a name="BKMK_Contacts"> </a>

Diese Tabelle enthält die Funktionen im Zusammenhang mit der Verwaltung von Chatkontakten und Kontakten mit Anwesenheitsfunktionen. 


| Feature/Funktion                                                                            | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Bereits ausgefüllte Liste „Kontakte“                                                                   | &#x2714;                                      |                           |                  |
| Liste „Kontakte“ anzeigen und ändern                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kontakte für Statusänderungsbenachrichtigungen markieren                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Private Beziehungen verwalten                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Unternehmensadressbuch durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Microsoft Outlook-Kontakte durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kontaktgruppen verwalten                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Verteilergruppen und Office 365-Gruppen erweitern                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Nach Reaktionsgruppen suchen  <br/> (nicht verfügbar in Skype for Business Online)                | &#x2714;                                      |                           | &#x2714;         |
| Gruppe „Letzte Kontakte“ anzeigen                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Gruppe „Aktuelle Unterhaltungen“ anzeigen                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Alternative Kontaktansichten anzeigen (z. B. Kachelansicht)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Sortieren von Kontakten nach Gruppe, Beziehung oder neu (Personen, die Sie zu Ihrer Kontaktliste hinzugefügt haben) | &#x2714;                                      |                           | &#x2714;         |
| Kontakte nach Status (Verfügbarkeit) sortieren                                                        | &#x2714;                                      |                           | &#x2714;         |
| Exchange-Kontakte suchen und hinzufügen                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Chatunterstützung
<a name="BKMK_IMSupport"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Chatunterstützung.

|Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Chatnachricht oder E-Mail an Kontakt initiieren  |&#x2714;|&#x2714;|&#x2714;|  
|In einem einzelnen Fenster mit Registerkarten zwischen mehreren Chats navigieren bzw. mehrere Unterhaltungen verfolgen   |&#x2714;|&#x2714;|&#x2714;| 
|Chatunterhaltungen in Outlook protokollieren  |&#x2714;|&#x2714; Wenn der serverseitige Konversations Verlauf aktiviert ist   |&#x2714;|   
|Rechtschreibung überprüfen |&#x2714;|&#x2714;||   
|Qualifikationssuche (mit SharePoint Server-Integration)   <br/> (Lokale Skype for Business-Server und lokale SharePoint 2013 sind für die Skill-Suche erforderlich.)  |&#x2714;||&#x2714;|
|Integration des beständigen Chats (Gruppen-Chats)   <br/> (nicht verfügbar für Skype for Business Online)|&#x2714;||&#x2714;|  
|Beständigen Chatroom mit einem Klick zu einer Skype for Business-Besprechung eskalieren   <br/> (nicht verfügbar für Skype for Business Online) |&#x2714;||&#x2714;| 
|Inlinebilder von Absender und Empfänger im Chatfenster |&#x2714;||&#x2714;| 
|Freihandnachrichten empfangen |&#x2714;||&#x2714;| 
|„Hohe Priorität“ für Chatnachrichten festlegen |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Unterstützung für Besprechungen
<a name="BKMK_Conferencing"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für Besprechungen.

> [!NOTE]
>  Skype for Business-Besprechungsfunktionen stehen in Skype for Business Online Standalone Plan 1 nicht zur Verfügung.  Plan 1 wird eingestellt [](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

In Skype-zu-Skype-Sitzungen können Benutzer mit Skype for Business Online-Plan 1 an Desktopfreigabe- und Anwendungsfreigabesitzungen teilnehmen, wenn sie von anderen Benutzern dazu eingeladen werden, die über Zugriff auf Freigabefunktionen verfügen.
Einzelheiten hierzu finden Sie in der [Beschreibung des Skype for Business Online-Diensts](https://technet.microsoft.com/library/jj822172.aspx). 

|Feature/Funktion | Skype for Business 2016-Client | Skype for Business auf dem Mac | Skype for Business Web App | Skype for Business 2015-Client | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Computeraudio hinzufügen  |&#x2714;|&#x2714;|& # x2714; (erfordert Plug-in)  |&#x2714;|&#x2714;| 
|Video hinzufügen |&#x2714;|&#x2714;|& # x2714; (erfordert Plug-in) |&#x2714;|&#x2714;| 
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung    |&#x2714;|&#x2714;|&#x2714; Nur anzeigen   ||| 
|Steuerelemente für Referenten in Besprechungen verwenden |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Auf detaillierte Teilnehmerliste der Besprechung zugreifen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|An Chats mit mehreren Teilnehmern teilnehmen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Desktop freigeben (sofern aktiviert)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (erfordert Plug-in) |&#x2714;| &#x2714;|
|Programm freigeben (sofern aktiviert) |&#x2714;|Nur anzeigen   |& # x2714; (erfordert Plug-in)  |&#x2714;|&#x2714;|   
|Anonyme Teilnehmer hinzufügen (sofern aktiviert) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahl-Audio-Besprechungen & # x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Besprechung mit „Jetzt besprechen“ initiieren|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren |&#x2714;| &#x2778; Anmerkungen sind nicht verfügbar   |&#x2714;|&#x2714;|&#x2714;| 
|In Microsoft PowerPoint-Dateien navigieren |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|OneNote-Besprechungsnotizen hinzufügen und bearbeiten  |&#x2714;||Nur bearbeiten (nicht hinzufügen)  |&#x2714;|&#x2714;|
|Whiteboard verwenden |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Umfragen durchführen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Dateien zur gemeinsamen Verwendung mit anderen hochladen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen |Outlook oder Skype for Business Web Scheduler  |Outlook oder Skype for Business Web Scheduler |Skype for Business Web Scheduler |Outlook oder Skype for Business Web Scheduler   |Outlook-oder lync Web Scheduler |  
|Q&amp;A Manager |&#x2714;|||||
|Teilnehmervideo deaktivieren |&#x2714;||&#x2714;|||
|Besprechungschat deaktivieren |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer stummschalten |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Alle zu Teilnehmern machen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Skype Meeting Broadcast erstellen |&#x2714;|||||
|Planen von Besprechungen im Namen des Delegierenden durch die Stellvertretung |&#x2714;|&#x2714;|&#x2714;|||
|Stellvertretungen zwischen Skype for Business und Outlook synchronisieren |&#x2714;||&#x2714;|&#x2714;|| 
|Videospotlight festlegen (Video sperren) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Steuerung der Bildschirmübertragung übergeben/übernehmen  |&#x2714;||&#x2714;|||

 &#x2776;  Teilnehmer können keine Desktops steuern, die von Skype for Business für Mac, lync für Mac 2011 oder Communicator für Mac 2011-Benutzer freigegeben werden. Skype for Business für Mac, lync für Mac 2011 und Communicator für Mac 2011-Benutzer können keine Desktops steuern, die von Windows-Benutzern freigegeben werden. Das funktioniert auch bei Skype for Business Web App auf Max OSX nicht.

 &#x2777;  Für Skype for Business Online erfordert dieses Feature Microsoft PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.

 &#x2778;  Der lync für Mac 2011-Client kann Microsoft Office 2013 PowerPoint-Präsentationen nicht anzeigen, wenn Sie von der Skype for Business Web App in einer Konferenz freigegeben wurden.

&#x2779;  Für Skype for Business 2016-apps müssen Sie Klick-und-Los, Build 16.0.4227 oder höher verwenden.

&#x2780;  Für Skype for Business 2015-apps müssen Sie über das September-Update, Build 15.0.4747 oder höher verfügen.

## <a name="voice-telephony-support"></a>Unterstützung für VoIP (Telefonie)
<a name="BKMK_Telephony"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für VoIP-Dienste.

> [!NOTE]
> Skype for Business-Sprachfeatures (Telefonie) sind auf bestimmte Skype for Business Online-Abonnement Pläne limitiert. Einzelheiten hierzu finden Sie in der [Beschreibung des Skype for Business Online-Diensts](https://technet.microsoft.com/library/jj822172.aspx). 

 | Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----| 
|Anruf initiieren |&#x2714;|&#x2714;|&#x2714;|
|Kontakt per Mausklick anrufen |&#x2714;|&#x2714;|&#x2714;|
|Anrufdurchstellung |&#x2714;|&#x2714;|&#x2714;|  
|Anrufweiterleitung verwalten |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Einstellungen für Teamanrufe verwalten |&#x2714;||&#x2714; &#x2776; |
|Stellvertretungen verwalten |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Anruf an eine Reaktionsgruppe initiieren|&#x2714;||&#x2714; &#x2776; |
|Unterstützung für Notrufe (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Chat Benachrichtigung an SIP-URI (s) für E-911-Anruf |&#x2714;|&#x2714;|&#x2714;|
|Chat Benachrichtigung in Verteilerliste für E-911-Anruf|&#x2714;|&#x2714;|&#x2714;|
|Mit Voicemail verbinden, Begrüßung einrichten oder ändern |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Benachrichtigung über verpasste Anrufe |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertretung-Szenario) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Anrufe eines anderen Benutzers verwalten, wenn eine Stellvertretung konfiguriert ist |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anruf parken |&#x2714;||&#x2714; &#x2776; |
|Gruppenanrufannahme |&#x2714;||&#x2714; &#x2776; |
|Standortbasiertes Routing |&#x2714;|&#x2714;|&#x2714;| 
|Reaktionsgruppe/Teamanrufgruppe verwalten |&#x2714;||&#x2714;|

 &#x2776;  Diese Funktion steht in Skype for Business Online nicht zur Verfügung.

## <a name="external-users-support"></a>Unterstützung für externe Benutzer
<a name="BKMK_ExternalUsers"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für externe Benutzer, die im PSTN verwaltet werden.


|Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Chat mit öffentlichem Kontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Chat mit Partnerkontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Anrufe mit zwei oder mehr Teilnehmern mit externen Benutzern durchführen   <br/> (nicht verfügbar in Skype for Business Online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Aufzeichnungsunterstützung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für das Aufzeichnen von Besprechungen.

| Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |   
|:-----|:-----|:-----|:-----|  
|Clientseitige Aufzeichnung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Clientseitige Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Bevorzugte Auflösung für die Aufzeichnung auswählen  |&#x2714;||&#x2714;|

 &#x2776;  Die Aufzeichnung steht in einigen eigenständigen Skype for Business Online-Plänen nicht zur Verfügung. Für die Aufzeichnungsfunktion ist Vollzugriff auf den Skype for Business-Client erforderlich.

 &#x2777;  Die Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen steht in Skype for Business Online nicht zur Verfügung.

## <a name="modern-authentication"></a>Moderne Authentifizierung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Funktionen, die Unterstützung für moderne Authentifizierung erfordern. 

Die moderne Authentifizierung erfordert auch eine Topologie, die in Skype for Business-Topologien beschrieben ist, die [mit moderner Authentifizierung unterstützt werden](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md).


 | Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Moderne Authentifizierung |&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung |& # x2714; (nur Domänen verbundenes Gerät) |&#x2714;|& # x2714; (nur Domänen verbundenes Gerät)  |
|Kerberos-Authentifizierung |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Unterstützung für Archivierung, Compliance und Protokollierung
<a name="BKMK_Archiving"> </a>

Diese Tabelle enthält Features, die sich auf die Unterstützung von Archivierungs-und Protokollierungsfunktionen beziehen.


 | Feature/Funktion | Skype for Business 2015, 2016 oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Archivieren von Chat Unterhaltungen im Outlook-Konversations Verlauf|&#x2714; &#x2776; |&#x2714; Wenn der serverseitige Konversations Verlauf aktiviert ist  |&#x2714; &#x2776; | 
|Client seitige Archivierung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Client seitige Archivierung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen (nicht verfügbar in Skype for Business Online)  |&#x2714;||&#x2714;|
|Zugriff auf Anmelde Protokolle aus dem Skype for Business-Symbol in der Taskleiste |&#x2714;||&#x2714;|

 &#x2776;  Für Skype for Business Online-Benutzer erfordert dieses Feature Exchange Online und wird vom Exchange-Postfach des Benutzers in-situ-Speicher-Attribut gesteuert.

## <a name="client-limitations"></a>Client Einschränkungen
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Grundlegende Einschränkungen für Clients
<a name="Full-Basic"> </a>

Die folgenden Features sind mit dem vollständigen Client verfügbar und sind für den Standard Client nicht verfügbar: 

- Einstellungen für Teamanrufe verwalten

- Stellvertretungen verwalten

- Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertretung-Szenario)

- Anrufe eines anderen Benutzers verwalten, wenn eine Stellvertretung konfiguriert ist

- Verwalten einer großen Anzahl von Anrufen

- Anruf an eine Reaktionsgruppe initiieren

- Anruf parken

- Grußformel ändern

- Gruppenanrufannahme

### <a name="online-or-hybrid-user-account-limitations"></a>Einschränkungen für Online-oder Hybrid Benutzerkonten
<a name="Online-Hybrid"> </a>

Benutzerkonten können entweder online oder lokal vorhanden sein und sich auf die für diesen Benutzer verfügbaren Features auswirken. Benutzer mit Konten in Skype for Business Online haben keinen Zugriff auf die folgenden Funktionen, auch nicht mit dem vollständigen Client: 

- Erweiterte Anwesenheitsinformationen: Verwenden eines Fotos von einer öffentlichen Website für mein Bild

- Kontakte: Suchen nach Antwortgruppen

- Chat-Unterstützung: beständiger Chat (Gruppen-Chat)-Integration

- Chat-Unterstützung: eskalieren eines beständigen Chatrooms zu einer Skype for Business-Besprechung mit nur einem Mausklick

- Externe Benutzer: Durchführen von zwei-oder Mehrparteiengesprächen mit externen Benutzern

## <a name="see-also"></a>Siehe auch
<a name="Types"> </a>

[Planen für Clients und Geräte](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Letzte Updates für Skype for Business-Versionen, die Windows Installer (MSI) verwenden](../../SfbServer/sfb-client-updates.md)
