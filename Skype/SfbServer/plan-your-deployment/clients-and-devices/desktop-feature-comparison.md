---
title: Vergleich der Desktopclientfeatures für Skype for Business Server 2015
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
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
description: 'Zusammenfassung: Skype for Business Server 2015 oder Skype for Business Onlineadministratoren können diese Tabellen verwenden, um zu verstehen, welche Features auf welchen Clients unterstützt werden.'
ms.openlocfilehash: c3c7e8a744f678a1453c52f57f7d97ae96cb0588cf6bc416ad04007a35eeba6f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318818"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Vergleich der Desktopclientfeatures für Skype for Business Server 2015

**Zusammenfassung:** Skype for Business Server 2015 oder Skype for Business Onlineadministratoren können diese Tabellen verwenden, um zu verstehen, welche Features auf welchen Clients unterstützt werden.
  
 Überprüfen Sie vor der Bereitstellung oder dem Upgrade auf Skype for Business, welche Clients bereits in Ihrer Organisation verwendet werden. Verwenden Sie die folgenden Tabellen, um die Auswirkungen der Featureunterstützung auf diese Clients zu verstehen. Dies kann Ihnen helfen, Änderungen an die Benutzer zu kommunizieren, den Rolloutvorgang zu beschleunigen und die Vorteile des Upgrades auf den neuesten Client vollständig zu verstehen.
  
Einige features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Onlineadministratoren können unter [Skype for Business Onlinedienstbeschreibung](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description) Informationen zu den verschiedenen verfügbaren Plänen finden.

Unter Vergleich der [Desktopclientfeatures für Skype for Business 2019](../../../SfBServer2019/plan/feature-comparison.md) finden Sie Informationen zur Clientunterstützung am Skype for Business Server 2019.
  
