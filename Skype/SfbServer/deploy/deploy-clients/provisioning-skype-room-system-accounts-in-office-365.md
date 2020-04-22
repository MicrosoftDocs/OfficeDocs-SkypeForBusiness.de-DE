---
title: Einrichten von Skype Room System-Konten in Microsoft 365 und Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lesen Sie dieses Thema, um mehr über die Einrichtung von Skype Room System-Konten in Microsoft 365 oder Office 365 zu erfahren.
ms.openlocfilehash: e2796d9a81f918c0503382e23aad5ead711240e7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779711"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Einrichten von Skype Room System-Konten in Microsoft 365 und Office 365
 
Lesen Sie dieses Thema, um mehr über die Einrichtung von Skype Room System-Konten in Office 365 zu erfahren.
  
Im folgenden Abschnitt wird die Kontoverwaltung für Skype Room System für eine Office 365 Organisation behandelt.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Voraussetzungen für Microsoft 365 und Office 365

Ihr Online-Mandant muss die folgenden Anforderungen erfüllen:
  
- Der Plan Microsoft 365 oder Office 365 muss Skype for Business Online Plan 2 oder Office 365 E1, E3 oder E5 enthalten. <br/>Ausführliche Informationen zu Skype for Business Online Plänen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx).
    
- Ihr Mandant muss die Konferenzfunktion von Skype for Business aktiviert haben.
    
- Ihr Mandant muss Exchange Online aktiviert haben. 
    
- Der Remote Administrator des Mandanten muss über den folgenden PowerShell-Zugriff verfügen:
    
  - Exchange-Remote-PowerShell-Zugriff
    
  - Skype for Business Online Remote-PowerShell-Zugriff
    
  - Windows Azure Active Directory-Modul für Windows PowerShell für den Zugriff auf Office 365 Verzeichniszugriff
    
Für das Skype Room-Konto ist die folgende Lizenzierung erforderlich:
  
- Zum Aktivieren von Skype-Besprechungen ist eine Skype for Business Online Plan 2-oder Office 365 E1-oder E3-Lizenz erforderlich.
    
- Um den Raum mit der Enterprise-VoIP-Funktion zu berechtigen, damit der Raum mit einer Telefonnummer aktiviert werden kann, ist ein Skype for Business Online Plan 2 mit der Telefon System Lizenz oder Office 365 E5 erforderlich (1).
    
- Wenn Sie Einwahl Funktionen aus einer Besprechung benötigen, benötigen Sie eine Audio-Konferenz-und Telefon System Lizenz.  Wenn Sie Auswähl Funktionen aus einer Besprechung benötigen, benötigen Sie einen Plan für Inlands-oder Inlandsanrufe und internationale Anrufe. 
    
- Eine Exchange Online Lizenz ist für das Skype Room-Konto nicht erforderlich, da das Konto als Ressourcen Postfachkonto konfiguriert werden sollte.
    
## <a name="provisioning-overview"></a>Übersicht über die Überstellung

Das folgende Diagramm bietet eine Übersicht über den Ablauf der Bereitstellung von Skype Room System-Konten in Office 365.
  
