---
title: Vergleich der Desktopclientfeatures für Skype for Business Server 2019
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Skype for Business Server 2019- oder Skype for Business Online-Administratoren können diese Tabellen verwenden, um zu verstehen, welche Funktionen auf welchen Clients unterstützt werden.'
ms.openlocfilehash: 9fcc86f59943ef770947b8311952b03f213d268b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808715"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Vergleich der Desktopclientfeatures für Skype for Business Server 2019

**Zusammenfassung:** Skype for Business Server 2019- oder Skype for Business Online-Administratoren können diese Tabellen verwenden, um zu verstehen, welche Funktionen auf welchen Clients unterstützt werden.

 Überprüfen Sie vor dem Bereitstellen oder Upgrade auf Skype for Business Server, welche Clients bereits in Ihrer Organisation verwendet werden. Verwenden Sie die folgenden Tabellen, um die Auswirkungen der Featureunterstützung auf diese Clients zu verstehen. Dies kann Ihnen helfen, Änderungen an die Benutzer zu kommunizieren, das Tempo des Rolloutprozesses zu ändern und die Vorteile eines Upgrades auf den neuesten Client vollständig zu verstehen.

Einige features available with Skype for Business Server 2019 are not available in Skype for Business Online; Weitere [Informationen finden Sie unter Einschränkungen des Online- oder Hybridbenutzerkontos.](feature-comparison.md#Online-Hybrid) Skype for Business Online Admins können informationen zu den verschiedenen verfügbaren Plänen in der [Skype for Business](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) Online -Dienstbeschreibung finden.

In den folgenden Tabellen sind die Features dargestellt, die für jeden Client verfügbar sind, der mit Skype for Business Server 2019 oder Skype for Business Online verwendet werden kann. Sie können sich auch auf den Vergleich der [Funktionen des mobilen](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) Clients für Skype for Business für Smart Phone- und Tablet-Client-Funktionsvergleiche beziehen. Die Clientzugriffslizenz oder Benutzerabonnementlizenz, die Ihre Organisation erwirbt, hat auch Auswirkungen darauf, welche Features ihren Benutzern zur Verfügung stehen. Ob Sie den vollständigen oder einfachen Client für Benutzer bereitstellen, hängt von der Lizenz oder dem Plan ab, den Ihre Organisation kauft. Weitere Informationen [finden Sie im Lizenzierungshandbuch.](https://products.office.com/skype-for-business/it-pros)

> [!IMPORTANT]
> Skype for Business Server 2019 und Skype for Business Online unterstützen die folgenden zuvor veröffentlichten Clients: Lync 2013, Skype for Business 2015 und Skype for Business 2016 sowie den Skype for Business 2019-Client. Informationen zu diesen Clients bei Verwendung mit anderen Servern finden Sie in den Clientvergleichstabellen für [Lync Server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) und desktopclient feature [comparison for Skype for Business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> Der Skype for Business Web App-Browserclient und die Windows 10-App für Skype-Besprechungen bieten nur [Besprechungsunterstützung.](feature-comparison.md#BKMK_Conferencing) Weitere Informationen zu diesen Clients finden Sie unter "Planen von [Besprechungen"-Clients (Web App](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) und Besprechungs-App).

## <a name="enhanced-presence-support"></a>Erweiterte Anwesenheitsunterstützung
<a name="BKMK_EnhancedPresence"> </a>

In dieser Tabelle werden die Features für erweiterte Anwesenheitsinformationen behandelt, die über einen einfachen Hinweis hinausgehen, ob ein Benutzer online, offline, beschäftigt usw. ist. 


| Feature/Funktion                                                                                  | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Veröffentlichungsstatus                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Anzeigen des Status                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Statushinweise und Abwesenheitsnotizen anzeigen                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Benutzerdefinierten Standort hinzufügen                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Eigene Notiz hinzufügen                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Verwenden eines Fotos von einer beliebigen öffentlichen Website für "Mein Bild"  <br/> (nicht verfügbar in Skype for Business Online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776; unterstützt den Veröffentlichungsstatus nicht basierend auf Frei/Gebucht-Kalenderinformationen.

## <a name="contacts-and-contact-groups-support"></a>Unterstützung für Kontakte und Kontaktgruppen
<a name="BKMK_Contacts"> </a>

In dieser Tabelle werden die Features im Zusammenhang mit der Verwaltung von Kontakten für Im- und Anwesenheitsfunktionen behandelt. 


| Feature/Funktion                                                                            | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Vordefinierte Kontaktliste                                                                   | &#x2714;                                      |                           |                  |
| Anzeigen und Ändern der Kontaktliste                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Private Beziehungen verwalten                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Unternehmensadressbuch durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Microsoft Outlook-Kontakte durchsuchen                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Kontaktgruppen verwalten                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Erweitern von Verteilergruppen und Microsoft 365-Gruppen                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Nach Reaktionsgruppen suchen  <br/> (nicht verfügbar in Skype for Business Online)                | &#x2714;                                      |                           | &#x2714;         |
| Gruppe "Letzte Kontakte" anzeigen                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Gruppe "Aktuelle Unterhaltungen" anzeigen                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Alternative Kontaktansichten anzeigen (z. B. Kachelansicht)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Sortieren von Kontakten nach Gruppe, Beziehung oder Neu (Personen, die Sie zu ihrer Kontaktliste hinzugefügt haben) | &#x2714;                                      |                           | &#x2714;         |
| Sortieren von Kontakten nach Status (Verfügbarkeit)                                                        | &#x2714;                                      |                           | &#x2714;         |
| Suchen und Hinzufügen von Exchange-Kontakten                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Unterstützung von Im-Hilfe-En
<a name="BKMK_IMSupport"> </a>

In dieser Tabelle werden Features im Zusammenhang mit der Unterstützung von Verbindungen behandelt.

|Feature/Funktion | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Initiieren von Nachrichten mit oder E-Mail an einen Kontakt  |&#x2714;|&#x2714;|&#x2714;|  
|Navigieren zwischen mehreren Chatunterhaltungen/Nachverfolgen mehrerer Unterhaltungen in einem einzigen Fenster mit Registerkarten   |&#x2714;|&#x2714;|&#x2714;| 
|Sofortnachrichtenunterhaltungen in Outlook protokollieren  |&#x2714;|&#x2714; Wenn der serverseitige Unterhaltungsverlauf aktiviert ist   |&#x2714;|   
|Rechtschreibung überprüfen |&#x2714;|&#x2714;||   
|Qualifikationssuche (mit SharePoint Server-Integration)  <br/> (Für die Qualifikationssuche sind lokale Skype for Business Server- und lokale SharePoint 2013-Server erforderlich.)  |&#x2714;||&#x2714;|
|Integration von beständigen Chat (Gruppenchat)  <br/> (nicht verfügbar für Skype for Business Online)|&#x2714;||&#x2714;|  
|Eskalieren eines Chatrooms für beständigen Chat zu einer Skype for Business-Besprechung mit nur einem Klick  <br/> (nicht verfügbar für Skype for Business Online) |&#x2714;||&#x2714;| 
|Inlinebilder des Absenders und Empfängers im Fenster "Im Nachrichten" |&#x2714;||&#x2714;| 
|Empfangen von Freihandnachrichten |&#x2714;||&#x2714;| 
|Festlegen von Nachrichten mit hoher Wichtigkeit |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Support für Besprechungen
<a name="BKMK_Conferencing"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Besprechungsunterstützung.

> [!NOTE]
>  Skype for Business-Besprechungsfeatures sind im eigenständigen Skype for Business Online Plan 1 nicht verfügbar.  Plan 1 wird [eingestellt.](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
)

In Skype-zu-Skype-Sitzungen kann ein Skype for Business Online Plan 1-Benutzer an der Desktopfreigabe und Anwendungsfreigabe teilnehmen, wenn er von einem Benutzer eingeladen wird, der Zugriff auf Freigabefunktionen hat.
Ausführliche Informationen finden Sie in der [Skype for Business Online-Dienstbeschreibung.](https://technet.microsoft.com/library/jj822172.aspx) 

|Feature/Funktion | Skype for Business 2016-Client | Skype for Business auf dem Mac | Skype for Business Web App | Skype for Business 2015-Client | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Computeraudiofunktionen hinzufügen  |&#x2714;|&#x2714;|&#x2714;(erfordert Plug-In)  |&#x2714;|&#x2714;| 
|Video hinzufügen |&#x2714;|&#x2714;|&#x2714;(erfordert Plug-In) |&#x2714;|&#x2714;| 
|Video mit mehrerenPartys anzeigen (Katalogansicht)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung    |&#x2714;|&#x2714;|&#x2714; A0   ||| 
|Steuerelemente für Referenten in Besprechungen verwenden |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Auf detaillierte Besprechungsliste zugreifen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Desktop freigeben (sofern aktiviert)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (erfordert Plug-In) |&#x2714;| &#x2714;|
|Programm freigeben (sofern aktiviert) |&#x2714;|Nur Ansicht   |&#x2714;(erfordert Plug-In)  |&#x2714;|&#x2714;|   
|Anonyme Teilnehmer hinzufügen (sofern aktiviert) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahlaudiobesprechungen &#x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Initiieren einer Sofortsitzung|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren |&#x2714;| &#x2778; Anmerkungen nicht verfügbar   |&#x2714;|&#x2714;|&#x2714;| 
|Navigieren in Microsoft PowerPoint-Dateien |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Hinzufügen und Bearbeiten von OneNote-Besprechungsnotizen  |&#x2714;||Nur bearbeiten (nicht hinzufügen)  |&#x2714;|&#x2714;|
|Whiteboard verwenden |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Abstimmungen durchführen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Hochladen von Dateien für die Freigabe für andere |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen |Outlook oder Skype for Business Web Scheduler  |Outlook oder Skype for Business Web Scheduler |Skype for Business Web Scheduler |Outlook oder Skype for Business Web Scheduler   |Outlook oder Lync Web Scheduler |  
|&amp;F-A-Manager |&#x2714;|||||
|Teilnehmervideo deaktivieren |&#x2714;||&#x2714;|||
|Deaktivieren von Besprechungsbenachrichtigungen |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Stummschalten der Zielgruppe |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Machen Sie jeden zu einem Teilnehmer |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Erzeugen von Skype Meeting Broadcast |&#x2714;|||||
|Stellvertretung kann eine Besprechung im Auftrag eines Stellvertreters planen |&#x2714;|&#x2714;|&#x2714;|||
|Synchronisieren von Stellvertretung zwischen Skype for Business und Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|Festlegen von Video spotlight (Sperrvideo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Übernehmen/Übernehmen der Steuerung der Bildschirmfreigabe  |&#x2714;||&#x2714;|||

 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business für Mac-, Lync für Mac 2011- oder Communicator für Mac 2011-Benutzer freigegeben werden. Benutzer von Skype for Business für Mac, Lync für Mac 2011 und Communicator für Mac 2011 können keine Desktops steuern, die von Windows-Benutzern gemeinsam genutzt werden. Dies funktioniert auch nicht für Skype for Business Web App unter Max OSX.

 &#x2777; für Skype for Business Online erfordert diese Funktion Microsoft PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.

 &#x2778; Der Lync für Mac 2011-Client kann Microsoft Office 2013 -PowerPoint-Präsentationen nicht anzeigen, wenn sie in einer Konferenz von skype for Business Web App freigegeben wurden.

&#x2779; Für Skype for Business 2016-Apps müssen Sie Klick-und-Ausführen, Build 16.0.4227 oder höher verwenden.

&#x2780; Für Skype for Business 2015-Apps müssen Sie über das SeptemberUpdate, Build 15.0.4747 oder höher, verfügen.

## <a name="voice-telephony-support"></a>Sprachunterstützung (Telefonie)
<a name="BKMK_Telephony"> </a>

In dieser Tabelle werden Features im Zusammenhang mit der Unterstützung von Sprachdiensten behandelt.

> [!NOTE]
> Die Funktionen von Skype for Business Voice (Telefonie) sind auf bestimmte Skype for Business Online-Abonnementpläne beschränkt. Ausführliche Informationen finden Sie in der [Skype for Business Online-Dienstbeschreibung.](https://technet.microsoft.com/library/jj822172.aspx) 

 | Feature/Funktion | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----| 
|Initiieren eines Anrufs |&#x2714;|&#x2714;|&#x2714;|
|Kontakt durch Mausklick anrufen |&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten |&#x2714;|&#x2714;|&#x2714;|  
|Anrufweiterleitung verwalten |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Einstellungen für Teamanruf verwalten |&#x2714;||&#x2714; &#x2776; |
|Verwalten von Stellvertretungen |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Anruf an eine Reaktionsgruppe initiieren|&#x2714;||&#x2714; &#x2776; |
|Unterstützen von Notrufdiensten (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Benachrichtigung über E-Mail-Benachrichtigungen an SIP-URI(n) für E-911-Anrufe |&#x2714;|&#x2714;|&#x2714;|
|Benachrichtigung über Eine Nachricht an verteilerliste für E-911-Anrufe|&#x2714;|&#x2714;|&#x2714;|
|Herstellen einer Verbindung mit Voicemail, Einrichten oder Ändern der Begrüßung |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Benachrichtigung über verpasste Anrufe |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Anrufe parken |&#x2714;||&#x2714; &#x2776; |
|Gruppenanrufannahme |&#x2714;||&#x2714; &#x2776; |
|Standortbasierte Weiterleitung |&#x2714;|&#x2714;|&#x2714;| 
|Reaktionsgruppe/Teamanrufgruppe verwalten |&#x2714;||&#x2714;|

 &#x2776; Diese Funktion ist in Skype for Business Online nicht verfügbar.

## <a name="external-users-support"></a>Unterstützung für externe Benutzer
<a name="BKMK_ExternalUsers"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Unterstützung für externe Benutzer, die im Telefonnetz (PSTN) gespeichert sind.


|Feature/Funktion | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Sofortnachricht mit öffentlichem Kontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Sofortnachricht mit Partnerkontakt initiieren |&#x2714;|&#x2714;|&#x2714;| 
|Anrufe mit zwei oder mehr Teilnehmern mit externen Benutzern durchführen  <br/> (nicht verfügbar in Skype for Business Online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Aufzeichnungsunterstützung
<a name="BKMK_Recording"> </a>

In dieser Tabelle werden Features im Zusammenhang mit der Unterstützung für die Aufzeichnung von Besprechungen behandelt.

| Feature/Funktion | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |   
|:-----|:-----|:-----|:-----|  
|Clientseitige Aufzeichnung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Clientseitige Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Auswählen der bevorzugten Aufzeichnungsauflösung  |&#x2714;||&#x2714;|

 &#x2776; Aufzeichnung ist in bestimmten eigenständigen Skype for Business Online-Plänen nicht verfügbar. Die Aufzeichnung erfordert vollständige Skype for Business-Clientrechte.

 &#x2777; Aufzeichnung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen ist in Skype for Business Online nicht verfügbar.

## <a name="modern-authentication"></a>Moderne Authentifizierung
<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Features, die Unterstützung für die moderne Authentifizierung erfordern. 

Die moderne Authentifizierung erfordert auch eine Topologie, die in [Skype for Business-Topologien](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md)beschrieben wird, die mit moderner Authentifizierung unterstützt werden.


 | Feature/Funktion | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client | 
|:-----|:-----|:-----|:-----|  
|Moderne Authentifizierung |&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung |&#x2714;(nur In die Domäne eingetretenes Gerät) |&#x2714;|&#x2714;(nur In die Domäne eingetretenes Gerät)  |
|Kerberos-Authentifizierung |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Archivierungs-, Kompatibilitäts- und Protokollierungsunterstützung
<a name="BKMK_Archiving"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Unterstützung von Archivierungs- und Protokollierungsfunktionen.


 | Feature/Funktion | Skype for Business 2015-, 2016- oder 2019-Client | Skype for Business auf dem Mac | Lync 2013-Client |  
|:-----|:-----|:-----|:-----|  
|Archivierung von Chatunterhaltungen im Unterhaltungsverlauf von Outlook|&#x2714; &#x2776; |&#x2714; Wenn der serverseitige Unterhaltungsverlauf aktiviert ist  |&#x2714; &#x2776; | 
|Clientseitige Archivierung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Clientseitige Archivierung von Dateiübertragungen, freigegebenen OneNote-Seiten und PowerPoint-Anmerkungen (in Skype for Business Online nicht verfügbar)  |&#x2714;||&#x2714;|
|Zugreifen auf Anmeldeprotokolle über das Skype for Business-Symbol in der Taskleiste |&#x2714;||&#x2714;|

 &#x2776; Für Skype for Business Online-Benutzer erfordert diese Funktion Exchange Online und wird vom In-Place A0 des Benutzers gesteuert.

## <a name="client-limitations"></a>Clienteinschränkungen
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Einschränkungen für Basisclients
<a name="Full-Basic"> </a>

Die folgenden Features sind mit dem vollständigen Client verfügbar und nicht mit dem Basic-Client: 

- Einstellungen für Teamanruf verwalten

- Verwalten von Stellvertretungen

- Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario)

- Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde

- Hohes Anrufaufkommen verwalten

- Anruf an eine Reaktionsgruppe initiieren

- Anrufe parken

- Ändern der Begrüßung

- Gruppenanrufannahme

### <a name="online-or-hybrid-user-account-limitations"></a>Online- oder Hybridbenutzerkontoeinschränkungen
<a name="Online-Hybrid"> </a>

Benutzerkonten können entweder online oder lokal vorhanden sein, und dies wirkt sich auf die Features aus, die diesem Benutzer zur Verfügung stehen. Benutzer mit Konten in Skype for Business Online haben keinen Zugriff auf die folgenden Funktionen, auch nicht mit dem vollständigen Client: 

- Erweiterte Anwesenheit: Verwenden eines Fotos von einer beliebigen öffentlichen Website für "Mein Bild"

- Kontakte: Suchen nach Reaktionsgruppen

- Chatunterstützung: Integration des beständigen Chats (Gruppenchat)

- Chatunterstützung: Eskalieren eines Chatrooms für beständigen Chat zu einer Skype for Business-Besprechung mit nur einem Klick

- Externe Benutzer: Anrufe mit zwei oder mehreren Parteien mit externen Benutzern durchführen

## <a name="see-also"></a>Siehe auch
<a name="Types"> </a>

[Planen von Clients und Geräten](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Neueste Updates für Skype for Business-Versionen, die Windows Installer (MSI) verwenden](../../SfbServer/sfb-client-updates.md)
