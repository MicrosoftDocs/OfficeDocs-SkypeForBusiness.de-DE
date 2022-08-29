---
title: Erstellen von Ressourcenkonten für Räume und freigegebene Teams-Geräte
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Artikel finden Sie Informationen zum Erstellen von Ressourcenkonten für Räume und freigegebene Geräte, einschließlich Microsoft Teams-Räume, Teams-Räume auf Surface Hub und Hot-Desking auf Teams-Displays.
ms.openlocfilehash: 45cd61b476f10f673150653144bdb79a47604962
ms.sourcegitcommit: 17f4baf85e1ac6a2af5f5c6ea2d5aae763efd917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405157"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Erstellen und Konfigurieren von Ressourcenkonten für Räume und freigegebene Teams-Geräte

Dieser Artikel enthält Die Schritte zum Erstellen von Ressourcenkonten für freigegebene Räume und Geräte sowie Schritte zum Konfigurieren von Ressourcenkonten für Microsoft Teams-Räume unter Windows, Teams-Räume unter Android, Teams-Räume auf Surface Hub und Hot-Desking auf Teams-Displays.

Microsoft 365-Ressourcenkonten sind Postfach- und Teams-Konten, die bestimmten Ressourcen wie einem Raum oder Projektor zugeordnet sind. Diese Ressourcenkonten können automatisch mithilfe von Regeln, die Sie beim Erstellen definieren, auf Besprechungseinladungen reagieren. Wenn Sie z. B. über eine gemeinsame Ressource wie einen Konferenzraum verfügen, können Sie ein Ressourcenkonto für diesen Konferenzraum einrichten, das Besprechungseinladungen je nach Verfügbarkeit des Kalenders automatisch annimmt oder ablehnt. 

Jedes Ressourcenkonto ist für eine einzelne Microsoft Teams-Räume-Installation eindeutig, oder Teams zeigt eine Hot-Desking-Implementierung an.

