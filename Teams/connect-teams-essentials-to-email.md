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
description: Erfahren Sie, wie Sie Microsoft Teams Essentials (AAD Identity) mit einem vorhandenen E-Mail-System mit Kalender wie Google Workspace verbinden
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcea261be727c01382d55c4a2861541291fcb343
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823586"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Verbinden Microsoft Teams Essentials (AAD Identity) zu einem vorhandenen E-Mail-System mit Kalender

Dieses Handbuch enthält Konfigurationsschritte zum Verbinden von Microsoft Teams Essentials (AAD Identity) mit einem vorhandenen E-Mail-System mit Kalender.

Microsoft Teams Essentials (AAD Identity) vereint das Beste aus Teams mit Besprechungen, Chats, Anrufen und Zusammenarbeit. Teams Essentials (AAD Identity) kann eine Verbindung mit Ihrem vorhandenen E-Mail-System herstellen, um eine integrierte Oberfläche bereitzustellen, z. B. alle Teams Benachrichtigungen in einem vorhandenen E-Mail-Posteingang, alle Kalenderereignisse in Teams und die Möglichkeit, sich mit Ihrer vorhandenen E-Mail-Adresse bei Teams anzumelden.

Nach der Verbindung können Sie Antworten auf geplante Besprechungen und Einladungen zur Zusammenarbeit in Ihrem Postfach und Microsoft Teams sehen. Sie können auch eingehende Besprechungen aus Ihrem Kalender anzeigen und mit ihnen interagieren, indem Sie Teams und Besprechungssoftware von Drittanbietern wie Google Workspace verwenden.

## <a name="prerequisites"></a>Voraussetzungen

Die Konfigurationsschritte in diesem Artikel umfassen den Prozess der automatischen Weiterleitung von Elementen aus Exchange Online. Standardmäßig ist die automatische Weiterleitung durch die Antispam-Ausgehende Richtlinie deaktiviert. Diese Richtlinie muss aktiviert sein, um Teams Essentials mit einem vorhandenen Postfach- und Kalendersystem zu verbinden.

So aktivieren Sie die automatische Weiterleitung:

1. Wechseln Sie zum Microsoft 365 Defender Portal unter<https://security.microsoft.com/>
2. Wechseln Sie im linken Navigationsmenü im Abschnitt "Richtlinien" zu **"E-Mail & Zusammenarbeitsrichtlinien** > **& Regeln** >  "**Antispamrichtlinie** für **Bedrohungsrichtlinien** > ".
3. Wählen Sie auf der Seite **"Antispamrichtlinien** " die Option **"Ausgehende Antispamrichtlinie" (Standard)** aus der Liste aus.
4. Wählen Sie im daraufhin angezeigten Flyout "Richtliniendetails" die Option **"Schutzeinstellungen bearbeiten** " aus, um die Regel für die automatische Weitergabe zu ändern.
5. Ändern Sie unter " **Weiterleitungsregeln**" die Bedingung für die automatische Weiterleitung in **"Ein" – die Weiterleitung ist aktiviert** , und speichern Sie Ihre Änderungen.

:::image type="content" source="media/essentials-antispam.png" alt-text="Abbildung des Microsoft Defender Portal-Antispam-Flyouts für ausgehende Richtlinien mit &quot;Ein&quot;, &quot;Weiterleitung&quot; ist unter &quot;Weiterleitungsregeln&quot; aktiviert." :::

