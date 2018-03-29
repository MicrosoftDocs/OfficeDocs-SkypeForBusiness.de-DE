---
title: Bereitstellung von Skype Room System-Konten in Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System-Konten in Office 365 bereitgestellt werden.
ms.openlocfilehash: be90831eba5f16f5a3b41f4c74c26333bf728926
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="6b257-103">Bereitstellung von Skype Room System-Konten in Office 365</span><span class="sxs-lookup"><span data-stu-id="6b257-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="6b257-104">Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System-Konten in Office 365 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6b257-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="6b257-105">Der folgende Abschnitt behandelt Skype Raum Systemkonto Bereitstellung für Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6b257-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="6b257-106">Office 365-Softwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="6b257-106">Office 365 prerequisites</span></span>

<span data-ttu-id="6b257-107">Ihr Onlinemandant muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="6b257-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="6b257-108">Office 365-Plan muss Skype für Business Online – Plan 2, Plan 3 oder Office 365 E1, E3 oder E5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b257-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="6b257-109">Ihres Mandanten benötigen die Möglichkeit, Konferenzen Skype für Unternehmen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b257-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="6b257-110">Für Ihren Mandanten muss Exchange Online aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="6b257-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="6b257-111">Ihr Remote-Mandantenadministrator muss über folgenden PowerShell-Zugriff verfügen:</span><span class="sxs-lookup"><span data-stu-id="6b257-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="6b257-112">Exchange – Remote-PowerShell-Zugriff</span><span class="sxs-lookup"><span data-stu-id="6b257-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="6b257-113">Skype für Business Online Remote PowerShell access</span><span class="sxs-lookup"><span data-stu-id="6b257-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="6b257-114">Windows Azure Active Directory-Modul für Windows PowerShell Access Office 365 Directory Access</span><span class="sxs-lookup"><span data-stu-id="6b257-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="6b257-115">Für das Skype Room-Konto ist folgende Lizenzierung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6b257-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="6b257-116">Einen Skype für Business Online – Plan 2 oder Office 365 E1 oder E3 Lizenz ist erforderlich, um Skype Besprechungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6b257-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="6b257-117">Um den Chatroom mit dem Enterprise-VoIP-Funktion berechtigen, damit der Chatroom mit einer Telefonnummer aktiviert werden kann, ist eine Skype für Business Online – Plan 2 mit dem Cloud PBX Add-on oder Office 365 E5 erforderlich ist (1).</span><span class="sxs-lookup"><span data-stu-id="6b257-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="6b257-118">Die Verfügbarkeit der Ausstattung für Konferenzen über das Festnetz innerhalb beliebiger Besprechungen wird von der Lizenz des Besprechungsorganisators bestimmt.</span><span class="sxs-lookup"><span data-stu-id="6b257-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="6b257-119">Eine Exchange Online-Lizenz ist für das Skype Room-Konto nicht erforderlich, weil das Konto als Ressourcenpostfachkonto konfiguriert sein sollte.</span><span class="sxs-lookup"><span data-stu-id="6b257-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="6b257-120">Überblick über die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="6b257-120">Provisioning overview</span></span>

<span data-ttu-id="6b257-121">Die folgende Abbildung bietet eine Übersicht über das Skype Raum-Systemkonto-Flusses in Office 365-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6b257-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Skype Room System – Schritte zur Bereitstellung für O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="6b257-123">Erkennung eines neuen Konferenzraums</span><span class="sxs-lookup"><span data-stu-id="6b257-123">Identify a new conference room</span></span>

<span data-ttu-id="6b257-124">Möglicherweise haben Sie bereits ein Ressourcenpostfach Raum im Exchange, die das Feature scheduling bereitstellt, oder Sie erstellen ein Ressourcenpostfach zum ersten Mal auf Skype Raum System-Bereitstellung zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="6b257-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="6b257-125">In jedem Fall müssen Sie einen Raum in Ihrem Mandanten verwendet werden identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6b257-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="6b257-126">Die Exchange Online-Bereitstellung und Skype für Business Provision Abschnitte bieten einen Leitfaden für beide Arten von Konten.</span><span class="sxs-lookup"><span data-stu-id="6b257-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="6b257-127">Angenommen, beispielsweise stehen Ihnen die folgenden zwei Räume und Skype Raum System für beide bereitstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="6b257-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="6b257-128">Vorhandenes Ressourcenpostfachkonto: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6b257-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="6b257-129">Neues Ressourcenpostfachkonto: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6b257-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="6b257-130">Exchange-Onlinebereitstellung</span><span class="sxs-lookup"><span data-stu-id="6b257-130">Exchange Online provisioning</span></span>

