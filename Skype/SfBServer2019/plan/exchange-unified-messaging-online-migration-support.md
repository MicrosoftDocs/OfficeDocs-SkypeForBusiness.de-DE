---
title: Migrationsunterstützung für Exchange Unified Messaging Online
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft stellt den Exchange Unified Messaging Online-Dienst (-Service) bis Februar 2020 ein. In diesem Artikel wird zusammengefasst, was betroffene Kunden wissen sollten und was Sie tun müssen, um Ihre Geschäftskontinuität zu planen.
ms.openlocfilehash: ba9df18478057e9c32b0f2cea70a10c6c7ab36e8
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494188"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Migrationsunterstützung für Exchange Unified Messaging Online

In Bezug auf die [Ankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) vom 8. Februar 2019 wird Microsoft den Exchange Unified Messaging Online-Dienst ("Service") bis Februar 2020 zurückziehen. In diesem Artikel finden Sie eine Zusammenfassung der betroffenen Kunden, die Sie kennen sollten, um Ihre Geschäftskontinuität zu planen. 
 
Der Dienst wird von Kunden für Voicemail, automatische Telefonzentrale und/oder Fax-Integrationsdienste bereitgestellt. Microsoft plant, diesen Kunden zu helfen, zu ihren Cloud-basierten Diensten zu migrieren, die Tausende von Kunden unterstützen, die bereits in Skype for Business Online und Microsoft Teams unterstützt werden. 

Voicemail ist in erster Linie eine Microsoft-gesteuerte Migration; eine Beteiligung des Administrators und/oder Investitionen für eine Teilmenge von Kunden sind möglicherweise erforderlich. Bei der automatischen Telefonzentrale handelt es sich um eine von Administratoren gesteuerte Migration. Sie müssen die vorhandenen, von der automatischen Telefonzentrale stammenden Bäume im clouddienst der Cloud für automatische Telefonzentralen neu erstellen. Kunden, die mit einer Drittanbieter-Telefonanlage eine der Funktionen von "fremd" nutzen, werden nicht zu Skype Cloud Services migriert, da Sie keine PBX-Anlagen von Drittanbietern unterstützen. In [diesem Blog](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
)wurde letztes Jahr ein Pensionsplan für Drittanbieter angekündigt, und Kunden in diesem Bereitstellungsmodell können Ihre Benutzer zu einer der Unified Communications-Plattformen/-Dienste von Microsoft migrieren oder eine Voicemail von Drittanbietern erwerben und/oder Lösung für automatische Telefonzentrale für diese Benutzer. Die Integration von Faxen wird in den cloudbasierten Diensten nicht unterstützt. die Kunden müssen zu einer Drittanbieterlösung migrieren. 

### <a name="who-is-affected"></a>Wer ist betroffen?

Kunden, die eine der folgenden Features aus dem Exchange Unified Messaging-Online Dienst verwenden, sind davon betroffen:

- Voicemail-Dienst
- Dienst für automatische Telefonzentrale
- Fax-Integration

> [!Note]
> Kunden, die einen der lokalen Exchange-Server mit Unified Messaging verwenden, sind davon nicht betroffen. 