Weitere Informationen zum Konfigurieren ausgehender Spamrichtlinien finden Sie unter [Konfigurieren der ausgehenden Spamfilterung – Office 365 | Microsoft-Dokumentation](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Verbinden Teams Essentials zum Exchange Online mit Exchange lokal

Sie können alles genießen, was Teams Essentials (AAD) zu bieten hat, indem Sie einen Hybridansatz verwenden, um die Verbindung zwischen Microsoft Teams und Exchange Online mit Exchange lokal zu konfigurieren.

Damit der Kalenderzugriff für Ihre lokalen Postfächer funktioniert, befolgen Sie die Anleitungen unter[Configuring Teams calendar access for Exchange on-premises mailboxes – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Um Microsoft Teams-Räume in einer Hybridumgebung mit Exchange lokal bereitzustellen, besuchen Sie "[Bereitstellen Microsoft Teams-Räume mit Exchange lokal – Microsoft Teams | Microsoft-Dokumentation](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Verbinden Teams Essentials für E-Mail-Systeme von Drittanbietern mit Kalender

Wenn Sie nicht beabsichtigen, das Postfach Ihrer Organisation auf Microsoft 365 umzustellen, können Sie Teams Essentials mit einem vorhandenen E-Mail- und Kalendersystem von Drittanbietern verbinden. Mit dieser Verbindung können Sie Teams Benachrichtigungen in Ihrem vorhandenen E-Mail-System empfangen, während Sie vorhandene Besprechungseinladungen und Kalenderereignisse in Microsoft Teams anzeigen.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Verbinden Teams Essentials für E-Mails von Drittanbietern mithilfe der Vanity-Domäne (Beispiel für Google Workspace)

Im folgenden Abschnitt wird gezeigt, wie Sie Microsoft Teams mit einem vorhandenen E-Mail-System mit Kalender wie Google Workspace verbinden. Sie erreichen diese Verbindung, indem Sie das aktuelle E-Mail-System intakt lassen, alle E-Mails an Exchange Online weiterleiten und alles außer E-Mails des Kalendertyps filtern. Auf diese Weise werden Kalender-E-Mails automatisch im Teams Kalender angezeigt, der als E-Mails vom Typ "Mit Vorbehalt" akzeptiert wird, und E-Mails, die keine Kalender sind, werden gelöscht.

Alle in Microsoft 365 generierten E-Mails werden an Google Workspace weitergeleitet, sodass Benutzer Teams Erinnerungen und Benachrichtigungen erhalten. Benutzeridentitäten wie die primäre E-Mail des Benutzers können dupliziert werden. Single Sign-On ist ebenfalls möglich, aber nicht erforderlich. Benutzer sollten entweder aus dem Kalender eines Drittanbieters oder aus Teams Kalender an Teams Besprechungen teilnehmen können. Ein weiteres Teams-Features funktioniert wie erwartet.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Abbildung eines Diagramms des Nachrichtenflusses zwischen EXO und Gmail":::

Diese Beispiele basieren auf dem [Verbinden-ExchangeOnline PowerShell-Befehllet](/powershell/module/exchange/connect-exchangeonline), das Teil des [Exchange Online PowerShell V2-Moduls](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps) ist. Wenn beim Ausführen von Verbinden-ExchangeOnline eine Fehlermeldung angezeigt wird, stellen Sie sicher, dass Sie die empfohlenen Anweisungen zum Installieren des Moduls mithilfe [des EXO V2-Moduls](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module) befolgt haben. Wenn Connect-ExchangeOnline Anmeldeinformationen einfordert, müssen Sie unbedingt ein Mandantenadministratorkonto verwenden.

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>Schritt 1: Einrichten einer neuen Microsoft 365 Mandantendomäne

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com>.

2. Wechseln Sie zu "**Domänen** **einrichten** > ", und wählen **Sie "Domäne hinzufügen"** aus, um Ihre vorhandene Domäne hinzuzufügen. Wenn Sie keine Domäne hinzufügen, verwenden Personen in Ihrer Organisation die onmicrosoft.com Domäne für ihre E-Mail-Adressen, bis Sie dies tun. Achten Sie darauf, Ihre Domäne hinzuzufügen, bevor Sie Benutzer hinzufügen, damit Sie sie nicht zweimal einrichten müssen.

3. Überprüfen Sie die Domäne mit einem TXT-Eintrag, indem Sie die Schritte unter ["Überprüfen mit einem TXT-Eintrag"](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true) ausführen.

4. Wenn Sie dazu aufgefordert werden, wählen Sie "**Nicht zulassen, dass Microsoft 365 DNS konfigurieren"** aus.

5. Wenn Sie dazu aufgefordert werden, lassen Sie die vorhandenen MX-Einträge unverändert.

6. Aktualisieren Sie den vorhandenen SPF TXT-Eintrag so, dass er Microsoft 365 enthält.

7. Konfigurieren Sie DomainKeys Identified Mail (DKIM) für Microsoft 365, indem Sie die folgenden Schritte ausführen, um [DKIM manuell einzurichten](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true).

8. Melden Sie sich wieder bei der Microsoft 365 Admin Center an<https://admin.microsoft.com/AdminPortal/>, um DKIM zu aktivieren.

9. Wählen Sie im Navigationsbereich auf der linken Seite "**Domänen einrichten"** >  aus.

10. Aktivieren Sie mithilfe des Kontrollkästchens Ihre vorhandene Nicht-Microsoft-Domäne (z. B. TomislavK@thephone-company.com) aus den aktuellen Domänenlisten.

11. Wählen Sie die Schaltfläche mit **drei vertikalen Punkten** aus, um ein Menü zu öffnen.

12. Wählen Sie im Menü "**Als Standard festlegen" aus**.

13. **Bestätigen Sie die Festlegung als Standard** in dem Fenster, in dem ihre vorhandene Domäne als Standard festgelegt wird.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Abbildung des Bestätigungsdialogfelds zum Festlegen der Domäne als Standard":::

    Weitere Anleitungen zum Hinzufügen einer Domäne zu Microsoft 365 finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)".

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>Schritt 2: Hinzufügen von Benutzern und Zuweisen von Teams Essentials-Lizenzen

1. Wechseln Sie zum Admin Center, um <https://admin.microsoft.com> einen einzelnen Benutzer hinzuzufügen.

2. Wechseln Sie zu **"Aktive Benutzer"** >  und wählen Sie "**Benutzer hinzufügen"** aus.

3. Geben Sie im Bereich " **Grundlagen einrichten" die grundlegenden** Benutzerinformationen ein, und wählen Sie dann **"Weiter**" aus.
    - **Namen:** Geben Sie den Vor- und Nachnamen, den Anzeigenamen und den Benutzernamen ein.
    - **Domäne:** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn der Benutzername des Benutzers beispielsweise "Jakob" lautet und die Domäne contoso.com ist, melden sie sich mithilfe von jakob@contoso.com an.
    - **Kennworteinstellungen:** Wählen Sie aus, ob Sie das automatisch generierte Kennwort verwenden oder Ihr eigenes sicheres Kennwort für den Benutzer erstellen möchten.  Bestimmen Sie, ob Sie das Kennwort in einer E-Mail senden möchten, wenn der Benutzer hinzugefügt wird.

4. Wählen Sie im Bereich " **Produktlizenzen zuweisen** " den Speicherort und die entsprechende Lizenz für den Benutzer aus. Wenn Keine Lizenzen verfügbar sind, können Sie trotzdem einen Benutzer hinzufügen und weitere Lizenzen kaufen. Wählen Sie "Weiter" aus.

5. Erweitern Sie im **Bereich "Optionale Einstellungen** " **die Option "Rollen** ", wenn Sie diesen Benutzer zu einem Administrator machen möchten. Erweitern Sie **Profilinformationen** , um zusätzliche Informationen zum Benutzer hinzuzufügen.

6. Wählen Sie **"Weiter**", überprüfen Sie die Einstellungen Ihres neuen Benutzers, nehmen Sie bei Bedarf weitere Änderungen vor, wählen Sie " **Hinzufügen fertig stellen**" aus, und schließen Sie dann.

Wenn Sie mehrere Benutzer gleichzeitig hinzufügen möchten, befolgen Sie die empfohlenen Schritte unter ["Benutzer hinzufügen" und "Lizenzen zuweisen" – Microsoft 365 Administrator | Microsoft-Dokumentation](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>Schritt 3: Konfigurieren von Google Workspace

***Konfigurieren Sie die duale E-Mail-Zustellung für Microsoft 365 und Strip-Anlagen:***

1. Führen Sie die Schritte von Google zum Einrichten der dualen Übermittlung aus: <https://support.google.com/a/answer/9228551?hl=en>

2. Route für Office 365 hinzufügen

    - Go the Google Admin console at <https://admin.google.com>)
    - Wechseln Sie zu Apps > Google Workspace > Gmail > Hosts.
    - Geben Sie einen Routennamen ein. (Beispiel: Microsoft 365)
    - Wählen Sie "Einzelner Host" aus, und geben Sie den für die Domäne in Microsoft 365 angegebenen MX-Eintrag ein (z. B.: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Smarthostmethode zum Auflösen des ATTR35-Antwortcodes, wenn E-Mails an Exchange lokal/Exchange Online gesendet werden:**
    - Wählen Sie "Einzelner Host" aus, und geben Sie den MX-Eintrag für die ursprüngliche Domäne des Mandanten als Smarthost ein. Die ursprüngliche Domäne weist das Format GUID.onmicrosoft.com auf. Eine GUID ist ein eindeutiger Wert, der jeder Organisation im Rahmen ihrer Registrierung im Dienst bereitgestellt wird. Eine GUID ist eine 128-Bit-Ganzzahl (16 Bytes), die auf allen Computern und Netzwerken verwendet werden kann, wo ein eindeutiger Bezeichner erforderlich ist.
    - Sie können die Befehlszeile verwenden: nslookup -type MX GUID.onmicrosoft.com zum Auflösen des MX-Eintrags (z. B.: contosolandscaping2.mail.protection.outlook.com)
    - **Port auswählen:25**
    - Fortfahren mit empfohlenen Optionen

3. Konfigurieren der Route zu Office 365

    - Öffnen Sie die **Google Admin-Konsole** unter<https://admin.google.com>

    - Go to **Apps** > **Google Workspace** > **Gmail** > **Routing**

    - Wählen Sie auf der Registerkarte "**Routing**" die Option **"Konfigurieren"** aus.

    - Geben Sie **den Namen** für die Regel ein. (Z. B. Gmail zum Office 365)

    - Damit **sich E-Mail-Nachrichten auswirken,** wählen Sie sowohl **eingehenden** als auch **internen Empfang** aus.

    - Wählen Sie unter **"Für die oben genannten Nachrichtentypen" die** Option "**Nachricht ändern"** aus.

    - Wählen Sie unter **"Auch zugestellt an****" die Option "Weitere Empfänger hinzufügen**" und dann "**Hinzufügen" aus, um die sekundäre E-Mail-Route hinzuzufügen.**

    - Wählen Sie unter **"Empfänger**" den Abwärtspfeil "" und dann **"Erweitert**" aus.

    - Wählen Sie **"Route ändern" aus.**

    - Wählen Sie in der Liste die sekundäre E-Mail-Route aus, die Sie zuvor erstellt haben.

    - Wählen Sie unter **"Anlagen**" **die Option "Anlagen aus Nachricht entfernen" aus**.

    - Scrollen Sie nach unten, und wählen Sie **"Speichern"** aus.

***Fügen Sie Ihre Unterdomäne im Google-Arbeitsbereich hinzu, um E-Mails von Microsoft 365 zu empfangen.***

  Als Nächstes erstellen Sie Weiterleitungsregeln für Microsoft 365 Postfächer an Ihre Unterdomäne. Wählen Sie eine Unterdomäne aus, die in Google Workspace zum Empfangen von E-Mails von Microsoft 365 verwendet werden soll (z. B. g.contosolandscaping2.m365master.com)

1. Starten Sie bei **Google Admin Konsole** (bei admin.google.com)

2. Wechseln sie zu **"Domänen verwalten" in****Kontodomänen** >  > 

3. Wählen Sie **"Domäne hinzufügen" aus.**

4. Geben Sie den ausgewählten Domänennamen ein.

5. **Benutzeraliasdomäne** auswählen

6. Wählen Sie **"Domäne hinzufügen & Überprüfung starten**" aus.

7. Warten Sie, bis die Überprüfung abgeschlossen ist, und aktualisieren Sie die Seite.

8. Aktivieren **von Gmail** auswählen

9. Wählen Sie **"MX-Eintragssetup überspringen"** und dann **"WEITER**" aus.

10. Notieren Sie sich im Dialogfeld "**E-Mail an einen anderen Server** weiterleiten" den Server, an den E-Mails weitergeleitet werden sollen (z. B. aspmx.l.google.com), und wählen Sie "**Ich verwende einen anderen E-Mail-Server**" aus.

***Zulassen, dass E-Mails von Microsoft 365 den SPAM-Filter umgehen***

1. Suchen Sie einen entsprechenden Header aus dem Microsoft 365 Mandanten, indem Sie eine E-Mail an einen Benutzer im Google-Arbeitsbereich senden.

2. Öffnen Sie die Nachricht, und wählen Sie **"Original anzeigen" aus**.

3. Wählen Sie einen E-Mail-Header aus, der E-Mails, die von Ihrem Microsoft 365 Mandanten stammen, eindeutig identifiziert. (Beispiel: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Wechseln Sie zur **Google Admin-Konsole** unter<https://admin.google.com>

5. Go to **Apps** > **Google Workspace** > **Gmail** > **Compliance**

6. Navigieren Sie zu **"Inhaltscompliance**", und wählen Sie **"Konfigurieren" aus**.

7. Geben Sie der Einstellung einen Namen. Beispiel: Zulassenliste Microsoft 365 E-Mail.For example, Allowlist Microsoft 365 email.

8. Unter **E-Mail-Nachrichten, die sich auf die** Eingehende Überprüfung auswirken

9. **Wählen Sie unter "Ausdrücke hinzufügen", die den Inhalt beschreiben, nach dem Sie in jeder Nachricht suchen möchten****, aus, ob einer der folgenden Ausdrücke mit der Nachricht übereinstimmt**.

10. Wählen Sie unter **"Ausdrücke**" die Option **"Xi hinzufügen"** aus. Wählen **Sie unter "Einstellung hinzufügen" die Option** "**Erweiterte Inhaltszustimmung" aus**.

11. Wählen Sie unter **"Speicherort****" die Option "Vollständige Kopfzeilen" aus.**

12. Wählen Sie unter **"Übereinstimmungstyp****" die Option "Volltext**" aus.

13. Geben Sie unter "Inhalt" den E-Mail-Header ein, der E-Mails identifiziert, die von Ihrem Microsoft 365 Mandanten stammen (z. B. X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Wählen Sie **"Speichern" aus.**

15. **Führen Sie im Feld "Wenn die oben genannten Ausdrücke übereinstimmen" das folgende** Feld aus, > **Nachricht ändern** und den **Spamfilter für diese Nachricht** unter **"Spam**" umgehen aktivieren.

16. Wählen Sie **"Speichern" aus.**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>Schritt 4: Konfigurieren Microsoft 365 Einstellungen für die Integration

*Konfigurieren Sie den Connector zum Weiterleiten von E-Mails von Microsoft 365 an Gmail:*

1. Wechseln Sie zum **Microsoft Admin Center** unter<https://admin.microsoft.com/AdminPortal>

2. Wählen Sie im linken Navigationsmenü **"Alle anzeigen** " aus.

3. Wählen Sie **unter Admin Center** **Exchange** aus, um das Exchange Admin Center auf einer neuen Registerkarte zu öffnen.

4. Wählen Sie im linken Navigationsmenü des **Exchange Admin Centers** die Option **"E-Mail-Flussconnectors** > " aus, öffnen Sie das Überlaufmenü (...) und wählen Sie "Connector hinzufügen" aus.

5. Wählen Sie unter **"Verbindung von**" im Fenster "Neuer Verbinder" **Office 365**

6. Wählen Sie unter **"Verbindung**" den E-Mail-Server Ihrer Organisation und dann **"Weiter**" aus.

7. Geben Sie einen **Namen** für den neuen Connector ein (z. B. "An Gmail") und fahren Sie mit **"Weiter"** fort.

8. Wählen Sie im Abschnitt **"Verbinder verwenden** " **"Nur" aus, wenn eine Transportregel eingerichtet ist, die Nachrichten an diesen Connector umleitet** , und wählen Sie **"Weiter**" aus.

9. Geben Sie im Abschnitt "Routing" den entsprechenden Smartmailhost ein (z. B. aspmx.l.google.com), wählen Sie **+** aus, und fahren Sie dann mit **"Weiter**" fort.

10. Übernehmen Sie im Abschnitt **"Sicherheitseinschränkungen**" die Standardeinstellungen, indem Sie "**Weiter**" auswählen.

11. Geben Sie im **Abschnitt "Überprüfungs-E-Mail**" eine gültige E-Mail-Adresse für das Gmail-System ein (z. B. johannal@g.contosolandscaping2.m365master.com), wählen Sie das **Pluszeichen (+)** und dann "**Überprüfen**" aus.

12. Warten Sie, bis die Überprüfung abgeschlossen ist, und wenn die Überprüfung erfolgreich war, drücken Sie "Weiter".

13. Überprüfen **Sie unter "Konnektor überprüfen**", ob die Konfiguration korrekt ist, und drücken Sie "Connector erstellen".

14. Wenn die Benachrichtigung "Connector erstellt" angezeigt wird, drücken **Sie "Fertig"**.

*Weiterleiten von E-Mails von Microsoft 365 Postfächern an Gmail:*

1. Verwenden Sie das **Microsoft 365 Admin Center**, um jedes Postfach zu aktualisieren, oder Sie können ein **PowerShell-Skript** wie das folgende verwenden:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Problembehandlung bei Verbinden-ExchangeOnline:**

    Tritt beim Ausführen von Verbinden-ExchangeOnline ein Fehler auf? Dies kann das Ergebnis der regel zur automatischen E-Mail-Weiterleitung In Ihrer Organisation sein. Standardmäßig ist die automatische Weiterleitung deaktiviert. Um Teams Essentials mit Google Workspace zu verbinden, muss die Regel aktiviert sein.

    Geben Sie das folgende Skript ein:

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    Führen Sie anschließend die folgenden Befehle aus:

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*Konfigurieren sie Exchange Online direkt zur Kalendertransportregel:*

1. Wenn Sie diese Einstellung konfigurieren, werden Kalenderseinladungen automatisch akzeptiert, sodass sie in Teams Kalender angezeigt werden, ohne dass Benutzer mit der Einladung in Outlook Web App interagieren müssen.

2. Das folgende Skript kann zum Erstellen der Transportregeln verwendet werden:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*Outlook im Web für Postfächer deaktivieren:*

1. Befolgen Sie die Anweisungen unter [Aktivieren oder Deaktivieren von Outlook im Web für ein Postfach in Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app), um Outlook im Web für Postfächer zu deaktivieren.

2. Sie können Outlook im Web mithilfe von **Exchange Admin Center** oder **PowerShell** deaktivieren. Sie können das folgende PowerShell-Beispiel verwenden, um Outlook im Web für alle Postfächer zu deaktivieren:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>Schritt 5: Konfigurieren Exchange Online Domäne für internes Relay

Mit diesem Schritt wird sichergestellt, dass E-Mails zur endgültigen Lösung an das Drittanbietersystem gesendet werden.

1. Wechseln Sie zum **Microsoft Admin Center** unter<https://admin.microsoft.com/AdminPortal>

2. Wählen Sie im linken Navigationsbereich **"Alle anzeigen" aus**.

3. Wählen Sie unter **Admin Center** **Exchange** aus, um Exchange Admin Center auf einer neuen Registerkarte zu öffnen.

4. Wählen Sie **Exchange Admin Center** im linken Navigationsmenü die Option "**E-Mail-Fluss**" und dann "**Akzeptierte Domänen**" aus.

5. Tippen Sie auf den im Drittanbietersystem konfigurierten Domänennamen (z. B. contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Abbildung der Einstellungen des Exchange Admin Center für den Nachrichtenfluss.":::

6. Wählen Sie **"Internes Relay**" aus, und klicken Sie dann auf **"Speichern"**.

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Abbildung des Vorgangs des Speicherns der internen Relay-Einstellung.":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>Schritt 2: Erstellen einer Regel zum Löschen aller eingehenden E-Mails an Exchange Online mit Ausnahme von Kalendern

1. Sie können diese Regel im **Exchange Admin Center** oder **PowerShell** konfigurieren. Sie können das folgende **PowerShell-Beispiel** verwenden, um die Regel zu erstellen:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Verbinden Teams Essentials für E-Mails von Drittanbietern, die keine Vanity-Domäne verwenden (Gmail-Beispiel)

Sie können eine Teams Besprechung direkt über Google Workspace planen und daran teilnehmen, indem Sie ein Gmail-Consumerkonto mit Teams Essentials verbinden, wobei Sie sich in erster Linie auf das [Teams G Suite-Add-On](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60) verlassen. Dadurch haben Sie die Möglichkeit, Video- und Audiokonferenzen mit Bildschirmfreigabe, Besprechungschat, digitalen Whiteboards und mehr zu planen.

Sie konfigurieren Gmail so, dass E-Mails von Exchange Online abgerufen werden, um sicherzustellen, dass in Microsoft 365 generierte E-Mails erfolgreich in Gmail eintreffen und Teams. Sicherheitsstandards müssen möglicherweise deaktiviert werden, um diese Verbindung herzustellen, was die Verwendung eines starken eindeutigen Kennworts erforderlich macht. Eine benutzerdefinierte Domäne ist für dieses Szenario nicht erforderlich, kann aber in Microsoft 365 für die Verwendung in Gmail konfiguriert werden, wenn Sie eine verwenden möchten.

:::image type="content" source="media/essentials-gmail.png" alt-text="Image depiciting the mail flow between Teams Essentials and Gmail":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. Stellen Sie sicher, dass Sie ein Gmail-Konto eingerichtet haben

Wenn Sie bereits über ein vorhandenes Konto verfügen, können Sie mit dem nächsten Schritt fortfahren. Wenn nicht, besuchen [Sie "Neues Google-Konto](https://accounts.google.com/SignUp?hl=en) erstellen", um ein neues Gmail-Konto einzurichten.

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. Einrichten Ihres Microsoft 365 Mandanten

*Konfigurieren sie Teams AAD-Benutzer:*

1. Befolgen Sie die Anleitungen unter["Benutzer hinzufügen" und weisen Sie Lizenzen](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) zum Hinzufügen mehrerer Benutzer zu.

*Konfigurieren des Identitätsschutzes:*

1. Deaktivieren Sie die Sicherheitsstandards, wenn sie aktiv sind.

2. Konfigurieren der mehrstufigen Authentifizierung für Benutzer

3. Wenn Sie bedingten Zugriff verwenden, stellen Sie sicher, dass Sie eine Ausnahme für den POP-Zugriff auf das Postfach bilden.

*Domäne zum Microsoft 365 Admin Center hinzufügen (optional):*

1. Wählen Sie im Navigationsbereich Einstellungen > Domäne und dann "Domäne hinzufügen" aus.

2. Geben Sie Ihren Domänennamen in das entsprechende Feld ein.

3. Folgen Sie den Anweisungen auf dem Bildschirm, um Ihre Domäne mit TXT-Eintrag zu überprüfen.

4. Wenn Sie dazu aufgefordert werden, erlauben Sie Microsoft, DNS zu konfigurieren

5. Führen Sie die Anweisungen zum Überprüfen der MX-Eintragsroute zu Microsoft 365

6. Konfigurieren des SPF TXT-Eintrags für Microsoft 365

7. Befolgen Sie die Anweisungen zum Konfigurieren von DKIM TXT-Einträgen für Microsoft 365

8. Stellen Sie sicher, dass DKIM aktiviert ist, indem Sie sich abmelden und sich wieder beim Admin Center anmelden.

#### <a name="3-configure-gmail"></a>3. Konfigurieren von Gmail

1. Konfigurieren von Gmail zum Abrufen Exchange Online E-Mails in das System

2. Konfigurieren des Teams Kalender-Add-Ins

3. Aktivieren von Gmail für die Verwendung der Unternehmensdomäne (optional)
