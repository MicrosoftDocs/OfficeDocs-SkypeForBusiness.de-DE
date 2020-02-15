---
title: Einrichten von Skype Room System-Konten in Office 365
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
description: Lesen Sie dieses Thema, um mehr über die Einrichtung von Skype Room System-Konten in Office 365 zu erfahren.
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037725"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="86d7b-103">Einrichten von Skype Room System-Konten in Office 365</span><span class="sxs-lookup"><span data-stu-id="86d7b-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="86d7b-104">Lesen Sie dieses Thema, um mehr über die Einrichtung von Skype Room System-Konten in Office 365 zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="86d7b-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="86d7b-105">Im folgenden Abschnitt wird die Kontoverwaltung für Skype Room System für einen Office 365 Mandanten behandelt.</span><span class="sxs-lookup"><span data-stu-id="86d7b-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="86d7b-106">Voraussetzungen für Office 365</span><span class="sxs-lookup"><span data-stu-id="86d7b-106">Office 365 prerequisites</span></span>

<span data-ttu-id="86d7b-107">Ihr Online-Mandant muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="86d7b-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="86d7b-108">Der Office 365 Plan muss Skype for Business Online Plan 2 oder Office 365 E1, E3 oder E5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="86d7b-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="86d7b-109">Ausführliche Informationen zu Skype for Business Online Plänen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="86d7b-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="86d7b-110">Ihr Mandant muss die Konferenzfunktion von Skype for Business aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="86d7b-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="86d7b-111">Ihr Mandant muss Exchange Online aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="86d7b-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="86d7b-112">Der Remote Administrator des Mandanten muss über den folgenden PowerShell-Zugriff verfügen:</span><span class="sxs-lookup"><span data-stu-id="86d7b-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="86d7b-113">Exchange-Remote-PowerShell-Zugriff</span><span class="sxs-lookup"><span data-stu-id="86d7b-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="86d7b-114">Skype for Business Online Remote-PowerShell-Zugriff</span><span class="sxs-lookup"><span data-stu-id="86d7b-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="86d7b-115">Windows Azure Active Directory-Modul für Windows PowerShell für den Zugriff auf Office 365 Verzeichniszugriff</span><span class="sxs-lookup"><span data-stu-id="86d7b-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="86d7b-116">Für das Skype Room-Konto ist die folgende Lizenzierung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="86d7b-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="86d7b-117">Zum Aktivieren von Skype-Besprechungen ist eine Skype for Business Online Plan 2-oder Office 365 E1-oder E3-Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86d7b-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="86d7b-118">Um den Raum mit der Enterprise-VoIP-Funktion zu berechtigen, damit der Raum mit einer Telefonnummer aktiviert werden kann, ist ein Skype for Business Online Plan 2 mit der Telefon System Lizenz oder Office 365 E5 erforderlich (1).</span><span class="sxs-lookup"><span data-stu-id="86d7b-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="86d7b-119">Wenn Sie Einwahl Funktionen aus einer Besprechung benötigen, benötigen Sie eine Audio-Konferenz-und Telefon System Lizenz.</span><span class="sxs-lookup"><span data-stu-id="86d7b-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="86d7b-120">Wenn Sie Auswähl Funktionen aus einer Besprechung benötigen, benötigen Sie einen Plan für Inlands-oder Inlandsanrufe und internationale Anrufe.</span><span class="sxs-lookup"><span data-stu-id="86d7b-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="86d7b-121">Eine Exchange Online Lizenz ist für das Skype Room-Konto nicht erforderlich, da das Konto als Ressourcen Postfachkonto konfiguriert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="86d7b-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="86d7b-122">Übersicht über die Überstellung</span><span class="sxs-lookup"><span data-stu-id="86d7b-122">Provisioning overview</span></span>

<span data-ttu-id="86d7b-123">Das folgende Diagramm bietet eine Übersicht über den Ablauf der Bereitstellung von Skype Room System-Konten in Office 365.</span><span class="sxs-lookup"><span data-stu-id="86d7b-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Schritte zur Vorgehensweise für das Skype Room-System für O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="86d7b-125">Identifizieren eines neuen Konferenzraums</span><span class="sxs-lookup"><span data-stu-id="86d7b-125">Identify a new conference room</span></span>

<span data-ttu-id="86d7b-126">Möglicherweise verfügen Sie bereits über ein Ressourcen Raumpostfach in Exchange, das das Planungsfeature bereitstellt, oder Sie erstellen zum ersten Mal ein Ressourcenpostfach, um die Bereitstellung von Skype Room System zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="86d7b-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="86d7b-127">In jedem Fall müssen Sie ein Raum Konto angeben, das in Ihrem Mandanten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86d7b-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="86d7b-128">Die Abschnitte Exchange Online Bereitstellungs-und Skype for Business Bereitstellung bieten Anleitungen für beide Arten von Konten.</span><span class="sxs-lookup"><span data-stu-id="86d7b-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="86d7b-129">Angenommen, Sie verfügen über die folgenden zwei Räume, und Sie möchten Skype Room System für beide bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="86d7b-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="86d7b-130">Vorhandenes Ressourcen Postfachkonto: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="86d7b-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="86d7b-131">Neues Ressourcen Postfachkonto: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="86d7b-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="86d7b-132">Exchange Online-Provision</span><span class="sxs-lookup"><span data-stu-id="86d7b-132">Exchange Online provisioning</span></span>

