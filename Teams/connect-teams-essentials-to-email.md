---
title: Verbinden Microsoft Teams Essentials (AAD Identity) zu einem vorhandenen E-Mail-System mit Kalender
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft Teams Essentials (AAD Identity) mit einem vorhandenen E-Mail-System mit Kalender wie Google Workspace verbinden.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 682f7bcd4e90e96534e954cd0e22c6f5952db08b
ms.sourcegitcommit: 563567ab140d5802756170c846dade3645d0b9e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284793"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Verbinden Microsoft Teams Essentials (AAD Identity) zu einem vorhandenen E-Mail-System mit Kalender

Dieser Leitfaden enthält Konfigurationsschritte zum Verbinden von Microsoft Teams Essentials (AAD Identity) mit einem vorhandenen E-Mail-System mit Kalender.

Microsoft Teams Essentials (AAD Identity) vereint das Beste aus Teams mit Besprechungen, Chats, Anrufen und Zusammenarbeit. Teams Essentials (AAD Identity) kann eine Verbindung mit Ihrem vorhandenen E-Mail-System herstellen, um eine integrierte Erfahrung zu bieten, z. B. alle Teams-Benachrichtigungen in einem vorhandenen E-Mail-Posteingang, alle Kalenderereignisse in Teams und die Möglichkeit, sich mit Ihrer vorhandenen E-Mail-Adresse bei Teams anmelden zu können.

Sobald die Verbindung besteht, können Sie Antworten auf geplante Besprechungen und Einladungen zur Zusammenarbeit in Ihrem Postfach und in Microsoft Teams. Sie können auch eingehende Besprechungen aus Ihrem Kalender anzeigen und mit ihnen Teams Besprechungssoftware eines Drittanbieters wie Google Workspace verwenden.

## <a name="prerequisites"></a>Voraussetzungen

Die Konfigurationsschritte in diesem Artikel beinhalten den Vorgang der automatischen Weiterleitung von Elementen Exchange Online. Standardmäßig ist die automatische Weiterleitung durch die Antispamrichtlinie für ausgehende E-Mails deaktiviert. Diese Richtlinie muss aktiviert sein, um Teams Essentials mit einem vorhandenen Postfach- und Kalendersystem verbinden zu können.

So aktivieren Sie die automatische Weiterleitung

1. Wechseln Sie zum Microsoft 365 Defender-Portal unter<https://security.microsoft.com/>
2. Wechseln Sie im linken Navigationsmenü im Abschnitt **Richtlinien &** Richtlinien für die & Bedrohungsrichtlinien Antispam zu Richtlinien für die  >    >    >  **E-Mail-Zusammenarbeit.**
3. Wählen Sie **auf der Seite Antispamrichtlinien** in der Liste die Option Antispam-Richtlinie für ausgehende **E-Mails (Standard)** aus.
4. Wählen Sie im nun angezeigten  Flyout mit den Richtliniendetails Schutzeinstellungen bearbeiten aus, um die Regel für die automatische Auswahl zu ändern.
5. Ändern **Sie unter Weiterleitungsregeln** die Bedingung für die automatische Weiterleitung in **Ein –** Weiterleitung ist aktiviert, und speichern Sie Ihre Änderungen.

:::image type="content" source="media/essentials-antispam.png" alt-text="Abbildung des Antispam-Richtlinien-Flyouts "Microsoft Defender Portal" mit der Einstellung "Ein, Weiterleitung ist aktiviert" unter "Weiterleitungsregeln"." :::

