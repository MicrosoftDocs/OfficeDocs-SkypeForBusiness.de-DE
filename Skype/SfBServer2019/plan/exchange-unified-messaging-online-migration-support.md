---
title: Migrationsunterstützung für Exchange Unified Messaging Online
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft gibt den Exchange Unified Messaging Online (ExchUMO)-Dienst bis zum 28. Februar 2020 zurück. In diesem Artikel wird zusammengefasst, was betroffene Kunden wissen und tun sollten, um ihre Geschäftskontinuität zu planen.
ms.openlocfilehash: 4da55c9004224c68e4e65c56038c5491fac5a0ab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116513"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Migrationsunterstützung für Exchange Unified Messaging Online

> [!IMPORTANT]
> **Der Unified Messaging-Dienst in Exchange Online ist ab dem 28. Februar 2020 um 17:00 Uhr Pazifischer Zeit nicht mehr unterstützt. Alle Voicemailkonten wurden von Microsoft zum Cloud Voicemaildienst migriert. Der verbleibende Datenverkehr der automatischen Attendant wird nicht überwacht und kann jederzeit unterbrochen werden.**

In Bezug [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) auf die Ankündigung vom 8. Februar 2019 gibt Microsoft den Exchange Unified Messaging Online (ExchUMO)-Dienst bis zum 28. Februar 2020 zurück. Dieser Artikel enthält eine Zusammenfassung der Informationen, die betroffene Kunden kennen und tun sollten, um ihre Geschäftskontinuität zu planen.

ExchUMO wird von Kunden für Voicemail, automatische Telefonkonferenz, Anrufwarteschlange und Faxintegrationsdienste bereitgestellt. Microsoft plant, Kunden bei der Migration zu Telefonsystemdiensten zu unterstützen, die bereits Tausende von Kunden in Skype for Business Online und Microsoft Teams unterstützen.

Voicemail ist in erster Linie eine von Microsoft gesteuerte Migration. Für eine Teilmenge von Kunden ist möglicherweise eine Administratorbeteiligung und/oder Investition erforderlich. Bei der automatischen Attendant handelt es sich um eine vom Administrator gesteuerte Migration. Sie müssen die vorhandenen automatischen ExchUMO-Attendantenstrukturen im Cloud- automatische Telefonzentrale neu erstellen. Kunden, die eine der ExchUMO-Funktionen mit einer Nebenstellenanlage eines Drittanbieters nutzen, werden nicht zu Skype-Clouddiensten migriert, da sie keine Nebenstellenanlagen von Drittanbietern unterstützen. In diesem Blog wurde ein Vorsorgeplan für den Drittanbietersupport [angekündigt,](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)und Kunden in diesem Bereitstellungsmodell können ihre Benutzer zu einer der Unified Communications-Plattformen/-Dienste von Microsoft migrieren oder eine Voicemail- und/oder automatische Telefonielösung eines Drittanbieters für diese Benutzer erwerben. Die Faxintegration wird in den cloudbasierten Diensten nicht unterstützt. Kunden müssen zu einer Drittanbieterlösung migrieren.

## <a name="who-is-affected"></a>Wer ist betroffen?

Kunden, die eines der folgenden Features des Exchange Unified Messaging Online-Diensts verwenden, sind betroffen:

- Voicemaildienst
- automatische Telefonzentrale-Dienst
- Anrufwarteschlangedienst
- Faxintegration

> [!Note]
> Kunden, die einen der Exchange Server mit Unified Messaging verwenden, sind davon nicht betroffen.

