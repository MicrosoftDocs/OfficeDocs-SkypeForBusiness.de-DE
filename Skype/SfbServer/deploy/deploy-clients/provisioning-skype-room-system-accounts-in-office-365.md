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
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="f6380-103">Bereitstellung von Skype Room System-Konten in Office 365</span><span class="sxs-lookup"><span data-stu-id="f6380-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="f6380-104">Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System-Konten in Office 365 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6380-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="f6380-105">Im folgenden Abschnitt wird die Bereitstellung des Skype Room-System Kontos für einen Office 365-Mandanten behandelt.</span><span class="sxs-lookup"><span data-stu-id="f6380-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="f6380-106">Office 365-Softwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="f6380-106">Office 365 prerequisites</span></span>

<span data-ttu-id="f6380-107">Ihr Onlinemandant muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="f6380-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="f6380-108">Der Office 365-Plan muss Skype for Business Online Plan 2 oder Office 365 E1, E3 oder E5 umfassen.</span><span class="sxs-lookup"><span data-stu-id="f6380-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="f6380-109">Einzelheiten zu den Skype for Business Online-Plänen finden Sie in der [Skype for Business Online-Dienstbeschreibung](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6380-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="f6380-110">Ihr Mandant muss die Konferenzfunktion von Skype for Business aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="f6380-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="f6380-111">Für Ihren Mandanten muss Exchange Online aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="f6380-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="f6380-112">Ihr Remote-Mandantenadministrator muss über folgenden PowerShell-Zugriff verfügen:</span><span class="sxs-lookup"><span data-stu-id="f6380-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="f6380-113">Exchange – Remote-PowerShell-Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6380-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="f6380-114">Skype for Business Online-Remote-PowerShell-Zugriff</span><span class="sxs-lookup"><span data-stu-id="f6380-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="f6380-115">Windows Azure Active Directory-Modul für Windows PowerShell für den Zugriff auf den Office 365-Verzeichniszugriff</span><span class="sxs-lookup"><span data-stu-id="f6380-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="f6380-116">Für das Skype Room-Konto ist folgende Lizenzierung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f6380-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="f6380-117">Eine Skype for Business Online Plan 2-oder Office 365 E1-oder E3-Lizenz ist erforderlich, um Skype-Besprechungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f6380-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="f6380-118">Wenn Sie den Raum mit der Enterprise-VoIP-Funktion berechtigen möchten, damit der Raum mit einer Telefonnummer aktiviert werden kann, ist ein Skype for Business Online-Plan 2 mit der Telefon System Lizenz oder Office 365 E5 erforderlich (1).</span><span class="sxs-lookup"><span data-stu-id="f6380-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="f6380-119">Wenn Sie in einer Besprechung Einwahl Funktionen benötigen, benötigen Sie eine Audiokonferenz-und Telefon System Lizenz.</span><span class="sxs-lookup"><span data-stu-id="f6380-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="f6380-120">Wenn Sie aus einer Besprechung heraus Wählfunktionen benötigen, benötigen Sie einen Inlands-, Inlands-und Auslandsanruf Plan.</span><span class="sxs-lookup"><span data-stu-id="f6380-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="f6380-121">Eine Exchange Online-Lizenz ist für das Skype Room-Konto nicht erforderlich, weil das Konto als Ressourcenpostfachkonto konfiguriert sein sollte.</span><span class="sxs-lookup"><span data-stu-id="f6380-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="f6380-122">Überblick über die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f6380-122">Provisioning overview</span></span>

<span data-ttu-id="f6380-123">Das folgende Diagramm bietet eine Übersicht über den Bereitstellungs Fluss des Skype Room System-Kontos in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6380-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Skype Room System – Schritte zur Bereitstellung für O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="f6380-125">Erkennung eines neuen Konferenzraums</span><span class="sxs-lookup"><span data-stu-id="f6380-125">Identify a new conference room</span></span>

<span data-ttu-id="f6380-126">Möglicherweise verfügen Sie bereits über ein Ressourcen Raumpostfach in Exchange, das das Planungsfeature bereitstellt, oder Sie erstellen zum ersten Mal ein Ressourcenpostfach, um die Bereitstellung von Skype-Systemen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f6380-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="f6380-127">In jedem Fall müssen Sie ein Raum Konto angeben, das in Ihrem Mandanten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f6380-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="f6380-128">Die Abschnitte Exchange Online Provision und Skype for Business bieten Anleitungen für beide Arten von Konten.</span><span class="sxs-lookup"><span data-stu-id="f6380-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="f6380-129">Angenommen, Sie haben die folgenden zwei Räume, und Sie möchten das Skype Room-System für beide bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="f6380-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="f6380-130">Vorhandenes Ressourcenpostfachkonto: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="f6380-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="f6380-131">Neues Ressourcenpostfachkonto: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="f6380-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="f6380-132">Exchange-Onlinebereitstellung</span><span class="sxs-lookup"><span data-stu-id="f6380-132">Exchange Online provisioning</span></span>

<span data-ttu-id="f6380-133">Stellen Sie zunächst eine Verbindung mit Exchange Online PowerShell her, indem Sie die Anweisungen im Thema [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)befolgen.</span><span class="sxs-lookup"><span data-stu-id="f6380-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="f6380-134">Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein vorhandenes Ressourcen Raum-Postfachkonto für das Skype Room-System einzurichten:</span><span class="sxs-lookup"><span data-stu-id="f6380-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="f6380-135">Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um ein neues Exchange-Ressourcen Postfachkonto für Skype Room System zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f6380-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="f6380-136">Mit den vorherigen Befehlen können Sie ein neues Exchange-Ressourcen Postfachkonto für die Nutzung des Skype Room-Systems einrichten oder erstellen, indem Sie das Konto aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f6380-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="f6380-137">Nach dem Erstellen des Postfachs können Sie das Cmdlet "Satz-CalendarProcessing" in Exchange Online PowerShell verwenden, um das Postfach zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f6380-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="f6380-138">Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.</span><span class="sxs-lookup"><span data-stu-id="f6380-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="f6380-139">Zuweisen einer Skype for Business Online-Lizenz</span><span class="sxs-lookup"><span data-stu-id="f6380-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="f6380-140">Sie können jetzt eine Lizenz für Skype for Business Online (Plan 2) oder Skype for Business Online (Plan 3) mithilfe des Office 365-Verwaltungsportals zuweisen, wie unter [zuweisen oder Entfernen von Lizenzen für Office 365 for Business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in [Skype for Business-Add-on beschrieben Lizenzierung](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="f6380-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="f6380-141">Nachdem Sie eine Lizenz für Skype for Business Online zugewiesen haben, können Sie sich anmelden und überprüfen, ob das Konto mit einem Skype for Business-Client aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="f6380-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="f6380-142">Skype for Business Online-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f6380-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="f6380-143">Nachdem ein Ressourcen Raum-Postfachkonto wie zuvor angezeigt erstellt und aktiviert wurde und Sie das Konto für Skype for Business Online lizenziert haben, wird das Konto von der Exchange Online-Gesamtstruktur mit der Skype for Business Online-Gesamtstruktur synchronisiert, indem Sie die Windows Azure Active Directory-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="f6380-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="f6380-144">Die folgenden Schritte sind erforderlich, um das Skype Room-System Konto im Skype for Business Online-Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6380-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="f6380-145">Diese Schritte sind für ein vorhandenes Ressourcen Postfachkonto oder ein neu erstelltes Konto (confrm1 oder confrm2) identisch, da beide Konten nach der Aktivierung in Exchange Online auf die gleiche Weise mit Skype for Business Online synchronisiert werden:</span><span class="sxs-lookup"><span data-stu-id="f6380-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="f6380-146">Erstellen Sie eine PowerShell-Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="f6380-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="f6380-147">Beachten Sie, dass Sie das Skype for Business Online Connector-Modul und den Microsoft Online Services-Anmelde-Assistenten herunterladen müssen, um sicherzustellen, dass Ihr Computer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f6380-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="f6380-148">Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6380-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="f6380-149">Führen Sie den folgenden Befehl aus, um ein Skype Room-System Konto für Skype for Business zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6380-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="f6380-150">Sie können die RegistrarPool-Adresse abrufen, in der Ihre Skype for Business-Benutzer von einem Ihrer vorhandenen Konten verwaltet werden, indem Sie den folgenden Befehl zum Zurückgeben dieser Eigenschaft verwenden:</span><span class="sxs-lookup"><span data-stu-id="f6380-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="f6380-151">Kennwortablauf</span><span class="sxs-lookup"><span data-stu-id="f6380-151">Password expiration</span></span>

<span data-ttu-id="f6380-152">In Office 365 sieht die Standardrichtlinie für den Ablauf von Kennwörtern für alle Ihre Benutzerkonten eine Laufzeit von 90 Tagen vor, es sei denn, Sie konfigurieren einer andere Richtlinie für den Ablauf von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="f6380-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="f6380-153">Bei Skype Room-System Konten können Sie die Einstellung Kennwort läuft nie ab mit den folgenden Schritten auswählen.</span><span class="sxs-lookup"><span data-stu-id="f6380-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="f6380-154">Erstellen Sie eine Windows Azure Active Directory-Sitzung, indem Sie Ihre Mandantenanmeldedaten als globaler Administrator verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6380-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="f6380-155">Legen Sie die Einstellung "Kennwort läuft nie ab" für das zuvor mit dem folgenden Befehl erstellte Skype Room-System Raum Konto fest:</span><span class="sxs-lookup"><span data-stu-id="f6380-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="f6380-156">Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6380-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="f6380-157">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="f6380-157">Validate</span></span>

<span data-ttu-id="f6380-158">Zur Überprüfung sollten Sie in der Lage sein, sich mit einem Skype for Business-Client bei dem von Ihnen erstellten Konto anzumeldet.</span><span class="sxs-lookup"><span data-stu-id="f6380-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

