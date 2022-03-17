---
title: Erstellen von Ressourcenkonten für Räume und freigegebene Teams Geräte
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Artikel finden Sie Informationen zum Erstellen von Ressourcenkonten für Räume und freigegebene Geräte, einschließlich Microsoft Teams-Räume, Teams-Räume auf Surface Hub und Hot-King auf Teams Bildschirmen.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514546"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Erstellen und Konfigurieren von Ressourcenkonten für Räume und freigegebene Teams Geräte

Dieser Artikel enthält Die Schritte zum Erstellen von Ressourcenkonten für gemeinsam genutzte Räume und Geräte sowie Schritte zum Konfigurieren von Ressourcenkonten für Microsoft Teams-Räume auf Windows, Teams-Räume unter Android, Teams-Räume auf Surface Hub und Hot-King auf Teams werden angezeigt.

Microsoft 365 Ressourcenkonten sind Postfach- und Teams-Konten, die für bestimmte Ressourcen wie einen Raum oder Projektor dedizierte sind. Diese Ressourcenkonten können automatisch mithilfe von Regeln, die Sie beim Erstellen definieren, auf Besprechungs-Einladungen antworten. Wenn Sie z. B. über eine allgemeine Ressource wie einen Konferenzraum verfügen, können Sie ein Ressourcenkonto für diesen Konferenzraum einrichten, mit dem Besprechungs-Einladungen je nach Verfügbarkeit des Kalenders automatisch akzeptiert oder ablehnen werden.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> Wenn Sie Ihr Ressourcenkonto für die Zusammenarbeit mit Skype for Business müssen, lesen Sie Bereitstellen Microsoft Teams-Räume [mit Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="requirements"></a>Anforderungen

Je nach Ihrer Umgebung benötigen Sie eine oder mehrere Rollen zum Erstellen von Ressourcenkonten.

|**Umgebung**|**Erforderliche Rollen**|
|-----|-----|
|Azure Active Directory  <br/> |Globaler Administrator oder Benutzeradministrator  <br/> |
|Active Directory  <br/> |Active Directory Enterprise Administratoren oder Domänenadministratoren oder über delegierte Rechte zum Erstellen von Benutzern verfügen. Azure Active Directory Verbinden Synchronisierungsrechte.  <br/> |
|Exchange Online  <br/> |Globaler Administrator oder Exchange Administrator   <br/> |
|Exchange Server  <br/> |Exchange Organisationsverwaltung oder Empfängerverwaltung   <br/> |

Wenn Sie Ressourcenkonten für ihr Konto Teams-Räume, muss der UPN mit der SMTP-Adresse des Ressourcenkontos übereinstimmen. Weitere [Informationen Microsoft Teams-Räume Sie vor](requirements.md) der Bereitstellung Teams-Räume.

### <a name="what-license-do-you-need"></a>Welche Lizenz benötigen Sie?

Bevor Sie ein Microsoft 365 erstellen, überprüfen Sie, welche Art von Lizenz erforderlich ist:

- **Teams-Besprechungen** Wenn Sie das Ressourcenkonto einem gemeinsam genutzten Gerät zuordnen möchten, z. B. einem Microsoft Teams-Raum oder Teams-Bildschirm mit Hot-King, und es zur Teilnahme an einer Teams-Besprechung verwenden möchten, damit die Teilnehmer über dieses Gerät Video und Audio präsentieren können, benötigen Sie eine Besprechungsraum-Lizenz. Weitere Informationen zur Lizenzierung für Besprechungsräume finden Sie unter Teams Besprechungsraum [Lizenzierung](rooms-licensing.md).

- **PSTN-Anrufe** Wenn Sie möchten, dass die Ressource Anrufe an eine externe Telefonnummer (als "Telefon im öffentlichen Telefonnetz" oder "PSTN-Anruf" bezeichnet) anruft oder von dieser erhält, benötigen Sie eine Microsoft 365 Telefonsystem- oder Microsoft 365 Business Voice-Lizenz. Schritt 1 müssen Sie nur in der folgenden Übersicht abschließen. Weitere Informationen finden [Sie Microsoft Teams unter Hinzufügen von Add-On-Lizenzen](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- &mdash;Wenn Sie zum Buchen einer Ressource nur ein Ressourcenkonto verwenden,&mdash; laden Sie die Ressource zu Ihrer Besprechung ein, und lassen Sie sie die Einladung automatisch annehmen oder ablehnen. Sie müssen dem Ressourcenkonto keine Lizenz zuweisen, und Sie müssen nur Schritt 1 in der folgenden Übersicht abschließen.  

## <a name="overview"></a>Übersicht

**Schritt 1: Erstellen** [eines neuen Ressourcenkontos](#create-a-resource-account) Wenn ein Raumpostfach bereits vorhanden ist und Sie es in ein Ressourcenkonto konvertieren möchten, können Sie ein vorhandenes [Raumpostfach Exchange ändern](?tabs=existing-account#create-a-resource-account).

**Schritt 2 –**  Konfigurieren Sie dann [Ihr Konto für Teams](#configure-mailbox-properties) Besprechungen.

**Schritt 3 –**  Wenn das Ressourcenkonto einem gemeinsam genutzten Gerät zugeordnet werden soll, z. B. Teams mit Hot-King angezeigt wird, deaktivieren Sie den [Kennwortablauf](#turn-off-password-expiration).

**Schritt 4 –**  Weisen Sie [schließlich eine Besprechungsraumlizenz zu,](#assign-a-meeting-room-license) damit das Konto auf ihre Microsoft Teams.

Nachdem Sie ihre Ressourcenkonten erstellt und konfiguriert haben, [](#next-steps) lesen Sie Nächste Schritte zum Überprüfen zusätzlicher Setupaufgaben, einschließlich Verteilergruppen, Netzwerkfunktionen und Aufrufen von.

## <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

> [!TIP]
> Beim Benennen der Ressourcenkonten empfiehlt es sich, am Anfang der E-Mail-Adresse eine Standardbenennungskonvention zu verwenden. Dies hilft beim Erstellen dynamischer Gruppen, um die Verwaltung in Ihrer Azure Active Directory. Sie könnten z. B. "mtr-" für alle Ressourcenkonten verwenden, die den Ressourcen zugeordnet Microsoft Teams-Räume.

> [!TIP]
> Es wird empfohlen, alle Ressourcenkonten mithilfe von Ressourcenkonten Exchange Online und Azure Active Directory.

Erstellen Sie ein Ressourcenkonto mithilfe einer Methode auf einer der folgenden Registerkarten:

#### <a name="in-microsoft-365-admin-center"></a>[**In Microsoft 365 Admin Center**](#tab/m365-admin-center)

1. Melden Sie sich beim Microsoft 365 Admin Center an.

2. Geben Sie die Administratoranmeldeinformationen für Ihren mandanten Microsoft 365 an.

3. Wechseln Sie **im** linken Bereich zu Ressourcen, und wählen Sie dann Räume **& aus**. Wenn diese Optionen im linken Bereich nicht verfügbar sind, müssen Sie möglicherweise Zuerst alle **anzeigen** auswählen.

4. Wählen Sie **Ressourcenpostfach hinzufügen aus,** um ein neues Raumkonto zu erstellen. Geben Sie einen Anzeigenamen und eine E-Mail-Adresse für das Konto ein, wählen Sie **Hinzufügen** und dann Schließen **aus**.

5. Standardmäßig werden Ressourcenkonten mit den folgenden Einstellungen konfiguriert:

    - Wiederholen von Besprechungen zulassen
    - Automatisches Ablehnen von Besprechungen außerhalb der folgenden Grenzwerte
      - Buchungsfenster (Tage): 180
      - Maximale Dauer (Stunden): 24
    - Automatisches Annehmen von Besprechungsanfragen

    Wenn Sie diese ändern möchten, wählen Sie **Terminplanungsoptionen festlegen aus** , bevor Sie Schließen **auswählen**. Wenn Sie sie später ändern möchten, wechseln Sie zu **ResourcesRooms** >  **& und** wählen Sie das Ressourcenkonto aus. Wählen Sie dann **unter Buchungsoptionen** die Option **Bearbeiten aus**.

6. Wechseln Sie zu **BenutzerAktive** >  Benutzer, und wählen Sie den von Ihnen erstellten Raum aus, um den Eigenschaftenbereich zu öffnen.

7. Weisen Sie als Nächstes dem Ressourcenkonto ein Kennwort zu. Wählen Sie im Bereich Kennwort **zurücksetzen aus**.
 
8. Die Anforderung, dass Benutzer das Kennwort auf einem gemeinsam genutzten Gerät ändern müssen, verursacht Anmeldeprobleme. Deaktivieren Sie **Bei der ersten Anmeldung das Ändern ihres Kennworts** durch diesen Benutzer erforderlich, und wählen Sie **Zurücksetzen aus**.

9. Legen Sie **im Abschnitt Lizenzen und Apps** **Standort auswählen** auf das Land oder die Region, in dem bzw. der das Gerät installiert werden soll. Wählen Sie dann die Lizenz aus, die Sie zuweisen möchten, z. Besprechungsraum. Wählen Sie dann **Änderungen speichern aus**. Die Lizenz kann je nach Ihrer Organisation variieren.

Informationen zum Ändern der Einstellungen des Ressourcenpostfachs finden Sie unter [Konfigurieren](#configure-mailbox-properties) von Postfacheigenschaften oder Verwenden Exchange Admin Center.

Möglicherweise müssen Sie auch Bandbreitenrichtlinien oder Besprechungsrichtlinien auf dieses Konto anwenden. Weitere [Informationen finden Sie unter](#next-steps) Nächste Schritte.

#### <a name="with-exchange-online"></a>[**Mit Exchange Online**](#tab/exchange-online)

1. Verbinden Sie [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Raumpostfächern sind standardmäßig keine Konten zugeordnet. Fügen Sie beim Erstellen eines Raumpostfachs ein Konto hinzu, damit es sich bei anderen Microsoft Teams.

    Wenn Sie ein neues Ressourcenpostfach erstellen:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Wenn Sie sich nicht in einer Exchange-Hybridkonfiguration, können Sie mit dem nächsten Schritt, Konfigurieren von [Postfacheigenschaften, fortfahren](#configure-mailbox-properties).

Wenn Sie sich in einer Exchange-Hybridkonfiguration befinden, müssen Sie eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzufügen. Weitere [Informationen finden Sie unter Synchronisieren Office 365 und Verwalten von](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) Benutzerkonten.

#### <a name="with-exchange-server"></a>[**Mit Exchange Server**](#tab/exchange-server)

  1. Verbinden sie Exchange Verwaltungsshell. [Öffnen Sie die Exchange-Verwaltungsshell](/powershell/exchange/exchange-server/open-the-exchange-management-shell), oder stellen Sie mithilfe der [Remote-PowerShell Exchange mit Ihrem Exchange-Server eine Verbindung herstellen.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

   2. So erstellen Sie ein neues Raumpostfach

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

   - Konto: ConferenceRoom01@contoso.com
  
   - Name: ConferenceRoom01

   - Alias: ConferenceRoom01

   - Kontokennwort: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Ändern eines vorhandenen Exchange-Raumpostfachs**](#tab/existing-account)

Wenn Sie ein vorhandenes Raumpostfach so ändern möchten, dass es ein Ressourcenkonto wird, verwenden Sie die folgende Syntax:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert ConferenceRoom02 hat, und das Kennwort auf 9898P@ $$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Wenn Sie sich in einer Exchange-Hybridkonfiguration befinden, müssen Sie auch eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzufügen. Weitere [Informationen finden Sie unter Synchronisieren Office 365 und Verwalten von](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) Benutzerkonten.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Wenn Sie dieses Konto für "Room on Teams Room on Surface Hub" erstellen, sollten Sie ActiveSync auch für dieses Konto aktivieren. Auf diese Weise können Sie E-Mails direkt von der Surface Hub senden, die Sie für Features wie Whiteboard verwenden können. Weitere [Informationen finden Sie unter Anwenden von ActiveSync-Richtlinien auf Surface Hub](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) Gerätekonten.

---

> [!IMPORTANT]
> Wenn Sie dieses Ressourcenkonto nur zum Buchen von Speicherplatz und zum automatischen Annehmen oder Ablehnen von Einladungen verwenden, haben Sie die Einrichtung abgeschlossen. Wenn Sie dieses Ressourcenkonto für PSTN-Anrufe verwenden, finden Sie unter Hinzufügen [Microsoft Teams Add-On-Lizenzen](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) Informationen zur erforderlichen Lizenz.
>
> Fahren Sie nur dann mit dem nächsten Abschnitt fort, wenn das Ressourcenkonto für ein Teams-Räume-Gerät auf Windows, Teams-Räume unter Android, Teams-Räume auf Surface Hub oder eine Teams-Anzeige mit Hot-King verwendet wird.

## <a name="configure-mailbox-properties"></a>Konfigurieren von Postfacheigenschaften

Konfigurieren Exchange powerShell online oder lokal die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

- **Automatisieren der Verarbeitung: `AutoAccept`** Besprechungsorganisatoren erhalten die Entscheidung über die Raumreservierung direkt ohne eingreifende Menschlichen.

- **AddOrganizerToSubject: `$false`** Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.

- **DeleteComments: `$false`** Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei. Dies ist erforderlich, um externe Besprechungen Teams Besprechungen von Drittanbietern zu verarbeiten, um eine Touch-Teilnahmeerfahrung zu ermöglichen.

- **DeleteSubject: `$false`** Behalten Sie den Betreff eingehender Besprechungsanfragen bei.

- **ProcessExternalMeetingMessages: `$true`** Gibt an, ob Besprechungsanfragen, die außerhalb der Organisation Exchange werden, Exchange werden. Erforderlich für externe Teams und [Besprechungen von Drittanbietern](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Es wird sichergestellt, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.

- **AddAdditionalResponse: `$true`** Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.

- **AdditionalResponse: "Dies ist Microsoft Teams Besprechungsraum!"** Der zusätzliche Text, der der Besprechungsakzeptanzantwort hinzugefügt werden soll.

In diesem Beispiel werden die folgenden Einstellungen für ein Raumpostfach namens ConferenceRoom01 konfiguriert:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Deaktivieren des Kennwortablaufs

Wenn das Kennwort für das Ressourcenkonto abläuft, kann sich das Gerät nach dem Ablaufdatum nicht mehr anmelden. Das Kennwort muss dann für das Ressourcenkonto geändert und dann auf jedem Gerät aktualisiert werden. Um dies zu vermeiden, können Sie den Kennwortablauf deaktivieren.
  
> [!NOTE]
> Das **Festlegen von Kennwort läuft nie ab** ist eine Voraussetzung für geteilte Microsoft Teams Geräte. Wenn Ihre Domänenregeln Kennwörter verhindern, die nicht ablaufen, müssen Sie für jedes neue Teams eine Ausnahme erstellen.

Führen Sie die Schritte auf einer der folgenden Registerkarten aus, um den Kennwortablauf zu deaktivieren:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Zuerst müssen Verbinden Active Directory PowerShell hinzufügen:

```PowerShell
   Connect-AzureAD
```

Lesen Sie dann Festlegen eines [Kennworts, dass nie abläuft](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

In diesem Beispiel wird das Kennwort für das Konto so ConferenceRoom01@contoso.com, dass es nie abläuft.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Verbinden MSOnline-PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Details zu Active Directory finden Sie [unter Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Legen Sie mithilfe der folgenden Syntax das Kennwort so ein, dass es nie abläuft:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In diesem Beispiel wird das Kennwort für das Konto so ConferenceRoom01@contoso.com, dass es nie abläuft.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (lokal)**](#tab/active-directory1-password/)

1. Verbinden Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Details zu Active Directory PowerShell finden Sie unter [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Legen Sie mithilfe der folgenden Syntax das Kennwort so ein, dass es nie abläuft:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In diesem Beispiel wird das Kennwort für das Konto so ConferenceRoom01@contoso.com, dass es nie abläuft.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Zuweisen einer Besprechungsraumlizenz

Für das Ressourcenkonto ist eine Lizenz Microsoft 365 oder Office 365 erforderlich, um sich bei einem Microsoft Teams.

> [!NOTE]
> Microsoft Teams-Räume Standard und Microsoft Teams-Räume Premium sind die beiden verfügbaren SKUs für gemeinsame Besprechungsraumgeräte, einschließlich Teams-Räume. Für Besprechungsraumanzeigen mit Teams ist eine Lizenz für Besprechungsraum erforderlich. Weitere Informationen finden Sie unter [Teams von Besprechungsraumlizenzen](rooms-licensing.md).

Informationen zum Zuweisen von Lizenzen mithilfe der Microsoft 365 Admin Center Sie unter [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users). Informationen zum Zuweisen von Lizenzen Azure AD Sie auf einer der folgenden Registerkarten:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Verbinden zu Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Details zu Active Directory finden Sie unter [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Weisen Sie Ihrem Ressourcenkonto mithilfe des Cmdlets einen Verwendungsstandort `Set-AzureADUser` zu. Dies bestimmt, welche Lizenz-SKUs verfügbar sind.

    In diesem Beispiel befindet sich der Benutzer in den USA:

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Verwenden Sie dann , `Get-AzureADSubscribedSku` um eine Liste der verfügbaren SKUs für Ihre Organisation Microsoft 365 oder Office 365 abzurufen.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Verwenden Sie zum Zuweisen der Lizenz `Set-AzureADUser` das Cmdlet, und konvertieren Sie die Lizenz-SKU-ID (siehe Schritt 2) in ein PowerShell-Lizenztypobjekt. Weisen Sie dieses Objekt dann dem Ressourcenkonto zu. Im folgenden Beispiel ist die Lizenz-SKU-ID 6070a4c8-34c6-4937-8dfb-39bbc6397a60 und wird dem Konto conferenceroom01@contoso.com:

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Verbinden sie zu MSOnline-PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Details zu Active Directory finden Sie [unter Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Weisen Sie Ihrem Ressourcenkonto mithilfe des Cmdlets einen Verwendungsstandort `Set-MsolUser` zu. Dies bestimmt, welche Lizenz-SKUs verfügbar sind.

    In diesem Beispiel befindet sich der Benutzer in den USA.
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Anschließend können Sie verwenden, `Get-MsolAccountSku` um eine Liste der verfügbaren SKUs für Ihre Organisation Microsoft 365 oder Office 365 abzurufen.

4. Verwenden Sie zum Zuweisen der Lizenz das `Set-MsolUser` Cmdlet. In diesem Beispiel wird die Lizenz "contoso:MEETING_ROOM" dem Konto conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Um die Kontoerstellung und Lizenzzuweisung zu überprüfen, melden Sie sich mit dem von Ihnen erstellten Konto bei Teams-Client an.

## <a name="next-steps"></a>Nächste Schritte

### <a name="network-and-bandwidth"></a>Netzwerk und Bandbreite

Möglicherweise müssen Sie auf dieses Konto benutzerdefinierte Netzwerk-, Bandbreiten- oder Besprechungsrichtlinien anwenden. Weitere Informationen zu Netzwerk- und Bandbreitenrichtlinien finden Sie unter [Besprechungsrichtlinieneinstellungen für & Video](/microsoftteams/meeting-policies-audio-and-video). Für Teams-Räume sollten Sie die Bandbreite der Besprechungsrichtlinie auf 10 MBit/s festlegen.

Aktivieren Sie für die Zusammenarbeit Live PowerPoint, Whiteboard und freigegebene Notizen. Möglicherweise möchten Sie eine Besprechungsrichtlinie erstellen, um Teilnehmer- und Gasteinstellungen für die Besprechung Teams-Räume. Überprüfen Sie beispielsweise die Einstellungen für den Wartebereich, z. B. welche Teilnehmer automatisch zu Besprechungen teilnehmen sollen. Weitere Informationen zu Besprechungsrichtlinien Teams Sie unter [Verwalten von Besprechungsrichtlinien in Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Anrufe

Es gibt keine eindeutigen Anforderungen zum Aktivieren des Aufrufs von mit Ressourcenkonten. Sie aktivieren das Ressourcenkonto für Aufrufe auf die gleiche Weise wie einen normalen Benutzer.

> [!NOTE]
> Wir empfehlen, Voicemail für freigegebene Geräte zu deaktivieren, indem Sie den Geräteressourcenkonten eine Anrufrichtlinie zuweisen. Weitere [Informationen finden Sie unter](../teams-calling-policy.md) Anrufe und Teams in einer Telefonkonferenz.

### <a name="configure-distribution-groups"></a>Konfigurieren von Verteilergruppen

Zum Organisieren der Besprechungsraumstandorte können Sie Ihre Geräteressourcenkonten Exchange Verteilergruppen hinzufügen. Wenn Sie beispielsweise Niederlassungen an drei verschiedenen geografischen Standorten haben, können Sie drei Verteilergruppen erstellen und jedem Standort die entsprechenden Ressourcenkonten hinzufügen. Weitere Informationen finden Sie unter [Erstellen einer Liste von Räumen](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>Verwandte Artikel

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Microsoft Teams-Räume-Lizenzierung](rooms-licensing.md)
