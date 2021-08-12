---
title: Bereitstellen Skype Raumsystemkonten in Microsoft 365 und Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lesen Sie dieses Thema, um mehr über die Bereitstellung Skype Raumsystemkonten in Microsoft 365 oder Office 365 zu erfahren.
ms.openlocfilehash: e50d0df6b0ae3c03299756d9f917083fc2518cb64d7b049d0d7b23eb4f64b063
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307946"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Bereitstellen Skype Raumsystemkonten in Microsoft 365 und Office 365
 
Lesen Sie dieses Thema, um mehr über die Bereitstellung Skype Raumsystemkonten in Microsoft 365 oder Office 365 zu erfahren.
  
Der folgende Abschnitt behandelt Skype Bereitstellung von Raumsystemkonten.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>voraussetzungen für Microsoft 365 und Office 365

Ihr Onlinemandant muss die folgenden Anforderungen erfüllen:
  
- Der Microsoft 365- oder Office 365-Plan muss Skype for Business Onlineplan 2 oder Office 365 E1, E3 oder E5 enthalten. <br/>Ausführliche Informationen zu Skype for Business Onlineplänen finden Sie in der [Skype for Business Onlinedienstbeschreibung.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
    
- Für Ihren Mandanten muss die Konferenzfunktion Skype for Business aktiviert sein.
    
- Ihr Mandant muss Exchange Online aktiviert haben. 
    
- Ihr Mandanten-Remoteadministrator muss über den folgenden PowerShell-Zugriff verfügen:
    
  - Exchange Remote-PowerShell-Zugriff
    
  - Skype for Business Online-Remote-PowerShell-Zugriff
    
  - Windows Azure Active Directory-Modul für Windows PowerShell für den Zugriff auf Microsoft 365 oder Office 365 Verzeichniszugriff
    
Für das Skype Room-Konto ist die folgende Lizenzierung erforderlich:
  
- Um Skype Besprechungen zu aktivieren, ist eine Lizenz für Skype for Business Onlineplan 2 oder Office 365 E1 oder E3 erforderlich.
    
- Um den Raum mit der Enterprise-VoIP Funktion zu befähigen, damit der Raum mit einer Telefonnummer aktiviert werden kann, ist ein Skype for Business OnlinePlan 2 mit der Telefonsystem-Lizenz oder Office 365 E5 erforderlich (1).
    
- Wenn Sie Einwahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Audiokonferenz und Telefonsystem Lizenz.  Wenn Sie Ausgehende Funktionen aus einer Besprechung benötigen, benötigen Sie einen Anrufplan für Inland oder Inland und Ausland. 
    
- Für das Skype Room-Konto ist keine Exchange Online Lizenz erforderlich, da das Konto als Ressourcenpostfachkonto konfiguriert werden sollte.
    
## <a name="provisioning-overview"></a>Übersicht über die Bereitstellung

Das folgende Diagramm enthält eine Übersicht über den Bereitstellungsfluss Skype Raumsystemkonto.
  
![Skype Schritte zur Raumsystembereitstellung](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifizieren eines neuen Konferenzraums

Möglicherweise verfügen Sie bereits über ein Ressourcenraumpostfach in Exchange, das das Planungsfeature bereitstellt, oder Sie erstellen möglicherweise zum ersten Mal ein Ressourcenpostfach, um Skype Raumsystembereitstellung zu vereinfachen. In jedem Fall müssen Sie ein Raumkonto identifizieren, das in Ihrem Mandanten verwendet werden soll. Die Abschnitte Exchange Online Bereitstellung und Skype for Business Bereitstellung enthalten Anleitungen für beide Arten von Konten. Angenommen, Sie haben die folgenden beiden Räume, und Sie möchten Skype Raumsystem für beide bereitstellen:
  
- Vorhandenes Ressourcenpostfachkonto: confrm1@contoso.onmicrosoft.com
    
- Neues Ressourcenpostfachkonto: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online-Bereitstellung

Stellen Sie zunächst eine Verbindung mit Exchange Online PowerShell her, indem Sie die Anweisungen im Thema [Verbinden Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)befolgen.
  
Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein vorhandenes Ressourcenraumpostfachkonto für Skype Raumsystem festzulegen:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Um ein neues Exchange Ressourcenpostfachkonto für Skype Raumsystem zu erstellen, führen Sie die folgenden Befehle in Exchange Online PowerShell aus:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Mit den vorherigen Befehlen wurde ein neues Exchange Ressourcenpostfachkonto für Skype Raumsystemnutzung eingerichtet oder erstellt, indem das Konto aktiviert wird.
  
Nach dem Erstellen des Postfachs können Sie das Cmdlet Set-CalendarProcessing in Exchange Online PowerShell verwenden, um das Postfach zu konfigurieren. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter lokale Bereitstellungen mit einzelner Gesamtstruktur.

## <a name="assigning-a-skype-for-business-online-license"></a>Zuweisen einer Skype for Business Onlinelizenz

Jetzt können Sie eine lizenz Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3) zuweisen, indem Sie das Microsoft 365 Verwaltungsportal verwenden, wie unter Zuweisen oder Entfernen von [Lizenzen für Microsoft 365 business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in Skype for Business [Add-On-Lizenzierung](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)beschrieben. 
  
Nachdem Sie eine Lizenz für Skype for Business Online zugewiesen haben, können Sie sich anmelden und überprüfen, ob das Konto mit einem beliebigen Skype for Business-Client aktiv ist.
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Onlinebereitstellung

Nachdem ein Ressourcenraumpostfachkonto erstellt und wie zuvor gezeigt aktiviert wurde und Sie das Konto für Skype For Business Online lizenziert haben, wird das Konto mithilfe der Windows Azure Active Directory Gesamtstruktur von der Exchange Online Gesamtstruktur mit Skype for Business Onlinegesamtstruktur synchronisiert. Die folgenden Schritte sind erforderlich, um das Skype Raumsystemkonto im Skype for Business Onlinepool bereitzustellen. Diese Schritte sind für ein vorhandenes Ressourcenpostfachkonto oder ein neu erstelltes Konto (confrm1 oder confrm2) identisch, da nach der Aktivierung in Exchange Online beide Konten auf die gleiche Weise mit Skype for Business Online synchronisiert werden:
  
1. Erstellen Sie eine Remote-PowerShell-Sitzung. Beachten Sie, dass Sie [Teams PowerShell-Modul](/microsoftteams/teams-powershell-install)herunterladen müssen.
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Führen Sie den folgenden Befehl aus, um ein Skype Raumsystemkonto für Skype for Business zu aktivieren:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Mit dem folgenden Befehl können Sie die RegistrarPool-Adresse abrufen, unter der Ihre Skype for Business Benutzer von einem Ihrer vorhandenen Konten verwaltet werden, um diese Eigenschaft zu zurückgeben:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) wird für Skype Raumsystemkonten nicht unterstützt. 

## <a name="password-expiration"></a>Kennwortablauf

In Microsoft 365 oder Office 365 beträgt die Standardmäßige Kennwortablaufrichtlinie für alle Benutzerkonten 90 Tage, es sei denn, Sie konfigurieren eine andere Kennwortablaufrichtlinie. Für Skype Room System-Konten können Sie die Einstellung "Kennwort läuft nie ab" mit den folgenden Schritten auswählen.
  
1. Erstellen Sie eine Windows Azure Active Directory Sitzung mithilfe der Anmeldeinformationen ihres globalen Mandantenadministrators.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Set the Password never expires setting for the Skype Room System room account created previously by using the following command:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="validate"></a>Validieren

Zur Überprüfung sollten Sie jeden Skype for Business Client verwenden können, um sich bei dem von Ihnen erstellten Konto anzumelden.