Weitere Informationen zum Konfigurieren von Richtlinien für ausgehende Spamnachrichten finden Sie unter [Konfigurieren der Filterung für ausgehende Spamnachrichten – Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Verbinden Teams Essentials für Exchange Online mit Exchange lokal

Sie können all das genießen, was Teams Essentials (AAD) zu bieten hat, indem Sie einen hybriden Ansatz verwenden, um die Verbindung zwischen Microsoft Teams und Exchange Online mit der lokalen Exchange zu konfigurieren.

Folgen Sie den Anweisungen unter Konfigurieren des Teams-Kalenderzugriffs für lokale Exchange-Postfächer –[Microsoft Tech Community,](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009) damit der Kalenderzugriff für Ihre lokalen Postfächer funktioniert.

Informationen zum Microsoft Teams-Räume einer Hybridumgebung mit lokalem Exchange finden Sie unter Bereitstellen von Microsoft Teams-Räume mit Exchange [lokal – Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Verbinden Teams Essentials für E-Mail-Systeme von Drittanbietern mit Kalender

Wenn Sie nicht planen, das Postfach Ihrer Organisation auf Microsoft 365 umschalten, können Sie Teams Essentials mit einem vorhandenen E-Mail- und Kalendersystem eines Drittanbieters verbinden. Über diese Verbindung können Sie Benachrichtigungen Teams in Ihrem vorhandenen E-Mail-System empfangen, während Sie vorhandene Besprechungs-Einladungen und Kalenderereignisse in Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Verbinden Teams Essentials für E-Mails von Drittanbietern mithilfe der Vanity-Domäne (Google Workspace-Beispiel)

Im folgenden Abschnitt wird gezeigt, wie Sie Microsoft Teams mit einem vorhandenen E-Mail-System mit Kalender verbinden, z. B. Google Workspace. Sie erreichen diese Verbindung, indem Sie das aktuelle E-Mail-System intakt lassen, alle E-Mails an Exchange Online weiterleiten und alles außer E-Mails des Kalendertyps filtern. Dabei werden Kalender-E-Mails automatisch im Kalender angezeigt, Teams als E-Mails vom Typ "Mit Tentative" und "Nicht-Kalender" akzeptiert werden.

Alle in einer App Microsoft 365 E-Mails werden an Google Workspace weitergeleitet, sodass Benutzer Teams Erinnerungen und Benachrichtigungen erhalten. Benutzeridentitäten, wie die primäre E-Mail-Adresse des Benutzers, können dupliziert werden. Einmaliges Anmelden ist ebenfalls möglich, aber nicht erforderlich. Benutzer sollten über den Kalender Teams eines Drittanbieters oder über ihren Kalender Teams können. Ein Teams Features funktioniert wie erwartet.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Abbildung eines Diagramms des E-Mail-Nachrichtenflusses zwischen EXO und Gmail":::

Diese Beispiele beruhen auf [dem Verbinden-ExchangeOnline-PowerShell-Commandlet,](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) das Teil des [PowerShell V2 Exchange Online Moduls ist.](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true) Wenn bei der Ausführung von Verbinden-ExchangeOnline eine Fehlermeldung angezeigt wird, stellen Sie sicher, dass Sie die empfohlenen Anweisungen zum Installieren des Moduls mit dem [EXO V2-Modul installiert haben.](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true) Wenn Connect-ExchangeOnline zur Eingabe von Anmeldeinformationen aufgefordert werden, stellen Sie sicher, dass Sie ein Mandantenadministratorkonto verwenden.

**Schritt 1: Einrichten einer neuen Mandantendomäne Microsoft 365 Mandanten**

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com> .

2. Wechseln Sie zu **Domänen**  >  **einrichten,** und wählen **Sie Domäne hinzufügen aus,** um Ihre vorhandene Domäne hinzuzufügen. Wenn Sie keine Domäne hinzufügen, verwenden die Personen in Ihrer Organisation die onmicrosoft.com-Domäne für ihre E-Mail-Adressen, bis Sie dies tun. Stellen Sie sicher, dass Sie Ihre Domäne hinzufügen, bevor Sie Benutzer hinzufügen, damit Sie sie nicht zweimal einrichten müssen.

3. Überprüfen Sie die Domäne mit einem TXT-Eintrag, indem Sie die schritte unter [Überprüfen mit einem TXT-Eintrag ausführen.](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)

4. Wenn Sie dazu aufgefordert werden, wählen **Sie Do not allow Microsoft 365 to configure DNS** aus.

5. Lassen Sie die vorhandenen MX-Einträge an Ort und Stelle, wenn Sie dazu aufgefordert werden, ohne sie zu ändern.

6. Aktualisieren Sie den vorhandenen SPF TXT-Eintrag so, dass er Microsoft 365.

7. Konfigurieren Sie DKIM (DomainKeys Identified Mail) für Microsoft 365, indem Sie die folgenden Schritte ausführen, um [DKIM manuell zu einrichten.](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)

8. Melden Sie sich wieder beim Microsoft 365 Admin Center bei <https://admin.microsoft.com/AdminPortal/> an, um DKIM zu aktivieren

9. Wählen Sie im Navigationsbereich auf der linken Seite Setup  >  **Domains aus.**

10. Wählen Sie mithilfe des Kontrollkästchens Ihre vorhandene Nicht-Microsoft-Domäne (z. B. JohannaL@contosolandscapting2.m365master.com) aus der aktuellen Liste der Domänen aus.

11. Wählen Sie die Schaltfläche mit **drei vertikalen Punkten aus,** um ein Menü zu öffnen.

12. Wählen Sie im Menü als **Standard festlegen aus.**

13. **Bestätigen Sie set as default** in dem Fenster, das angezeigt wird, um Ihre vorhandene Domäne als Standard festlegen.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Abbildung des Bestätigungsdialogfelds zum Festlegen der Domäne als Standard":::

    Wenn Sie weitere Anleitungen zum Hinzufügen einer Domäne zu Microsoft 365 möchten, führen Sie die unter Hinzufügen [einer](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Domäne zu einem Microsoft 365.

**Schritt 2: Hinzufügen von Benutzern und Zuweisen Teams Essentials-Lizenzen**

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com> , um einen einzelnen Benutzer hinzuzufügen.

2. Wechseln Sie zu **Aktive**  >  **Benutzer,** und wählen Sie **Benutzer hinzufügen aus.**

3. Geben Sie **im Bereich Grundlagen einrichten** die grundlegenden Benutzerinformationen ein, und wählen Sie dann Weiter **aus.**
    - **Name:** Geben Sie den Vor- und Nachnamen, den Anzeigenamen und den Benutzernamen ein.
    - **Domäne:** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn beispielsweise der Benutzername des Benutzers "Jakob" ist und die Domäne "contoso.com" ist, melden sie sich mit der jakob@contoso.com.
    - **Kennworteinstellungen:** Wählen Sie aus, ob Sie das automatisch generierte Kennwort verwenden oder ein eigenes, starkes Kennwort für den Benutzer erstellen möchten.  Bestimmen Sie, ob Sie das Kennwort in einer E-Mail senden möchten, wenn der Benutzer hinzugefügt wird.

4. Wählen Sie **im Bereich Produktlizenzen** zuweisen den Speicherort und die entsprechende Lizenz für den Benutzer aus. Wenn Ihnen keine Lizenzen zur Verfügung stehen, können Sie trotzdem einen Benutzer hinzufügen und weitere Lizenzen kaufen. Wählen Sie Weiter aus.

5. Erweitern Sie **im Bereich** Optionale Einstellungen die Option **Rollen,** wenn Sie diesen Benutzer zum Administrator machen möchten. Erweitern **Sie Profilinformationen,** um weitere Informationen zum Benutzer hinzuzufügen.

6. Wählen **Sie Weiter** aus, überprüfen Sie die Einstellungen des neuen Benutzers, nehmen Sie bei Bedarf weitere Änderungen vor, wählen Sie dann Hinzufügen fertig stellen und dann schließen aus. 

Wenn Sie mehrere Benutzer gleichzeitig hinzufügen möchten, folgen Sie den empfohlenen Schritten unter Hinzufügen von Benutzern und Zuweisen von Lizenzen [– Microsoft 365 administratoradministrator | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**Schritt 3: Konfigurieren von Google Workspace**

***Konfigurieren sie die duale Übermittlung von E-Microsoft 365, um Anlagen zu entfernen und zu entfernen:***

1. Führen Sie die Google-Schritte zum Einrichten der dualen Übermittlung aus: <https://support.google.com/a/answer/9228551?hl=en>

2. Hinzufügen einer Route Office 365

    - Wechseln Sie zur Google Admin-Konsole unter <https://admin.google.com> )
    - Wechseln Sie zu Apps > Google Workspace > Gmail > Hosts.
    - Geben Sie einen Routennamen ein. (Beispiel: Microsoft 365)
    - Wählen Sie "Single host" aus, und geben Sie den mx-Eintrag ein, der für Domäne in Microsoft 365 ist (Beispiel: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Smarthost-Methode zum Auflösen des ATTR35-Antwortcodes beim Senden von E-Mails Exchange lokale/lokale Exchange Online:**
    - Wählen Sie "Single host" aus, und geben Sie den MX-Eintrag für die ursprüngliche Domäne des Mandanten als Smarthost ein. Die ursprüngliche Domäne hat das Format GUID.onmicrosoft.com. Eine GUID ist ein eindeutiger Wert, der für jede Organisation im Rahmen ihrer Registrierung im Dienst bereitgestellt wird. Eine GUID ist eine ganze 128-Bit-Ganzzahl (16 Byte), die überall dort verwendet werden kann, wo ein eindeutiger Bezeichner erforderlich ist.
    - Sie können die Befehlszeile verwenden: nslookup -type MX GUID.onmicrosoft.com zum Auflösen des MX-Eintrags (Beispiel: contosolandscaping2.mail.protection.outlook.com)
    - Wählen **Sie Port:25 aus.**
    - Fortfahren mit empfohlenen Optionen

3. Konfigurieren der Route für Office 365

    - Öffnen Sie die **Google Admin-Konsole** unter <https://admin.google.com>

    - Wechseln Sie zu **Apps**  >  **Google Workspace**  >  **Gmail**  >  **Routing.**

    - Wählen Sie auf **der Registerkarte "Routing"** die Option **"Konfigurieren" aus.**

    - Geben **Sie Name** für Regel ein. (Beispiel: Gmail to Office 365)

    - Damit sich **E-Mail-Nachrichten auf auswirken,** wählen Sie **sowohl "Eingehende"** als auch  **"Interner Empfang" aus.**

    - Wählen **Sie unter Für die oben genannten Nachrichtentypen** die Option Nachricht ändern **aus.**

    - Wählen **Sie unter Auch liefern an** die Option Weitere **Empfänger** hinzufügen und dann Hinzufügen aus, um die **sekundäre E-Mail-Route hinzuzufügen.**

    - Wählen **Sie unter** Empfänger den Nach-unten-Pfeil "" und dann Erweitert **aus.**

    - Wählen Sie **Route ändern aus.**

    - Wählen Sie in der Liste die zuvor erstellte sekundäre E-Mail-Route aus.

    - Wählen **Sie unter Anlagen** die Option Anlagen aus Nachricht entfernen **aus.**

    - Scrollen Sie nach unten, und wählen **Sie Speichern aus.**

***Fügen Sie Ihre Unterdomäne in Google Workspace hinzu, um E-Mails von ihrem Microsoft 365.***

  Als Nächstes erstellen Sie Weiterleitungsregeln für Microsoft 365 an Ihre Unterdomäne. Wählen Sie eine Unterdomäne aus, die in Google Workspace verwendet werden soll, um E-Microsoft 365 zu empfangen (z. B. g.contosolandscaping2.m365master.com)

1. Starten bei **der Google Admin-Konsole** (admin.google.com)

2. Wechseln Sie zu **"Kontodomänen**  >    >  **verwalten".**

3. Wählen Sie **"Domäne hinzufügen" aus.**

4. Geben Sie den ausgewählten Domänennamen ein.

5. Domäne **"Benutzeralias" auswählen**

6. Wählen Sie **"Domäne hinzufügen" & Überprüfung starten aus.**

7. Warten Sie, bis die Überprüfung abgeschlossen ist, und aktualisieren Sie die Seite.

8. Wählen Sie **Gmail aktivieren aus.**

9. Wählen Sie **Setup des MX-Eintrags überspringen** und dann WEITER **aus.**

10. Notieren Sie **sich** im Dialogfeld E-Mail an einen anderen Server routen den Server, an den E-Mails umgestellt werden sollen (z. B. aspmx.l.google.com), und wählen Sie Ich verwende einen anderen **E-Mail-Server aus.**

***Verhindern des Spamfilters Microsoft 365 von E-Mails von E-Mails***

1. Suchen Sie nach einer geeigneten Kopfzeile Microsoft 365 Mandanten, indem Sie eine E-Mail an einen Benutzer in Google Workspace senden.

2. Öffnen Sie die Nachricht, und wählen **Sie Original anzeigen aus.**

3. Wählen Sie einen E-Mail-Header aus, der E-Mails eindeutig identifiziert, die von Ihrem Mandanten Microsoft 365 werden. (Beispiel: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Wechseln Sie zur **Google Admin-Konsole** unter <https://admin.google.com>

5. Wechseln Sie zur **Google**  >  **Workspace**  >  **Gmail-Compliance für**  >  **Apps.**

6. Navigieren Sie zur **Inhaltskonformität,** und wählen Sie **Konfigurieren aus.**

7. Geben Sie der Einstellung einen Namen. Beispielsweise können Sie mit Allowlist Microsoft 365-Mail senden.

8. Auswirkungen **der Prüfung auf eingehende** Nachrichten unter E-Mail-Nachrichten

9. Wählen **Sie unter Ausdrücke hinzufügen,** die den Inhalt beschreiben, nach dem Sie in den einzelnen Nachrichten suchen möchten aus, ob EINER der folgenden Ausdrücke **mit der Nachricht übereinstimmen soll.**

10. Wählen **Sie unter Ausdrücke** die **Option Addieren** aus. Wählen **Sie unter Einstellung hinzufügen** die Option Erweiterte **Inhaltseinstellung aus.**

11. Wählen Sie **unter "Ort"** **die Option "Vollständige Kopfzeilen" aus.**

12. Wählen **Sie unter Übereinstimmungstyp** die Option **Vollständiger Text aus.**

13. Geben Sie unter Inhalt den E-Mail-Header ein, der E-Mails, die von Ihrem Microsoft 365-Mandanten gesendet wurden, eindeutig identifiziert (Beispiel: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Wählen Sie **Speichern aus.**

15. Gehen Sie **im Feld Wenn die obigen Ausdrücke** übereinstimmen wie folgt vor, > Nachricht ändern aus, und aktivieren Sie unter Spam das Kontrollkästchen Spamfilter für  **diese** Nachricht **umgehen.**

16. Wählen Sie **Speichern aus.**

**Schritt 4: Konfigurieren Microsoft 365 Einstellungen für die Integration**

*Konfigurieren des Connectors zum Routen von E-Mails Microsoft 365 Gmail:*

1. Wechseln Sie zum **Microsoft Admin Center unter**<https://admin.microsoft.com/AdminPortal>

2. Wählen **Sie im linken** Navigationsmenü Alle anzeigen aus.

3. Wählen **Sie unter Admin Center** Exchange, um das Exchange Admin Center auf einer neuen Registerkarte zu öffnen. 

4. Wählen Sie **Exchange** linken Navigationsmenü des Admin Centers E-Mail-Fluss-Connectors aus, öffnen Sie das Überlaufmenü (...), und wählen Sie  >  Verbinder hinzufügen aus.

5. Wählen **Sie im Fenster** "Neuer Verbinder" unter Verbindung von die Option **Office 365**

6. Wählen **Sie unter Verbindung** den E-Mail-Server Ihrer Organisation und dann Weiter **aus.**

7. Geben Sie einen **Namen für** den neuen Connector ein (Beispiel: In Gmail), und fahren Sie mit Weiter **fort.**

8. Wählen Sie **im Abschnitt Verwendung von Connector** die Option Nur wenn eine Transportregel eingerichtet ist, die Nachrichten an diesen Connector umleitt, und dann Weiter **aus.** 

9. Geben Sie im Abschnitt Routing den entsprechenden Smartmailhost ein (z. B. aspmx.l.google.com), wählen Sie **+** aus, und fahren Sie dann mit Weiter **fort.**

10. Übernehmen Sie **im Abschnitt Sicherheitseinschränkungen** die Standardeinstellungen, indem Sie Weiter **auswählen.**

11. Geben Sie **im** Abschnitt Überprüfungs-E-Mail eine gültige E-Mail-Adresse für das Gmail-System ein (z. B. johannal@g.contosolandscaping2.m365master.com), wählen Sie das Pluszeichen **(+)** und dann Überprüfen **aus.**

12. Warten Sie, bis die Überprüfung abgeschlossen ist und wenn die Überprüfung erfolgreich war, klicken Sie auf Weiter.

13. Überprüfen **Sie unter "Connector überprüfen",** ob die Konfiguration richtig ist, und drücken Sie "Connector erstellen".

14. Wenn die Benachrichtigung Verbinder erstellt angezeigt wird, drücken Sie **Fertig**

*Weiterleiten von E-Mails Microsoft 365 Postfächern an Gmail*

1. Verwenden Sie **Microsoft 365 Admin Center,** um die einzelnen Postfächer zu aktualisieren, oder verwenden Sie ein **PowerShell-Skript** wie das folgende:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*Konfigurieren Exchange Online einer Transportregel für "Direkt zum Kalender"*

1. Durch das Konfigurieren dieser Einstellung werden Kalender einladend automatisch akzeptiert, sodass sie im Kalender Teams angezeigt werden, ohne dass Benutzer mit der Einladung in der Kalenderansicht Outlook Web App.

2. Das folgende Skript kann zum Erstellen der Transportregeln verwendet werden:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*Deaktivieren Outlook im Web Für Postfächer*

1. Folgen Sie den Anweisungen unter Aktivieren oder [Deaktivieren Outlook im Web Postfachs in](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) Exchange Online, um Outlook im Web für Postfächer zu deaktivieren.

2. Sie können Outlook im Web mithilfe Exchange **Admin Center oder** **PowerShell deaktivieren.** Sie können das folgende PowerShell-Beispiel verwenden, um die Outlook im Web für alle Postfächer zu deaktivieren:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**Schritt 5: Konfigurieren Exchange Online für internes Relay**

Mit diesem Schritt wird sichergestellt, dass E-Mails zur endgültigen Auflösung an das Drittanbietersystem gesendet werden.

1. Wechseln Sie zum **Microsoft Admin Center unter**<https://admin.microsoft.com/AdminPortal>

2. Wählen Sie in der linken Navigationsleiste Alle **anzeigen aus.**

3. Wählen **Sie unter Admin Center** die Option **Exchange** aus, um Exchange Admin Center auf einer neuen Registerkarte zu öffnen.

4. Wählen **Exchange im Admin**  Center im linken Navigationsmenü die Option Nachrichtenfluss und dann **Akzeptierte Domänen aus.**

5. Tippen Sie auf den im Drittanbietersystem konfigurierten Domänennamen (z. B. contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Abbildung der Einstellungen Exchange Admin Center für Nachrichtenfluss.":::

6. Wählen Sie **Internes Relay** aus, und klicken Sie dann auf **Speichern.**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Abbildung, die das Speichern der Einstellung für internes Relay zeigt.":::

**Schritt 6: Erstellen einer Regel zum Löschen aller eingehenden E-Mails Exchange Online mit Ausnahme von Kalendern**

1. Sie können diese Regel im Exchange **Admin Center** oder **in PowerShell konfigurieren.** Sie können zum Erstellen der Regel das folgende **PowerShell-Beispiel** verwenden:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Verbinden Teams Essentials für E-Mails von Drittanbietern, die keine Vanity-Domäne verwenden (Gmail-Beispiel)

Sie können eine Teams-Besprechung direkt aus Google Workspace planen und an ihr teilnehmen, indem Sie ein Gmail-Konto für Endverbraucher mit Teams Essentials verbinden, in dem sie hauptsächlich auf das [G Suite Add On](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60)Teams sind. Dadurch haben Sie die Möglichkeit, Video- und Audiokonferenzen mit Bildschirmfreigabe, Besprechungschat, digitalen Whiteboards und mehr zu planen.

Sie konfigurieren Gmail so, dass E-Mails aus Exchange Online E-Mails pullt werden, um sicherzustellen, dass E-Mails, die in Microsoft 365 und E-Mails Teams in Gmail erfolgreich empfangen werden, erfolgreich empfangen werden. Sicherheitseinstellungen müssen möglicherweise deaktiviert werden, um diese Verbindung herzustellen, wodurch die Verwendung eines starken eindeutigen Kennworts unerlässlich wird. Eine benutzerdefinierte Domäne ist in diesem Szenario nicht erforderlich, kann aber in Microsoft 365 für die Verwendung in Gmail konfiguriert werden, wenn Sie eine verwenden möchten.

:::image type="content" source="media/essentials-gmail.png" alt-text="Bild zur Verbildlichung des Nachrichtenflusses zwischen Teams Essentials und Gmail":::

**Stellen Sie sicher, dass Sie ein Gmail-Konto eingerichtet haben.**

Wenn Sie bereits über ein Konto verfügen, können Sie mit dem nächsten Schritt fortfahren. Wenn nicht, besuchen Sie [Erstellen eines neuen Google-Kontos,](https://accounts.google.com/SignUp?hl=en) um ein neues Gmail-Konto zu erstellen.

**2. Einrichten Des Mandanten Microsoft 365 Mandanten**

*Konfigurieren Teams AAD Von Benutzern*

1. Folgen Sie den Anweisungen unter[Hinzufügen von Benutzern und Zuweisen von Lizenzen](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) zum Hinzufügen mehrerer Benutzer.

*Konfigurieren des Identitätsschutzes*

1. Deaktivieren Sie die Sicherheitseinstellungen, wenn diese aktiv sind.

2. Konfigurieren der mehrstufigen Authentifizierung für Benutzer

3. Wenn Sie bedingten Zugriff verwenden, achten Sie darauf, für POP-Zugriff auf Postfach eine Ausnahme zu machen.

*Hinzufügen einer Domäne zu Microsoft 365 Admin Center (optional)*

1. Wählen Sie unter "Navigation" Einstellungen > aus, und wählen Sie dann Domäne hinzufügen aus.

2. Geben Sie Ihren Domänennamen in das entsprechende Feld ein.

3. Folgen Sie den Anweisungen auf dem Bildschirm, um Ihre Domäne mit einem TXT-Eintrag zu überprüfen.

4. Zulassen, dass Microsoft DNS konfiguriert, wenn Sie dazu aufgefordert werden

5. Führen Sie die Anweisungen zum Überprüfen der Route des MX-Eintrags zu Microsoft 365

6. Konfigurieren des SPF TXT-Eintrags zum Microsoft 365

7. Führen Sie die Anweisungen zum Konfigurieren von DKIM TXT-Einträgen für Microsoft 365

8. Überprüfen, ob DKIM aktiviert ist, indem Sie sich abmelden und wieder beim Admin Center anmelden

**3. Konfigurieren von Gmail**

1. Konfigurieren von Gmail zum Exchange Online von E-Mails in sein System

2. Konfigurieren des Teams Kalender-Add-Ins

3. Aktivieren von Gmail für die Verwendung der Unternehmensdomäne (optional)
