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
ms.localizationpriority: medium
description: Microsoft stellt den Dienst Exchange Unified Messaging Online (ExchUMO) bis zum 28. Februar 2020 ein. In diesem Artikel wird zusammengefasst, was betroffene Kunden wissen und tun sollten, um ihre Geschäftskontinuität zu planen.
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676367"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Migrationsunterstützung für Exchange Unified Messaging Online

> [!IMPORTANT]
> **Der Unified Messaging-Dienst in Exchange Online ist ab dem 28. Februar 2020, 17 Uhr Pazifische Zeit, nicht mehr unterstützt. Alle Voicemail-Konten wurden von Microsoft zu Cloud-Voicemail Dienst migriert. Der verbleibende Datenverkehr der automatischen Telefonzentrale wird nicht überwacht und kann jederzeit unterbrochen werden.**

In Bezug auf die [Ankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) am 8. Februar 2019 stellt Microsoft den Dienst Exchange Unified Messaging Online (ExchUMO) bis zum 28. Februar 2020 ein. Dieser Artikel enthält eine Zusammenfassung dessen, was betroffene Kunden wissen und tun sollten, um ihre Geschäftskontinuität zu planen.

ExchUMO wird von Kunden für Voicemail, automatische Telefonzentrale, Anrufwarteschleife und Faxintegrationsdienste bereitgestellt. Microsoft plant, Kunden bei der Migration zu Telefonsystem Diensten zu unterstützen, die bereits Tausende von Kunden auf Skype for Business Online und Microsoft Teams unterstützen.

Voicemail ist in erster Linie eine von Microsoft gesteuerte Migration. Für eine Teilmenge von Kunden sind möglicherweise Administratorbeteiligungen und/oder Investitionen erforderlich. Die automatische Telefonzentrale ist eine administratorgesteuerte Migration. Sie müssen die vorhandenen automatischen ExchUMO-Telefonzentralenstrukturen im Cloud-Clouddienst für automatische Telefonzentralen neu erstellen. Kunden, die eines der ExchUMO-Features mit einer Nebenstellenanlage eines Drittanbieters nutzen, werden nicht zu Skype Clouddiensten migriert, da sie keine PbX-Systeme von Drittanbietern unterstützen. In [diesem Blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853) wurde ein Einstellungsplan für den Support von Drittanbietern angekündigt, und Kunden in diesem Bereitstellungsmodell können ihre Benutzer zu einer der Unified Communications-Plattformen/-Dienste von Microsoft migrieren oder eine Voicemail- und/oder automatische Telefonzentralenlösung von Drittanbietern für diese Benutzer erwerben. Die Faxintegration wird in den cloudbasierten Diensten nicht unterstützt. Kunden müssen zu einer Drittanbieterlösung migrieren.

## <a name="who-is-affected"></a>Wer ist betroffen?

Kunden, die eine der folgenden Features aus dem Exchange Unified Messaging Online-Dienst verwenden, sind betroffen:

- Voicemaildienst
- Automatischer Telefonzentralendienst
- Anrufwarteschleifendienst
- Faxintegration

> [!Note]
> Kunden, die einen der Exchange Server lokal mit Unified Messaging verwenden, sind davon nicht betroffen.