> [!NOTE]
> Wenn Sie Microsoft Teams-Bereiche verwenden, meldet sich das Teams-Räume Ressourcenkonto sowohl bei Teams-Räume als auch bei den zugehörigen Teams-Bereichen an.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> Wenn Sie Ihr Ressourcenkonto für die Arbeit mit Skype for Business aktivieren müssen, lesen [Sie "Bereitstellen Microsoft Teams-Räume mit Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="requirements"></a>Anforderungen

Je nach Umgebung benötigen Sie eine oder mehrere Rollen, um Ressourcenkonten zu erstellen.

|**Umgebung**|**Erforderliche Rollen**|
|-----|-----|
|Azure Active Directory  <br/> |Globaler Administrator oder Benutzeradministrator  <br/> |
|Active Directory  <br/> |Active Directory-Unternehmensadministratoren, Domänenadministratoren oder verfügen über delegierte Rechte zum Erstellen von Benutzern. Azure Active Directory Connect-Synchronisierungsrechte.  <br/> |
|Exchange Online  <br/> |Globaler Administrator oder Exchange-Administrator   <br/> |
|Exchange Server  <br/> |Exchange-Organisationsverwaltung oder Empfängerverwaltung   <br/> |

Wenn Sie Ressourcenkonten für Teams-Räume erstellen, muss der UPN mit der SMTP-Adresse des Ressourcenkontos übereinstimmen. Lesen Sie [Microsoft Teams-Räume Anforderungen](requirements.md), bevor Sie Teams-Räume bereitstellen.

### <a name="what-license-do-you-need"></a>Welche Lizenz benötigen Sie?

Bevor Sie ein Microsoft 365-Ressourcenkonto erstellen, überprüfen Sie, welche Art von Lizenz benötigt wird:

- **Teams-Besprechungen** Wenn Sie das Ressourcenkonto einem freigegebenen Gerät zuordnen möchten, z. B. einem Microsoft Teams-Raum oder einer Microsoft Teams-Anzeige mit Hot-Desking, und es verwenden möchten, um an einer Teams-Besprechung teilzunehmen, damit Teilnehmer es verwenden können, um Video und Audio darüber zu präsentieren, benötigen Sie eine Besprechungsraumlizenz. Weitere Informationen zur Lizenzierung für Besprechungsräume finden Sie unter [Microsoft Teams-Besprechungsraumlizenzierung](rooms-licensing.md).

- **PSTN-Anrufe** Wenn Sie möchten, dass die Ressource Anrufe an oder von einer externen Telefonnummer (so genanntes Public Switched Telephone Network oder PSTN-Anruf) entgegennehmen kann, benötigen Sie ein Microsoft 365-Telefonsystem oder Microsoft 365 Business Voice Lizenz. Sie müssen nur Schritt 1 in der folgenden Übersicht ausführen. Weitere Informationen finden Sie unter [Microsoft Teams-Add-On-Lizenzen](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .

- Wenn Sie nur ein Ressourcenkonto zum Buchen einer Ressource&mdash;verwenden, laden Sie die Ressource zu Ihrer Besprechung ein und lassen Sie sie automatisch die Einladung&mdash;annehmen oder ablehnen, die Sie dem Ressourcenkonto nicht zuweisen müssen, und Sie müssen schritt 1 nur in der folgenden Übersicht ausführen.  

## <a name="overview"></a>Übersicht

**Schritt 1:** [Erstellen eines neuen Ressourcenkontos](#create-a-resource-account). Wenn ein Raumpostfach bereits vorhanden ist und Sie es in ein Ressourcenkonto konvertieren möchten, können Sie [ein vorhandenes Exchange-Raumpostfach ändern](?tabs=existing-account#create-a-resource-account).

**Schritt 2 -**  [Konfigurieren Sie dann Ihr Konto](#configure-mailbox-properties) für Teams-Besprechungen.

**Schritt 3 -**  Wenn das Ressourcenkonto einem freigegebenen Gerät zugeordnet werden soll, z. B. wenn Teams mit hot-desking angezeigt wird, [deaktivieren Sie den Kennwortablauf](#turn-off-password-expiration).

**Schritt 4 -**  [Weisen Sie schließlich eine Besprechungsraumlizenz](#assign-a-meeting-room-license) zu, damit das Konto auf Microsoft Teams zugreifen kann.

Nachdem Sie Ihre Ressourcenkonten erstellt und konfiguriert haben, lesen Sie [die nächsten Schritte](#next-steps) zum Überprüfen zusätzlicher Setupaufgaben, einschließlich Verteilergruppen, Netzwerkfunktionen und Anrufen.

## <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

> [!TIP]
> Beim Benennen Ihrer Ressourcenkonten wird empfohlen, am Anfang der E-Mail-Adresse eine Standardbenennungskonvention zu verwenden. Dies hilft beim Erstellen dynamischer Gruppen, um die Verwaltung in Azure Active Directory zu vereinfachen. Sie können z. B. "mtr-" für alle Ressourcenkonten verwenden, die Microsoft Teams-Räume zugeordnet werden.

> [!TIP]
> Es wird empfohlen, alle Ressourcenkonten mit Exchange Online und Azure Active Directory zu erstellen.

Erstellen Sie ein Ressourcenkonto mithilfe einer Methode auf einer der folgenden Registerkarten:

#### <a name="in-microsoft-365-admin-center"></a>[**In Microsoft 365 Admin Center**](#tab/m365-admin-center)

1. Melden Sie sich beim Microsoft 365 Admin Center an.

2. Geben Sie die Administratoranmeldeinformationen für Ihren Microsoft 365-Mandanten an.

3. Wechseln Sie im linken Bereich zu **"Ressourcen** ", und wählen Sie dann **"Räume & Ausrüstung**" aus. Wenn diese Optionen im linken Bereich nicht verfügbar sind, müssen Sie möglicherweise zuerst **"Alle anzeigen"** auswählen.

4. Wählen Sie **"Ressource hinzufügen"** aus, um ein neues Raumkonto zu erstellen. Geben Sie einen Anzeigenamen und eine E-Mail-Adresse für das Konto ein, wählen Sie **"Hinzufügen"** und dann " **Schließen**" aus.

5. Ressourcenkonten sind standardmäßig mit den folgenden Einstellungen konfiguriert:

    - Besprechungsserien zulassen
    - Automatisches Ablehnen von Besprechungen außerhalb der folgenden Grenzwerte
      - Buchungsfenster (Tage): 180
      - Maximale Dauer (Stunden): 24
    - Automatisches Annehmen von Besprechungsanfragen

    Wenn Sie sie ändern möchten, wählen Sie **"Buchungsoptionen bearbeiten** " aus, bevor Sie **"Schließen**" auswählen. Wenn Sie sie später ändern möchten, wechseln Sie zu **Ressourcenräume** > **& Ausrüstung**, wählen Sie das Ressourcenkonto aus. Wählen Sie dann unter **"Buchungsoptionen**" die Option **"Bearbeiten"** aus.

6. Wechseln **Sie zu "Aktive Benutzer"** > , und wählen Sie den Von Ihnen erstellten Raum aus, um den Eigenschaftenbereich zu öffnen.

7. Weisen Sie als Nächstes dem Ressourcenkonto ein Kennwort zu. Wählen Sie im Bereich " **Kennwort zurücksetzen" aus**.
 
8. Wenn Benutzer das Kennwort auf einem freigegebenen Gerät ändern müssen, treten Anmeldeprobleme auf. Deaktivieren Sie das Kontrollkästchen **"Diesen Benutzer auffordern, sein Kennwort zu ändern, wenn er sich zum ersten Mal anmeldet**, und wählen Sie **"Kennwort zurücksetzen" aus**.

9. Legen Sie im Abschnitt **"Lizenzen und Apps****" den Speicherort "Auswählen"** auf das Land oder die Region fest, in dem das Gerät installiert wird. Wählen Sie dann die Lizenz aus, die Sie zuweisen möchten, z. B. den Besprechungsraum, und wählen Sie " **Änderungen speichern"** aus. Die Lizenz kann je nach Organisation variieren.

Informationen zum Ändern der Einstellungen des Ressourcenpostfachs finden [Sie unter Konfigurieren von Postfacheigenschaften](#configure-mailbox-properties) oder Verwenden des Exchange Admin Centers.

Möglicherweise müssen Sie auch Bandbreitenrichtlinien oder Besprechungsrichtlinien auf dieses Konto anwenden. Weitere Informationen finden Sie unter ["Nächste Schritte](#next-steps) ".

#### <a name="with-exchange-online"></a>[**Mit Exchange Online**](#tab/exchange-online)

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) her.

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Standardmäßig verfügen Raumpostfächer nicht über zugeordnete Konten. Fügen Sie beim Erstellen eines Raumpostfachs ein Konto hinzu, damit es sich bei Microsoft Teams authentifizieren kann.

    Wenn Sie ein neues Ressourcenpostfach erstellen:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

    - Konto: ConferenceRoom01@contoso.com
          
    - Name: ConferenceRoom01
        
     - Alias: ConferenceRoom01
        
     - Kontokennwort: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Wenn Sie sich nicht in einer Exchange-Hybridkonfiguration befinden, können Sie mit dem nächsten Schritt fortfahren: [Konfigurieren von Postfacheigenschaften](#configure-mailbox-properties).

Wenn Sie sich in einer Exchange-Hybridkonfiguration befinden, müssen Sie eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzufügen. Weitere Informationen finden Sie unter [Lokales Synchronisieren und Office 365 Benutzerkontenverzeichnissen](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

#### <a name="with-exchange-server"></a>[**Mit Exchange Server**](#tab/exchange-server)

  1. Stellen Sie eine Verbindung mit der Exchange-Verwaltungsshell her. [Öffnen Sie die Exchange-Verwaltungsshell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) , oder [stellen Sie eine Verbindung mit Ihrem Exchange-Server mithilfe von Remote-PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell) her.

   2. So erstellen Sie ein neues Raumpostfach:

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

Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach so zu ändern, dass es ein Ressourcenkonto wird:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert "ConferenceRoom02" aufweist, und das Kennwort wird auf 9898P@$$W 0rd festgelegt.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Wenn Sie sich in einer Exchange-Hybridkonfiguration befinden, müssen Sie auch eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzufügen. Weitere Informationen finden Sie unter [Lokales Synchronisieren und Office 365 Benutzerkontenverzeichnissen](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) " und ["Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)".

> [!NOTE]
> Wenn Sie dieses Konto für Teams Room auf Surface Hub erstellen, sollten Sie auch ActiveSync für dieses Konto aktivieren. Auf diese Weise können Sie E-Mails direkt über den Surface Hub senden, den Sie für Features wie Whiteboard verwenden können. Weitere Informationen finden Sie unter [Anwenden von ActiveSync-Richtlinien auf Gerätekonten (Surface Hub](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) ).

---

> [!IMPORTANT]
> Wenn Sie dieses Ressourcenkonto nur verwenden, um Platz zu reservieren und Einladungen automatisch anzunehmen oder abzulehnen, haben Sie die Einrichtung abgeschlossen. Wenn Sie dieses Ressourcenkonto für PSTN-Anrufe verwenden, lesen Sie [die Microsoft Teams-Add-On-Lizenzen](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) , um zu ermitteln, welche Lizenz benötigt wird.
>
> Fahren Sie nur dann mit dem nächsten Abschnitt fort, wenn das Ressourcenkonto für eine Teams-Räume unter Windows, Teams-Räume unter Android, Teams-Räume auf Surface Hub oder eine Teams-Anzeige mit Hot-Desking bestimmt ist.

## <a name="configure-mailbox-properties"></a>Konfigurieren von Postfacheigenschaften

Konfigurieren Sie in Exchange PowerShell online oder lokal die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

- **AutomateProcessing: `AutoAccept`** Besprechungsorganisatoren erhalten die Raumreservierungsentscheidung direkt ohne menschliches Eingreifen.

- **AddOrganizerToSubject: `$false`** Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.

- **DeleteComments: `$false`** Behalten Sie text im Nachrichtentext eingehender Besprechungsanfragen bei. Dies ist erforderlich, um externe Teams- und Drittanbieterbesprechungen zu verarbeiten, um one Touch Join-Erfahrung zu bieten.

- **DeleteSubject: `$false`** Behalten Sie den Betreff eingehender Besprechungsanfragen bei.

- **ProcessExternalMeetingMessages: `$true`** Gibt an, ob Besprechungsanfragen verarbeitet werden sollen, die außerhalb der Exchange-Organisation stammen. Erforderlich für externe [Teams-Besprechungen und Besprechungen von Drittanbietern](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Stellt sicher, dass das private Kennzeichen, das vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, unverändert bleibt.

- **AddAdditionalResponse: `$true`** Der durch den Parameter "AdditionalResponse" angegebene Text wird Besprechungsanfragen hinzugefügt.

- **AdditionalResponse: "Dies ist ein Microsoft Teams-Besprechungsraum!"** Der zusätzliche Text, der der Besprechungsakzeptanzantwort hinzugefügt werden soll.

In diesem Beispiel werden diese Einstellungen für ein Raumpostfach namens ConferenceRoom01 konfiguriert:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Ausführliche Informationen zu Syntax und Parametern finden [Sie unter Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Deaktivieren des Kennwortablaufs

Wenn das Kennwort für das Ressourcenkonto abläuft, wird sich das Gerät nach dem Ablaufdatum nicht mehr anmelden. Das Kennwort muss dann für das Ressourcenkonto geändert und dann auf jedem Gerät aktualisiert werden. Um dies zu vermeiden, können Sie den Ablauf des Kennworts deaktivieren.
  
> [!NOTE]
> Das Festlegen des **Kennworts läuft nie ab** , ist eine Anforderung für freigegebene Microsoft Teams-Geräte. Wenn Ihre Domänenregeln Kennwörter verbieten, die nicht ablaufen, müssen Sie eine Ausnahme für jedes Teams-Geräteressourcenkonto erstellen.

Führen Sie die Schritte auf einer der folgenden Registerkarten aus, um den Kennwortablauf zu deaktivieren:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Stellen Sie zunächst eine Verbindung mit Active Directory PowerShell her:

```PowerShell
   Connect-AzureAD
```

Lesen [Sie dann "Kennwort festlegen", damit es nie abläuft](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire).

In diesem Beispiel wird festgelegt, dass das Kennwort für das Konto ConferenceRoom01@contoso.com nie abläuft.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Herstellen einer Verbindung mit MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Ausführliche Informationen zu Active Directory finden Sie unter [Azure Active Directory (MSOnline).For details about Active Directory, see Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Legen Sie das Kennwort so fest, dass es nie abläuft, indem Sie die folgende Syntax verwenden:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In diesem Beispiel wird festgelegt, dass das Kennwort für das Konto ConferenceRoom01@contoso.com nie abläuft.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (lokal)**](#tab/active-directory1-password/)

1. Herstellen einer Verbindung mit Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Ausführliche Informationen zu Active Directory PowerShell finden Sie unter [ActiveDirectory](/powershell/module/activedirectory/).

2. Legen Sie das Kennwort so fest, dass es nie abläuft, indem Sie die folgende Syntax verwenden:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In diesem Beispiel wird festgelegt, dass das Kennwort für das Konto ConferenceRoom01@contoso.com nie abläuft.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Zuweisen einer Besprechungsraumlizenz

Das Ressourcenkonto benötigt eine Microsoft 365- oder Office 365-Lizenz, um sich bei Microsoft Teams anzumelden.

> [!NOTE]
> Microsoft Teams-Räume Standard und Microsoft Teams-Räume Premium sind die beiden verfügbaren SKUs für gemeinsam genutzte Besprechungsraumgeräte, einschließlich Teams-Räume. Eine Besprechungsraumlizenz ist für Teams-Displays mit Hot-Desking erforderlich. Weitere Informationen finden Sie unter [Lizenzierung von Teams-Besprechungsräumen](rooms-licensing.md).

Informationen zum Zuweisen von Lizenzen mithilfe der Microsoft 365 Admin Center finden [Sie unter Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users). Informationen zum Zuweisen von Lizenzen mitHilfe von Azure AD finden Sie auf einer der folgenden Registerkarten:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Herstellen einer Verbindung mit Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Ausführliche Informationen zu Active Directory finden Sie unter [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Weisen Sie Ihrem Ressourcenkonto mithilfe des `Set-AzureADUser` Cmdlets einen Verwendungsspeicherort zu. Dadurch wird bestimmt, welche Lizenz-SKUs verfügbar sind.

    In diesem Beispiel befindet sich der Benutzer im USA (USA):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Verwenden Sie `Get-AzureADSubscribedSku` diese Option, um eine Liste der verfügbaren SKUs für Ihre Microsoft 365- oder Office 365-Organisation abzurufen.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Verwenden Sie zum Zuweisen der Lizenz das `Set-AzureADUser` Cmdlet, und konvertieren Sie die Lizenz-SKU-ID (siehe Schritt 2) in ein PowerShell-Lizenztypobjekt. Weisen Sie das Objekt dann dem Ressourcenkonto zu. Im folgenden Beispiel lautet die Lizenz-SKU-ID 6070a4c8-34c6-4937-8dfb-39bbc6397a60 und wird dem Konto conferenceroom01@contoso.com zugewiesen:

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

1. Stellen Sie eine Verbindung mit MSOnline PowerShell her.

   ```PowerShell
   Connect-MsolService
   ```

    Ausführliche Informationen zu Active Directory finden Sie unter [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Weisen Sie Ihrem Ressourcenkonto mithilfe des `Set-MsolUser` Cmdlets einen Verwendungsspeicherort zu. Dadurch wird bestimmt, welche Lizenz-SKUs verfügbar sind.

    In diesem Beispiel befindet sich der Benutzer im USA (USA).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Anschließend können `Get-MsolAccountSku` Sie eine Liste der verfügbaren SKUs für Ihre Microsoft 365- oder Office 365-Organisation abrufen.

4. Verwenden Sie zum Zuweisen der Lizenz das `Set-MsolUser` Cmdlet. In diesem Beispiel wird die Lizenz "contoso:MEETING_ROOM" dem Konto conferenceroom01@contoso.com zugewiesen:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Um die Kontoerstellung und Lizenzzuweisung zu überprüfen, melden Sie sich mit dem von Ihnen erstellten Konto bei einem beliebigen Teams-Client an.

## <a name="next-steps"></a>Nächste Schritte

### <a name="meeting-policies"></a>Besprechungsrichtlinien

Möglicherweise müssen Sie benutzerdefinierte Netzwerk-, Bandbreiten- oder Besprechungsrichtlinien auf dieses Konto anwenden. Weitere Informationen zu Netzwerk- und Bandbreitenrichtlinien finden Sie unter [Besprechungsrichtlinieneinstellungen für Audio & Video](/microsoftteams/meeting-policies-audio-and-video). Für Teams-Räume wird empfohlen, die Bandbreite der Besprechungsrichtlinien auf 10 MBit/s festzulegen.

Aktivieren Sie für Zusammenarbeitszwecke PowerPoint Live, Whiteboard und freigegebene Notizen. Es wird empfohlen, die Besprechungsrichtlinieneinstellung "Jetzt in privaten Besprechungen besprechen" zu aktivieren. Möglicherweise möchten Sie eine Besprechungsrichtlinie erstellen, um Teilnehmer- und Gasteinstellungen für Teams-Räume anzupassen. Überprüfen Sie beispielsweise die Wartebereichseinstellungen, z. B. welche Teilnehmer Besprechungen automatisch zulassen sollen. Weitere Informationen zu Teams-Besprechungsrichtlinien finden [Sie unter Verwalten von Besprechungsrichtlinien in Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Anrufe

Es gibt keine eindeutigen Anforderungen zum Aktivieren von Aufrufen mit Ressourcenkonten. Sie aktivieren das Ressourcenkonto für Das Aufrufen auf die gleiche Weise, wie Sie einen normalen Benutzer aktivieren.

> [!NOTE]
> Es wird empfohlen, Voicemail für freigegebene Geräte zu deaktivieren, indem Sie den Geräteressourcenkonten eine Anrufrichtlinie zuweisen. Weitere Informationen finden Sie [unter Anrufen und Anrufweiterleitung in Teams](../teams-calling-policy.md) .

### <a name="configure-distribution-groups-for-teams-calendar"></a>Konfigurieren von Verteilergruppen für Teams-Kalender

Zum Organisieren ihrer Besprechungsraumspeicherorte können Sie Ihre Geräteressourcenkonten zu Exchange-Verteilergruppen hinzufügen. Wenn Sie beispielsweise Niederlassungen an drei verschiedenen geografischen Standorten haben, können Sie drei Verteilergruppen erstellen und jedem Standort die entsprechenden Ressourcenkonten hinzufügen. Weitere Informationen finden Sie unter [Erstellen einer Chatroomliste](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Konfigurieren von Orten für Outlook-Kalender
Damit Besprechungsraumspeicherorte in der Outlook-Raumsuche angezeigt werden, müssen Sie das Set-Place Exchange PowerShell-Cmdlet verwenden. Die Raumsuche in Outlook wird nicht nur Set-Place aufgefüllt, sondern ermöglicht es Ihnen auch, zusätzliche Metadaten hinzuzufügen, z. B. die Kapazität des Raums oder den Boden des Gebäudes, in dem sich der Raum befindet. Weitere Informationen finden Sie unter [Set-Place](/powershell/module/exchange/set-place).

## <a name="related-articles"></a>Verwandte Artikel

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Microsoft Teams-Räume-Lizenzierung](rooms-licensing.md)