In den folgenden Tabellen sind die Features aufgeführt, die für jeden Client verfügbar sind, der mit Skype for Business Server 2015 oder Skype for Business Online funktioniert. Möglicherweise möchten Sie auch auf den Vergleich der [Mobilen Clientfeatures für Skype for Business](mobile-feature-comparison.md) für Vergleiche von Smart Phone- und Tablet-Clientfeatures verweisen. Die Clientzugriffslizenz oder Benutzerabonnementlizenz, die Ihre Organisation erwirbt, wirkt sich auch darauf aus, welche Features Ihren Benutzern zur Verfügung stehen. Ob Sie den vollständigen oder einfachen Client für Benutzer bereitstellen, hängt von der Lizenz oder dem Plan ab, den Ihre Organisation kauft. Weitere Informationen finden Sie im [Lizenzierungshandbuch.](https://products.office.com/skype-for-business/it-pros)
  
> [!IMPORTANT]
> Skype for Business Server 2015 und Skype for Business Online unterstützen die folgenden zuvor veröffentlichten Clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Telefon Edition und Lync 2010 Attendant. Informationen zu diesen Clients bei Verwendung mit anderen Servern finden Sie in den [Clientvergleichstabellen für Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables) und [clientvergleichstabellen für Lync Server 2010.](/previous-versions/office/skype-server-2010/gg425836(v=ocs.14))

> [!NOTE]
> Der **Lync 2010-Telefonzentralenclient** wird in Skype for Business Online nicht unterstützt.

> [!NOTE]
> Der Skype for Business-Web-App Browserclient und Skype Besprechungs-App Windows 10-App bieten nur [Besprechungsunterstützung.](desktop-feature-comparison.md#BKMK_Conferencing) Weitere Informationen zu diesen Clients finden Sie unter [Planen von Besprechungsclients (Web App und Besprechungs-App).](meetings-clients.md)
  
## <a name="enhanced-presence-support"></a>Erweiterte Anwesenheitsunterstützung

<a name="BKMK_EnhancedPresence"> </a>

Diese Tabelle enthält die Erweiterten Anwesenheitsfunktionen, die über eine einfache Angabe hinausgehen, ob ein Benutzer online, offline, beschäftigt usw. ist.
  
|Feature/Funktion|Skype for Business 2015- oder 2016-Client|Skype for Business auf dem Mac|Lync 2013-Client|Lync Windows Store-App|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator für Mac 2011|Lync für Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Veröffentlichungsstatus |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Anzeigen des Status   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Statushinweise und Abwesenheitsnotizen anzeigen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Benutzerdefinierten Standort hinzufügen |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Eigene Notiz hinzufügen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Verwenden eines Fotos von einer beliebigen öffentlichen Website für "Mein Bild" (nicht verfügbar in Skype for Business Online) |&#x2714;||&#x2714;|||||||

 &#x2776; Unterstützt nicht den Veröffentlichungsstatus basierend auf Frei/Gebucht-Kalenderinformationen.
  
## <a name="contacts-and-contact-groups-support"></a>Unterstützung für Kontakte und Kontaktgruppen

<a name="BKMK_Contacts"> </a>

In dieser Tabelle werden die Features im Zusammenhang mit der Verwaltung von Chat- und Anwesenheitskontakten behandelt.

|Feature/Funktion|Skype for Business 2015- oder 2016-Client|Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Vorab ausgefüllte Kontaktliste |&#x2714;|||||||||
|Anzeigen und Ändern der Kontaktliste |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Private Beziehungen verwalten |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Unternehmensadressbuch durchsuchen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft Outlook-Kontakte durchsuchen |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Kontaktgruppen verwalten |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Erweitern von Verteilergruppen und Microsoft 365-Gruppen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Nach Reaktionsgruppen suchen  <br/> (in Skype for Business Online nicht verfügbar) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Gruppe "Letzte Kontakte" anzeigen |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Gruppe "Aktuelle Unterhaltungen" anzeigen |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Alternative Kontaktansichten anzeigen (z. B. Kachelansicht) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sortieren von Kontakten nach Gruppe, Beziehung oder Neu (Personen, die Sie zu ihrer Kontaktliste hinzugefügt haben) |&#x2714;||&#x2714;|Sortieren nach Gruppe |&#x2714;|&#x2714;||||
|Sortieren von Kontakten nach Status (Verfügbarkeit) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Suchen und Hinzufügen von Exchange Kontakten |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Chatunterstützung

<a name="BKMK_IMSupport"> </a>

In dieser Tabelle werden Features im Zusammenhang mit der Chatunterstützung behandelt.

|Feature/Funktion | Skype for Business 2015- oder 2016-Client | Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Chat mit oder E-Mail an einen Kontakt initiieren |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Navigieren zwischen mehreren Chatunterhaltungen/Nachverfolgen mehrerer Unterhaltungen in einem einzigen Fenster mit Registerkarten |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Sofortnachrichtenunterhaltungen in Outlook protokollieren |&#x2714;|&#x2714;Wenn der serverseitige Unterhaltungsverlauf aktiviert ist  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Gespeichert in Communicator für Mac |Gespeichert in Lync für Mac |
|Vorbereitete Unterhaltungsvorlagen verwenden |||||&#x2714;|&#x2714;||||
|Rechtschreibprüfung |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Qualifikationssuche (mit SharePoint Serverintegration)  <br/> (Lokale Skype for Business Server und lokale SharePoint 2013 sind für die Qualifikationssuche erforderlich.) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Integration des beständigen Chats (Gruppenchat)  <br/> (nicht für Skype for Business Online verfügbar) |&#x2714;||&#x2714;|||||||
|Eskalieren eines Chatrooms für beständigen Chat zu einer Skype for Business Besprechung mit einem Klick  <br/> (nicht für Skype for Business Online verfügbar) |&#x2714;||&#x2714;|||||||
|Inlinebilder von Absender und Empfänger im Chatfenster |&#x2714;||&#x2714;|&#x2714;||||||
|Freihandnachrichten senden ||||&#x2714;||||||
|Empfangen von Freihandnachrichten |&#x2714;||&#x2714;|&#x2714;||||||
|Festlegen von Chatnachrichten mit hoher Wichtigkeit |&#x2714;||&#x2714;|||||||
|Übertragen von Dateien in Peer-to-Peer-Chatunterhaltungen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Unterstützung von Besprechungen

<a name="BKMK_Conferencing"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Unterstützung von Besprechungen.
  
> [!NOTE]
> Skype for Business Besprechungsfeatures sind in Skype for Business eigenständigen Onlineplan 1 nicht verfügbar.  Plan 1 wird [eingestellt.](../../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement.md)

In Skype-zu-Skype-Sitzungen kann ein Benutzer von Skype for Business Onlineplan 1 an der Desktopfreigabe und Anwendungsfreigabe teilnehmen, wenn er von einem Benutzer eingeladen wird, der Zugriff auf Freigabefeatures hat.
Ausführliche Informationen finden Sie in der [Skype for Business Onlinedienstbeschreibung.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
  
|Feature/Funktion | Skype for Business 2016-Client | Skype for Business auf dem Mac | Skype for Business Web App | Skype for Business 2015-Client | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Computeraudiofunktionen hinzufügen |&#x2714;|&#x2714;|&#x2714;(Plug-In erforderlich) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video hinzufügen |&#x2714;|&#x2714;|&#x2714;(erfordert Plug-In) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Videobasierte Bildschirmübertragung |&#x2714;|&#x2714;|&#x2714;Schreibgeschützt |||||||||
|Steuerelemente für Referenten in Besprechungen verwenden |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Auf detaillierte Besprechungsliste zugreifen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Desktop freigeben (sofern aktiviert) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (erfordert Plug-In) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Programm freigeben (sofern aktiviert) |&#x2714;|Nur Ansicht   |&#x2714;(erfordert Plug-In) |&#x2714;|&#x2714;||&#x2714;||||Nur Ansicht |
|Anonyme Teilnehmer hinzufügen (sofern aktiviert) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Verwenden von Einwahlaudiobesprechungen |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Initiieren einer Sofortbesprechung |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren |&#x2714;| &#x2778; Anmerkungen nicht verfügbar |&#x2714;|&#x2714;|&#x2714;|Nur vorhanden |&#x2714;|||| nur &#x2778; Ansicht, Anmerkungen nicht verfügbar |
|Navigieren in Microsoft PowerPoint-Dateien |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Hinzufügen und Bearbeiten OneNote Besprechungsnotizen |&#x2714;||Nur bearbeiten (nicht hinzufügen) |&#x2714;|&#x2714;|||||||
|Whiteboard verwenden |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Abstimmungen durchführen |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Hochladen dateien für andere Personen freigeben |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Besprechung oder Konferenz planen |Outlook oder Skype for Business Web Scheduler |Outlook oder Skype for Business Web Scheduler |Skype for Business Web Scheduler |Outlook oder Skype for Business Web Scheduler |Outlook oder Lync Web Scheduler |Outlook oder Lync Web Scheduler |Outlook ||||Outlook |
|F &amp; A-Manager |&#x2714;|||||||||||
|Deaktivieren des Teilnehmervideos|&#x2714;||&#x2714;|||||||||
 | |Deaktivieren von Chatnachrichten für Besprechungen  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Stummschalten der Zielgruppe   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Machen Sie jeden zum Teilnehmer |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Erzeugen von Skype-Besprechung Broadcast  |&#x2714;|||||||||||
|Stellvertretung kann eine Besprechung im Namen des Delegators planen  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Synchronisieren von Delegaten zwischen Skype for Business und Outlook |&#x2714;||&#x2714;|||||||||
|Video-Spotlight festlegen (Video sperren) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Steuerung der Bildschirmfreigabe erteilen/übernehmen |&#x2714;||&#x2714;|||||||||

 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business für Mac-, Lync für Mac 2011- oder Communicator für Mac 2011-Benutzer freigegeben werden. Skype for Business für Mac, Lync für Mac 2011 und Communicator für Mac 2011 können Benutzer keine Desktops steuern, die von Windows Benutzern freigegeben wurden. Dies funktioniert auch nicht für Skype for Business-Web-App auf Max OSX.
  
 &#x2777; Für Skype for Business Online erfordert dieses Feature Microsoft PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.
  
 &#x2778; Der Lync für Mac 2011-Client kann Microsoft Office 2013 PowerPoint Präsentationen nicht anzeigen, wenn sie von der Skype for Business-Web-App in einer Konferenz freigegeben wurden.
  
## <a name="voice-telephony-support"></a>Sprachunterstützung (Telefonie)

<a name="BKMK_Telephony"> </a>

Diese Tabelle enthält Funktionen im Zusammenhang mit der Unterstützung von VoIP-Diensten.
  
> [!NOTE]
> Skype for Business Die VoIP-Funktionen (Telefonie) sind auf bestimmte Skype for Business Online-Abonnementpläne beschränkt. Ausführliche Informationen finden Sie in der [Skype for Business Onlinedienstbeschreibung.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
  
| Feature/Funktion | Skype for Business 2015- oder 2016-Client | Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Initiieren eines Anrufs |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontakt durch Mausklick anrufen  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Anrufweiterleitung verwalten |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Einstellungen für Teamanruf verwalten |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Verwalten von Stellvertretungen |&#x2714;|&#x2714;erfordert Skype for Business Server 2015 CU4 oder höher |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Anruf an eine Reaktionsgruppe initiieren |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Unterstützen von Notrufdiensten (E-911)  |&#x2714;|&#x2714;erfordert Skype for Business Server 2015 CU6 oder höher |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Chatbenachrichtigung an SIP-URI(s) für E-911-Anrufe |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Chatbenachrichtigung an Verteilerliste für E-911-Anruf |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Verbinden zu Voicemail, Einrichten oder Ändern der Begrüßung |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Benachrichtigung über verpasste Anrufe |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Hohes Anrufaufkommen verwalten |||||&#x2714;|&#x2714;||||
|Anrufe parken  |&#x2714;||&#x2714; &#x2776; |||||||
|Gruppenanrufannahme  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Standortbasierte Weiterleitung  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Verwalten von Reaktionsgruppen-/Teamanrufgruppen |&#x2714;||&#x2714;|||||||
|Automatische Telefonzentralenanruf annehmen |&#x2714;||&#x2714;|||||||

&#x2776; Dieses Feature ist in Skype for Business Online nicht verfügbar.
  
## <a name="external-users-support"></a>Unterstützung für externe Benutzer

<a name="BKMK_ExternalUsers"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Unterstützung für externe Benutzer, die im PSTN verwaltet werden.

|Feature/Funktion | Skype for Business 2015- oder 2016-Client | Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sofortnachricht mit öffentlichem Kontakt initiieren  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Sofortnachricht mit Partnerkontakt initiieren |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Anrufe mit zwei oder mehr Teilnehmern mit externen Benutzern durchführen  <br/> (in Skype for Business Online nicht verfügbar) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Unterstützung von Aufzeichnungen

<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Unterstützung für die Aufzeichnung von Besprechungen.
  
| Zukunft/Funktion** | Skype for Business 2015- oder 2016-Client | Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Clientseitige Aufzeichnung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Clientseitige Aufzeichnung von Dateiübertragungen, freigegebenen OneNote Seiten und PowerPoint Anmerkungen |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Auswählen der bevorzugten Auflösung der Aufzeichnung |&#x2714;||&#x2714;|||||||

 &#x2776; Aufzeichnung ist in bestimmten eigenständigen Skype for Business Online-Plänen nicht verfügbar. Die Aufzeichnung erfordert vollständige Skype for Business Clientrechte.
  
 &#x2777; Aufzeichnung von Dateiübertragungen, freigegebenen OneNote Seiten und PowerPoint Anmerkungen ist in Skype for Business Online nicht verfügbar.
  
## <a name="modern-authentication"></a>Moderne Authentifizierung

<a name="BKMK_Recording"> </a>

Diese Tabelle enthält Features, die Unterstützung für die moderne Authentifizierung erfordern.
  
Für die moderne Authentifizierung ist auch eine Topologie erforderlich, die in Skype for Business topologien beschrieben ist, [die mit moderner Authentifizierung unterstützt werden.](../../plan-your-deployment/modern-authentication/topologies-supported.md)

| Feature/Funktion | Skype for Business 2015- oder 2016-Client | Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator für Mac 2011 | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Moderne Authentifizierung |&#x2714;|&#x2714;|&#x2714;|||||||
|Mehrstufige Authentifizierung  |&#x2714;|&#x2714;|&#x2714;|||||||
|Zertifikatbasierte Authentifizierung  |&#x2714;(nur In die Domäne eingebundenes Gerät)| &#x2714;|&#x2714;(nur In die Domäne eingebundenes Gerät)  |||||||
|Kerberos-Authentifizierung |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Archivierungs-, Compliance- und Protokollierungsunterstützung

<a name="BKMK_Archiving"> </a>

Diese Tabelle enthält Features im Zusammenhang mit der Unterstützung von Archivierungs- und Protokollierungsfunktionen.

| Feature/Funktion | Skype for Business 2015- oder 2016-Client | Skype for Business auf dem Mac | Lync 2013-Client | Lync Windows Store-App | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator für Mac 2011** | Lync für Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archivierung von Chatunterhaltungen im Outlook Unterhaltungsverlauf |&#x2714; &#x2776; |&#x2714;Wenn der serverseitige Unterhaltungsverlauf aktiviert ist |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Gespeichert in Communicator für Mac |Gespeichert in Lync für Mac |
|Clientseitige Archivierung von Audio, Video, Anwendungsfreigabe, Desktopfreigabe und hochgeladenen Inhalten |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Clientseitige Archivierung von Dateiübertragungen, freigegebenen OneNote Seiten und PowerPoint Anmerkungen  <br/> (in Skype for Business Online nicht verfügbar)|&#x2714;||&#x2714;||&#x2714;|||||
|Zugreifen auf Anmeldeprotokolle über Skype for Business Symbol in der Taskleiste |&#x2714;||&#x2714;|||||||

 &#x2776; Für Skype for Business Onlinebenutzer erfordert dieses Feature Exchange Online und wird durch das Exchange Postfach In-Place Hold-Attribut des Benutzers gesteuert.
  
## <a name="client-limitations"></a>Clienteinschränkungen

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Einschränkungen für Basisclients

<a name="Full-Basic"> </a>

Die folgenden Features sind mit dem vollständigen Client verfügbar und nicht mit dem Standardclient verfügbar:

- Einstellungen für Teamanruf verwalten
- Verwalten von Stellvertretungen
- Anrufe eines anderen Benutzers verwalten, wenn eine Delegierung konfiguriert wurde
- Hohes Anrufaufkommen verwalten
- Anruf an eine Reaktionsgruppe initiieren
- Anrufe parken
- Begrüßung ändern
- Gruppenanrufannahme
- E-Mails über verpasste Anrufe werden nicht generiert, wenn ein Benutzerstatus UM deaktiviert ist und sie einen älteren Outlook-Client (2013 oder früher) verwenden.

### <a name="online-or-hybrid-user-account-limitations"></a>Einschränkungen für Online- oder Hybridbenutzerkonten

<a name="Online-Hybrid"> </a>

Benutzerkonten können entweder online oder lokal vorhanden sein, was sich auf die für diesen Benutzer verfügbaren Features auswirkt. Benutzer mit Konten auf Skype for Business Online haben keinen Zugriff auf die folgenden Features, auch nicht mit dem vollständigen Client:
  
- Erweiterte Anwesenheit: Verwenden eines Fotos von einer beliebigen öffentlichen Website für "Mein Bild"
- Kontakte: Suchen nach Reaktionsgruppen
- Chatunterstützung: Integration des beständigen Chats (Gruppenchat)
- Chatunterstützung: Eskalieren eines Chatrooms für beständigen Chat zu einer Skype for Business Besprechung mit einem Klick
- Externe Benutzer: Durchführen von Anrufen mit zwei oder mehr Teilnehmern mit externen Benutzern

## <a name="see-also"></a>Siehe auch

<a name="Types"> </a>

[Planen von Clients und Geräten](clients-and-devices.md)

[Neueste Updates für Versionen von Skype for Business, die Windows Installer (MSI) verwenden](../../sfb-client-updates.md)