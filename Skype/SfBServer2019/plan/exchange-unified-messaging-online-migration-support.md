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
description: Microsoft gibt den dienst Exchange Unified Messaging Online (ExchUMO) bis zum 28. Februar 2020 zurück. In diesem Artikel wird zusammengefasst, was betroffene Kunden wissen und tun sollten, um ihre Geschäftskontinuität zu planen.
ms.openlocfilehash: 66a3446b667d000e3cd0a043e60e2f0ea0eae183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606824"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Migrationsunterstützung für Exchange Unified Messaging Online

> [!IMPORTANT]
> **Der Unified Messaging-Dienst in Exchange Online wird ab dem 28. Februar 2020, 17:00 Uhr Pacific Time, nicht mehr unterstützt. Alle Voicemailkonten wurden von Microsoft zu Cloud-Voicemail Dienst migriert. Der verbleibende Datenverkehr der automatischen Telefonzentrale wird nicht überwacht und kann jederzeit unterbrochen werden.**

In Bezug auf die [Ankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) vom 8. Februar 2019 gibt Microsoft den Dienst Exchange Unified Messaging Online (ExchUMO) bis zum 28. Februar 2020 zurück. Dieser Artikel enthält eine Zusammenfassung dessen, was betroffene Kunden wissen und tun sollten, um ihre Geschäftskontinuität zu planen.

ExchUMO wird von Kunden für Voicemail, automatische Telefonzentrale, Anrufwarteschleife und Faxintegrationsdienste bereitgestellt. Microsoft plant, Kunden bei der Migration zu Telefonsystem Diensten zu unterstützen, die bereits Tausende von Kunden auf Skype for Business Online und Microsoft Teams unterstützen.

Voicemail ist in erster Linie eine von Microsoft gesteuerte Migration; Die Administratorbeteiligung und/oder -investition kann für eine Teilmenge der Kunden erforderlich sein. Die automatische Telefonzentrale ist eine vom Administrator gesteuerte Migration. Sie müssen die vorhandenen Strukturen der automatischen ExchUMO-Telefonzentrale im Cloud-Clouddienst für automatische Telefonzentralen neu erstellen. Kunden, die eine der ExchUMO-Features mit einer Pbx eines Drittanbieters nutzen, werden nicht zu Skype Clouddiensten migriert, da sie keine PbX-Systeme von Drittanbietern unterstützen. In [diesem Blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)wurde ein Einstellungsplan für Drittanbieterunterstützung angekündigt, und Kunden in diesem Bereitstellungsmodell können ihre Benutzer zu einer der Unified Communications-Plattformen/-Dienste von Microsoft migrieren oder eine Voicemail- und/oder automatische Telefonzentralenlösung von Drittanbietern für diese Benutzer erwerben. Die Faxintegration wird in den cloudbasierten Diensten nicht unterstützt. Kunden müssen zu einer Drittanbieterlösung migrieren.

## <a name="who-is-affected"></a>Wer ist betroffen?

Kunden, die eines der folgenden Features des Exchange Unified Messaging Online-Diensts verwenden, sind betroffen:

- Voicemaildienst
- Dienst für automatische Telefonzentrale
- Anrufwarteschleifendienst
- Faxintegration

> [!Note]
> Kunden, die eines der Exchange Server lokal mit Unified Messaging verwenden, sind davon nicht betroffen.