<span data-ttu-id="86d7b-133">Stellen Sie zunächst eine Verbindung mit Exchange Online PowerShell her, indem Sie die Anweisungen im Thema [Verbinden mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)befolgen.</span><span class="sxs-lookup"><span data-stu-id="86d7b-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="86d7b-134">Um ein vorhandenes Ressourcen Raum-Postfachkonto für Skype Room System festzulegen, führen Sie die folgenden Befehle in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="86d7b-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="86d7b-135">Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein neues Exchange-Ressourcen Postfachkonto für Skype Room System zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="86d7b-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="86d7b-136">In den vorherigen Befehlen wurde ein neues Exchange-Ressourcen Postfachkonto für die Nutzung des Skype Room-Systems durch Aktivieren des Kontos eingerichtet oder erstellt.</span><span class="sxs-lookup"><span data-stu-id="86d7b-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="86d7b-137">Nachdem Sie das Postfach erstellt haben, können Sie das Cmdlet "CalendarProcessing" in Exchange Online PowerShell verwenden, um das Postfach zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86d7b-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="86d7b-138">Weitere Informationen finden Sie in den Schritten 3 bis 6 unter "lokale Bereitstellungen mit einzelner Gesamtstruktur".</span><span class="sxs-lookup"><span data-stu-id="86d7b-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="86d7b-139">Zuweisen einer Skype for Business Online Lizenz</span><span class="sxs-lookup"><span data-stu-id="86d7b-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="86d7b-140">Jetzt können Sie eine Skype for Business Online (Plan 2)-oder Skype for Business Online (Plan 3)-Lizenz mithilfe des Office 365-Verwaltungsportals zuweisen, wie unter [zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in [Skype for Business Add-on-Lizenzierung](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86d7b-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="86d7b-141">Nachdem Sie eine Lizenz für Skype for Business Online zugewiesen haben, können Sie sich anmelden und überprüfen, ob das Konto mit einem Skype for Business-Client aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="86d7b-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="86d7b-142">Skype for Business Online-Provision</span><span class="sxs-lookup"><span data-stu-id="86d7b-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="86d7b-143">Nachdem ein Ressourcen Raum-Postfachkonto erstellt und wie zuvor gezeigt aktiviert wurde und Sie das Konto für Skype for Business Online lizensiert haben, wird das Konto über die Exchange Online-Gesamtstruktur mit Skype for Business Online Gesamtstruktur synchronisiert. Windows Azure Active Directory Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="86d7b-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="86d7b-144">Die folgenden Schritte sind erforderlich, um das Skype Room-System Konto im Skype for Business Online Pool zu stellen.</span><span class="sxs-lookup"><span data-stu-id="86d7b-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="86d7b-145">Diese Schritte sind für ein vorhandenes Ressourcen Postfachkonto oder ein neu erstelltes Konto identisch (confrm1 oder confrm2), da beide Konten nach der Aktivierung in Exchange Online auf dieselbe Weise mit Skype for Business Online synchronisiert werden:</span><span class="sxs-lookup"><span data-stu-id="86d7b-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="86d7b-146">Erstellen Sie eine Remote-PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="86d7b-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="86d7b-147">Beachten Sie, dass Sie Skype for Business Online Connector-Modul und Microsoft Online Services-Anmeldeassistent herunterladen und sicherstellen müssen, dass Ihr Computer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="86d7b-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="86d7b-148">Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="86d7b-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="86d7b-149">Führen Sie den folgenden Befehl aus, um ein Skype Room System-Konto für Skype for Business zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="86d7b-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="86d7b-150">Sie können die RegistrarPool-Adresse abrufen, in der Ihre Skype for Business Benutzer von einem Ihrer vorhandenen Konten verwaltet werden, indem Sie den folgenden Befehl zum Zurückgeben dieser Eigenschaft verwenden:</span><span class="sxs-lookup"><span data-stu-id="86d7b-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="86d7b-151">Die mehrstufige Authentifizierung (MFA) wird für Skype Room System-Konten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="86d7b-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="86d7b-152">Kennwortablauf</span><span class="sxs-lookup"><span data-stu-id="86d7b-152">Password expiration</span></span>

<span data-ttu-id="86d7b-153">In Office 365 ist die standardmäßige Kennwortablaufrichtlinie für alle Ihre Benutzerkonten 90 Tage, es sei denn, Sie konfigurieren eine andere Kennwortablaufrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="86d7b-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="86d7b-154">Für Skype Room System-Konten können Sie die Einstellung Kennwort läuft nie ab mit den folgenden Schritten auswählen.</span><span class="sxs-lookup"><span data-stu-id="86d7b-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="86d7b-155">Erstellen Sie eine Windows Azure Active Directory-Sitzung mithilfe der Anmeldeinformationen für den globalen mandantenadministrator.</span><span class="sxs-lookup"><span data-stu-id="86d7b-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="86d7b-156">Legen Sie die Einstellung Kennwort läuft nie ab für das zuvor mit dem folgenden Befehl erstellte Skype Room-System Raum Konto fest:</span><span class="sxs-lookup"><span data-stu-id="86d7b-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="86d7b-157">Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="86d7b-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="86d7b-158">Validieren</span><span class="sxs-lookup"><span data-stu-id="86d7b-158">Validate</span></span>

<span data-ttu-id="86d7b-159">Zur Überprüfung sollten Sie einen beliebigen Skype for Business-Client verwenden können, um sich bei dem von Ihnen erstellten Konto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="86d7b-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