Erfahren Sie mehr über die Auswirkungen der Benutzer- und Administratorerfahrung auf [die Benutzererfahrung.](#user-experience-impact)

## <a name="migration-plan-overview"></a>Übersicht über den Migrationsplan

Microsoft hat verschiedene Kundenbereitstellungen identifiziert, die Features von ExchUMO nutzen, und unterstützt Kunden bei der Migration basierend auf dem folgenden Plan.

|Kundengruppe |Zeitachse  |Details  |
|---------|---------|---------|
|Kunden, die für die Migration bereit sind<br><br>Zu migrierende Features:<br><ul><li>Voicemail</ul>   |   März – Mai 2019  |Beispiele:<ul><li>    Kunden mit einfacher Voicemailbereitstellung und -verwendung<li>Kunden, die alle Anforderungen für Microsoft zum Ausführen der Migration festgelegt haben<ul>|
|Kunden mit Voraussetzungen<br><br>Zu migrierende Features:<br><ul><li>Voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschlange</ul> |  Mai – Dezember 2019 |Beispiele: <br><ul><li>Hybridkonfiguration ist nicht abgeschlossen<li>Hybride PSTN-Nummern werden nicht eingerichtet</ul>|
|Kunden, die eine Administratorbeteiligung & Kundeninvestitionen benötigen<br><br>Zu migrierende Features:<ul><li>voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschlangen<li>Faxintegration</ul>| Bis Februar 2020  | Beispiele: <br><ul><li>Der ExchUMO-Dienst wird von Nebenstellenanlagen von Drittanbietern genutzt<li>Kunden mit PstN Subscriber Access-Anforderungen<li>Kunden auf SFB 2010 (nicht unterstützt)<li>Faxintegration</ul> |

## <a name="voicemail-migration-guidelines"></a>Richtlinien für die Voicemailmigration

### <a name="get-informed"></a>Informieren

Machen Sie sich mit der [Blogansage](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) und diesem Artikel vertraut, um eine reibungslose Migration für Ihre Benutzer zu planen. Weitere Informationen zu den Voicemailfunktionen des Telefonsystems finden Sie unter Überprüfen der [Skype for Business-Voicemail](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) und -Optionen.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Einrichten einer Skype for Business-Hybridtopologie

Wenn Sie keine Skype for Business-Hybridtopologie eingerichtet haben, müssen Sie dies tun, um eine reibungslose Migration Ihrer Voicemailbenutzer zu ermöglichen. Weitere Informationen finden Sie unter [Configure Skype for Business hybrid.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)

> [!Note]
> Sie müssen Ihre Benutzer für die Migration des Voicemaildiensts nicht online migrieren. Damit lokale Benutzer den Voicemaildienst des Telefonsystems nutzen können, muss jedoch eine Hybridtopologie eingerichtet werden.

### <a name="plan-your-auto-attendant-migration"></a>Planen der Migration der automatischen Attendant

Administratoren können jederzeit mit der Migration ihrer automatischen Attendanten von ExchUMO zur automatischen Cloud-Attendant beginnen. Weitere [Informationen finden Sie unter Einrichten einer automatischen Cloud-Attendant.](/microsoftteams/create-a-phone-system-auto-attendant)

Microsoft stellt weiterhin zusätzliche funktionen für automatische Attendanten bereit, die Kunden möglicherweise für ihre Migration benötigen. Administratoren sollten den Featuresatz auswerten und die Instanzen der automatischen Attendant entsprechend migrieren. Einen Featurelistenvergleich finden Sie in der [Featurematrix für cloudbasierte Dienste von ExchUMO und Azure.](#exchumo-and-azure-cloud-based-services-feature-matrix)

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planen der Voicemailüberprüfung und -tests nach der Migration

Die Voicemailmigration wird von Microsoft gesteuert. Administratoren sind nicht verpflichtet, etwas zu tun, da die erforderliche Hybridtopologie eingerichtet ist. Microsoft führt die erforderlichen Überprüfungen und Tests durch, um sicherzustellen, dass die Voicemailmigration der Benutzer nicht unterbrochen wird. Administratoren werden aufgefordert, Tests und Überprüfungen auf ihrer Seite durchzuführen. Einen [empfohlenen Testplan finden](#suggested-test-plan-and-post-migration-validation-for-admins) Sie unter Vorgeschlagene Testplanung und Überprüfung nach der Migration für Administratoren.

> [!Note]
> Lync Server 2010 wird nicht unterstützt. Wenn Sie sich in einer 2010-Serverbereitstellung befinden, sollten Sie ein Serverupgrade planen oder eine Migration Ihrer Benutzer zu Microsoft Teams in Betracht ziehen.  

### <a name="monitor-the-admin-notification-center"></a>Überwachen des Admin Notification Centers

Sehen Sie sich einen Hinweis im Admin Notification Center mit weiteren Details und einer Zeitachse zur Migration Ihrer Benutzer an. Benachrichtigungen werden mindestens 30 Tage vor Dem Migrationszeitraum gesendet.

> [!Note]
> Wenn Sie eine Benachrichtigung mit der Migrationszeitachse Ihrer Benutzer erhalten haben und Ihre Migration aus einem geschäftskritischen Grund verschieben möchten, können Sie dies tun, indem Sie sich an den Microsoft-Support wenden. Sie können Die Migration nicht über das 28. Februar 2020 hinausgehen. Für Kunden, die weitere Fragen haben, wenden Sie sich bitte an Ihr Kontoteam oder den Microsoft-Support. Kunden, die bereits Microsoft 365 oder Office 365 verwenden, können einen Supportfall über das Microsoft 365 Admin Center einreichen.

### <a name="consider-opting-in-for-a-planned-migration"></a>Erwägen, sich für eine geplante Migration zu entscheiden

Sie können sich für eine geplante Migration des Voicemaildiensts zu CVM entscheiden. Bevor Sie sich dafür entscheiden, lesen Sie die Details dieses Artikels, insbesondere die folgenden Abschnitte:

- Migrationsschritte (in diesem Abschnitt)
- Featurematrix für cloudbasierte Dienste von ExchUMO und Azure
- Auswirkungen auf die Benutzerfreundlichkeit

Wenn Sie eine verwaltete Migration auswählen, erhalten Sie im Microsoft 365 Admin Portal Message Center keine Benachrichtigung über 30 Tage vor der Migration.

Um sich für eine geplante Migration zu entscheiden, senden Sie eine E-Mail-Anforderung von der [E-Mail-Adresse](mailto:cvm@microsoft.com) Ihres Administrators an cvm@microsoft.com mit den folgenden Informationen:

- Bevorzugtes Datum (Dienstag): Migrationswellen werden jeden Dienstag ausgeführt. Wählen Sie ein Datum an einem Dienstag aus, der nicht über den 3.12.2019 hinaus liegt.
 
- Mandanten-ID: 32 Zeichen Zahl in diesem Format 0046728c-688a-4472-a38f-098fec60ac6x. Sie finden Ihre Mandanten-ID im Microsoft 365-Verwaltungsportal unter Azure AD oder mithilfe des folgenden PowerShell-Cmdlets: `Get-CsTenant | Select ObjectId`

Sie erhalten eine E-Mail-Bestätigung, sobald Ihr Mandant erfolgreich migriert wurde.

## <a name="auto-attendant-migration-guidelines"></a>Migrationsrichtlinien für automatische Attendanten

Microsoft 365- und Office 365-Organisationsadministratoren müssen ihre automatischen Exchange UM Online-Telefone im Microsoft Cloud automatische Telefonzentrale-Dienst neu erstellen und ihre lokalen Telefonnummern vor dem Exchange UMO-Dienstrentendatum 28. Februar 2020 auf diese umschalten. Dies ist die empfohlene Richtlinie zum erfolgreichen Migrieren und Testen neuer automatischer Cloud-Attendanten. Wenn Sie über eine große Anzahl automatischer Attendanten verfügen, können Sie die [Exchange UM-automatische Telefonzentrale](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) in Cloud automatische Telefonzentrale Migrationsskripts verwenden, um die Massenmigration automatischer Attendanten zu vereinfachen.

### <a name="auto-attendant-setup"></a>Einrichten der automatischen Telefonzentrale

Es wird dringend empfohlen, die Einrichtung Ihrer neuen automatischen Attendanten frühzeitig zu starten, um Last-Minute-Probleme zu vermeiden und sich mit der Funktionalität und Erfahrung des Cloud-automatische Telefonzentrale vertraut zu machen. Für automatische Attendanten, die mindestens ein Lückenfeature erfordern, können Sie die automatischen Attendanten erstellen und testen, wenn die Lückenfeatures zur Vorbereitung auf die Bereitstellung verfügbar sind. Weitere Informationen zu Lückenfeatures finden Sie im [Anhang](#appendix).

1. Verwenden Sie die Exchange UMO-Cmdlets, um die Konfiguration vorhandener automatischer Attendanten mithilfe von [Get-UMAutoAttendant zu exportieren.](/powershell/module/exchange/unified-messaging/get-umautoattendant)  
2. Verwenden Sie [das Cmdlet Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell, um die Begrüßungsmediendateien (sofern verwendet) zu exportieren und in das MP3-Format zu konvertieren.
3. Befolgen Sie die Anweisungen unter [Planen](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) automatischer Cloud-Attendanten und Einrichten einer automatischen Cloud-Attendant zum Erstellen automatischer Attendanten mithilfe des Microsoft Teams Admin Center oder der Powershell. [](/microsoftteams/create-a-phone-system-auto-attendant)
4. Überprüfen Sie Ihre Begrüßungen, wenn sich die Menüoptionen geändert haben.
5. Konfigurieren Sie Übertragungen an Ihre Reaktionsgruppen mithilfe der Problemumgehung "Automatische Telefonzentrale Anrufübertragung an PSTN" im Abschnitt Bekannte [Probleme](#known-issues) in diesem Artikel.  
6. Testen Sie die neuen automatischen Telefonanten, indem Sie sie intern aufrufen oder eine Testtelefonnummer zuweisen.  

### <a name="cutover"></a>Übernahmemigration

1. Wechseln Sie Ihre Telefonnummern von automatischen Exchange UMO-Telefon attendants zu den neuen automatischen Telefonanten.
2. Verschieben Sie den SIP-URI aus dem Contact-Objekt in das Ressourcenkonto.
3. Testen und überprüfen Sie Ihre automatischen Telefonanten mithilfe der neu zugewiesenen Telefonnummern.

## <a name="appendix"></a>Anhang

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Featurematrix für cloudbasierte Dienste von ExchUMO und Azure

| Dienst | Featureebene | Feature | Anmerkungen  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Dienstfeatures| Unterstützung von Nebenstellenanlagen von Drittanbietern    | Einschließlich aller Features, die für Nebenstellenanlagen von Drittanbietern bereitgestellt werden, z. B. MWI (Message Waiting Indicator) mithilfe von SIP-Benachrichtigungsnachrichten von Exchange UM Online | N   | v    |
| VM | Dienstfeatures  | Unterstützen von Skype for Business Server   |  | v | v    |
| VM | Dienstfeatures | Microsoft Teams unterstützen|  | v | N    |
| VM | Dienstfeatures | eDiscovery und Hold  | Für Sicherheit und Compliance  | v | v    |
| VM | Dienstfeatures | Unterstützung von Exchange-Regeln | Für Sicherheit und Compliance  | v | v    |
| VM | Benutzerfeatures | PSTN-Einwahlzugriff  | Teilnehmerzugriff  | N | v    |
| VM | Benutzerfeatures | Stellvertretung  | E-Mail mit verpassten Anrufen  | N | v    |
| VM | Benutzerfeatures | PSTN-Outlook Voice Access   | Teilnehmerzugriff  | N | v    |
| VM | Benutzerfeatures | Einwahl mithilfe eines authentifizierten Endpunkts | Aufrufen des Voicemaildiensts zum Abhören von Sprachnachrichten und Ändern von Voicemaileinstellungen| v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren von Voicemail   |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Ändern der persönlichen Begrüßung  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Erstellen einer OOF-Begrüßung  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Ändern der Standardsprache  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Überschreiben der Standardgrrüße mit TTS  |  | v | N    |
| VM | Benutzerfeatures | Aufzeichnen persönlicher Begrüßungen (authentifizierte Geräte) |  | v | v    |
| VM | Benutzerfeatures | Aufzeichnen persönlicher Begrüßungen (PSTN) – Wiedergabe über Telefon |  | N | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren der Transkription |  | N | v    |
| VM | Benutzerfeatures | Transkription  |  | v | v    |
| VM | Benutzerfeatures | MWI (Message Waiting Indicator) mithilfe von SIP-Benachrichtigungsnachrichten |  | N | v    |
| VM | Benutzerfeatures | MP3-Audiodateiformat in Outlook    |  | v | v    |
| VM | Benutzerfeatures | Steuerung der variablen Geschwindigkeitssteuerung |  | v | v    |
| VM | Benutzerfeatures | Weiterleiten einer Voicemail  | Weiterleiten einer empfangenen Voicemail an andere Benutzer | v | v    |
| VM | Benutzerfeatures | Senden einer Sprachnachricht an eine Gruppe von Benutzern  |Voicemailübertragung   | N | v   |
| VM | Benutzerfeatures | Voicemailbenachrichtigung mithilfe von SMS    | Benutzer können eine SMS empfangen, wenn sie über eine neue Voicemail verfügen    | N | v    |
| VM | Benutzerfeatures | Unterstützte Begrüßungssprachen | Details hier: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| VM | Benutzerfeatures | Mailboxansageregeln |  | v | v    |
| VM | Benutzerfeatures | Wiedergabe über Telefon (PSTN) – zum Abspielen von Nachrichten | Rufen Sie mich in meiner Zelle an, um die Sprachnachricht zu hören  | N | v    |
| VM | Benutzerfeatures | Wiedergabe über Telefon (Auth)- zum Abspielen von Nachrichten | Rufen Sie mich auf meinem authentifizierten Gerät auf  | N | v    |
| VM | Benutzerfeatures | Freigegebenes Postfach zwischen mehreren Benutzern |  | v | v    |
| VM | Anruferfeatures  | Anrufererfahrung – geschützte Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als geschützt zu markieren.| N | v    |
| VM | Anruferfeatures  | Anrufererfahrung – private Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als privat zu markieren.  | N | v    |
| VM | Anruferfeatures  | Erkennung von Stille   |  | N | v    |
| VM | Tenant-Admin Features | Geschützte Voicemail auf Serverebene    | Mandantenadministrator kann eine Dienstebenenregel konfigurieren, um eingehende Voicemail als geschützt zu kennzeichnen | v | v    |
| VM | Tenant-Admin Features | Ändern des Zeitlimits für die Aufzeichnungsdauer  |     | v | v    |
| VM | Tenant-Admin Features | Timeout für die Änderung der Stilleerkennung    |  | Nicht zutreffend    | v    |
| VM | Tenant-Admin Features | Ändern der Anzahl der Eingabefehler | CVM: hart codiert auf 3 | N | v    |
| VM | Tenant-Admin Features | Ändern der Standardsprache |  | v | v    |
| VM | Tenant-Admin Features | Deaktivieren/Aktivieren der Transkription |  | v | v    |
| VM | Tenant-Admin Features | Deaktivieren/Aktivieren einer Benachrichtigung über verpasste Anrufe |  | N | v    |
| VM | Tenant-Admin Features | Helfen Sie Microsoft bei der Verbesserung der Voicemailvorschau    |  | v | v    |
| VM | Tenant-Admin Features | Anpassen der Textnachricht für aktivierte Benutzer|  | Nicht zutreffend    | v    |
| VM | Tenant-Admin Features | Transkription der Profanitätsmaske|  | v | N    |
| VM | Tenant-Admin Features | Voicemailrichtlinie    |   | v | v    |
| VM | Tenant-Admin Features | Verwaltung des Webportals   |  | CY19   | v    |
| VM | Tenant-Admin Features | PowerShell   |  | v | v    |
| UM | Benutzerfeatures | MWI (Message Waiting Indicator) auf Skype for Business-zertifizierten Telefonen   |Kann vom Telefonpartner bereitgestellt werden  | Nein | Ja    |
| AA | Dienstfeatures | AA support 3rd-party PBX    |  | N | v    |
| AA | Dienstfeatures | Unterstützen von Skype for Business Server   |  | v | v    |
| AA | Dienstfeatures | Microsoft Teams unterstützen|  | v | N    |
| AA | Dienstfeatures | Wahl nach Name, DTMF-Eingabe    |  | v | v    |
| AA | Dienstfeatures | Wahl nach Name, Spracheingabe  |  | v | v    |
| AA | Dienstfeatures | Mehrsprachige Unterstützung | Sprachdetails hier: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| AA | Dienstfeatures | Übertragung an Operator, CQ oder einen Benutzer |  | v | v    |
| AA | Dienstfeatures | Interne Übertragung an die PSTN-Nummer (DID RNL)  |  | v | v    |
| AA | Dienstfeatures | Externe Übertragung an die PSTN-Nummer  |  | Lesen Sie den Abschnitt Bekannte Probleme weiter unten. | v    |
| AA | Dienstfeatures | Geschäftszeiten |  | v | v    |
| AA | Dienstfeatures | Menüoptionen | Optionen für das IVR-Menü  | v | v    |
| AA | Dienstfeatures | Zuweisen einer Cloud-PSTN-Nummer zu AA |  | v | N    |
| AA | Dienstfeatures | Zuweisen einer on-prem-PSTN-Nummer zu AA  |  | v | v    |
| AA | Dienstfeatures | Benutzerdefinierte Benutzerauswahl  | Aktivieren der Anrufer zum Erreichen einer benutzerdefinierten Liste von Organisationsbenutzern| v | v    |
| AA | Dienstfeatures | Behandlung nach Stunden und Feiertagen  |  | v | v    |
| AA | Dienstfeatures | Benutzerdefinierte Begrüßung mithilfe von Text in Sprache  |  | v | v    |
| AA | Dienstfeatures | Durchwahl wählen   | Erreichen eines Benutzers durch Wählen ihrer Durchwahl  | v   | v    |
| AA | Dienstfeatures | Postfach für Anrufer, die eine Nachricht hinterlassen    |  | v   | v    |
| AA | Dienstfeatures | Mehrere PstN-Nummernzuweisungen an eine AA|  | v | v    |
| AA | Tenant-Admin Features | Verwaltung des Webportals   |  | v | N    |
| AA | Tenant-Admin Features | PowerShell-Cmdlets  |  | v | v    |
| Fax| Dienstfeatures | Faxintegration|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Vorgeschlagene Testplanung und Überprüfung nach der Migration für Administratoren

Um zu überprüfen, ob Ihre Benutzer zu Cloud Voicemail migriert wurden, lassen Sie eine Voicemail an einen Benutzer, und überprüfen Sie den Nachrichtentext in Outlook. Cloud Voicemailnachrichten verfügen über eine Fußzeile mit den informationen:

"Vielen Dank für die Verwendung von Transkription! Wenn oben keine Aufzeichnung angezeigt wird, liegt dies daran, dass die Audioqualität nicht klar genug war, um sie zu transkribieren."

Wenn Sie die Voicemailfunktionalität testen, nachdem Ihre Benutzer migriert wurden, sollten Sie die folgenden Szenarien berücksichtigen:

- Überprüfen des Voicemailzugriffs für alle Endpunkttypen in Ihrer Organisation, z. B. Apps und IP-Telefone.
- Überprüfen Sie mit Beispielbenutzern, ob die konfigurierten personalisierten Begrüßungen für Anrufer abgespielt werden.
- Wenn Ihre Organisation eine gesetzliche Oder Complianceanforderung zum Deaktivieren der Transkription für Benutzer hat, stellen Sie sicher, dass die Transkription nach der Migration deaktiviert ist. Weitere Informationen finden Sie unter [Einrichten von Cloud Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Wenn Sie zuvor Exchange-VM-Richtlinien und -Regeln konfiguriert haben, stellen Sie sicher, dass sie wirksam sind.
- Machen Sie sich mit den PowerShell-Cmdlets des Cloud-Voicemaildiensts vertraut, um Benutzereinstellungen zu ändern.  

### <a name="user-experience-impact"></a>Auswirkungen auf die Benutzerfreundlichkeit

Im Folgenden finden Sie eine Übersicht über die Migration von Endbenutzer-Voicemail.


|Umgebung  |Ändern der Benutzeroberfläche|
|---------|---------|
|E-Mail-Benachrichtigung | Keine Änderung<br>Es wird keine E-Mail an Benutzer gesendet, die sie über die Aktivierung/Migration des Voicemailkontos informieren. |
|Zugriff auf vorherige Nachrichten | Keine Änderung<br>Benutzer haben Zugriff auf ihre vorherigen Voicemailnachrichten in allen unterstützten Endpunkten. |
|Empfangen von virtuellen Computer in Outlook, SFB Apps| Keine Änderung<br>Benutzer erhalten weiterhin ihre Voicemailnachrichten in allen unterstützten Endpunkten. |
|Transkription | Erweitert<br>Die CVM-Transkription hat eine wesentlich höhere Genauigkeitsrate und unterstützte Sprachen als ExchUMO. |
|Benutzereinstellung | Neue Erfahrung<br>Benutzer können ihre Einstellungen über ein Benutzereinstellungsportal (User Setting Portal, USP) ändern. Benutzer können über einen Hyperlink in ihrer Voicemail-E-Mail oder über die User-Settings auf ihrem User-Settings auf ihre #A1 zugreifen. https://aka.ms/vmsettings.
 |Features| Weitere Informationen finden Sie im Featuresatzvergleich. |
|Outlook-Regeln für VM-Nachrichten | Keine Änderung<br>Zuvor erstellte Regeln gelten für CVM-Nachrichten nach der Migration.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Benutzerverwaltung und -bereitstellung in CVM

Neue Skype for Business-Benutzer werden automatisch für Cloud voicemail bereitgestellt, wenn sie erstellt werden. Es ist keine zusätzliche Administratorarbeit oder Lizenz erforderlich, um neue Voicemailbenutzer bereitstellen zu können. Weitere Informationen zur Richtlinienverwaltung für vorhandene und neue Benutzer finden Sie unter Einrichten von [Cloud Voicemail.](/microsoftteams/set-up-phone-system-voicemail)

### <a name="admin-auto-attendant-management-experience"></a>Verwaltungserfahrung automatische Telefonzentrale Administratoren

Weitere Informationen zu automatischen Attendanten finden Sie unter [Einrichten einer automatischen Cloud-Attendant](/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Bekannte Probleme

#### <a name="greeting-inconsistencies"></a>Inkonsistenzen der Begrüßung

Der Teilnehmerzugriff funktioniert möglicherweise weiterhin für Ihren Mandanten, bis der Dienst vollständig eingestellt ist, auch nachdem alle Benutzer zu Cloud Voicemail migriert wurden. Um Verwirrung und eine inkonsistente Benutzererfahrung zu vermeiden, deaktivieren Sie den Teilnehmerzugriff, da sich die Begrüßungen nach der Migration ändern. Entfernen Sie dazu den EXUM-Kontakt für jede Teilnehmerzugriffsleitung mithilfe `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` von .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>automatische Telefonzentrale Anrufübertragung an PSTN

Um einen anruf automatischen Telefonanruf über Skype for Business Server oder einen Reaktionsgruppesdienst (Response Group Service, RGS) auf Skype for Business Server an eine externe PSTN-Telefonnummer zu übertragen, erstellen Sie einen neuen lokalen Benutzer, für den die Anrufumwahl auf die Festnetznummer oder die RGS-Telefonnummer festgelegt ist. Der Benutzer muss aktiviert und ordnungsgemäß für Enterprise-VoIP konfiguriert sein und eine Sprachrichtlinie zugewiesen haben.

#### <a name="shared-mailbox-is-still-accessible"></a>Auf freigegebenes Postfach kann weiterhin zugegriffen werden

Ein freigegebenes Postfach, das mit Exchange UM Online konfiguriert wurde, erhält auch nach der Migration zu CVM weiterhin Nachrichten und ist für Benutzer über Outlook zugänglich. Der Zugriff auf das Ändern der Begrüßungsnachrichten dieser Postfächer ist jedoch nach der Migration zu CVM nicht mehr verfügbar. Kunden mit freigegebenen Postfächern, die zum Erfassen automatischer Telefonanrufer verwendet werden, sollten die Funktionen "Automatische Telefon attendants" und "Call Queues Shared Mailbox" nutzen, sobald sie freigegeben wurden (ETA Oktober 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Banneranzeigen "Benutzername verwendet Skype for Business nicht"

Der CVM-Dienst basiert auf der Microsoft Teams-Infrastruktur, und Anrufe von einem Skype for Business-Client können dazu führen, dass auf dem Client ein Informationsbanner angezeigt wird, der lautet: "Benutzername verwendet Skype for Business nicht. Wechseln Sie zu Teams, oder starten Sie eine Skype-Besprechung, um eine reichhaltigere Erfahrung zu ermöglichen."
Aktualisieren Sie den Skype for #A0 Ihrer Benutzer auf das neueste C2R-Clientupdate, um zu verhindern, dass dieses Banner angezeigt wird.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Einrichten von Voicemail" führt Sie zu OWA

Wenn Sie **auf Voicemail vom** Client einrichten klicken, werden Skype for Business Server 2015/2013-Kunden nach der Migration zu CVM weiterhin zur Seite des Office Web Access (OWA)-Portals weitergeleitet. Alle Einstellungen wurden von der Registerkarte Voicemail in OWA entfernt, und ein Banner wird mit einem Umleitungslink angezeigt, um Benutzer zum Portal für cvM-Benutzereinstellungen zu leiten.

#### <a name="changing-greeting-remotely"></a>Remote ändern der Begrüßung

Der Zugriff auf PSTN-Abonnenten wird in CVM nicht unterstützt. Für Benutzer, die ihre Begrüßung remote ändern müssen, wurde dem Voicemail-IVR-Dienst für mobile Clients die Menüoption "Begrüßung ändern" hinzugefügt. Benutzer können diesen Dienst aufrufen, indem sie die Taste "1" auf dem mobilen Clientwählpad drücken und halten.