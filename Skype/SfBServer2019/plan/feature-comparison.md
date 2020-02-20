---
title: Vergleich der Desktop-Clientfunktionen für Skype for Business Server 2019
ms.author: v-lanac
author: LanaChin
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
description: 'Zusammenfassung: Skype for Business Server 2019 oder Skype for Business Online Administratoren können diese Tabellen verwenden, um zu verstehen, welche Features auf welchen Clients unterstützt werden.'
ms.openlocfilehash: f8b50614d663104e1307b233449ccffc0e26adb5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129488"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Vergleich der Desktop-Clientfunktionen für Skype for Business Server 2019

**Zusammenfassung:** Skype for Business Server 2019 oder Skype for Business Online Administratoren können diese Tabellen verwenden, um zu verstehen, welche Features auf welchen Clients unterstützt werden.

 Überprüfen Sie vor dem bereitstellen oder Aktualisieren auf Skype for Business Server, welche Clients in Ihrer Organisation bereits verwendet werden. Verwenden Sie die folgenden Tabellen, um die Auswirkungen der Funktionsunterstützung auf diese Clients zu verstehen. Dies kann Ihnen helfen, Änderungen an Benutzern zu kommunizieren, den Roll-out-Prozess zu beschleunigen und die Vorteile des Upgrades auf den neuesten Client vollständig zu verstehen.