Erfahren Sie mehr über die Auswirkungen der Benutzer- und Administratorerfahrung auf [die Auswirkungen auf die Benutzerfreundlichkeit](#user-experience-impact).

## <a name="migration-plan-overview"></a>Übersicht über den Migrationsplan

Microsoft hat verschiedene Kundenbereitstellungen identifiziert, die Features von ExchUMO nutzen, und hilft Kunden bei der Migration basierend auf dem folgenden Plan.

|Kundengruppe |Zeitachse  |Details  |
|---------|---------|---------|
|Kunden, die zur Migration bereit sind<br><br>Zu migrierenden Features:<br><ul><li>Voicemail</ul>   |   März – Mai 2019  |Beispiele:<ul><li>    Kunden mit einfacher Voicemailbereitstellung und -nutzung<li>Kunden, für die alle Anforderungen festgelegt sind, damit Microsoft die Migration ausführen kann<ul>|
|Kunden mit Voraussetzungen<br><br>Zu migrierenden Features:<br><ul><li>Voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschleife</ul> |  Mai – Dezember 2019 |Beispiele: <br><ul><li>Die Hybridkonfiguration ist nicht abgeschlossen.<li>Hybrid-PSTN-Nummern sind nicht eingerichtet</ul>|
|Kunden, die eine Administratorbeteiligung & Kundeninvestitionen erfordern<br><br>Zu migrierenden Features:<ul><li>voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschlangen<li>Faxintegration</ul>| Bis Februar 2020  | Beispiele: <br><ul><li>ExchUMO-Dienst wird von Drittanbieter-PBX genutzt<li>Kunden mit PSTN-Zugriffsanforderungen für Abonnenten<li>Kunden im SFB 2010 (nicht unterstützt)<li>Faxintegration</ul> |

## <a name="voicemail-migration-guidelines"></a>Richtlinien für die Voicemailmigration

### <a name="get-informed"></a>Informieren

Machen Sie sich mit der [Blogankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) und diesem Artikel vertraut, um eine reibungslose Migration für Ihre Benutzer zu planen. Weitere Informationen zu den Telefonsystem Voicemail-Funktionen finden [Sie unter "Überprüfen Skype for Business Voicemail" und den Optionen](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8).  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Einrichten einer Skype for Business Hybridtopologie

Wenn Sie keine Skype for Business Hybridtopologie eingerichtet haben, müssen Sie dies tun, um eine reibungslose Migration Ihrer Voicemailbenutzer zu ermöglichen. Weitere Informationen finden [Sie unter Konfigurieren Skype for Business Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md).

> [!Note]
> Sie müssen Ihre Benutzer für die Migration des Voicemaildiensts nicht online migrieren. Damit lokale Benutzer jedoch Telefonsystem Voicemaildienst nutzen können, muss eine Hybridtopologie eingerichtet werden.

### <a name="plan-your-auto-attendant-migration"></a>Planen der Migration der automatischen Telefonzentrale

Administratoren können jederzeit mit der Migration ihrer automatischen Telefonzentralen von ExchUMO zur automatischen Cloud-Telefonzentrale beginnen. Weitere Informationen finden [Sie unter Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant) .

Microsoft bietet weiterhin zusätzliche Funktionen für automatische Telefonzentralen, die Kunden für ihre Migration möglicherweise für erforderlich halten. Administratoren sollten den Featuresatz auswerten und ihre Instanzen der automatischen Telefonzentrale entsprechend migrieren. Einen Featurelistenvergleich finden Sie in der [Featurematrix "ExchUMO" und "Azure cloud-based services"](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planen der Überprüfung und Tests Ihrer Voicemail nach der Migration

Die Voicemailmigration ist von Microsoft gesteuert. Administratoren sind nicht verpflichtet, etwas zu tun, da die erforderliche Hybridtopologie eingerichtet ist. Microsoft führt die erforderlichen Überprüfungen und Tests durch, um sicherzustellen, dass die Voicemailmigration der Benutzer nicht gestört wird. Administratoren werden aufgefordert, Tests und Validierungen auf ihrer Seite durchzuführen. Einen [empfohlenen Testplan finden Sie unter "Vorgeschlagener Testplan" und Überprüfung nach der Migration für Administratoren](#suggested-test-plan-and-post-migration-validation-for-admins) .

> [!Note]
> Lync Server 2010 wird nicht unterstützt. Wenn Sie sich in einer 2010-Serverbereitstellung befinden, sollten Sie ein Serverupgrade planen oder erwägen, Ihre Benutzer zu Microsoft Teams zu migrieren.  

### <a name="monitor-the-admin-notification-center"></a>Überwachen des Admin Benachrichtigungscenters

Achten Sie auf einen Hinweis im Admin Notification Center mit weiteren Details und einer Zeitachse zur Migration Ihrer Benutzer. Benachrichtigungen werden mindestens 30 Tage vor dem Migrationszeitraum gesendet.

> [!Note]
> Wenn Sie eine Benachrichtigung mit der Migrationszeitachse Ihrer Benutzer erhalten haben und die Migration aus einem geschäftskritischen Grund verschieben möchten, können Sie dies tun, indem Sie sich an Microsoft-Support wenden. Sie können Ihre Migration nicht über das Rentendatum des 28. Februar 2020 hinaus verschieben. Für Kunden, die möglicherweise weitere Fragen haben, wenden Sie sich bitte an Ihr Kontoteam oder Microsoft-Support. Kunden, die bereits Microsoft 365 oder Office 365 verwenden, können über die Microsoft 365 Admin Center einen Supportfall einreichen.

### <a name="consider-opting-in-for-a-planned-migration"></a>Erwägen Sie, sich für eine geplante Migration zu entscheiden

Sie können sich für eine geplante Migration des Voicemaildiensts zu CVM entscheiden. Lesen Sie vor der Teilnahme die Details dieses Artikels, insbesondere die folgenden Abschnitte:

- Migrationsschritte (dieser Abschnitt)
- Funktionsmatrix für ExchUMO und Azure Cloud-basierte Dienste
- Auswirkungen auf die Benutzerfreundlichkeit

Wenn Sie eine verwaltete Migration auswählen, erhalten Sie im Nachrichtencenter des Microsoft 365 Admin-Portals keine Benachrichtigung vor der Migration.

Um sich für eine geplante Migration zu entscheiden, senden Sie eine E-Mail-Anforderung von der E-Mail-Adresse Ihres Administrators an [cvm@microsoft.com](mailto:cvm@microsoft.com) mit den folgenden Informationen:

- Bevorzugtes Datum (Dienstage): Migrationswellen werden jeden Dienstag ausgeführt. Bitte wählen Sie ein Datum an einem Dienstag aus, der nicht über den 03.12.2019 hinausgeht.
 
- Mandanten-ID: 32 Zeichen Nummer in diesem Format 0046728c-688a-4472-a38f-098fec60ac6x. Sie finden Ihre Mandanten-ID im Microsoft 365-Verwaltungsportal unter Azure AD oder mit dem folgenden PowerShell-Cmdlet:`Get-CsTenant | Select ObjectId`

Sie erhalten eine E-Mail-Bestätigung, sobald Ihr Mandant erfolgreich migriert wurde.

## <a name="auto-attendant-migration-guidelines"></a>Migrationsrichtlinien für automatische Telefonzentralen

Microsoft 365 und Office 365 Organisationsadministratoren müssen ihre Exchange automatischen UM Online-Telefonzentralen im automatischen Telefonzentralendienst von Microsoft Cloud neu erstellen und ihre lokalen Telefonnummern vor dem Exchange UMO-Dienstende am 28. Februar 2020 auf sie umstellen. Dies ist die empfohlene Richtlinie zum erfolgreichen Migrieren und Testen neuer automatischer Cloudtelefonzentralen. Wenn Sie über eine große Anzahl von automatischen Telefonzentralen verfügen, können Sie die [Exchange Um Auto Attendant to Cloud Auto Attendant Migration Scripts](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) verwenden, um die Massenmigration von automatischen Telefonzentralen zu vereinfachen.

### <a name="auto-attendant-setup"></a>Einrichten der automatischen Telefonzentrale

Es wird dringend empfohlen, dass Sie die Einrichtung Ihrer neuen automatischen Telefonzentralen frühzeitig starten, um Last-Minute-Probleme zu vermeiden und sich mit der Funktionalität und Erfahrung des cloudbasierten Telefonzentralendiensts vertraut zu machen. Für automatische Telefonzentralen, die eine oder mehrere Gap-Features erfordern, können Sie die automatischen Telefonzentralen erstellen und testen, wenn die Lückenfeatures zur Vorbereitung auf die Bereitstellung verfügbar sind. Weitere Informationen zu Lückenfeatures finden Sie im [Anhang](#appendix).

1. Verwenden Sie die Exchange UMO-Cmdlets, um die Konfiguration vorhandener automatischer Telefonzentralen mithilfe von [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant) zu exportieren.  

2. Verwenden Sie das Cmdlet ["Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt)" in Exchange Online PowerShell, um die Begrüßungsmediendateien (sofern verwendet) zu exportieren und in .mp3 Format zu konvertieren.

3. Befolgen Sie die Anweisungen in ["Planen automatischer Cloudtelefonzentralen](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)" und ["Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant) zum Erstellen automatischer Telefonzentralen mithilfe des Microsoft Teams Admin Center oder powerShell".

4. Überprüfen Sie Ihre Begrüßungen, wenn sich die Menüoptionen geändert haben.

5. Konfigurieren Sie Übertragungen an Ihre Reaktionsgruppen mithilfe der Problemumgehung "Automatische Telefonzentralenanrufübertragung an PSTN" im Abschnitt ["Bekannte Probleme](#known-issues) " dieses Artikels.  

6. Testen Sie die neuen automatischen Telefonzentralen, indem Sie sie intern anrufen oder eine Testtelefonnummer zuweisen.  

### <a name="cutover"></a>Übernahmemigration

1. Wechseln Sie Ihre Telefonnummern von Exchange automatischen UMO-Telefonzentralen zu den neuen automatischen Telefonzentralen.
2. Verschieben Sie den SIP-URI aus dem Kontaktobjekt in das Ressourcenkonto.
3. Testen und überprüfen Sie Ihre automatischen Telefonzentralen mithilfe der neu zugewiesenen Telefonnummern.

## <a name="appendix"></a>Anhang

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Funktionsmatrix für ExchUMO und Azure Cloud-basierte Dienste

| Dienst | Featureebene | Feature | Hinweise  | Cloud-VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Dienstfeatures| Unterstützung von Festnetztelefonanlagen von Drittanbietern    | Einschließen aller Funktionen, die an Nebenstellenanlagen von Drittanbietern wie MWI (Message Waiting Indicator) mithilfe von SIP-Benachrichtigungen von Exchange UM Online bereitgestellt werden | N   | J    |
| VM | Dienstfeatures  | Support Skype for Business Server   |  | v | v    |
| VM | Dienstfeatures | Support Microsoft Teams|  | J | N    |
| VM | Dienstfeatures | eDiscovery und Haltebereich  | Für Sicherheit und Compliance  | v | v    |
| VM | Dienstfeatures | Exchange Regelunterstützung | Für Sicherheit und Compliance  | v | v    |
| VM | Benutzerfeatures | PSTN-Einwahlzugriff  | Abonnentenzugriff  | N | J    |
| VM | Benutzerfeatures | Stellvertretung  | Verpasste Anruf-E-Mail  | N | J    |
| VM | Benutzerfeatures | PSTN-Outlook Voice Access   | Abonnentenzugriff  | N | J    |
| VM | Benutzerfeatures | Einwahl mithilfe eines authentifizierten Endpunkts | Aufrufen des Voicemaildiensts zum Abhören von Sprachnachrichten und Ändern der Voicemaileinstellungen| v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren von Voicemail   |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Ändern der persönlichen Begrüßung  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Erstellen einer OOF-Begrüßung  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Ändern der Standardsprache  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Überschreiben der Standardansage mit TTS  |  | J | N    |
| VM | Benutzerfeatures | Aufzeichnen persönlicher Begrüßungen (authentifiziertes Gerät) |  | v | v    |
| VM | Benutzerfeatures | Aufzeichnen persönlicher Begrüßungen (PSTN) – Wiedergabe per Telefon |  | N | J    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren der Transkription |  | N | J    |
| VM | Benutzerfeatures | Transkription  |  | v | v    |
| VM | Benutzerfeatures | MWI (Message Waiting Indicator) mit SIP-Benachrichtigungsnachrichten |  | N | J    |
| VM | Benutzerfeatures | MP3-Audiodateiformat in Outlook    |  | v | v    |
| VM | Benutzerfeatures | Wiedergabesteuerung mit variabler Geschwindigkeit |  | v | v    |
| VM | Benutzerfeatures | Weiterleiten einer Voicemail  | Weiterleiten einer empfangenen Voicemail an andere Benutzer | v | v    |
| VM | Benutzerfeatures | Senden einer Sprachnachricht an eine Gruppe von Benutzern  |Voicemail-Übertragung   | N | J   |
| VM | Benutzerfeatures | Voicemailbenachrichtigung mit SMS    | Benutzer können eine SMS erhalten, wenn sie über eine neue Voicemail verfügen    | N | J    |
| VM | Benutzerfeatures | Unterstützte Begrüßungssprachen | Details hier: [Was sind automatische Cloud-Telefonzentralen?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| VM | Benutzerfeatures | Mailboxansageregeln |  | v | v    |
| VM | Benutzerfeatures | Wiedergabe auf Telefon (PSTN) – zum Wiedergeben von Nachrichten | Rufen Sie mich in meiner Zelle an, um die Sprachnachricht zu hören.  | N | J    |
| VM | Benutzerfeatures | Auf Telefon wiedergeben (Auth)- zum Wiedergeben von Nachrichten | Rückruf auf meinem authentifizierten Gerät  | N | J    |
| VM | Benutzerfeatures | Freigegebenes Postfach zwischen mehreren Benutzern |  | v | v    |
| VM | Anruferfeatures  | Anrufererfahrung – geschützte Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als geschützt zu markieren.| N | J    |
| VM | Anruferfeatures  | Anrufererfahrung – private Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als privat zu markieren.  | N | J    |
| VM | Anruferfeatures  | Erkennung von Stille   |  | N | J    |
| VM | Tenant-Admin-Features | Geschützte Voicemail auf Serverebene    | Mandantenadministratoren können eine Regel auf Dienstebene konfigurieren, um eingehende Voicemail als geschützt zu kennzeichnen. | v | v    |
| VM | Tenant-Admin-Features | Ändern des Zeitlimits für die Aufzeichnungsdauer  |     | v | v    |
| VM | Tenant-Admin-Features | Timeout für die Erkennung von Änderungsstille    |  | Nicht zutreffend    | v    |
| VM | Tenant-Admin-Features | Ändern der Anzahl von Eingabefehlern | CVM: hartcodiert auf 3 | N | J    |
| VM | Tenant-Admin-Features | Ändern der Standardsprache |  | v | v    |
| VM | Tenant-Admin-Features | Transkription deaktivieren/aktivieren |  | v | v    |
| VM | Tenant-Admin-Features | Deaktivieren/Aktivieren der Benachrichtigung über verpasste Anrufe |  | N | J    |
| VM | Tenant-Admin-Features | Helfen Sie Microsoft, die Voicemailvorschau zu verbessern    |  | v | v    |
| VM | Tenant-Admin-Features | Anpassen von Textnachrichten für aktivierte Benutzer|  | Nicht zutreffend    | J    |
| VM | Tenant-Admin-Features | Transkriptions-Profanitätsmaskierung|  | J | N    |
| VM | Tenant-Admin-Features | Voicemailrichtlinie    |   | v | v    |
| VM | Tenant-Admin-Features | Webportalverwaltung   |  | CY19   | v    |
| VM | Tenant-Admin-Features | PowerShell   |  | v | v    |
| UM | Benutzerfeatures | Message Waiting Indicator (MWI) auf Skype for Business zertifizierten Telefonen   |Kann vom Telefonpartner zur Verfügung gestellt werden  | Nein | Ja    |
| AA | Dienstfeatures | AA-Unterstützung für Festnetztelefonanlagen von Drittanbietern    |  | N | J    |
| AA | Dienstfeatures | Support Skype for Business Server   |  | v | v    |
| AA | Dienstfeatures | Support Microsoft Teams|  | J | N    |
| AA | Dienstfeatures | Namenswahl, DTMF-Eingabe    |  | v | v    |
| AA | Dienstfeatures | Wählen nach Name, Spracheingabe  |  | v | v    |
| AA | Dienstfeatures | Unterstützung für mehrere Sprachen | Sprachdetails hier: [Was sind automatische Cloud-Telefonzentralen?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| AA | Dienstfeatures | Übertragung an Operator, CQ oder einen Benutzer |  | v | v    |
| AA | Dienstfeatures | Interne Übertragung auf PSTN-Nummer (DID RNL)  |  | v | v    |
| AA | Dienstfeatures | Externe Übertragung auf PSTN-Nummer  |  | Sehen Sie sich den Abschnitt "Bekannte Probleme" unten an. | v    |
| AA | Dienstfeatures | Geschäftszeiten |  | v | v    |
| AA | Dienstfeatures | Menüoptionen | IVR-Menüoptionen  | v | v    |
| AA | Dienstfeatures | Zuweisen einer Cloud-PSTN-Nummer zu AA |  | J | N    |
| AA | Dienstfeatures | Zuweisen einer lokalen PSTN-Nummer zu AA  |  | v | v    |
| AA | Dienstfeatures | Benutzerdefinierte Benutzerauswahl  | Ermöglichen, dass Anrufer eine angepasste Liste von Organisationsbenutzern erreichen| v | v    |
| AA | Dienstfeatures | Nach feierabend- und feiertagsbehandlung  |  | v | v    |
| AA | Dienstfeatures | Benutzerdefinierte Begrüßung mitHilfe von Text zu Sprache  |  | v | v    |
| AA | Dienstfeatures | Durchwahl wählen   | Erreichen eines Benutzers durch Wählen der Erweiterung  | v   | v    |
| AA | Dienstfeatures | Postfach für AA-Anrufer zum Hinterlassen einer Nachricht    |  | v   | v    |
| AA | Dienstfeatures | Mehrere PSTN-Nummernzuweisungen zu einem AA|  | v | v    |
| AA | Tenant-Admin-Features | Webportalverwaltung   |  | J | N    |
| AA | Tenant-Admin-Features | PowerShell-Cmdlets  |  | v | v    |
| Fax| Dienstfeatures | Faxintegration|  | N | J    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Vorgeschlagener Testplan und Überprüfung nach der Migration für Administratoren

Um zu überprüfen, ob Ihre Benutzer zu Cloud-Voicemail migriert wurden, überlassen Sie einem Benutzer eine Voicemail, und überprüfen Sie den Nachrichtentext in Outlook. Cloud-Voicemail Nachrichten haben eine Fußzeile mit folgendem Wortlaut:

"Vielen Dank, dass Sie Transkription verwendet haben! Wenn oben kein Transkript angezeigt wird, liegt das daran, dass die Audioqualität nicht klar genug war, um sie zu transkribieren."

Achten Sie beim Testen der Voicemailfunktionen nach der Migration Ihrer Benutzer darauf, die folgenden Szenarien zu berücksichtigen:

- Überprüfen des Voicemailzugriffs über alle Endpunkttypen in Ihrer Organisation hinweg, z. B. Apps und IP-Telefone.
- Überprüfen Sie mit Beispielbenutzern, ob die konfigurierten personalisierten Begrüßungen für Anrufer wiedergegeben werden.
- Wenn Ihre Organisation eine gesetzliche oder Compliance-Anforderung hat, um die Transkription für Benutzer zu deaktivieren, stellen Sie sicher, dass sie nach der Migration deaktiviert ist. Weitere Informationen finden [Sie unter Einrichten Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Wenn Sie zuvor Exchange VM-Richtlinien und -Regeln konfiguriert haben, stellen Sie sicher, dass diese wirksam sind.
- Machen Sie sich mit den PowerShell-Cmdlets des Cloud-Voicemail diensts zum Ändern von Benutzereinstellungen vertraut.  

### <a name="user-experience-impact"></a>Auswirkungen auf die Benutzerfreundlichkeit

Nachfolgend sehen Sie eine Übersicht über die Migrationserfahrung von Endbenutzer-Voicemails.


|Umgebung  |Änderung der Benutzeroberfläche|
|---------|---------|
|E-Mail-Benachrichtigung | Keine Änderung<br>Es werden keine E-Mails an Benutzer gesendet, die sie über die Aktivierung/Migration des Voicemailkontos benachrichtigen. |
|Zugriff auf vorherige Nachrichten | Keine Änderung<br>Benutzer haben Zugriff auf ihre vorherigen Voicemailnachrichten in allen unterstützten Endpunkten. |
|Empfangen von virtuellen Computern in Outlook, SFB-Apps| Keine Änderung<br>Benutzer erhalten weiterhin ihre Voicemailnachrichten in allen unterstützten Endpunkten. |
|Transkription | Verbesserte<br>Die CVM-Transkription hat eine viel höhere Genauigkeitsrate und unterstützte Sprachen als ExchUMO. |
|Benutzereinstellung | Neue Erfahrung<br>Benutzer können ihre Einstellungen über ein Benutzereinstellungsportal (User Setting Portal, USP) ändern. Benutzer können über einen Link in ihrer Voicemail-E-Mail oder über die Schaltfläche User-Settings auf ihrem SFB-Client auf ihren USP zugreifen. https://aka.ms/vmsettings.
 |Features| Weitere Informationen finden Sie im Vergleich der Featuresätze. |
|Outlook regeln für VM-Nachrichten | Keine Änderung<br>Zuvor erstellte Regeln gelten nach der Migration für CVM-Nachrichten.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Benutzerverwaltung und -bereitstellung in CVM

Neue Skype for Business Benutzer werden automatisch für Cloud-Voicemail bereitgestellt, wenn sie erstellt werden. Für die Bereitstellung neuer Voicemail-Benutzer ist keine zusätzliche Administratorarbeit oder -lizenz erforderlich. Weitere Informationen zur Richtlinienverwaltung für vorhandene und neue Benutzer finden Sie unter ["Einrichten von Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail)".

### <a name="admin-auto-attendant-management-experience"></a>Admin Verwaltungsoberfläche der automatischen Telefonzentrale

Weitere Informationen zu automatischen Telefonzentralen finden [Sie unter Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Bekannte Probleme

#### <a name="greeting-inconsistencies"></a>Grußinkonsistenzen

Der Abonnentenzugriff funktioniert möglicherweise weiterhin für Ihren Mandanten, bis der Dienst vollständig eingestellt wurde, auch nachdem alle Ihre Benutzer zu Cloud-Voicemail migriert wurden. Um Verwirrung bei Benutzern und eine inkonsistente Erfahrung zu vermeiden, deaktivieren Sie den Abonnentenzugriff, da sich die Begrüßungen nach der Migration ändern. Entfernen Sie dazu den EXUM-Kontakt für jede Abonnentenzugriffszeile mithilfe von `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Automatische Telefonzentralenanrufübertragung an das PSTN

Um einen automatischen Telefonzentralenanruf über Skype for Business Server oder einen Reaktionsgruppendienst (Response Group Service, RGS) auf Skype for Business Server an eine externe PSTN-Telefonnummer zu übertragen, erstellen Sie einen neuen lokalen Benutzer, bei dem die Anrufweiterleitung auf die PSTN-Telefonnummer oder die RGS-Telefonnummer festgelegt ist. Der Benutzer muss für Enterprise-VoIP aktiviert und ordnungsgemäß konfiguriert sein und eine VoIP-Richtlinie zugewiesen haben.

#### <a name="shared-mailbox-is-still-accessible"></a>Auf das freigegebene Postfach kann weiterhin zugegriffen werden.

Ein freigegebenes Postfach, das mit Exchange UM Online konfiguriert wurde, empfängt nach der Migration zu CVM weiterhin Nachrichten und ist über Outlook für Benutzer zugänglich. Der Zugriff auf das Ändern der Begrüßungsnachrichten dieser Postfächer ist jedoch nach der Migration zu CVM nicht mehr verfügbar. Kunden mit freigegebenen Postfächern, die zum Erfassen von Anrufern für automatische Telefonzentralen verwendet werden, sollten nach der Veröffentlichung (ETA Oktober 2019) die Funktionen "Automatische Telefonzentralen" und "Freigegebene Postfachfunktionen für Anrufwarteschleifen" nutzen.
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Das Banner "Benutzername verwendet nicht Skype for Business" wird angezeigt.

Der CVM-Dienst basiert auf der Microsoft Teams-Infrastruktur, und Aufrufe von einem Skype for Business-Client können dazu führen, dass auf dem Client ein Informationsbanner angezeigt wird, das lautet: "Benutzername verwendet nicht Skype for Business. Um eine umfassendere Erfahrung zu erhalten, wechseln Sie zu Teams, oder starten Sie eine Skype Besprechung."
Stellen Sie sicher, dass Sie den Skype for Business Client Ihrer Benutzer auf das neueste C2R-Clientupdate aktualisieren, um zu verhindern, dass dieses Banner angezeigt wird.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Einrichten von Voicemail" führt Sie zu OWA

Wenn Sie vom Client aus auf "**Voicemail einrichten**" klicken, werden Kunden von Skype for Business Server 2015/2013 nach der Migration zu CVM weiterhin zur Portalseite Office Web Access (OWA) wechseln. Alle Einstellungen wurden von der Voicemail-Registerkarte in OWA entfernt, und ein Banner wird mit einem Umleitungslink angezeigt, um Benutzer zum CVM-Benutzereinstellungsportal zu bringen.

#### <a name="changing-greeting-remotely"></a>Remoteänderung der Begrüßung

PSTN-Abonnentenzugriff wird in CVM nicht unterstützt. Für Benutzer, die ihre Ansage remote ändern müssen, wurde dem Voicemail-IVR-Dienst für mobile Clients eine Menüoption "Ihre Begrüßung ändern" hinzugefügt. Benutzer können diesen Dienst anrufen, indem sie die Taste "1" auf der Wähltastatur des mobilen Clients drücken und gedrückt halten.