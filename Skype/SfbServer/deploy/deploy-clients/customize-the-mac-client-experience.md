---
title: Anpassen der Mac-Clienterfahrung in Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: Dieser Artikel beschreibt die für den Skype for Business für Mac-Client verfügbaren Clienteinstellungen und Standardwerte sowie deren Bearbeitung außerhalb der App.
ms.openlocfilehash: ae7f3a5c63a77820aba24e93d820ae2eff9176ad
ms.sourcegitcommit: 25066ab000f7615aff31f77d9d39c266c65e2aa5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2018
ms.locfileid: "22912843"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="f3140-103">Anpassen der Mac-Clienterfahrung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3140-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="f3140-104">Dieser Artikel beschreibt die für den Skype for Business für Mac-Client verfügbaren Clienteinstellungen und Standardwerte sowie deren Bearbeitung außerhalb der App.</span><span class="sxs-lookup"><span data-stu-id="f3140-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="f3140-105">Einstellungen für Skype for Business für Mac-Client</span><span class="sxs-lookup"><span data-stu-id="f3140-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="f3140-106">Bestimmte Features und Verhaltensweisen, die Skype für Unternehmen auf Mac-Clients zur Verfügung stehen, werden über Voreinstellungen auf dem Client festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f3140-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="f3140-107">Die Skype für Mac Vorlieben Unternehmen befinden sich in einer Datei auf Macs, der die Skype für befindet sich unter folgendem Pfad Business-Client installiert ist:</span><span class="sxs-lookup"><span data-stu-id="f3140-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="f3140-108">**~/Library/Containers/com.Microsoft.SkypeForBusiness/Data/Library/Preferences/com.Microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="f3140-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="f3140-109">Wenn diese Einstellungen festlegen möchten, erhalten Sie auf einer terminal ein auf dem Client-Mac und als benötigt, geben Sie Standardeinstellungen Write com.microsoft.SkypeForBusiness wichtige Befehle mithilfe der Einstellungsschlüssel in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f3140-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="f3140-110">**Client-Einstellungsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="f3140-110">**Client preference keys**</span></span>


