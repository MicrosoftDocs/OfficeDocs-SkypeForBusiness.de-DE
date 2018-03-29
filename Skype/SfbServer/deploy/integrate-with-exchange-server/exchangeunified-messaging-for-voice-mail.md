---
title: Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Zusammenfassung: Konfigurieren Sie Exchange Server Unified Messaging für Skype für Voicemail Business Server.'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="34862-103">Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34862-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="34862-104">**Zusammenfassung:** Konfigurieren von Exchange Server Unified Messaging für Skype für Voicemail Business Server.</span><span class="sxs-lookup"><span data-stu-id="34862-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="34862-105">Skype für Business Server 2015 können Sie Voicemail-Nachrichten in Exchange Server 2016 oder Exchange Server 2013 gespeichert haben. Diese Voicemailnachrichten werden dann als e-Mail-Nachrichten in die Posteingänge der Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34862-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="34862-106">Wenn Sie die Server-zu-Server-Authentifizierung zwischen Skype für Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 bereits konfiguriert haben, sind Sie bereit, So richten Sie unified messaging.</span><span class="sxs-lookup"><span data-stu-id="34862-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="34862-107">Hierzu müssen Sie zuerst erstellen und zuweisen ein neuen Wählplans für unified messaging auf Ihrem Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="34862-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="34862-108">Diese beiden Befehle (von in der Exchange-Verwaltungsshell ausgeführt) konfigurieren beispielsweise einen neuen 3 Ziffer Wählplan für Exchange:</span><span class="sxs-lookup"><span data-stu-id="34862-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="34862-p102">Im ersten Befehl im Beispiel geben der Parameter „VoIPSecurity“ und der Parameterwert „Secured“ an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ „SipName“ gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert „1“ für „CountryOrRegionCode“ gibt an, dass der Wählplan für die USA gilt.</span><span class="sxs-lookup"><span data-stu-id="34862-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="34862-111">Im zweiten Befehl gibt der an den Parameter „ConfiguredInCountryOrRegionGroups“ übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="34862-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="34862-112">Der Wert des Parameters "Anywhere,\*,\*,\*" legt Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="34862-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="34862-113">Gruppenname („Anywhere“)</span><span class="sxs-lookup"><span data-stu-id="34862-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="34862-114">AllowedNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige Nummernzeichenfolge zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="34862-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="34862-115">DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige gewählte Nummer zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="34862-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="34862-116">TextComment (\*, ein Platzhalterzeichen, das angibt, dass alle Textbefehl zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="34862-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="34862-117">Die Erstellung eines neuen Wählplans sorgt zusätzlich für die Erstellung einer standardmäßigen Postfachrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="34862-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="34862-118">Nach dem Erstellen und Konfigurieren des neuen Wählplans müssen Sie das neue Wählplan an Ihre unified messaging-Server aus, und ändern Sie den Startmodus des betreffenden Servers hinzufügen. Insbesondere müssen Sie den Startmodus zu "Dual" festlegen.</span><span class="sxs-lookup"><span data-stu-id="34862-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="34862-119">Sie können diese beiden Aufgaben aus in der Exchange-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="34862-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="34862-120">Nach dem Konfigurieren der unified messaging-Servers sollten Sie als Nächstes ausführen das Cmdlet Enable-ExchangeCertificate, um sicherzustellen, dass Ihre Exchange-Zertifikat auf den unified messaging-Dienst angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="34862-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="34862-p105">Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="34862-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="34862-123">Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="34862-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="34862-124">Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="34862-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="34862-p106">Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:</span><span class="sxs-lookup"><span data-stu-id="34862-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="34862-127">Sie können Unified Messaging für einen Benutzer mit einem Befehl wie dem folgenden aktivieren:</span><span class="sxs-lookup"><span data-stu-id="34862-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="34862-p107">Im vorherigen Befehl steht der Parameter „Extensions“ für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.</span><span class="sxs-lookup"><span data-stu-id="34862-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="34862-130">Nach dem Aktivieren des Postfachs sollte der Benutzer „kenmyer@litwareinc.com“ Exchange Unified Messaging verwenden können.</span><span class="sxs-lookup"><span data-stu-id="34862-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="34862-131">Sie können überprüfen, ob der Benutzer mit Exchange UM verbinden kann, indem das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) von innerhalb der Skype für Business Server-Verwaltungsshell ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="34862-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="34862-132">Wenn Sie einen zweiten Benutzer verfügen, die für unified messaging aktiviert wurde können Sie das Cmdlet " [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) " verwenden, um sicherzustellen, dass der zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.</span><span class="sxs-lookup"><span data-stu-id="34862-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