Einige Funktionen, die mit Skype for Business Server 2019 verfügbar sind, sind in Skype for Business Online nicht verfügbar; siehe [Einschränkungen für Online-oder Hybrid Benutzerkonten](feature-comparison.md#Online-Hybrid) für spezifische Informationen. Skype for Business Online-Administratoren möchten möglicherweise auf [Skype for Business Online Dienstbeschreibung](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) Bezug nehmen, um Informationen zu den verschiedenen verfügbaren Plänen zu erhalten.

In den folgenden Tabellen sind die Features aufgeführt, die für jeden Client verfügbar sind, der mit Skype for Business Server 2019 oder Skype for Business Online arbeitet. Möglicherweise möchten Sie auch auf den [Vergleich des mobilen Clientfeatures für Skype for Business](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) für Smartphone-und Tablet-Client Feature Vergleiche Bezug nehmen. Die Client Zugriffs-oder Benutzerabonnementlizenz, die Ihre Organisation kauft, wirkt sich auch auf die Funktionen aus, die Ihren Benutzern zur Verfügung stehen. Unabhängig davon, ob Sie den vollständigen oder einfachen Client für die Benutzer bereitstellen, hängt von der Lizenz oder dem Plan ab, den Ihre Organisation zum Kauf auswählt. Weitere Informationen finden Sie im [Lizenzierungs Handbuch](https://products.office.com/skype-for-business/it-pros) .

> [!IMPORTANT]
> Skype for Business Server 2019 und Skype for Business Online unterstützen die folgenden zuvor veröffentlichten Clients: lync 2013, Skype for Business 2015 und Skype for Business 2016, sowie den Skype for Business 2019-Client. Informationen zu diesen Clients, wenn Sie mit anderen Servern verwendet werden, finden Sie unter [Client comparison tables for lync Server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) and [Desktop Client Feature Comparison for Skype for Business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> Der Skype for Business-Webanwendungs-Browserclient und die Skype-Besprechungs-APP Windows 10 bieten nur [Unterstützung für Besprechungen](feature-comparison.md#BKMK_Conferencing). Weitere Informationen zu diesen Clients erhalten Sie unter [Planen von Besprechungs Clients (Webanwendung und Besprechungs-APP)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) .

## <a name="enhanced-presence-support"></a>Erweiterte Anwesenheits Unterstützung
<a name="BKMK_EnhancedPresence"> </a>

In dieser Tabelle werden die erweiterten Anwesenheitsfunktionen behandelt, die über einen einfachen Hinweis darauf hinausgehen, ob ein Benutzer online, offline, beschäftigt usw. ist. 


| Feature/Funktion                                                                                  | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Veröffentlichungsstatus                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Anzeigestatus                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Statushinweise und Abwesenheitsnotizen anzeigen                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Benutzerdefinierten Standort hinzufügen                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Eigene Notiz hinzufügen                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Verwenden eines Fotos von einer öffentlichen Website für "mein Bild"  <br/> (nicht verfügbar in Skype for Business Online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776; unterstützt den Veröffentlichungsstatus nicht basierend auf Frei/Gebucht-Kalenderinformationen.

## <a name="contacts-and-contact-groups-support"></a>Unterstützung für Kontakte und Kontaktgruppen
<a name="BKMK_Contacts"> </a>

In dieser Tabelle werden die Features im Zusammenhang mit der Verwaltung von Chat-und Anwesenheits Kontakten behandelt. 


| Feature/Funktion                                                                            | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Vorab aufgefüllte Kontaktliste                                                                   | &#x2714;                                      |                           |                  |
| Anzeigen und Ändern der Kontaktliste                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Private Beziehungen verwalten                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Unternehmensadressbuch durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Microsoft Outlook-Kontakte durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kontaktgruppen verwalten                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Erweitern von Verteilergruppen und Office 365 Gruppen                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Nach Reaktionsgruppen suchen  <br/> (nicht verfügbar in Skype for Business Online)                | &#x2714;                                      |                           | &#x2714;         |
| Gruppe "Letzte Kontakte" anzeigen                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Gruppe "Aktuelle Unterhaltungen" anzeigen                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Alternative Kontaktansichten anzeigen (z. B. Kachelansicht)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Sortieren von Kontakten nach Gruppe, Beziehung oder neu (Personen, die Sie zu Ihrer Kontaktliste hinzugefügt haben) | &#x2714;                                      |                           | &#x2714;         |
| Sortieren von Kontakten nach Status (Verfügbarkeit)                                                        | &#x2714;                                      |                           | &#x2714;         |
| Suchen und Hinzufügen von Exchange-Kontakten                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Chat Unterstützung
<a name="BKMK_IMSupport"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Chat Unterstützung.

|Feature/Funktion | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Initiieren von Chatnachrichten mit oder e-Mail an einen Kontakt  |&#x2714;|&#x2714;|&#x2714;|  
|Navigieren zwischen mehreren Chat Unterhaltungen/Nachverfolgen mehrerer Unterhaltungen in einem einzelnen Registerkartenfenster   |&#x2714;|&#x2714;|&#x2714;| 
|Sofortnachrichtenunterhaltungen in Outlook protokollieren  |&#x2714;|&#x2714;, wenn serverseitiger Unterhaltungsverlauf aktiviert ist   |&#x2714;|   
|Rechtschreibprüfung |&#x2714;|&#x2714;||   
|Skill Search (mit SharePoint Server Integration)  <br/> (Lokale Skype for Business Server und lokale SharePoint 2013 sind für die qualifikationssuche erforderlich.)  |&#x2714;||&#x2714;|
|Integration des beständigen Chats (Gruppenchat)  <br/> (nicht verfügbar für Skype for Business Online)|&#x2714;||&#x2714;|  
|Eskalieren eines beständigen Chatrooms zu einer Skype for Business Besprechung mit einem Mausklick  <br/> (nicht verfügbar für Skype for Business Online) |&#x2714;||&#x2714;| 
|Inline Bilder von Absender und Empfänger im Chatfenster |&#x2714;||&#x2714;| 
|Empfangen von frei Hand Meldungen |&#x2714;||&#x2714;| 
|Festlegen von Chatnachrichten als hohe Wichtigkeit |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Besprechungs Unterstützung
<a name="BKMK_Conferencing"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung von Besprechungen.

> [!NOTE]
>  Skype for Business besprechungsfeatures stehen in Skype for Business Online eigenständigen Plan 1 nicht zur Verfügung.  Plan 1 wird [zurückgezogen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

In Skype-zu-Skype-Sitzungen kann ein Skype for Business Online Plan 1-Benutzer an der Desktopfreigabe und Anwendungsfreigabe teilnehmen, wenn er von einem Benutzer eingeladen wird, der Zugriff auf Freigabefunktionen hat.
Ausführliche Informationen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx). 

|Feature/Funktion | Skype for Business 2016-Client | Skype for Business auf dem Mac | Skype for Business Web App | Skype for Business 2015-Client | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Computeraudiofunktionen hinzufügen  |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  |&#x2714;|&#x2714;| 
|Video hinzufügen |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in) |&#x2714;|&#x2714;| 
|Video mit mehreren Teilen anzeigen (Galerieansicht)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung    |&#x2714;|&#x2714;|Nur &#x2714; Ansicht   ||| 
|Steuerelemente für Referenten in Besprechungen verwenden |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Auf detaillierte Besprechungsliste zugreifen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Desktop freigeben (sofern aktiviert)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (erfordert Plug-in) |&#x2714;| &#x2714;|
|Programm freigeben (sofern aktiviert) |&#x2714;|Nur Ansicht   |&#x2714; (erfordert Plug-in)  |&#x2714;|&#x2714;|   
|Anonyme Teilnehmer hinzufügen (sofern aktiviert) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahl Audiokonferenzen &#x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Initiieren einer Sofortbesprechung|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren |&#x2714;| &#x2778; Anmerkungen nicht verfügbar   |&#x2714;|&#x2714;|&#x2714;| 
|Navigieren in Microsoft PowerPoint Dateien |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|OneNote-Besprechungsnotizen hinzufügen und bearbeiten  |&#x2714;||Nur bearbeiten (nicht hinzufügen)  |&#x2714;|&#x2714;|
|Whiteboard verwenden |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Abstimmungen durchführen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Hochladen von Dateien, die für andere Personen freigegeben werden |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen |Outlook-oder Skype for Business-Webplaner  |Outlook-oder Skype for Business-Webplaner |Skype for Business-Webplaner |Outlook-oder Skype for Business-Webplaner   |Outlook-oder lync-Webplaner |  
|Q&amp;ein Manager |&#x2714;|||||
|Video für Teilnehmer deaktivieren |&#x2714;||&#x2714;|||
|Besprechungs-Chat deaktivieren |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Benutzergruppe stumm schalten |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Jeder als Teilnehmer festlegen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Erstellen von Skype-Live Konferenz |&#x2714;|||||
|Delegieren kann eine Besprechung im Auftrag von "delegater" planen |&#x2714;|&#x2714;|&#x2714;|||
|Synchronisieren von Stellvertretungen zwischen Skype for Business und Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|Video Spotlight festlegen (Video sperren) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Zuweisen/übernehmen der Bildschirmfreigabe Steuerung  |&#x2714;||&#x2714;|||

 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business auf Mac, lync für Mac 2011 oder Communicator für Mac 2011-Benutzer gemeinsam verwendet werden. Skype for Business auf Mac, lync für Mac 2011 und Communicator für Mac 2011 können Benutzer keine Desktops steuern, die von Windows-Benutzern gemeinsam verwendet werden. Dies funktioniert auch nicht für Skype for Business-Webanwendung auf Max OSX.

 &#x2777; für Skype for Business Online erfordert dieses Feature Microsoft-PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.

 &#x2778; der Client für lync für Mac 2011 kann Microsoft Office 2013 PowerPoint-Präsentationen nicht anzeigen, wenn Sie von der Skype for Business-Webanwendung in einer Konferenz freigegeben wurden.

&#x2779; für Skype for Business 2016-apps müssen Sie Klick-und-Los, Build 16.0.4227 oder höher verwenden.

&#x2780; für Skype for Business 2015-apps benötigen Sie das September-Update, Build 15.0.4747 oder höher.

## <a name="voice-telephony-support"></a>Sprachunterstützung (Telefonie)
<a name="BKMK_Telephony"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung von Sprachdiensten.

> [!NOTE]
> Skype for Business Sprachfeatures (Telefonie) sind auf bestimmte Skype for Business Online Abonnement Pläne limitiert. Ausführliche Informationen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx). 

 | Feature/Funktion | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----| 
|Initiieren eines Anrufs |&#x2714;|&#x2714;|&#x2714;|
|Kontakt durch Mausklick anrufen |&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten |&#x2714;|&#x2714;|&#x2714;|  
|Anrufweiterleitung verwalten |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Einstellungen für Teamanruf verwalten |&#x2714;||&#x2714; &#x2776; |
|Verwalten von Stellvertretungen |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Anruf an eine Reaktionsgruppe initiieren|&#x2714;||&#x2714; &#x2776; |
|Support Emergency Services (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Chat Benachrichtigung zu SIP-URI (n) für E-911-Anruf |&#x2714;|&#x2714;|&#x2714;|
|Chat Benachrichtigung an Verteilerliste für E-911-Anruf|&#x2714;|&#x2714;|&#x2714;|
|Herstellen einer Verbindung mit Voicemail, einrichten oder Ändern der Begrüßung |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Benachrichtigung über verpasste Anrufe |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anrufe parken |&#x2714;||&#x2714; &#x2776; |
|Gruppenanrufannahme |&#x2714;||&#x2714; &#x2776; |
|Standortbasierte Weiterleitung |&#x2714;|&#x2714;|&#x2714;| 
|Verwalten der Reaktionsgruppe/Team anrufgruppe |&#x2714;||&#x2714;|

 &#x2776; dieses Feature ist in Skype for Business Online nicht verfügbar.

## <a name="external-users-support"></a>Unterstützung externer Benutzer
<a name="BKMK_ExternalUsers"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für externe Benutzer, die im PSTN verwaltet werden.


|Feature/Funktion | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Sofortnachricht mit öffentlichem Kontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Sofortnachricht mit Partnerkontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Anrufe mit zwei oder mehr Teilnehmern mit externen Benutzern durchführen  <br/> (nicht verfügbar in Skype for Business Online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Aufnahme Unterstützung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung für die Aufzeichnung von Besprechungen.

| Feature/Funktion | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |   
|:-----|:-----|:-----|:-----|  
|Client seitige Aufzeichnung von Audio-, Video-, Anwendungsfreigaben, Desktopfreigabe und hochgeladenen Inhalten |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Client seitige Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Bevorzugte Aufzeichnungs Auflösung auswählen  |&#x2714;||&#x2714;|

 &#x2776; Aufzeichnung steht in bestimmten Skype for Business Online eigenständigen Plänen nicht zur Verfügung. Für die Aufzeichnung ist eine vollständige Skype for Business Client Rechte erforderlich.

 &#x2777; Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen ist in Skype for Business Online nicht verfügbar.

## <a name="modern-authentication"></a>Moderne Authentifizierung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Features, die Unterstützung für die moderne Authentifizierung erfordern. 

Die moderne Authentifizierung erfordert auch eine Topologie, die in Skype for Business Topologien beschrieben ist, die [mit moderner Authentifizierung unterstützt werden](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md).


 | Feature/Funktion | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Moderne Authentifizierung |&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung |&#x2714; (nur Domäne-registriertes Gerät) |&#x2714;|&#x2714; (nur Domäne-registriertes Gerät)  |
|Kerberos-Authentifizierung |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Unterstützung bei Archivierung, Compliance und Protokollierung
<a name="BKMK_Archiving"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung von Archivierungs-und Protokollierungsfunktionen.


 | Feature/Funktion | Skype for Business 2015-, 2016-oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Archivieren von Chatnachrichten Unterhaltungen im Outlook-Unterhaltungsverlauf|&#x2714; &#x2776; |&#x2714;, wenn serverseitiger Unterhaltungsverlauf aktiviert ist  |&#x2714; &#x2776; | 
|Client seitige Archivierung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Client seitige Archivierung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen (nicht verfügbar in Skype for Business Online)  |&#x2714;||&#x2714;|
|Zugriff auf Anmelde Protokolle über Skype for Business Symbol in der Taskleiste |&#x2714;||&#x2714;|

 &#x2776; für Skype for Business Online Benutzer erfordert dieses Feature Exchange Online und wird durch das in-situ-Speicher-Attribut des Exchange-Postfachs des Benutzers gesteuert.

## <a name="client-limitations"></a>Client Einschränkungen
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Einschränkungen für Basisclients
<a name="Full-Basic"> </a>

Die folgenden Features stehen mit dem vollständigen Client zur Verfügung und sind mit dem Basis Client nicht verfügbar: 

- Einstellungen für Teamanruf verwalten

- Verwalten von Stellvertretungen

- Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario)

- Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde

- Hohes Anrufaufkommen verwalten

- Anruf an eine Reaktionsgruppe initiieren

- Anrufe parken

- Begrüßung ändern

- Gruppenanrufannahme

### <a name="online-or-hybrid-user-account-limitations"></a>Einschränkungen für Online-oder Hybrid Benutzerkonten
<a name="Online-Hybrid"> </a>

Benutzerkonten können entweder online oder lokal vorhanden sein und sich auf die für diesen Benutzer verfügbaren Features auswirken. Benutzer mit Konten auf Skype for Business Online haben keinen Zugriff auf die folgenden Funktionen, auch nicht mit dem vollständigen Client: 

- Erweiterte Anwesenheit: Verwenden eines Fotos von einer öffentlichen Website für "mein Bild"

- Kontakte: Suchen nach Reaktionsgruppen

- Chat Unterstützung: Integration von beständigen Chats (Gruppenchat)

- Chat Unterstützung: eskalieren eines beständigen Chatrooms zu einer Skype for Business Besprechung mit einem Mausklick

- Externe Benutzer: Durchführen von Anrufen mit zwei oder mehr Teilnehmern mit externen Benutzern

## <a name="see-also"></a>Siehe auch
<a name="Types"> </a>

[Planen von Clients und Geräten](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Neueste Updates für Versionen von Skype for Business, die Windows Installer (MSI) verwenden](../../SfbServer/sfb-client-updates.md)
