---
title: Bereitstellen von Skype Room System-Konten in Microsoft 365 und Office 365
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
description: In diesem Thema erfahren Sie mehr über die Bereitstellung von Skype Room System-Konten in Microsoft 365 oder Office 365.
ms.openlocfilehash: 8e44e648e12ec4db1e8acf9617c02937f9418c41
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569377"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Bereitstellen von Skype Room System-Konten in Microsoft 365 und Office 365
 
In diesem Thema erfahren Sie mehr über die Bereitstellung von Skype Room System-Konten in Microsoft 365 oder Office 365.
  
Der folgende Abschnitt behandelt die Bereitstellung von Skype Room System-Konten.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Voraussetzungen für Microsoft 365 und Office 365

Ihr Online-Mandant muss die folgenden Anforderungen erfüllen:
  
- Der Microsoft 365- oder Office 365-Plan muss Skype for Business Online Plan 2 oder Office 365 E1, E3 oder E5 enthalten. <br/>Ausführliche Informationen zu Skype for Business Online-Plänen finden Sie unter [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).
    
- Ihr Mandant muss die Konferenzfunktion von Skype for Business aktiviert haben.
    
- Ihr Mandant muss Exchange Online aktiviert haben. 
    
- Ihr Mandanten-Remoteadministrator muss über den folgenden PowerShell-Zugriff verfügen:
    
  - Exchange Remote PowerShell-Zugriff
    
  - Skype for Business Online Remote PowerShell-Zugriff
    
  - Windows Azure Active Directory Module für Windows PowerShell Zugriff auf Microsoft 365- oder Office 365-Verzeichniszugriff
    
Für das Skype Room-Konto ist die folgende Lizenzierung erforderlich:
  
- Zum Aktivieren von Skype-Besprechungen ist eine Skype for Business Online Plan 2- oder Office 365 E1- oder E3-Lizenz erforderlich.
    
- Um den Raum mit der Enterprise-VoIP-Funktion zu berechtigen, damit der Raum mit einer Telefonnummer aktiviert werden kann, ist ein Skype for Business Online Plan 2 mit der Telefonsystemlizenz oder Office 365 E5 erforderlich (1).
    
- Wenn Sie Einwahlfunktionen von einer Besprechung benötigen, benötigen Sie eine Audiokonferenz- und Telefonsystemlizenz.  Wenn Sie Einwahlfunktionen von einer Besprechung benötigen, benötigen Sie einen nationalen oder nationalen und internationalen Anrufplan. 
    
- Für das Skype Room-Konto ist keine Exchange Online-Lizenz erforderlich, da das Konto als Ressourcenpostfachkonto konfiguriert werden sollte.
    
## <a name="provisioning-overview"></a>Übersicht über die Bereitstellung

Das folgende Diagramm bietet eine Übersicht über den Bereitstellungsfluss des Skype Room System-Kontos.
  
