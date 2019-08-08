---
title: Bereitstellung von Skype Room System-Konten in Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System-Konten in Office 365 bereitgestellt werden.
ms.openlocfilehash: 5df77e9a9e5e3ca67eb831596c12516457a15c45
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235065"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Bereitstellung von Skype Room System-Konten in Office 365
 
Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System-Konten in Office 365 bereitgestellt werden.
  
Im folgenden Abschnitt wird die Bereitstellung des Skype Room-System Kontos für einen Office 365-Mandanten behandelt.
  
## <a name="office-365-prerequisites"></a>Office 365-Softwarekomponenten

Ihr Onlinemandant muss die folgenden Anforderungen erfüllen:
  
- Der Office 365-Plan muss Skype for Business Online Plan 2 oder Office 365 E1, E3 oder E5 umfassen. <br/>Einzelheiten zu den Skype for Business Online-Plänen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx).
    
- Ihr Mandant muss die Konferenzfunktion von Skype for Business aktiviert haben.
    
- Für Ihren Mandanten muss Exchange Online aktiviert sein. 
    
- Ihr Remote-Mandantenadministrator muss über folgenden PowerShell-Zugriff verfügen:
    
  - Exchange – Remote-PowerShell-Zugriff
    
  - Skype for Business Online-Remote-PowerShell-Zugriff
    
  - Windows Azure Active Directory-Modul für Windows PowerShell für den Zugriff auf den Office 365-Verzeichniszugriff
    
Für das Skype Room-Konto ist folgende Lizenzierung erforderlich:
  
- Eine Skype for Business Online Plan 2-oder Office 365 E1-oder E3-Lizenz ist erforderlich, um Skype-Besprechungen zu ermöglichen.
    
- Wenn Sie den Raum mit der Enterprise-VoIP-Funktion berechtigen möchten, damit der Raum mit einer Telefonnummer aktiviert werden kann, ist ein Skype for Business Online-Plan 2 mit der Telefon System Lizenz oder Office 365 E5 erforderlich (1).
    
- Wenn Sie in einer Besprechung Einwahl Funktionen benötigen, benötigen Sie eine Audiokonferenz-und Telefon System Lizenz.  Wenn Sie aus einer Besprechung heraus Wählfunktionen benötigen, benötigen Sie einen Inlands-, Inlands-und Auslandsanruf Plan. 
    
- Eine Exchange Online-Lizenz ist für das Skype Room-Konto nicht erforderlich, weil das Konto als Ressourcenpostfachkonto konfiguriert sein sollte.
    
## <a name="provisioning-overview"></a>Überblick über die Bereitstellung

Das folgende Diagramm bietet eine Übersicht über den Bereitstellungs Fluss des Skype Room System-Kontos in Office 365.
  
![Skype Room System – Schritte zur Bereitstellung für O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Erkennung eines neuen Konferenzraums

Möglicherweise verfügen Sie bereits über ein Ressourcen Raumpostfach in Exchange, das das Planungsfeature bereitstellt, oder Sie erstellen zum ersten Mal ein Ressourcenpostfach, um die Bereitstellung von Skype-Systemen zu vereinfachen. In jedem Fall müssen Sie ein Raum Konto angeben, das in Ihrem Mandanten verwendet werden soll. Die Abschnitte Exchange Online Provision und Skype for Business bieten Anleitungen für beide Arten von Konten. Angenommen, Sie haben die folgenden zwei Räume, und Sie möchten das Skype Room-System für beide bereitstellen:
  
- Vorhandenes Ressourcenpostfachkonto: confrm1@contoso.onmicrosoft.com
    
- Neues Ressourcenpostfachkonto: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange-Onlinebereitstellung

Stellen Sie zunächst eine Verbindung mit Exchange Online PowerShell her, indem Sie die Anweisungen im Thema [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)befolgen.
  
Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein vorhandenes Ressourcen Raum-Postfachkonto für das Skype Room-System einzurichten:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein neues Exchange-Ressourcen Postfachkonto für Skype Room System zu erstellen:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Mit den vorherigen Befehlen können Sie ein neues Exchange-Ressourcen Postfachkonto für die Nutzung des Skype Room-Systems einrichten oder erstellen, indem Sie das Konto aktivieren.
  
Nach dem Erstellen des Postfachs können Sie das Cmdlet "Satz-CalendarProcessing" in Exchange Online PowerShell verwenden, um das Postfach zu konfigurieren. Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.

## <a name="assigning-a-skype-for-business-online-license"></a>Zuweisen einer Skype for Business Online-Lizenz

Sie können jetzt eine Lizenz für Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3) mithilfe des Office 365-Verwaltungsportals zuweisen, wie unter [zuweisen oder Entfernen von Lizenzen für Office 365 for Business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in [Skype for Business-Add-on beschrieben Lizenzierung](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Nachdem Sie eine Lizenz für Skype for Business Online zugewiesen haben, können Sie sich anmelden und überprüfen, ob das Konto mit einem Skype for Business-Client aktiv ist.
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online-Bereitstellung

Nachdem ein Ressourcen Raum-Postfachkonto wie zuvor angezeigt erstellt und aktiviert wurde und Sie das Konto für Skype for Business Online lizenziert haben, wird das Konto von der Exchange Online-Gesamtstruktur mit der Skype for Business Online-Gesamtstruktur synchronisiert, indem Sie die Windows Azure Active Directory-Gesamtstruktur. Die folgenden Schritte sind erforderlich, um das Skype Room-System Konto im Skype for Business Online-Pool bereitzustellen. Diese Schritte sind für ein vorhandenes Ressourcen Postfachkonto oder ein neu erstelltes Konto (confrm1 oder confrm2) identisch, da beide Konten nach der Aktivierung in Exchange Online auf die gleiche Weise mit Skype for Business Online synchronisiert werden:
  
1. Erstellen Sie eine PowerShell-Remotesitzung. Beachten Sie, dass Sie das Skype for Business Online Connector-Modul und den Microsoft Online Services-Anmelde-Assistenten herunterladen müssen, um sicherzustellen, dass Ihr Computer konfiguriert ist. Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Führen Sie den folgenden Befehl aus, um ein Skype Room-System Konto für Skype for Business zu aktivieren:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Sie können die RegistrarPool-Adresse abrufen, in der Ihre Skype for Business-Benutzer von einem Ihrer vorhandenen Konten verwaltet werden, indem Sie den folgenden Befehl zum Zurückgeben dieser Eigenschaft verwenden:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Kennwortablauf

In Office 365 sieht die Standardrichtlinie für den Ablauf von Kennwörtern für alle Ihre Benutzerkonten eine Laufzeit von 90 Tagen vor, es sei denn, Sie konfigurieren einer andere Richtlinie für den Ablauf von Kennwörtern. Bei Skype Room-System Konten können Sie die Einstellung Kennwort läuft nie ab mit den folgenden Schritten auswählen.
  
1. Erstellen Sie eine Windows Azure Active Directory-Sitzung, indem Sie Ihre Mandantenanmeldedaten als globaler Administrator verwenden.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Legen Sie die Einstellung "Kennwort läuft nie ab" für das zuvor mit dem folgenden Befehl erstellte Skype Room-System Raum Konto fest:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei dem von Ihnen erstellten Konto anzumeldet.

