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
description: Microsoft stellt den Exchange Unified Messaging Online-Dienst ("Moreo") bis zum 28. Februar 2020 in Ruhestand. In diesem Artikel wird zusammengefasst, was betroffene Kunden wissen sollten und was Sie tun müssen, um Ihre Geschäftskontinuität zu planen.
ms.openlocfilehash: 5d7d9b2e488c61c881395ad00d2675d749e5e30f
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359301"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Migrationsunterstützung für Exchange Unified Messaging Online

> [!IMPORTANT]
> **Der Unified Messaging-Dienst in Exchange Online wird vom 28. Februar 2020, 17:00 Uhr Pacific Time, nicht mehr unterstützt. Alle Voicemail-Konten wurden von Microsoft zum Cloud-Voicemaildienst migriert. Jeder verbleibende automatische Telefonzentralen-Datenverkehr wird nicht überwacht und kann jederzeit gestört werden.**

In Bezug auf die [Ankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) am 8. Februar 2019 stellt Microsoft den Exchange Unified Messaging Online-Dienst ("Service") bis zum 28. Februar 2020 in Ruhestand. In diesem Artikel finden Sie eine Zusammenfassung der Auswirkungen, die betroffene Kunden kennen sollten und die Sie zur Planung Ihrer Geschäftskontinuität ausführen sollten.

Der Dienst wird von Kunden für Voicemail, automatische Telefonzentrale, Anrufwarteschlange und Fax-Integrationsdienste bereitgestellt. Microsoft plant, Kunden bei der Migration zu Telefon System Diensten zu unterstützen, die bereits Tausende von Kunden in Skype for Business Online und Microsoft Teams unterstützen.

Voicemail ist in erster Linie eine von Microsoft gesteuerte Migration; für eine Teilmenge der Kunden ist möglicherweise die Einbindung von Administratoren und/oder Investitionen erforderlich. Die automatische Telefonzentrale ist eine vom Administrator gesteuerte Migration; Sie müssen die vorhandenen automatischen Telefonzentralen-Strukturen in der Cloud-clouddienst der automatischen Telefonzentrale neu erstellen. Kunden, die eine der Funktionen von "Extras" mit einer Drittanbieter-Nebenstellenanlage nutzen, werden nicht zu Skype Cloud Services migriert, da Sie keine Drittanbieter-PBX-Systeme unterstützen. Ein ruhestandsplan für Drittanbieterunterstützung wurde in [diesem Blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)angekündigt, und Kunden in diesem Bereitstellungsmodell können Ihre Benutzer zu einer der Unified Communications Plattformen/Dienste von Microsoft migrieren oder eine Lösung für Voicemail und/oder automatische Telefonzentrale für diese Benutzer erwerben. Die Fax-Integration wird in den cloudbasierten Diensten nicht unterstützt; Kunden müssen zu einer Drittanbieterlösung migriert werden.

## <a name="who-is-affected"></a>Wer ist betroffen?

Kunden, die eines der folgenden Features aus dem Exchange Unified Messaging-Online Dienst verwenden, sind betroffen:

- Voicemail-Dienst
- Automatischer Telefonzentralen Dienst
- Anruf Warteschlangendienst
- Fax-Integration

> [!Note]
> Kunden, die eine der Exchange Server lokal mit Unified Messaging verwenden, sind davon nicht betroffen.