![Schritte zur Vorgehensweise für das Skype Room-System für O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identifizieren eines neuen Konferenzraums

Möglicherweise verfügen Sie bereits über ein Ressourcen Raumpostfach in Exchange, das das Planungsfeature bereitstellt, oder Sie erstellen zum ersten Mal ein Ressourcenpostfach, um die Bereitstellung von Skype Room System zu vereinfachen. In jedem Fall müssen Sie ein Raum Konto angeben, das in Ihrem Mandanten verwendet werden soll. Die Abschnitte Exchange Online Bereitstellungs-und Skype for Business Bereitstellung bieten Anleitungen für beide Arten von Konten. Angenommen, Sie verfügen über die folgenden zwei Räume, und Sie möchten Skype Room System für beide bereitstellen:
  
- Vorhandenes Ressourcen Postfachkonto: confrm1@contoso.onmicrosoft.com
    
- Neues Ressourcen Postfachkonto: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online-Provision

Stellen Sie zunächst eine Verbindung mit Exchange Online PowerShell her, indem Sie die Anweisungen im Thema [Verbinden mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)befolgen.
  
Um ein vorhandenes Ressourcen Raum-Postfachkonto für Skype Room System festzulegen, führen Sie die folgenden Befehle in Exchange Online PowerShell aus:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein neues Exchange-Ressourcen Postfachkonto für Skype Room System zu erstellen:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

In den vorherigen Befehlen wurde ein neues Exchange-Ressourcen Postfachkonto für die Nutzung des Skype Room-Systems durch Aktivieren des Kontos eingerichtet oder erstellt.
  
Nachdem Sie das Postfach erstellt haben, können Sie das Cmdlet "CalendarProcessing" in Exchange Online PowerShell verwenden, um das Postfach zu konfigurieren. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter "lokale Bereitstellungen mit einzelner Gesamtstruktur".

## <a name="assigning-a-skype-for-business-online-license"></a>Zuweisen einer Skype for Business Online Lizenz

Jetzt können Sie eine Skype for Business Online (Plan 2)-oder Skype for Business Online (Plan 3)-Lizenz mithilfe des Office 365-Verwaltungsportals zuweisen, wie unter [zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in [Skype for Business Add-on-Lizenzierung](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)beschrieben. 
  
Nachdem Sie eine Lizenz für Skype for Business Online zugewiesen haben, können Sie sich anmelden und überprüfen, ob das Konto mit einem Skype for Business-Client aktiv ist.
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online-Provision

Nachdem ein Ressourcen Raum-Postfachkonto erstellt und wie zuvor gezeigt aktiviert wurde und Sie das Konto für Skype for Business Online lizenziert haben, wird das Konto mit der Windows Azure Active Directory-Gesamtstruktur von der Exchange Online Gesamtstruktur mit Skype for Business Online Gesamtstruktur synchronisiert. Die folgenden Schritte sind erforderlich, um das Skype Room-System Konto im Skype for Business Online Pool zu stellen. Diese Schritte sind für ein vorhandenes Ressourcen Postfachkonto oder ein neu erstelltes Konto identisch (confrm1 oder confrm2), da beide Konten nach der Aktivierung in Exchange Online auf dieselbe Weise mit Skype for Business Online synchronisiert werden:
  
1. Erstellen Sie eine Remote-PowerShell-Sitzung. Beachten Sie, dass Sie Skype for Business Online Connector-Modul und Microsoft Online Services-Anmeldeassistent herunterladen und sicherstellen müssen, dass Ihr Computer konfiguriert ist. Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Führen Sie den folgenden Befehl aus, um ein Skype Room System-Konto für Skype for Business zu aktivieren:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Sie können die RegistrarPool-Adresse abrufen, in der Ihre Skype for Business Benutzer von einem Ihrer vorhandenen Konten verwaltet werden, indem Sie den folgenden Befehl zum Zurückgeben dieser Eigenschaft verwenden:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Die mehrstufige Authentifizierung (MFA) wird für Skype Room System-Konten nicht unterstützt. 

## <a name="password-expiration"></a>Kennwortablauf

In Office 365 ist die standardmäßige Kennwortablaufrichtlinie für alle Ihre Benutzerkonten 90 Tage, es sei denn, Sie konfigurieren eine andere Kennwortablaufrichtlinie. Für Skype Room System-Konten können Sie die Einstellung Kennwort läuft nie ab mit den folgenden Schritten auswählen.
  
1. Erstellen Sie eine Windows Azure Active Directory-Sitzung mithilfe der Anmeldeinformationen für den globalen mandantenadministrator.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Legen Sie die Einstellung Kennwort läuft nie ab für das zuvor mit dem folgenden Befehl erstellte Skype Room-System Raum Konto fest:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validieren

Zur Überprüfung sollten Sie einen beliebigen Skype for Business-Client verwenden können, um sich bei dem von Ihnen erstellten Konto anzumelden.