![Schritte zur Bereitstellung von Skype Room System](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifizieren eines neuen Konferenzraums

Möglicherweise verfügen Sie bereits über ein Ressourcenraumpostfach in Exchange, das das Planungsfeature bietet, oder Sie erstellen möglicherweise zum ersten Mal ein Ressourcenpostfach, um die Bereitstellung von Skype Room System zu erleichtern. In jedem Fall müssen Sie ein Raumkonto identifizieren, das in Ihrem Mandanten verwendet werden soll. Die Abschnitte Exchange Online Provision und Skype for Business Provision bieten Anleitungen für beide Arten von Konten. Angenommen, Sie verfügen über die folgenden beiden Räume, und Sie möchten Skype Room System für beide Bereitstellen:
  
- Vorhandenes Ressourcenpostfachkonto: confrm1@contoso.onmicrosoft.com
    
- Neues Ressourcenpostfachkonto: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online-Bereitstellung

Stellen Sie zunächst eine Verbindung mit Exchange Online PowerShell auf, indem Sie die Anweisungen im Thema [Connect to Exchange Online PowerShell befolgen.](https://go.microsoft.com/fwlink/p/?LinkId=396554)
  
Führen Sie zum Festlegen eines vorhandenen Ressourcenraumpostfachkontos für Skype Room System die folgenden Befehle in Exchange Online PowerShell aus:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein neues Exchange-Ressourcenpostfachkonto für Skype Room System zu erstellen:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Mit den vorherigen Befehlen wird ein neues Exchange-Ressourcenpostfachkonto für die Skype Room System-Verwendung eingerichtet oder erstellt, indem das Konto aktiviert wird.
  
Nach dem Erstellen des Postfachs können Sie das Set-CalendarProcessing in Exchange Online PowerShell verwenden, um das Postfach zu konfigurieren. Weitere Informationen finden Sie unter Schritte 3 bis 6 unter Lokale Bereitstellungen mit einer einzelnen Gesamtstruktur

## <a name="assigning-a-skype-for-business-online-license"></a>Zuweisen einer Skype for Business Online-Lizenz

Jetzt können Sie eine Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3)-Lizenz mithilfe des Microsoft 365-Verwaltungsportals zuweisen, wie unter Zuweisen oder Entfernen von Lizenzen für [Microsoft 365 Business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in [der Skype for Business-Add-On-Lizenzierung](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)beschrieben. 
  
Nachdem Sie eine Lizenz für Skype for Business Online zugewiesen haben, können Sie sich anmelden und überprüfen, ob das Konto mit einem beliebigen Skype for Business-Client aktiv ist.
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online-Bereitstellung

Nachdem wie oben gezeigt ein Ressourcenraumpostfachkonto erstellt und aktiviert wurde und Sie das Konto für Skype For Business Online lizenziert haben, wird das Konto mithilfe der Windows Azure Active Directory-Gesamtstruktur von der Exchange Online-Gesamtstruktur mit der Skype for Business Online-Gesamtstruktur synchronisiert. Die folgenden Schritte sind erforderlich, um das Skype Room System-Konto im Skype for Business Online-Pool bereitstellen zu können. Diese Schritte sind für ein vorhandenes Ressourcenpostfachkonto oder ein neu erstelltes Konto (confrm1 oder confrm2) identisch, da beide Konten nach der Aktivierung in Exchange Online auf die gleiche Weise mit Skype for Business Online synchronisiert werden:
  
1. Erstellen Sie eine Remote-PowerShell-Sitzung. Beachten Sie, dass Sie das [Teams PowerShell-Modul herunterladen müssen.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Führen Sie den folgenden Befehl aus, um ein Skype Room System-Konto für Skype for Business zu aktivieren:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Mithilfe des folgenden Befehls können Sie die RegistrarPool-Adresse abrufen, unter der Ihre Skype for Business-Benutzer von einem Ihrer vorhandenen Konten geheimst werden, um diese Eigenschaft zurückgibt:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Multi-Factor Authentication (MFA) wird für Skype Room System-Konten nicht unterstützt. 

## <a name="password-expiration"></a>Kennwortablauf

In Microsoft 365 oder Office 365 beträgt die Standardmäßige Kennwortablaufrichtlinie für alle Benutzerkonten 90 Tage, es sei denn, Sie konfigurieren eine andere Kennwortablaufrichtlinie. Für Skype Room System-Konten können Sie die Einstellung Kennwort nie abläuft mit den folgenden Schritten auswählen.
  
1. Erstellen Sie Windows Azure Active Directory-Sitzung mithilfe der Anmeldeinformationen des globalen Mandantenadministrators.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Legen Sie die Einstellung Kennwort läuft nie ab für das Skype Room System-Raumkonto, das zuvor mithilfe des folgenden Befehls erstellt wurde:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validieren

Zur Überprüfung sollten Sie einen beliebigen Skype for Business-Client verwenden können, um sich bei dem von Ihnen erstellten Konto zu anmelden.