Erfahren Sie mehr über die Auswirkungen der Benutzer und Administratoren auf die [Benutzererfahrung](#user-experience-impact).

## <a name="migration-plan-overview"></a>Übersicht über den Migrationsplan

Microsoft hat verschiedene Kundenbereitstellungen identifiziert, die Features von "erziehen" verwenden, und hilft Kunden beim Migrieren basierend auf dem folgenden Plan. 


|Kundengruppe |Zeitachse  |Details  |
|---------|---------|---------|
|Kunden, die bereit sind, zu migrieren<br><br>Zu migrierende Features:<br><ul><li>Voicemail</ul>   |   März – Mai 2019  |Beispiele<ul><li>    Kunden mit einfacher Voicemail-Bereitstellung und-Nutzung<li>Kunden, die alle Voraussetzungen für Microsoft zum Ausführen der Migration festgelegt haben<ul>|
|Kunden mit Voraussetzungen<br><br>Zu migrierende Features:<br><ul><li>Voicemail<li>Automatische Telefonzentrale</ul> |  Mai – Dezember 2019 |Beispiele <br><ul><li>Die Hybrid Konfiguration wurde nicht erstellt/abgeschlossen<li>Hybrid-PSTN-Nummern sind nicht eingerichtet</ul>|
|Kunden, die eine Einbindung des Administrators benötigen & Kundeninvestition<br><br>Zu migrierende Features:<ul><li>Voicemail<li>Automatische Telefonzentrale<li>Fax-Integration</ul>| Bis Februar 2020  | Beispiele <br><ul><li>Der Service wird von der Telefonanlage von Drittanbietern genutzt<li>Kunden mit PSTN-Teilnehmerzugriffs Anforderungen<li>Kunden im SFB 2010 (nicht unterstützt)<li>Fax-Integration</ul> |

## <a name="migration-steps"></a>Migrationsschritte

1.  **Informieren Sie sich**
 
    Machen Sie sich mit der [Blog Ankündigung](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) und diesem Artikel vertraut, um eine reibungslose Migration für Ihre Benutzer zu planen. Weitere Informationen zu den Cloud-Voicemail-Funktionen finden Sie unter [Skype for Business-Voicemail und Optionen](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) .  
 
2.  **Einrichten einer Skype for Business-Hybrid Topologie**

    Wenn Sie keine Skype for Business-Hybrid Topologie eingerichtet haben, müssen Sie dies tun, um eine reibungslose Migration Ihrer Voicemail-Benutzer zu ermöglichen. Weitere Informationen finden Sie unter [Konfigurieren von Skype for Business-Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > Sie müssen Ihre Benutzer nicht für die Migration des Voicemail-Diensts in Online migrieren. Damit lokale Benutzer jedoch den cloudbasierten Voicemaildienst nutzen können, muss eine Hybrid Topologie eingerichtet werden.

3. **Planen der Migration einer automatischen Telefonzentrale**
    
    Administratoren können jederzeit mit der Migration Ihrer automatischen Telefonzentralen in die automatische Cloud-Telefonzentrale beginnen. Weitere Informationen finden Sie unter [Einrichten einer automatischen Cloud-Telefonzentrale](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) . Microsoft plant die Bereitstellung zusätzlicher Funktionen für die automatische Telefonzentrale, die Kunden für Ihre Migration im März 2019 als kritisch erweisen. Administratoren sollten die Funktionsgruppe auswerten und Ihre Instanzen der automatischen Telefonzentrale entsprechend migrieren. Informationen zum Vergleich von Funktionslisten finden Sie in der Feature-Matrix für das Feature "auswerten [und Azure Cloud-based Services](#exchumo-and-azure-cloud-based-services-feature-matrix)".

4. **Planen der Überprüfung und Prüfung Ihrer Voicemail nach der Migration**

    Voicemail-Migration ist Microsoft-gesteuert; Administratoren müssen nichts Unternehmen, da die Voraussetzungen für die Hybrid Topologie festgelegt sind. Microsoft führt die erforderlichen Überprüfungen und Tests durch, um sicherzustellen, dass die Voicemail-Migration der Benutzer nicht gestört wird. Administratoren werden jedoch ermutigt, Tests und Validierungen auf Ihrer Seite durchzuführen.  Einen empfohlenen Testplan finden Sie unter [vorgeschlagene Testplanung und Überprüfung nach der Migration für Administratoren](#suggested-test-plan-and-post-migration-validation-for-admins) . 

    > [!Note]
    > Der Lync Server 2010 wird nicht unterstützt. Wenn Sie in einer 2010-Server Bereitstellung arbeiten, sollten Sie ein Server Upgrade planen oder Ihre Benutzer zu Microsoft Teams oder Skype for Business Online migrieren.  

5. **Überwachen des Administrator Benachrichtigungs Centers**

    Achten Sie auf eine Benachrichtigung im Administrator-Benachrichtigungs Center mit weiteren Details und einer Zeitachse zur Voicemail-Migration Ihrer Benutzer. Benachrichtigungen werden mindestens 30 Tage vor dem Migrationszeitraum gesendet. 

    > [!Note]
    > Wenn Sie eine Benachrichtigung mit der Migrations Zeitachse Ihrer Benutzer erhalten haben und Ihre Migration aus geschäftlichen Gründen verschieben möchten, können Sie dies tun, indem Sie sich an den Microsoft-Support wenden. Beachten Sie, dass Sie Ihre Migration nicht über das pensionierungs Datum hinaus verschieben können, 2020. Februar. Für Kunden, die möglicherweise weitere Fragen haben, wenden Sie sich bitte an Ihr Konto Team oder den Microsoft-Support. Kunden, die bereits Office 365 verwenden, können einen Supportfall über das Office 365-Administratorportal einreichen. 

6. **Entscheiden Sie sich für eine geplante Migration**

    Sie können sich für eine geplante Voicemail-Service-Migration in das Kooperationsangebot entscheiden. Bevor Sie sich entscheiden, lesen Sie die Details zu diesem Artikel, insbesondere die folgenden Abschnitte:

    - Migrationsschritte (dieser Abschnitt)
    - Feature-Matrix für die Dienstleistungen und Azure Cloud-based Services
    - Auswirkungen auf die Benutzeroberfläche

    Beachten Sie, dass Sie bei der Entscheidung für eine verwaltete Migration keine 30-Tage-Benachrichtigung im Microsoft 365 Admin Portal-Nachrichtencenter erhalten.
 
    Wenn Sie eine geplante Migration aktivieren möchten, senden Sie eine e-Mail-Anforderung an [cvm@Microsoft.com](mailto:cvm@microsoft.com)unter Verwendung der e-Mail-Adresse Ihres Administrators mit den folgenden Informationen:

    - Bevorzugtes Datum (dienstags): Migrationswellen werden jeden Dienstag ausgeführt. Bitte wählen Sie ein Datum an einem Dienstag aus, das nicht über 12/3/2019 hinausgeht.
 
    - Mandanten-ID: 32-Zeichenzahl in diesem Format 0046728c-688a-4472-a38f-098fec60ac6x. Sie können Ihre Mandanten-ID im Microsoft 365-Administratorportal unter Azure Active Directory oder durch Ausführen des folgenden PowerShell-Cmdlets finden:`Get-CsTenant | Select ObjectId`
 
    Sie erhalten eine e-Mail-Bestätigung, sobald Ihr Mandant erfolgreich migriert wurde. 

## <a name="appendix"></a>Anhang

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Feature-Matrix für die Dienstleistungen und Azure Cloud-based Services

| Dienst | Funktionsebene | Feature | Hinweise  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Dienst Features| Unterstützung von Drittanbieter-Telefonanlagen    | Einschließlich aller Funktionen, die von einer Drittanbieter-Telefonanlage bereitgestellt werden, wie MWI (Nachrichten Warteanzeige) mithilfe von SIP-Benachrichtigungen von Exchange um Online | N   | J    |
| VM | Dienst Features  | Support für Skype for Business Server   |  | Y | Y    |
| VM | Dienst Features | Microsoft Teams unterstützen|  | J | N    |
| VM | Dienst Features | eDiscovery und Haltebereich  | Für Sicherheit und Compliance  | Y | Y    |
| VM | Dienst Features | Unterstützung für Exchange-Regeln | Für Sicherheit und Compliance  | Y | Y    |
| VM | Benutzer Features | PSTN-Einwahlzugriff  | Teilnehmerzugriff  | N | J    |
| VM | Benutzer Features | PSTN Outlook Voice Access   | Teilnehmerzugriff  | N | J    |
| VM | Benutzer Features | Einwahl mit einem authentifizierten Endpunkt | Anrufen des Voicemail-Diensts zum Abhören von Sprachnachrichten und Ändern der Voicemail-Einstellungen| Y | Y    |
| VM | Benutzer Features | Benutzereinstellung zum Deaktivieren von Voicemail   |  | Y | Y    |
| VM | Benutzer Features | Benutzereinstellung zum Ändern der persönlichen Ansage  |  | Y | Y    |
| VM | Benutzer Features | Benutzereinstellung zum Erstellen einer Abwesenheitsansage  |  | Y | Y    |
| VM | Benutzer Features | Benutzereinstellung zum Ändern der Standardsprache  |  | Y | Y    |
| VM | Benutzer Features | Benutzereinstellung zum Überschreiben der Standardansage mit TTS  |  | J | N    |
| VM | Benutzer Features | Aufzeichnen persönlicher Begrüßungen (authentifiziertes Gerät) |  | Y | Y    |
| VM | Benutzer Features | Aufzeichnen persönlicher Begrüßungen (PSTN) – Wiedergabe über das Telefon |  | N | J    |
| VM | Benutzer Features | Benutzereinstellung zum Deaktivieren der Transkription |  | N | J    |
| VM | Benutzer Features | Transkription  |  | Y | Y    |
| VM | Benutzer Features | Visuelle Voicemail auf allen Endpunkten   | Mit Benutzersteuerelement zum wiedergeben, löschen, Nachrichten-Warteanzeige und Status-umschalten auf allen unterstützten Endpunkten  | Y | Y    |
| VM | Benutzer Features | MP3-Audio-Dateiformat in Outlook    |  | J | Y    |
| VM | Benutzer Features | Wiedergabesteuerung mit variabler Geschwindigkeit |  | J | Y    |
| VM | Benutzer Features | Weiterleiten einer Sprachnachricht  | Weiterleiten einer empfangenen Sprachnachricht an andere Benutzer | J | Y    |
| VM | Benutzer Features | Senden einer Sprachnachricht an eine Gruppe von Benutzern  |Voicemail-Übertragung   | N | J   |
| VM | Benutzer Features | Voicemail-Benachrichtigung über SMS    | Benutzer können eine SMS empfangen, wenn Sie eine neue Voicemail haben    | N | J    |
| VM | Benutzer Features | Unterstützte Gruß Sprachen | Weitere Informationen finden Sie hier:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | J | Y    |
| VM | Benutzer Features | Regeln für die Anrufannahme |  | J | Y    |
| VM | Benutzer Features | Wiedergabe über Telefon (PSTN) – zur Wiedergabe von Nachrichten | Anrufen in meiner Zelle, um die Sprachnachricht abzuhören  | N | J    |
| VM | Benutzer Features | Wiedergabe über Telefon (auth) – zur Wiedergabe von Nachrichten | Auf meinem authentifizierten Gerät anrufen  | J | Y    |
| VM | Benutzer Features | Freigegebenes Postfach zwischen mehreren Benutzern |  | J | Y    |
| VM | Funktionen für Anrufer  | Durch die Rufnummernanzeige geschützte Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als geschützt zu kennzeichnen.| N | J    |
| VM | Funktionen für Anrufer  | Anruferlebnis – private Voicemail | Der Anrufer kann eine Option auswählen, um eine aufgezeichnete Nachricht als "Privat" zu kennzeichnen.  | N | J    |
| VM | Funktionen für Anrufer  | Silence-Erkennung   |  | N | J    |
| VM | Mandanten-Administratorfunktionen | Geschützte Voicemail auf Server Ebene    | Mandanten-Administrator kann eine Regel auf Dienstebene konfigurieren, um eingehende Voicemail als geschützt zu kennzeichnen. | J | Y    |
| VM | Mandanten-Administratorfunktionen | Zeit Limit für das Ändern der Aufnahmedauer  | Für 5 Minuten fest programmiert    | N | J    |
| VM | Mandanten-Administratorfunktionen | Timeout für Silence-Erkennung ändern    |  | Nicht zutreffend    | Y    |
| VM | Mandanten-Administratorfunktionen | Ändern der Anzahl von Eingabefehlern | Prothesen: schwer codiert bis 3 | N | J    |
| VM | Mandanten-Administratorfunktionen | Ändern der Standardsprache |  | J | Y    |
| VM | Mandanten-Administratorfunktionen | Deaktivieren/Aktivieren der Transkription |  | Y | Y    |
| VM | Mandanten-Administratorfunktionen | Benachrichtigung über verpasste Anrufe deaktivieren/aktivieren |  | N | J    |
| VM | Mandanten-Administratorfunktionen | Hilfe für Microsoft beim Verbessern der Voicemailvorschau    |  | Y | Y    |
| VM | Mandanten-Administratorfunktionen | Anpassen der Textnachricht für aktivierte Benutzer|  | Nicht zutreffend    | Y    |
| VM | Mandanten-Administratorfunktionen | Maskierung für Transkriptions Obszönitäten|  | J | N    |
| VM | Mandanten-Administratorfunktionen | Voicemail-Richtlinie    |   | Y | Y    |
| VM | Mandanten-Administratorfunktionen | Web Portal-Verwaltung   |  | CY19   | Y    |
| VM | Mandanten-Administratorfunktionen | PowerShell   |  | Y | Y    |
| AA | Dienst Features | AA-Unterstützung von Drittanbieter-Telefonanlagen    |  | N | J    |
| AA | Dienst Features | Support für Skype for Business Server   |  | Y | Y    |
| AA | Dienst Features | Microsoft Teams unterstützen|  | J | N    |
| AA | Dienst Features | Wählen nach Name, DTMF-Eingabe    |  | Y | Y    |
| AA | Dienst Features | Wählen nach Name, Spracheingabe  |  | Y | Y    |
| AA | Dienst Features | Unterstützung für mehrere Sprachen | Einzelheiten zur Sprache finden Sie hier:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | Dienst Features | An Operator, CQ oder einen Benutzer übertragen |  | Y | Y    |
| AA | Dienst Features | Interne Übertragung an eine PSTN-Nummer (did RNL)  |  | Y | Y    |
| AA | Dienst Features | Externe Übertragung an PSTN-Nummer  |  | Q2CY19 | Y    |
| AA | Dienst Features | Geschäftszeiten |  | Y | Y    |
| AA | Dienst Features | Menü Optionen | IVR-Menü Optionen  | Y | Y    |
| AA | Dienst Features | Zuweisen einer Cloud-PSTN-Nummer zu AA |  | J | N    |
| AA | Dienst Features | Zuweisen einer lokalen PSTN-Nummer zu AA  |  | Y | Y    |
| AA | Dienst Features | Benutzerdefinierte Benutzerauswahl  | Aktivieren von Anrufern zum Erreichen einer angepassten Liste von Organisations Benutzern| Y | Y    |
| AA | Dienst Features | After-Hours-und Feiertags Behandlung  |  | Y | Y    |
| AA | Dienst Features | Benutzerdefinierte Begrüßung mithilfe von Text zu Sprache  |  | Y | Y    |
| AA | Dienst Features | Durchwahl Wahl   | Erreichen eines Benutzers durch Wählen der Durchwahl  | CY19   | Y    |
| AA | Dienst Features | Postfach für AA-Anrufer, um eine Nachricht zu hinterlassen    |  | CY19   | Y    |
| AA | Dienst Features | Zuordnung mehrerer PSTN-Nummern zu einem AA|  | Y | Y    |
| AA | Mandanten-Administratorfunktionen | Web Portal-Verwaltung   |  | J | N    |
| AA | Mandanten-Administratorfunktionen | PowerShell-Cmdlets  |  | Y | Y    |
| Fax| Dienst Features | Fax-Integration|  | N | J    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Empfohlener Testplan und Validierung nach der Migration für Administratoren

Stellen Sie beim Testen der Voicemail-Funktionalität nach der Migration Ihrer Benutzer sicher, dass Sie die folgenden Szenarien beachten:

- Überprüfen Sie den Voicemail-Zugriff über alle Endpunkttypen in Ihrer Organisation: apps und IP-Telefone. 
- Überprüfen Sie mit Beispiel Benutzern, ob die konfigurierten personalisierten Begrüßungen für Anrufer abgespielt werden.   
- Wenn Ihre Organisation über eine rechtliche oder Compliance-Anforderung verfügt, um die Transkription für Benutzer zu deaktivieren, stellen Sie sicher, dass Sie nach der Migration deaktiviert ist. Weitere Informationen finden Sie unter [Einrichten von Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail).
- Wenn Sie zuvor Exchange VM-Richtlinien und-Regeln konfiguriert haben, stellen Sie sicher, dass Sie effektiv sind.
- Machen Sie sich mit den PowerShell-Cmdlets von Cloud Voicemail Service vertraut, um Benutzereinstellungen zu ändern.  

### <a name="user-experience-impact"></a>Auswirkungen auf die Benutzeroberfläche

Im folgenden erfahren Sie, wie Sie eine Benutzer-Voicemail-Migrationsübersicht verwenden.


|Erfahrung  |Änderung der Benutzerfreundlichkeit|
|---------|---------|
|E-Mail-Benachrichtigung | Keine Änderung<br>Es werden keine e-Mails an Benutzer gesendet, die über die Aktivierung/Migration von Voicemail-Konten benachrichtigt werden. |
|Zugriff auf frühere Nachrichten | Keine Änderung<br>Benutzer können in allen unterstützten Endpunkten auf Ihre vorherigen Sprachnachrichten zugreifen. |
|Empfangen von VM in Outlook, SFB-apps| Keine Änderung<br>Die Benutzer erhalten weiterhin ihre Voicemail-Nachrichten in allen unterstützten Endpunkten. |
|Transkription | Verbesserte<br>Die Transkription von untergeordneten Daten hat eine wesentlich höhere Genauigkeitsrate und unterstützte Sprachen als "auslesen". |
|Benutzereinstellung | Neue Erfahrung<br>Benutzer können Ihre Einstellungen über ein Nutzer Einstellungs Portal (USP) ändern. Benutzer können über einen Link in Ihrer Voicemail-e-Mail oder über die Schaltfläche Benutzereinstellungen auf dem SFB-Client auf Ihr USP zugreifen. https://aka.ms/vmsettings.   
 |Funktionen| Details finden Sie im Feature-Sets-Vergleich. |
|Outlook-Regeln für VM-Nachrichten | Keine Änderung<br>Zuvor erstellte Regeln gelten für Nachrichten nach der Migration.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Benutzerverwaltung und-Bereitstellung in einem Kooperationssystem 

Neue Benutzer von Skype for Business werden beim Erstellen automatisch für Voicemail bereitgestellt. Für die Bereitstellungneuer Benutzer für Voicemail sind keine weiteren Administrator arbeiten oder Lizenzen erforderlich. Informationen zum Verwalten der Richtlinien für vorhandene und neue Benutzer finden Sie unter [Einrichten von Cloud-Voicemail](/microsoftteams/set-up-phone-system-voicemail) .

#### <a name="admin-auto-attendant-management-experience"></a>Verwaltungserfahrung des Administrators für die automatische Telefonzentrale 

Weitere Informationen zum Konfigurieren und Verwalten von automatischen Telefonzentralen finden Sie unter [Einrichten einer automatischen Cloud-Telefonzentrale](/MicrosoftTeams/create-a-phone-system-auto-attendant.md) . 