Erfahren Sie mehr über die Auswirkungen auf die Benutzer [Oberfläche](#user-experience-impact)und den Administrator.

## <a name="migration-plan-overview"></a>Übersicht über den Migrationsplan

Microsoft hat verschiedene Kundenbereitstellungen identifiziert, die Features von "prochumo" nutzen, und Kunden dabei helfen, die Migration basierend auf dem folgenden Plan durch zufinden.

|Kundengruppe |Zeitachse  |Details  |
|---------|---------|---------|
|Kunden, die zur Migration fähig sind<br><br>Zu migrierende Features:<br><ul><li>Voicemail</ul>   |   März – Mai 2019  |Beispiele:<ul><li>    Kunden mit einfacher Voicemail-Bereitstellung und-Nutzung<li>Kunden mit allen Anforderungen, die für Microsoft zum Ausführen der Migration eingerichtet wurden<ul>|
|Kunden mit Voraussetzungen<br><br>Zu migrierende Features:<br><ul><li>Voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschlange</ul> |  Mai — Dezember 2019 |Beispiele: <br><ul><li>Die Hybrid Konfiguration ist nicht abgeschlossen.<li>Hybride PSTN-Nummern sind nicht eingerichtet</ul>|
|Kunden, die eine Administratorbeteiligung & Kundeninvestition benötigen<br><br>Zu migrierende Features:<ul><li>voicemail<li>Automatische Telefonzentrale<li>Anrufwarteschlangen<li>Fax-Integration</ul>| Bis Februar 2020  | Beispiele: <br><ul><li>Der Dienst wird von einer Drittanbieter-Nebenstellenanlage genutzt.<li>Kunden mit PSTN-Teilnehmerzugriffs Anforderungen<li>Kunden im SFB 2010 (nicht unterstützt)<li>Fax-Integration</ul> |

## <a name="voicemail-migration-guidelines"></a>Richtlinien zur Voicemail-Migration

### <a name="get-informed"></a>Informieren Sie sich

Machen Sie sich mit der [Blog Ansage](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) und diesem Artikel vertraut, um eine reibungslose Migration für Ihre Benutzer zu planen. Weitere Informationen finden Sie unter [überprüfen Skype for Business Voicemail und Optionen](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) für die Voicemailfunktionen des Telefonsystems.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Einrichten einer Skype for Business Hybrid Topologie

Wenn Sie keine Skype for Business Hybrid Topologie eingerichtet haben, müssen Sie dies tun, um eine reibungslose Migration Ihrer Voicemail-Benutzer zu ermöglichen. Weitere Informationen finden Sie unter [configure Skype for Business Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) .

> [!Note]
> Sie müssen Ihre Benutzer nicht online für die Migration von Voicemail-Diensten migrieren. Damit lokale Benutzer den Voicemaildienst für den Telefon System nutzen können, muss jedoch eine Hybrid Topologie eingerichtet werden.

### <a name="plan-your-auto-attendant-migration"></a>Planen der Migration der automatischen Telefonzentrale

Administratoren können die Migration Ihrer automatischen Telefonzentralen jederzeit von der automatischen Telefonzentrale zur Cloud starten. Weitere Informationen finden Sie unter [Einrichten einer automatischen Cloud-Telefonzentrale](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) .

Microsoft stellt weiterhin zusätzliche Funktionen für die automatische Telefonzentrale bereit, die Kunden möglicherweise für Ihre Migration für erforderlich halten. Administratoren sollten den Featuresatz auswerten und die Instanzen der automatischen Telefonzentrale entsprechend migrieren. Einen Feature-List-Vergleich finden Sie in der Feature-Matrix von "Verzeichnis [Dienst und Azure Cloud-based Services](#exchumo-and-azure-cloud-based-services-feature-matrix)".

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planen der Überprüfung und des Tests für Voicemail nach der Migration

Die Voicemail-Migration wird von Microsoft gesteuert. Administratoren müssen nichts Unternehmen, da die Voraussetzung für eine Hybrid Topologie eingerichtet wurde. Microsoft führt die erforderliche Überprüfung und Tests durch, um sicherzustellen, dass die Voicemail-Migration der Benutzer nicht unterbrochen wird. Administratoren werden ermutigt, Tests und Validierungen auf Ihrer Seite durchzuführen. Weitere Informationen finden Sie unter [vorgeschlagener Testplan und Überprüfung nach der Migration für Administratoren](#suggested-test-plan-and-post-migration-validation-for-admins) für einen empfohlenen Testplan.

> [!Note]
> Lync Server 2010 wird nicht unterstützt. Wenn Sie sich in einer 2010-Server Bereitstellung befinden, sollten Sie ein Server Upgrade planen oder die Migration Ihrer Benutzer zu Microsoft Teams in Betracht gezogen.  

### <a name="monitor-the-admin-notification-center"></a>Überwachen des Administrator-Benachrichtigungs Centers

Achten Sie auf einen Hinweis im Admin Notification Center mit weiteren Details und einer Zeitachse zur Migration Ihrer Benutzer. Benachrichtigungen werden mindestens 30 Tage vor Ihrem Migrationszeitraum gesendet.

> [!Note]
> Wenn Sie eine Benachrichtigung mit dem Migrationszeitplan Ihrer Benutzer erhalten haben und die Migration aus geschäftlichen Gründen verschieben möchten, wenden Sie sich an den Microsoft-Support. Sie können die Migration nicht über das Ruhestands Datum vom 28. Februar 2020 hinaus verschieben. Wenden Sie sich für Kunden, die möglicherweise weitere Fragen haben, an Ihr Konto Team oder an den Microsoft-Support. Kunden, die bereits Microsoft 365 oder Office 365 verwenden, können einen Supportfall über das Microsoft 365 Admin Center übermitteln.

### <a name="consider-opting-in-for-a-planned-migration"></a>Sie sollten sich für eine geplante Migration entscheiden

Sie können sich für eine geplante Voicemail-Dienst Migration zu "Interservice" entscheiden. Lesen Sie vor der Entscheidung die Details zu diesem Artikel, insbesondere die folgenden Abschnitte:

- Migrationsschritte (dieser Abschnitt)
- Matrix für die Feature-und Azure-Cloud-basierte Dienste
- Auswirkungen auf die Benutzeroberfläche

Wenn Sie eine verwaltete Migration auswählen, erhalten Sie keine Benachrichtigung über 30 Tage vor der Migration im Microsoft 365-Verwaltungsportal-Nachrichtencenter.

Wenn Sie sich für eine geplante Migration entscheiden möchten, senden Sie eine e-Mail-Anforderung von der e-Mail-Adresse Ihres Administrators an [cvm@Microsoft.com](mailto:cvm@microsoft.com) mit den folgenden Informationen:

- Bevorzugtes Datum (dienstags): die Migrationswellen werden jeden Dienstag ausgeführt. Wählen Sie ein Datum an einem Dienstag aus, der nicht über 12/3/2019 liegt.
 
- Mandanten-ID: 32 characters number in diesem Format 0046728c-688a-4472-a38f-098fec60ac6x. Sie finden Ihre Mandanten-ID im Microsoft 365-Verwaltungsportal unter Azure AD oder mithilfe des folgenden PowerShell-Cmdlets: `Get-CsTenant | Select ObjectId`

Wenn Ihr Mandant erfolgreich migriert wird, erhalten Sie eine Bestätigung per e-Mail.

## <a name="auto-attendant-migration-guidelines"></a>Migrationsrichtlinien für die automatische Telefonzentrale

Administratoren von Microsoft 365 und Office 365 Organisation müssen Ihre automatischen Exchange um Online-Telefonzentralen im Microsoft Cloud-Dienst für automatische Telefonzentralen neu erstellen und ihre lokalen Telefonnummern vor dem Ruhestands Datum des Exchange UMO-Diensts vom 28. Februar 2020 umschalten. Dies ist die empfohlene Richtlinie für die erfolgreiche Migration und den Test neuer automatischer Cloud-Telefonzentralen. Wenn Sie eine große Anzahl von automatischen Telefonzentralen haben, können Sie die automatische Telefonzentrale mit der [Exchange um automatischen](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) Telefonzentrale migrieren, um die Massenmigration von automatischen Telefonzentralen zu vereinfachen.

### <a name="auto-attendant-setup"></a>Einrichtung der automatischen Telefonzentrale

Es wird dringend empfohlen, frühzeitig mit der Einrichtung ihrer neuen automatischen Telefonzentralen zu beginnen, um Probleme mit der Last Minute zu vermeiden und sich mit der Funktionalität und Erfahrung des automatischen Cloud-Telefonzentralen Diensts vertraut zu machen. Für automatische Telefonzentralen, die ein oder mehrere Lücken Features benötigen, können Sie die automatischen Telefonzentralen erstellen und testen, wenn die Lücken Funktionen zur Vorbereitung auf die Bereitstellung zur Verfügung stehen. Weitere Informationen zu GAP-Funktionen finden Sie im [Anhang](#appendix).

1. Verwenden Sie die Exchange UMO-Cmdlets, um die Konfiguration vorhandener automatischer Telefonzentralen mithilfe von [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)zu exportieren.  
2. Verwenden Sie das Cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) in Exchange Online PowerShell, um die Begrüßungs Mediendateien (sofern verwendet) zu exportieren und in das Format. MP3 umzuwandeln.
3. Befolgen Sie die Anweisungen in [Plan Cloud Auto Attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) , und [richten Sie eine automatische Cloud-Telefonzentrale ein](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) , um automatische Telefonzentralen mithilfe des Microsoft Teams Admin Center oder von PowerShell zu erstellen.
4. Überprüfen Sie Ihre Begrüßungen, wenn sich die Menü Optionen geändert haben.
5. Konfigurieren Sie Übertragungen an Ihre Reaktionsgruppen mithilfe der Problemumgehung für die automatische Telefonzentrale, die in diesem Artikel im Abschnitt [bekannte Probleme](#known-issues) mit PSTN-Telefon Übertragung an das Festnetz erfolgt.  
6. Testen Sie die neuen automatischen Telefonzentralen, indem Sie sie intern aufrufen oder eine Test Telefonnummer zuweisen.  

### <a name="cutover"></a>Übernahmemigration

1. Wechseln Sie Ihre Telefonnummern von automatischen Exchange UMO-Telefonzentralen zu den neuen automatischen Telefonzentralen.
2. Verschiebt den SIP-URI aus dem Kontaktobjekt in das Ressourcenkonto.
3. Testen und überprüfen Sie Ihre automatischen Telefonzentralen mithilfe der neu zugewiesenen Telefonnummern.

## <a name="appendix"></a>Anhang

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrix für die Feature-und Azure-Cloud-basierte Dienste

| Dienst | Funktionsebene | Feature | Anmerkungen  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Dienstfunktionen| Unterstützung für Drittanbieter-PBX    | Einschließlich aller Funktionen, die an Drittanbieter-Nebenstellenanlagen wie MWI (Message Waiting Indicator) mit SIP NOTIFY-Nachrichten von Exchange um Online bereitgestellt werden | N   | v    |
| VM | Dienstfunktionen  | Support Skype for Business Server   |  | v | v    |
| VM | Dienstfunktionen | Unterstützung von Microsoft Teams|  | v | N    |
| VM | Dienstfunktionen | eDiscovery und Aufbewahrung  | Für Sicherheit und Compliance  | v | v    |
| VM | Dienstfunktionen | Unterstützung von Exchange-Regeln | Für Sicherheit und Compliance  | v | v    |
| VM | Benutzerfunktionen | PSTN-Einwahlzugriff  | Teilnehmerzugriff  | N | v    |
| VM | Benutzerfunktionen | Stellvertretung  | e-Mail mit verpassten Anrufen  | N | v    |
| VM | Benutzerfunktionen | PSTN Outlook Voice Access   | Teilnehmerzugriff  | N | v    |
| VM | Benutzerfunktionen | Einwahl mit einem authentifizierten Endpunkt | Anrufen des Voicemail-Diensts zum Abhören von Sprachnachrichten und Ändern von Voicemail-Einstellungen| v | v    |
| VM | Benutzerfunktionen | Benutzereinstellung zum Deaktivieren von Voicemail   |  | v | v    |
| VM | Benutzerfunktionen | Benutzereinstellung zum Ändern der persönlichen Begrüßung  |  | v | v    |
| VM | Benutzerfunktionen | Benutzereinstellung zum Erstellen einer Abwesenheits Begrüßung  |  | v | v    |
| VM | Benutzerfunktionen | Benutzereinstellung zum Ändern der Standardsprache  |  | v | v    |
| VM | Benutzerfunktionen | Benutzereinstellung zum Überschreiben der Standardbegrüßung mit TTS  |  | v | N    |
| VM | Benutzerfunktionen | Aufzeichnen persönlicher Begrüßungen (authentifiziertes Gerät) |  | v | v    |
| VM | Benutzerfunktionen | Aufzeichnen persönlicher Begrüßungen (PSTN) – Wiedergabe über Telefon |  | N | v    |
| VM | Benutzerfunktionen | Benutzereinstellung zum Deaktivieren der Transkription |  | N | v    |
| VM | Benutzerfunktionen | Transkription  |  | v | v    |
| VM | Benutzerfunktionen | MWI (Message Waiting Indicator) mit SIP NOTIFY-Nachrichten |  | N | v    |
| VM | Benutzerfunktionen | MP3-Audiodatei Format in Outlook    |  | v | v    |
| VM | Benutzerfunktionen | Wiedergabesteuerung mit variabler Geschwindigkeit |  | v | v    |
| VM | Benutzerfunktionen | Weiterleiten einer Voicemail  | Weiterleiten einer empfangenen Voicemail an andere Benutzer | v | v    |
| VM | Benutzerfunktionen | Senden einer Sprachnachricht an eine Gruppe von Benutzern  |Voicemail-Übertragung   | N | v   |
| VM | Benutzerfunktionen | Voicemail-Benachrichtigung mit SMS    | Benutzer können eine SMS empfangen, wenn Sie über eine neue Voicemail verfügen    | N | v    |
| VM | Benutzerfunktionen | Unterstützte Gruß Sprachen | Details finden Sie hier: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| VM | Benutzerfunktionen | Mailboxansageregeln |  | v | v    |
| VM | Benutzerfunktionen | Wiedergabe über Telefon (PSTN) – zur Wiedergabe von Nachrichten | Rufen Sie mich in meiner Zelle an, um die Sprachnachricht zu hören  | N | v    |
| VM | Benutzerfunktionen | Wiedergabe über Telefon (Authentifizierung) – zur Wiedergabe von Nachrichten | Auf meinem authentifizierten Gerät anrufen  | v | v    |
| VM | Benutzerfunktionen | Freigegebenes Postfach zwischen mehreren Benutzern |  | v | v    |
| VM | Anrufer-Features  | Anrufer-Erfahrung – geschützte Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als geschützt zu markieren.| N | v    |
| VM | Anrufer-Features  | Anrufer-Erfahrung – private Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als privat zu kennzeichnen.  | N | v    |
| VM | Anrufer-Features  | Silence-Erkennung   |  | N | v    |
| VM | Mandantenadministrator Features | Geschützte Voicemail auf Server Ebene    | Mandantenadministrator kann eine Regel auf Dienstebene konfigurieren, um eingehende Voicemail als geschützt zu kennzeichnen. | v | v    |
| VM | Mandantenadministrator Features | Zeitbegrenzung für die Protokollierungs Dauer ändern  |     | v | v    |
| VM | Mandantenadministrator Features | Timeout für Silence-Erkennung ändern    |  | Nicht zutreffend    | v    |
| VM | Mandantenadministrator Features | Ändern der Anzahl von Eingabefehlern | Kooperations Code: hart codiert bis 3 | N | v    |
| VM | Mandantenadministrator Features | Ändern der Standardsprache |  | v | v    |
| VM | Mandantenadministrator Features | Transkription deaktivieren/aktivieren |  | v | v    |
| VM | Mandantenadministrator Features | Benachrichtigung über verpasste Anrufe deaktivieren/aktivieren |  | N | v    |
| VM | Mandantenadministrator Features | Hilfe zur Verbesserung der Voicemailvorschau für Microsoft-Sprachnachrichten    |  | v | v    |
| VM | Mandantenadministrator Features | Anpassen der Textnachricht für aktivierte Benutzer|  | Nicht zutreffend    | v    |
| VM | Mandantenadministrator Features | Maskierung von Transkriptions Obszönitäten|  | v | N    |
| VM | Mandantenadministrator Features | Voicemail-Richtlinie    |   | v | v    |
| VM | Mandantenadministrator Features | Webportal Verwaltung   |  | CY19   | v    |
| VM | Mandantenadministrator Features | PowerShell   |  | v | v    |
| UM | Benutzerfunktionen | Message Waiting Indicator (MWI) auf Skype for Business zertifizierten Telefonen   |Kann vom telefonpartner bereitgestellt werden  | Nein | Ja    |
| AA | Dienstfunktionen | AA-Support-Drittanbieter-Nebenstellenanlage    |  | N | v    |
| AA | Dienstfunktionen | Support Skype for Business Server   |  | v | v    |
| AA | Dienstfunktionen | Unterstützung von Microsoft Teams|  | v | N    |
| AA | Dienstfunktionen | Wählen nach Name, DTMF-Eingabe    |  | v | v    |
| AA | Dienstfunktionen | Wahl nach Name, Spracheingabe  |  | v | v    |
| AA | Dienstfunktionen | Mehrsprachige Unterstützung | Sprach Details finden Sie hier: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| AA | Dienstfunktionen | Transfer an Operator, CQ oder einen Benutzer |  | v | v    |
| AA | Dienstfunktionen | Interne Übertragung an die PSTN-Nummer (did können)  |  | v | v    |
| AA | Dienstfunktionen | Externe Übermittlung an PSTN-Nummer  |  | Siehe Abschnitt bekannte Probleme unten | v    |
| AA | Dienstfunktionen | Geschäftszeiten |  | v | v    |
| AA | Dienstfunktionen | Menü Optionen | Optionen für das IVR-Menü  | v | v    |
| AA | Dienstfunktionen | Zuweisen einer Cloud-PSTN-Nummer zu AA |  | v | N    |
| AA | Dienstfunktionen | Zuweisen einer PSTN-Nummer auf dem Prem zu AA  |  | v | v    |
| AA | Dienstfunktionen | Benutzerdefinierte Benutzerauswahl  | Aktivieren von benutzerdefinierten Listen von Organisations Benutzern durch Anrufer| v | v    |
| AA | Dienstfunktionen | After-Hours-und Holidays-Behandlung  |  | v | v    |
| AA | Dienstfunktionen | Benutzerdefinierte Begrüßung mit Text in Sprache  |  | v | v    |
| AA | Dienstfunktionen | Durchwahl wählen   | Erreichen eines Benutzers durch Wählen der Durchwahlnummer  | v   | v    |
| AA | Dienstfunktionen | Postfach für AA-Anrufer, um eine Nachricht zu hinterlassen    |  | v   | v    |
| AA | Dienstfunktionen | Mehrere PSTN-Nummern Zuweisungen an AA|  | v | v    |
| AA | Mandantenadministrator Features | Webportal Verwaltung   |  | v | N    |
| AA | Mandantenadministrator Features | PowerShell-Cmdlets  |  | v | v    |
| Fax| Dienstfunktionen | Fax-Integration|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Empfohlener Testplan und Überprüfung nach der Migration für Administratoren

Um zu überprüfen, ob Ihre Benutzer zu Cloud-Voicemail migriert wurden, lassen Sie eine Voicemail an einen Benutzer und überprüfen Sie den Nachrichtentext in Outlook. Cloud-Voicemail-Nachrichten haben eine Fußzeile, die lautet:

"Vielen Dank für die Verwendung der Transkription! Wenn ein Transkript oben nicht angezeigt wird, liegt es daran, dass die Audioqualität nicht eindeutig genug ist, um Sie zu transkribieren. "

Stellen Sie beim Testen der Voicemailfunktionen nach dem Migrieren der Benutzer sicher, dass Sie die folgenden Szenarien berücksichtigen:

- Überprüfen Sie den Voicemail-Zugriff auf alle Endpunkttypen in Ihrer Organisation, wie apps und IP-Telefone.
- Überprüfen Sie mit Beispiel Benutzern, dass die konfigurierten personalisierten Begrüßungen für Anrufer abgespielt werden.
- Wenn Ihre Organisation über eine rechtliche oder Compliance-Anforderung verfügt, um die Transkription für Benutzer zu deaktivieren, stellen Sie sicher, dass Sie nach der Migration deaktiviert ist. Weitere Informationen finden Sie unter [Einrichten von Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Wenn Sie zuvor Exchange VM-Richtlinien und-Regeln konfiguriert haben, stellen Sie sicher, dass Sie wirksam sind.
- Machen Sie sich mit dem Cloud Voicemail Service PowerShell-Cmdlets vertraut, um Benutzereinstellungen zu ändern.  

### <a name="user-experience-impact"></a>Auswirkungen auf die Benutzeroberfläche

Im folgenden finden Sie eine Übersicht über die benutzerfreundliche Voicemail-Migrationserfahrung.


|Umgebung  |Änderung der Benutzeroberfläche|
|---------|---------|
|E-Mail-Benachrichtigung | Keine Änderung<br>Es werden keine e-Mails an Benutzer gesendet, die Sie über die Aktivierung/Migration von Voicemail-Konten informieren. |
|Zugriff auf vorherige Nachrichten | Keine Änderung<br>Benutzer haben Zugriff auf Ihre vorherigen Voicemail-Nachrichten in allen unterstützten Endpunkten. |
|Empfangende VM in Outlook, SFB-apps| Keine Änderung<br>Benutzer erhalten weiterhin ihre Voicemail-Nachrichten in allen unterstützten Endpunkten. |
|Transkription | Verbesserte<br>Die Transkription von miteinander hat eine viel höhere Genauigkeitsrate und unterstützte Sprachen als "dichumo". |
|Benutzereinstellung | Neue Benutzeroberfläche<br>Benutzer können Ihre Einstellungen in einem Benutzer Einstellungs Portal (USP) ändern. Benutzer können über einen Hyperlink in Ihrer Voicemail-e-Mail oder über die Schaltfläche Benutzereinstellungen auf Ihrem SFB-Client auf Ihre USP zugreifen. https://aka.ms/vmsettings.
 |Features| Details finden Sie im Feature-Sets-Vergleich. |
|Outlook-Regeln für VM-Nachrichten | Keine Änderung<br>Zuvor erstellte Regeln gelten für Nachrichten nach der Migration.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Benutzerverwaltung und-Vorhaltung in einem Kooperationssystem

Neue Skype for Business Benutzer werden bei der Erstellung automatisch für die Cloud-Voicemail-Abteilung eingerichtet. Keine zusätzliche Administrator Arbeit oder Lizenz ist erforderlich, um neue Voicemail-Benutzer zur Verfügung zustellen. Weitere Informationen zur Richtlinienverwaltung für vorhandene und neue Benutzer finden Sie unter [Einrichten von Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail) .

### <a name="admin-auto-attendant-management-experience"></a>Verwaltungserfahrung bei der automatischen Telefonzentrale für Administratoren

Weitere Informationen zu automatischen Telefonzentralen finden Sie unter [Einrichten einer automatischen Cloud-Telefonzentrale](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Bekannte Probleme

#### <a name="greeting-inconsistencies"></a>Begrüßung Inkonsistenzen

Der Teilnehmerzugriff funktioniert möglicherweise weiterhin für den Mandanten, bis der Dienst vollständig zurückgezogen wird, selbst nachdem alle Benutzer zu Cloud Voicemail migriert wurden. Um Verwirrung und eine inkonsistente Benutzererfahrung zu vermeiden, deaktivieren Sie den Teilnehmerzugriff, da sich die Begrüßungen nach der Migration ändern. Entfernen Sie dazu den Exum-Kontakt für jede Teilnehmerzugriffs Verbindung mithilfe von `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Anrufweiterleitung für automatische Telefonzentrale an PSTN

Um einen Anruf einer automatischen Telefonzentrale über Skype for Business Server oder einen Reaktionsgruppendienst (RGS) auf Skype for Business Server an eine externe PSTN-Telefonnummer zu übertragen, erstellen Sie einen neuen lokalen Benutzer mit der Anrufweiterleitung, der auf die PSTN-Telefonnummer oder die RGS-Telefonnummer festgelegt ist. Der Benutzer muss für Enterprise-VoIP aktiviert und ordnungsgemäß konfiguriert sein und eine VoIP-Richtlinie zugewiesen haben.

#### <a name="shared-mailbox-is-still-accessible"></a>Freigegebenes Postfach ist weiterhin verfügbar

Ein freigegebenes Postfach, das mit Exchange um Online konfiguriert ist, empfängt weiterhin Nachrichten nach der Migration zu einem Benutzer Übersichts-und steht Benutzern über Outlook zur Verfügung. Allerdings ist der Zugriff zum Ändern der Grußnachrichten dieser Postfächer nicht mehr verfügbar, wenn Sie in das intergreifend migriert wurden. Kunden mit freigegebenen Postfächern, die zur Erfassung von Anrufern für die automatische Telefonzentrale verwendet werden, sollten die freigegebenen Postfachfunktionen für automatische Telefonzentralen und Anrufwarteschlangen nach der Veröffentlichung nutzen (ETA Oktober 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"Benutzername verwendet keine Skype for Business"-Banner Anzeigen

Der Dienst "Service" basiert auf der Microsoft Teams-Infrastruktur, und Anrufe von einem Skype for Business-Client können dazu führen, dass ein Informationsbanner auf dem Client angezeigt wird, der lautet: "username verwendet nicht Skype for Business. Um eine umfassendere Erfahrung zu erzielen, wechseln Sie zu Microsoft Teams, oder starten Sie eine Skype-Besprechung. "
Stellen Sie sicher, dass Sie den Skype for Business-Client Ihres Benutzers auf das neueste C2R-Client Update aktualisieren, um zu verhindern, dass dieses Banner angezeigt wird.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Einrichten von Voicemail" führt Sie zu OWA

Wenn **Sie auf Voicemail** vom Client einrichten klicken, werden Skype for Business Server 2015/2013-Kunden nach der Migration zu einem Microsoft Office-Portal (OWA) auf die Office-Webzugriffs-Portalseite weitergegeben. Alle Einstellungen wurden aus der Registerkarte Voicemail in OWA entfernt, und ein Banner wird mit einem Redirect-Link angezeigt, um Benutzer zum Benutzer Einstellungs Portal von Benutzern zu übernehmen.

#### <a name="changing-greeting-remotely"></a>Remote Begrüßung ändern

Der PSTN-Teilnehmerzugriff wird in einem Kooperationsnetz nicht unterstützt. Für Benutzer, die Ihre Begrüßung Remote ändern müssen, wurde der Voicemail-IVR-Dienst für mobile Clients eine Menüoption "Ihre Begrüßung ändern" hinzugefügt. Benutzer können diesen Dienst aufrufen, indem Sie die "1"-Taste auf der Wähltastatur des mobilen Clients gedrückt halten.