| <span data-ttu-id="f3140-111">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f3140-111">Key</span></span> | <span data-ttu-id="f3140-112">Typ</span><span class="sxs-lookup"><span data-stu-id="f3140-112">Type</span></span> | <span data-ttu-id="f3140-113">Wert</span><span class="sxs-lookup"><span data-stu-id="f3140-113">Value</span></span> | <span data-ttu-id="f3140-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3140-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3140-115">AutoDetectAutoDiscoveryURLs</span><span class="sxs-lookup"><span data-stu-id="f3140-115">AutoDetectAutoDiscoveryURLs</span></span>    |<span data-ttu-id="f3140-116">Bool</span><span class="sxs-lookup"><span data-stu-id="f3140-116">Bool</span></span>    |<span data-ttu-id="f3140-117">0 = manuelle Serverkonfiguration</span><span class="sxs-lookup"><span data-stu-id="f3140-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="f3140-118">1 = automatische Servererkennung (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="f3140-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="f3140-119">Geben Sie an, wie Skype für Unternehmen Transportprotokoll und Server, die während der Anmeldung verwendet identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f3140-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="f3140-120">Wenn Sie diese Richtlinieneinstellung aktivieren, müssen Sie **internalAutoDiscoveryURL** und **externalAutoDiscoveryURL** angeben.</span><span class="sxs-lookup"><span data-stu-id="f3140-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="f3140-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="f3140-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="f3140-122">String</span><span class="sxs-lookup"><span data-stu-id="f3140-122">String</span></span>    |<span data-ttu-id="f3140-123">Vollständige URL zur automatischen Erkennung</span><span class="sxs-lookup"><span data-stu-id="f3140-123">Full autodiscover URL</span></span>    |<span data-ttu-id="f3140-124">Interne URL zur automatischen Erkennung</span><span class="sxs-lookup"><span data-stu-id="f3140-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="f3140-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="f3140-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="f3140-126">String</span><span class="sxs-lookup"><span data-stu-id="f3140-126">String</span></span>    |<span data-ttu-id="f3140-127">Vollständige URL zur automatischen Erkennung</span><span class="sxs-lookup"><span data-stu-id="f3140-127">Full autodiscover URL</span></span>    |<span data-ttu-id="f3140-128">Externe URL zur automatischen Erkennung</span><span class="sxs-lookup"><span data-stu-id="f3140-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="f3140-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="f3140-129">httpProxyDomain</span></span>    |<span data-ttu-id="f3140-130">String</span><span class="sxs-lookup"><span data-stu-id="f3140-130">String</span></span>    ||<span data-ttu-id="f3140-131">HTTP-Proxy-Domäne</span><span class="sxs-lookup"><span data-stu-id="f3140-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="f3140-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="f3140-132">httpProxyUserName</span></span>    |<span data-ttu-id="f3140-133">String</span><span class="sxs-lookup"><span data-stu-id="f3140-133">String</span></span>    ||<span data-ttu-id="f3140-134">HTTP-Proxy-Benutzername</span><span class="sxs-lookup"><span data-stu-id="f3140-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="f3140-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="f3140-135">httpProxyPassword</span></span>    |<span data-ttu-id="f3140-136">String</span><span class="sxs-lookup"><span data-stu-id="f3140-136">String</span></span>    ||<span data-ttu-id="f3140-137">HTTP-Proxy-Kennwort</span><span class="sxs-lookup"><span data-stu-id="f3140-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="f3140-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="f3140-138">trustedDomainList</span></span>    |<span data-ttu-id="f3140-139">Array</span><span class="sxs-lookup"><span data-stu-id="f3140-139">Array</span></span>    ||<span data-ttu-id="f3140-140">Liste mit vertrauenswürdigen Domänen für HTTP-Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="f3140-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="f3140-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="f3140-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="f3140-142">Number</span><span class="sxs-lookup"><span data-stu-id="f3140-142">Number</span></span>    |<span data-ttu-id="f3140-143">300 (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="f3140-143">300 (default)</span></span>    |<span data-ttu-id="f3140-144">Automatisch akzeptiertes Timeout für Benutzer mit serverseitigem Konversationsverlauf.</span><span class="sxs-lookup"><span data-stu-id="f3140-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="f3140-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="f3140-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="f3140-146">Bool</span><span class="sxs-lookup"><span data-stu-id="f3140-146">Bool</span></span>    |<span data-ttu-id="f3140-147">0 = Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="f3140-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="f3140-148">1 = Aktiviert</span><span class="sxs-lookup"><span data-stu-id="f3140-148">1 = Enabled</span></span>    |<span data-ttu-id="f3140-149">Warnt den Benutzer beim Wählen einer Notrufnummer von einem unbekannten Standort aus.</span><span class="sxs-lookup"><span data-stu-id="f3140-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="f3140-150">"SipAddress"</span><span class="sxs-lookup"><span data-stu-id="f3140-150">sipAddress</span></span>    |<span data-ttu-id="f3140-151">String</span><span class="sxs-lookup"><span data-stu-id="f3140-151">String</span></span>    ||<span data-ttu-id="f3140-152">Die SIP-Adresse (e) verwendet, um Skype für Unternehmen anmelden.</span><span class="sxs-lookup"><span data-stu-id="f3140-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="f3140-153">Benutzername</span><span class="sxs-lookup"><span data-stu-id="f3140-153">userName</span></span>    |<span data-ttu-id="f3140-154">String</span><span class="sxs-lookup"><span data-stu-id="f3140-154">String</span></span>    ||<span data-ttu-id="f3140-155">Der UPN (UserName) verwendet, um Skype für Unternehmen anmelden.</span><span class="sxs-lookup"><span data-stu-id="f3140-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="f3140-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="f3140-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="f3140-157">Bool</span><span class="sxs-lookup"><span data-stu-id="f3140-157">Bool</span></span>    |<span data-ttu-id="f3140-158">0 = das Feld Benutzername auf das Hauptfenster im Anmeldebildschirm und im Dialogfeld Erweiterte Eigenschaften anzeigen</span><span class="sxs-lookup"><span data-stu-id="f3140-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="f3140-159">1 = zeigt das Feld Benutzername nur in das Dialogfeld Erweiterte Eigenschaften (Standard)</span><span class="sxs-lookup"><span data-stu-id="f3140-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="f3140-160">Geben Sie an, wo das Feld Benutzername bei der Anmeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f3140-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="f3140-161">Nutzungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="f3140-161">Usage examples</span></span>

<span data-ttu-id="f3140-162">Zum Hinzufügen einer einzelnen Domäne (Contoso.com) in die Liste der vertrauenswürdigen Domäne verwenden Sie die Taste TrustedDomainList wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f3140-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="f3140-163">Standardwerte schreiben com.microsoft.SkypeForBusiness TrustedDomainList-Array-"Contoso.com" hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f3140-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="f3140-164">Um mehrere Domänen zur Liste der vertrauenswürdigen Domänen hinzuzufügen, verwenden Sie den trustedDomainList-Schlüssel (siehe unten):</span><span class="sxs-lookup"><span data-stu-id="f3140-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="f3140-165">Standardwerte schreiben com.microsoft.SkypeForBusiness TrustedDomainList-Array-"sfb.com" "abc.com" "test.org" hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f3140-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="f3140-166">Nicht bearbeitete Beispieleinstellungen</span><span class="sxs-lookup"><span data-stu-id="f3140-166">Sample unedited settings</span></span>

<span data-ttu-id="f3140-167">Zu Referenzzwecken finden Sie hier eine Datei mit Beispieleinstellungen (nur Standardeinstellungen): </span><span class="sxs-lookup"><span data-stu-id="f3140-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