<span data-ttu-id="6b257-131">Zunächst, eine Verbindung mit Exchange Online PowerShell gemäß die Anweisungen im Thema [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="6b257-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="6b257-132">Wenn ein vorhandenes Postfachkonto für die Ressource Raum für Skype Raum System festlegen möchten, führen Sie die folgenden Befehle in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6b257-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="6b257-133">Führen Sie die folgenden Befehle in Exchange Online PowerShell, um ein neues Exchange-Postfach Ressourcenkonto für Skype Raum System zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6b257-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="6b257-134">Die oben angegebenen Befehle einrichten oder erstellen ein neues Exchange-Postfach Ressourcenkonto für Skype Raum Systemverwendung werden, da das Konto.</span><span class="sxs-lookup"><span data-stu-id="6b257-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="6b257-135">Das Cmdlet Set-CalendarProcessing in Exchange Online PowerShell können Sie nach dem Erstellen des Postfachs an, um das Postfach zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6b257-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="6b257-136">Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.</span><span class="sxs-lookup"><span data-stu-id="6b257-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="6b257-137">Skype for Business Online-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="6b257-137">Skype for Business Online provisioning</span></span>

<span data-ttu-id="6b257-138">Nachdem ein Ressource Postfach Raum erstellt und aktiviert, wie zuvor gezeigt wurde, wird das Konto aus der Gesamtstruktur Exchange Online mit Skype für Business Online Gesamtstruktur synchronisiert werden mithilfe von Windows Azure Active Directory-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="6b257-138">After a resource room mailbox account has been created and enabled as shown previously, the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="6b257-139">Die folgenden Schritte sind erforderlich, das Systemkonto von Skype Raum in der Skype für Business Online Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6b257-139">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="6b257-140">Diese Schritte sind identisch für ein vorhandenes Postfach Ressourcenkonto oder eines neu erstellten Kontos (confrm1 oder confrm2), da Nachdem sie im Exchange Online aktiviert sind, beide Konten zu Skype für Business Online auf die gleiche Weise synchronisiert werden soll:</span><span class="sxs-lookup"><span data-stu-id="6b257-140">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="6b257-141">Erstellen Sie eine PowerShell-Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="6b257-141">Create a Remote PowerShell session.</span></span> <span data-ttu-id="6b257-142">Beachten Sie, dass Sie benötigen Skype für Business Online Connectormodul und Microsoft Online Services-Anmeldeassistent herunterladen, und stellen Sie sicher, dass Ihr Computer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6b257-142">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="6b257-143">Weitere Informationen finden Sie unter [Konfigurieren von Your Computer für Lync Online-Verwaltung](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span><span class="sxs-lookup"><span data-stu-id="6b257-143">For more information, see [Configuring Your Computer for Lync Online Management](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="6b257-144">Um ein Systemkonto von Skype Raum für Skype für Unternehmen zu aktivieren, führen Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="6b257-144">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="6b257-145">Sie können die RegistrarPool Adresse, wo Ihre Skype für Unternehmensbenutzer mit den folgenden Befehl aus, um von einem Ihrer vorhandenen Konten verwaltet werden, gibt diese Eigenschaft erhalten:</span><span class="sxs-lookup"><span data-stu-id="6b257-145">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="6b257-146">Zuweisen einer Skype for Business Online-Lizenz</span><span class="sxs-lookup"><span data-stu-id="6b257-146">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="6b257-147">Nachdem Sie ein Systemkonto von Skype Raum in Skype für Unternehmen aktiviert haben, können Sie einen Skype für Business Online (Plan 2) zuweisen oder Skype für Business Online (Plan 3)-Lizenz mithilfe von administrativen Office 365-Portal, wie beschrieben in [zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) oder in [Skype für Business Add-On-Lizenzierung](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="6b257-147">After you enable a Skype Room System account in Skype for Business, you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="6b257-148">Nachdem Sie eine Lizenz für Skype für Business Online zuweisen, werden Sie können sich anmelden, und überprüfen, dass das Konto verwenden Skype für Business Client aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="6b257-148">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="password-expiration"></a><span data-ttu-id="6b257-149">Kennwortablauf</span><span class="sxs-lookup"><span data-stu-id="6b257-149">Password expiration</span></span>

<span data-ttu-id="6b257-150">In Office 365 sieht die Standardrichtlinie für den Ablauf von Kennwörtern für alle Ihre Benutzerkonten eine Laufzeit von 90 Tagen vor, es sei denn, Sie konfigurieren einer andere Richtlinie für den Ablauf von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="6b257-150">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="6b257-151">Wählen Sie für Skype Raum Systemkonten, das Kennwort läuft nie ab Einstellung die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="6b257-151">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="6b257-152">Erstellen Sie eine Windows Azure Active Directory-Sitzung, indem Sie Ihre Mandantenanmeldedaten als globaler Administrator verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b257-152">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="6b257-153">Set das Kennwort läuft nie ab Einstellung für das Skype Raum Raum Systemkonto zuvor erstellten mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="6b257-153">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="6b257-154">Weitere Informationen finden Sie unter [Using Windows PowerShell zum Verwalten von Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="6b257-154">For more information, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  