Erfahren Sie mehr über die Auswirkungen auf die Benutzer- und Administratorumgebung in [Bezug auf die Auswirkungen auf die Benutzererfahrung.](#user-experience-impact)

## <a name="migration-plan-overview"></a>Übersicht über den Migrationsplan

Microsoft hat verschiedene Kundenbereitstellungen identifiziert, die Features von ExchUMO nutzen, und unterstützt Kunden bei der Migration basierend auf dem folgenden Plan.

|Kundengruppe |Zeitachse  |Details  |
|---------|---------|---------|
|Kunden, die für die Migration bereit sind<br><br>Zu migrierende Features:<br><ul><li>Voicemail</ul>   |   März - Mai 2019  |Beispiele:<ul><li>    Kunden mit einfacher Voicemailbereitstellung und -verwendung<li>Kunden, für die alle Anforderungen für Microsoft für die Durchführung der Migration festgelegt wurden<ul>|
|Kunden mit Voraussetzungen<br><br>Zu migrierende Features:<br><ul><li>Voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschleife</ul> |  Mai - Dezember 2019 |Beispiele: <br><ul><li>Hybridkonfiguration ist nicht abgeschlossen<li>Hybrid-PSTN-Nummern sind nicht eingerichtet</ul>|
|Kunden, die eine Administratorbeteiligung & Kundeninvestitionen erfordern<br><br>Zu migrierende Features:<ul><li>voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschleifen<li>Faxintegration</ul>| Bis Februar 2020  | Beispiele: <br><ul><li>ExchUMO-Dienst wird von Nebenstellenanlagen von Drittanbietern genutzt.<li>Kunden mit Anforderungen für den PSTN-Abonnentenzugriff<li>Kunden auf SFB 2010 (nicht unterstützt)<li>Faxintegration</ul> |

## <a name="voicemail-migration-guidelines"></a>Richtlinien für die Voicemailmigration

### <a name="get-informed"></a>Informieren

Machen Sie sich mit der [Blogankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) und diesem Artikel vertraut, um eine reibungslose Migration für Ihre Benutzer zu planen. Weitere Informationen zu den Telefonsystem Voicemailfunktionen finden Sie unter ["Check Skype for Business voicemail and options".](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Einrichten einer Skype for Business Hybridtopologie

Wenn Sie keine Skype for Business Hybridtopologie eingerichtet haben, müssen Sie dies tun, um eine reibungslose Migration Ihrer Voicemailbenutzer zu ermöglichen. Weitere Informationen finden Sie unter [Konfigurieren Skype for Business Hybrid.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)

> [!Note]
> Sie müssen Ihre Benutzer für die Migration des Voicemaildiensts nicht online migrieren. Damit lokale Benutzer jedoch Telefonsystem Voicemaildienst nutzen können, muss eine Hybridtopologie eingerichtet werden.

### <a name="plan-your-auto-attendant-migration"></a>Planen der Migration ihrer automatischen Telefonzentrale

Administratoren können jederzeit mit der Migration ihrer automatischen Telefonzentralen von ExchUMO zur automatischen Cloudtelefonzentrale beginnen. Weitere Informationen finden Sie unter [Einrichten einer automatischen Cloudtelefonzentrale.](/microsoftteams/create-a-phone-system-auto-attendant)

Microsoft bietet weiterhin zusätzliche Funktionen für automatische Telefonzentralen, die Kunden möglicherweise für ihre Migration benötigen. Administratoren sollten den Featuresatz auswerten und ihre Instanzen der automatischen Telefonzentrale entsprechend migrieren. Einen Vergleich der Featureliste finden Sie in der Featurematrix für [ExchUMO und Azure cloudbasierte Dienste.](#exchumo-and-azure-cloud-based-services-feature-matrix)

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planen der Überprüfung und des Testens ihrer Voicemail nach der Migration

Die Voicemailmigration wird von Microsoft gesteuert. Administratoren müssen nichts unternehmen, da die erforderliche Hybridtopologie eingerichtet ist. Microsoft führt die erforderlichen Überprüfungen und Tests durch, um sicherzustellen, dass die Voicemailmigration der Benutzer nicht unterbrochen wird. Administratoren werden empfohlen, Tests und Überprüfungen auf ihrer Seite durchzuführen. Einen empfohlenen Testplan finden Sie unter ["Vorgeschlagener Testplan und Überprüfung nach der Migration für Administratoren".](#suggested-test-plan-and-post-migration-validation-for-admins)

> [!Note]
> Lync Server 2010 wird nicht unterstützt. Wenn Sie sich in einer Serverbereitstellung 2010 befinden, sollten Sie ein Serverupgrade planen oder erwägen, Ihre Benutzer zu Microsoft Teams zu migrieren.  

### <a name="monitor-the-admin-notification-center"></a>Überwachen des Admin Notification Centers

Sehen Sie sich einen Hinweis im Admin Notification Center mit weiteren Details und einer Zeitachse zur Migration Ihrer Benutzer an. Benachrichtigungen werden mindestens 30 Tage vor dem Migrationszeitraum gesendet.

> [!Note]
> Wenn Sie eine Benachrichtigung mit dem Migrationszeitpunkt Ihrer Benutzer erhalten haben und Ihre Migration aus einem unternehmenskritischen Grund verschieben möchten, können Sie sich dazu an den Microsoft-Support wenden. Sie können Ihre Migration nicht über das Datum der Einstellung vom 28. Februar 2020 hinaus verschieben. Kunden, die möglicherweise weitere Fragen haben, wenden Sie sich an Ihr Kontoteam oder den Microsoft-Support. Kunden, die bereits Microsoft 365 oder Office 365 verwenden, können einen Supportfall über die Microsoft 365 Admin Center einreichen.

### <a name="consider-opting-in-for-a-planned-migration"></a>Erwägen Sie, sich für eine geplante Migration zu entscheiden.

Sie können sich für eine geplante Migration des Voicemaildiensts zu CVM entscheiden. Bevor Sie sich anmelden, lesen Sie die Details dieses Artikels, insbesondere die folgenden Abschnitte:

- Migrationsschritte (dieser Abschnitt)
- Featurematrix für ExchUMO- und Azure-Clouddienste
- Auswirkungen auf die Benutzererfahrung

Wenn Sie eine verwaltete Migration auswählen, erhalten Sie keine 30-tage-Benachrichtigung vor der Migration im Nachrichtencenter Microsoft 365 Admin Portal.

Um sich für eine geplante Migration zu entscheiden, senden Sie eine E-Mail-Anforderung von der E-Mail-Adresse Ihres Administrators an [cvm@microsoft.com](mailto:cvm@microsoft.com) mit den folgenden Informationen:

- Bevorzugtes Datum (Dienstag): Migrationsströme werden jeden Dienstag ausgeführt. Wählen Sie ein Datum an einem Dienstag aus, das nicht über den 3.12.2019 hinausgeht.
 
- Mandanten-ID: 32 Zeichen in diesem Format 0046728c-688a-4472-a38f-098fec60ac6x. Sie finden Ihre Mandanten-ID im Microsoft 365 Verwaltungsportal unter Azure AD oder mit dem folgenden PowerShell-Cmdlet:`Get-CsTenant | Select ObjectId`

Sie erhalten eine E-Mail-Bestätigung, sobald Ihr Mandant erfolgreich migriert wurde.

## <a name="auto-attendant-migration-guidelines"></a>Migrationsrichtlinien für automatische Telefonzentralen

Microsoft 365 und Office 365 Organisationsadministratoren müssen ihre Exchange automatischen UM Online-Telefonzentralen im Microsoft Cloud Auto Attendant-Dienst neu erstellen und ihre lokalen Telefonnummern vor dem Einstellungsdatum des Exchange UMO-Diensts vom 28. Februar 2020 auf sie umstellen. Dies ist die empfohlene Richtlinie, um neue automatische Cloudtelefonzentralen erfolgreich zu migrieren und zu testen. Wenn Sie über eine große Anzahl automatischer Telefonzentralen verfügen, können Sie die Skripts Exchange automatische [UM-Telefonzentrale zur Migration](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automatischer Telefonzentralen in die Cloud verwenden, um die Massenmigration automatischer Telefonzentralen zu vereinfachen.

### <a name="auto-attendant-setup"></a>Einrichten der automatischen Telefonzentrale

Es wird dringend empfohlen, die Einrichtung Ihrer neuen automatischen Telefonzentralen frühzeitig zu starten, um Probleme in letzter Minute zu vermeiden und sich mit der Funktionalität und Erfahrung des Cloud-Telefonzentralendiensts vertraut zu machen. Für automatische Telefonzentralen, die eine oder mehrere Lückenfeatures erfordern, können Sie die automatischen Telefonzentralen erstellen und testen, wenn die Lückenfeatures für die Bereitstellung verfügbar sind. Weitere Informationen zu Lückenfeatures finden Sie im [Anhang.](#appendix)

1. Verwenden Sie die Exchange UMO-Cmdlets, um die Konfiguration vorhandener automatischer Telefonzentralen mithilfe von [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant)zu exportieren.  
2. Verwenden Sie das Cmdlet ["Export-UMprompt"](/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell, um die Begrüßungsmediendateien (sofern verwendet) zu exportieren und in .mp3 Format zu konvertieren.
3. Folgen Sie den Anweisungen unter [Planen automatischer Cloudtelefonzentralen](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) und [Einrichten einer automatischen Cloudtelefonzentrale](/microsoftteams/create-a-phone-system-auto-attendant) zum Erstellen automatischer Telefonzentralen mithilfe des Microsoft Teams Admin Centers oder von PowerShell.
4. Überprüfen Sie Ihre Begrüßungen, wenn sich die Menüoptionen geändert haben.
5. Konfigurieren Sie Übertragungen an Ihre Reaktionsgruppen mithilfe der Problemumgehung "Automatische Telefonzentralenanrufübertragung zu PSTN" im Abschnitt ["Bekannte Probleme"](#known-issues) dieses Artikels.  
6. Testen Sie die neuen automatischen Telefonzentralen, indem Sie sie intern anrufen oder eine Testtelefonnummer zuweisen.  

### <a name="cutover"></a>Übernahmemigration

1. Wechseln Sie Ihre Telefonnummern von Exchange automatischen UMO-Telefonzentralen zu den neuen automatischen Telefonzentralen.
2. Verschieben Sie den SIP-URI aus dem Kontaktobjekt in das Ressourcenkonto.
3. Testen und überprüfen Sie Ihre automatischen Telefonzentralen mithilfe der neu zugewiesenen Telefonnummern.

## <a name="appendix"></a>Anhang

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Featurematrix für ExchUMO- und Azure-Clouddienste

| Dienst | Featureebene | Feature | Anmerkungen  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Dienstfeatures| Unterstützen von Nebenstellenanlagen von Drittanbietern    | Einschließen aller Funktionen, die für Nebenstellenanlagen von Drittanbietern bereitgestellt werden, z. B. MWI (Message Waiting Indicator) mit SIP-Benachrichtigungsnachrichten von Exchange UM Online | N   | J    |
| VM | Dienstfeatures  | Support Skype for Business Server   |  | v | v    |
| VM | Dienstfeatures | Support Microsoft Teams|  | J | N    |
| VM | Dienstfeatures | eDiscovery und Aufbewahrung  | Für Sicherheit und Compliance  | v | v    |
| VM | Dienstfeatures | Exchange Unterstützung von Regeln | Für Sicherheit und Compliance  | v | v    |
| VM | Benutzerfeatures | PSTN-Einwahlzugriff  | Abonnentenzugriff  | N | J    |
| VM | Benutzerfeatures | Stellvertretung  | Verpasste Anruf-E-Mail  | N | J    |
| VM | Benutzerfeatures | PSTN-Outlook VoIP-Zugriff   | Abonnentenzugriff  | N | J    |
| VM | Benutzerfeatures | Einwahl mithilfe eines authentifizierten Endpunkts | Anrufen des Voicemaildiensts zum Abhören von Sprachnachrichten und Ändern von Voicemaileinstellungen| v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren von Voicemail   |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Ändern der persönlichen Begrüßung  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Erstellen einer OOF-Begrüßung  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Ändern der Standardsprache  |  | v | v    |
| VM | Benutzerfeatures | Benutzereinstellung zum Überschreiben der Standardbegrüßung mit TTS  |  | J | N    |
| VM | Benutzerfeatures | Aufzeichnen persönlicher Begrüßungen (authentifiziertes Gerät) |  | v | v    |
| VM | Benutzerfeatures | Aufzeichnen von persönlichen Begrüßungen (PSTN) – Wiedergabe auf dem Telefon |  | N | J    |
| VM | Benutzerfeatures | Benutzereinstellung zum Deaktivieren der Transkription |  | N | J    |
| VM | Benutzerfeatures | Transkription  |  | v | v    |
| VM | Benutzerfeatures | MWI (Message Waiting Indicator) mit SIP-Benachrichtigungsnachrichten |  | N | J    |
| VM | Benutzerfeatures | MP3-Audiodateiformat in Outlook    |  | v | v    |
| VM | Benutzerfeatures | Steuerung der Wiedergabe mit variabler Geschwindigkeit |  | v | v    |
| VM | Benutzerfeatures | Weiterleiten einer Voicemail  | Weiterleiten einer empfangenen Voicemail an andere Benutzer | v | v    |
| VM | Benutzerfeatures | Senden einer Sprachnachricht an eine Gruppe von Benutzern  |Voicemailübertragung   | N | J   |
| VM | Benutzerfeatures | Voicemailbenachrichtigung per SMS    | Benutzer können eine SMS empfangen, wenn sie über eine neue Voicemail verfügen    | N | J    |
| VM | Benutzerfeatures | Unterstützte Begrüßungssprachen | Details finden Sie hier: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| VM | Benutzerfeatures | Mailboxansageregeln |  | v | v    |
| VM | Benutzerfeatures | Wiedergeben auf dem Telefon (PSTN) – Zum Wiedergeben von Nachrichten | Rufen Sie mich in meiner Zelle auf, um die Sprachnachricht zu hören.  | N | J    |
| VM | Benutzerfeatures | Wiedergabe auf dem Telefon (Auth) – zum Wiedergeben von Nachrichten | Rufen Sie mich auf meinem authentifizierten Gerät auf  | N | J    |
| VM | Benutzerfeatures | Freigegebenes Postfach zwischen mehreren Benutzern |  | v | v    |
| VM | Anruferfeatures  | Anrufererfahrung – geschützte Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als geschützt zu kennzeichnen.| N | J    |
| VM | Anruferfeatures  | Anrufererfahrung – private Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als privat zu kennzeichnen.  | N | J    |
| VM | Anruferfeatures  | Stille erkennung   |  | N | J    |
| VM | features Tenant-Admin | Geschützte Voicemail auf Serverebene    | Mandantenadministratoren können eine Regel auf Dienstebene konfigurieren, um eingehende Voicemail als geschützt zu kennzeichnen. | v | v    |
| VM | features Tenant-Admin | Ändern des Zeitlimits für die Aufzeichnungsdauer  |     | v | v    |
| VM | features Tenant-Admin | Timeout für die Stilleerkennung ändern    |  | Nicht zutreffend    | J    |
| VM | features Tenant-Admin | Ändern der Anzahl von Eingabefehlern | CVM: hartcodiert auf 3 | N | J    |
| VM | features Tenant-Admin | Ändern der Standardsprache |  | v | v    |
| VM | features Tenant-Admin | Deaktivieren/Aktivieren der Transkription |  | v | v    |
| VM | features Tenant-Admin | Deaktivieren/Aktivieren einer Benachrichtigung über verpasste Anrufe |  | N | J    |
| VM | features Tenant-Admin | Helfen Sie Microsoft bei der Verbesserung der Voicemailvorschau    |  | v | v    |
| VM | features Tenant-Admin | Anpassen der Textnachricht für aktivierte Benutzer|  | Nicht zutreffend    | J    |
| VM | features Tenant-Admin | Profanitätsmaske für Transkription|  | J | N    |
| VM | features Tenant-Admin | Voicemailrichtlinie    |   | v | v    |
| VM | features Tenant-Admin | Webportalverwaltung   |  | CY19   | J    |
| VM | features Tenant-Admin | PowerShell   |  | v | v    |
| UM | Benutzerfeatures | Nachrichtenwarteindikator (Message Waiting Indicator, MWI) auf Skype for Business zertifizierten Telefonen   |Kann vom Telefonpartner bereitgestellt werden  | Nein | Ja    |
| AA | Dienstfeatures | AA-Unterstützung für Nebenstellenanlagen von Drittanbietern    |  | N | J    |
| AA | Dienstfeatures | Support Skype for Business Server   |  | v | v    |
| AA | Dienstfeatures | Support Microsoft Teams|  | J | N    |
| AA | Dienstfeatures | Wählen nach Name, DTMF-Eingabe    |  | v | v    |
| AA | Dienstfeatures | Wählen nach Name, Spracheingabe  |  | v | v    |
| AA | Dienstfeatures | Unterstützung für mehrere Sprachen | Sprachdetails hier: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| AA | Dienstfeatures | Übertragung an operator, CQ oder einen Benutzer |  | v | v    |
| AA | Dienstfeatures | Interne Übertragung auf PSTN-Nummer (DID RNL)  |  | v | v    |
| AA | Dienstfeatures | Externe Übertragung an PSTN-Nummer  |  | Lesen Sie den Abschnitt "Bekannte Probleme" weiter unten. | J    |
| AA | Dienstfeatures | Geschäftszeiten |  | v | v    |
| AA | Dienstfeatures | Menüoptionen | IVR-Menüoptionen  | v | v    |
| AA | Dienstfeatures | Zuweisen einer Cloud-PSTN-Nummer zu AA |  | J | N    |
| AA | Dienstfeatures | Zuweisen einer lokalen PSTN-Nummer zu AA  |  | v | v    |
| AA | Dienstfeatures | Benutzerdefinierte Benutzerauswahl  | Ermöglichen, dass Anrufer eine angepasste Liste von Organisationsbenutzern erreichen| v | v    |
| AA | Dienstfeatures | Behandlung nach Feierabend und Feiertagen  |  | v | v    |
| AA | Dienstfeatures | Benutzerdefinierte Begrüßung mit Text-zu-Sprache  |  | v | v    |
| AA | Dienstfeatures | Durchwahl wählen   | Erreichen eines Benutzers durch Wählen seiner Erweiterung  | v   | v    |
| AA | Dienstfeatures | Postfach für AA-Aufrufer, um eine Nachricht zu hinterlassen    |  | v   | v    |
| AA | Dienstfeatures | Mehrere PSTN-Nummernzuweisungen zu einem AA|  | v | v    |
| AA | features Tenant-Admin | Webportalverwaltung   |  | J | N    |
| AA | features Tenant-Admin | PowerShell-Cmdlets  |  | v | v    |
| Fax| Dienstfeatures | Faxintegration|  | N | J    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Vorgeschlagener Testplan und Überprüfung nach der Migration für Administratoren

Um zu überprüfen, ob Ihre Benutzer zu Cloud-Voicemail migriert wurden, überlassen Sie einem Benutzer eine Voicemail, und überprüfen Sie den Nachrichtentext in Outlook. Cloud-Voicemail Nachrichten haben eine Fußzeile, die Liest:

"Vielen Dank für die Verwendung der Transkription! Wenn oben keine Transkription angezeigt wird, liegt dies daran, dass die Audioqualität zum Transkribieren nicht klar genug war."

Berücksichtigen Sie beim Testen der Voicemailfunktionalität nach der Migration Ihrer Benutzer die folgenden Szenarien:

- Überprüfen des Voicemailzugriffs auf alle Endpunkttypen in Ihrer Organisation, z. B. Apps und IP-Telefone.
- Überprüfen Sie mit Beispielbenutzern, ob die konfigurierten personalisierten Begrüßungen für Anrufer wiedergegeben werden.
- Wenn Ihre Organisation eine gesetzliche oder Compliance-Anforderung zum Deaktivieren der Transkription für Benutzer hat, stellen Sie sicher, dass sie nach der Migration deaktiviert ist. Weitere Informationen finden Sie unter [Einrichten Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Wenn Sie zuvor Exchange VM-Richtlinien und -Regeln konfiguriert haben, stellen Sie sicher, dass diese effektiv sind.
- Machen Sie sich mit den PowerShell-Cmdlets des Cloud-Voicemail Diensts zum Ändern von Benutzereinstellungen vertraut.  

### <a name="user-experience-impact"></a>Auswirkungen auf die Benutzererfahrung

Es folgt eine Übersicht über die Voicemailmigration für Endbenutzer.


|Umgebung  |Änderung der Benutzererfahrung|
|---------|---------|
|E-Mail-Benachrichtigung | Keine Änderung<br>Es wird keine E-Mail an Benutzer gesendet, die sie über die Aktivierung/Migration des Voicemailkontos benachrichtigen. |
|Zugriff auf vorherige Nachrichten | Keine Änderung<br>Benutzer haben Zugriff auf ihre vorherigen Voicemailnachrichten an allen unterstützten Endpunkten. |
|Empfangen eines virtuellen Computers in Outlook, SFB-Apps| Keine Änderung<br>Benutzer erhalten weiterhin ihre Voicemailnachrichten an allen unterstützten Endpunkten. |
|Transkription | Verbesserte<br>Die CVM-Transkription hat eine wesentlich höhere Genauigkeitsrate und unterstützte Sprachen als ExchUMO. |
|Benutzereinstellung | Neue Erfahrung<br>Benutzer können ihre Einstellungen über ein Benutzereinstellungsportal (User Setting Portal, USP) ändern. Benutzer können über einen Link in ihrer Voicemail-E-Mail oder über die Schaltfläche User-Settings auf ihrem SFB-Client auf ihre USP zugreifen. https://aka.ms/vmsettings.
 |Features| Weitere Informationen finden Sie im Vergleich mit den Featuregruppen. |
|Outlook Regeln für VM-Nachrichten | Keine Änderung<br>Zuvor erstellte Regeln gelten nach der Migration für CVM-Nachrichten.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Benutzerverwaltung und -bereitstellung in CVM

Neue Skype for Business Benutzer werden bei der Erstellung automatisch für Cloud-Voicemail bereitgestellt. Es sind keine zusätzlichen Administratoraufgaben oder Lizenzen erforderlich, um neue Voicemailbenutzer bereitzustellen. Weitere Informationen zur Richtlinienverwaltung für vorhandene und neue Benutzer finden Sie unter ["Einrichten von Cloud-Voicemail".](/microsoftteams/set-up-phone-system-voicemail)

### <a name="admin-auto-attendant-management-experience"></a>Verwaltung der automatischen Telefonzentrale für Administratoren

Weitere Informationen zu automatischen Telefonzentralen finden Sie unter [Einrichten einer automatischen Cloudtelefonzentrale.](/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>Bekannte Probleme

#### <a name="greeting-inconsistencies"></a>Begrüßungsinkonsistenzen

Der Abonnentenzugriff funktioniert möglicherweise weiterhin für Ihren Mandanten, bis der Dienst vollständig eingestellt ist, auch nachdem alle Ihre Benutzer zu Cloud-Voicemail migriert wurden. Um Benutzerkonsistenz und eine inkonsistente Erfahrung zu vermeiden, deaktivieren Sie den Abonnentenzugriff, da sich die Begrüßungen nach der Migration ändern. Entfernen Sie dazu den EXUM-Kontakt für jede Teilnehmerzugriffszeile mit `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Automatische Anrufweiterleitung an das Telefonfestnetz

Um einen Anruf einer automatischen Telefonzentrale an eine externe PSTN-Telefonnummer über Skype for Business Server oder einen Reaktionsgruppendienst (Response Group Service, RGS) auf Skype for Business Server zu übertragen, erstellen Sie einen neuen lokalen Benutzer, für den die Anrufweiterleitung auf die PSTN-Telefonnummer oder die RGS-Telefonnummer festgelegt ist. Der Benutzer muss für Enterprise-VoIP aktiviert und ordnungsgemäß konfiguriert sein und eine VoIP-Richtlinie zugewiesen haben.

#### <a name="shared-mailbox-is-still-accessible"></a>Auf freigegebene Postfächer kann weiterhin zugegriffen werden

Ein freigegebenes Postfach, das mit Exchange UM Online konfiguriert wurde, empfängt nach der Migration zu CVM weiterhin Nachrichten und kann über Outlook für Benutzer zugänglich sein. Der Zugriff auf das Ändern der Begrüßungsnachrichten dieser Postfächer ist jedoch nach der Migration zu CVM nicht mehr verfügbar. Kunden mit freigegebenen Postfächern, die zum Erfassen automatischer Telefonzentralen-Anrufer verwendet werden, sollten nach der Veröffentlichung (ETA Oktober 2019) die Funktionen der automatischen Telefonzentralen und der Anrufwarteschleifen für freigegebene Postfächer nutzen.
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Banner "Benutzername verwendet nicht Skype for Business"

Der CVM-Dienst basiert auf der Microsoft Teams Infrastruktur, und Anrufe von einem Skype for Business-Client können dazu führen, dass ein Informationsbanner auf dem Client angezeigt wird, der lautet: "Benutzername verwendet Skype for Business nicht. Um eine umfassendere Erfahrung zu bieten, wechseln Sie zu Teams oder starten Sie eine Skype Besprechung."
Stellen Sie sicher, dass Sie den Skype for Business-Client Ihrer Benutzer auf das neueste C2R-Clientupdate aktualisieren, um zu verhindern, dass dieses Banner angezeigt wird.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Einrichten von Voicemail" führt Sie zu OWA

Durch Klicken auf "Einrichten von **Voicemail** vom Client" gelangen Skype for Business Server 2015/2013-Kunden nach der Migration zu CVM weiterhin zur Portalseite Office Web Access (OWA). Alle Einstellungen wurden von der Registerkarte "Voicemail" in OWA entfernt, und ein Banner wird mit einem Umleitungslink angezeigt, um Benutzer zum CVM-Benutzereinstellungsportal zu bringen.

#### <a name="changing-greeting-remotely"></a>Remote-Ändern der Begrüßung

Der PSTN-Abonnentenzugriff wird in CVM nicht unterstützt. Für Benutzer, die ihre Begrüßung remote ändern müssen, wurde dem Voicemail-IVR-Dienst für mobile Clients die Menüoption "Begrüßung ändern" hinzugefügt. Benutzer können diesen Dienst anrufen, indem sie die Taste "1" auf der Wähltastatur des mobilen Clients gedrückt halten.