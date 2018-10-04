---
title: Testen von einwahlkonferenzen in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Zusammenfassung: Erfahren Sie, wie einwahlkonferenzen in Skype für Business Server zu testen.'
ms.openlocfilehash: e86e2c136edd8520f12944768e327e0870106f6e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372839"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="b467e-103">Testen von einwahlkonferenzen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="b467e-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="b467e-104">**Zusammenfassung:** Erfahren Sie, wie einwahlkonferenzen in Skype für Business Server zu testen.</span><span class="sxs-lookup"><span data-stu-id="b467e-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="b467e-105">Zur endgültigen Bestätigung der Einwahlkonferenzkonfiguration können Sie nach Wähleinstellungen suchen, die eine Region für Einwahlkonferenzen aufweisen, die von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern suchen, für die keine Region für Einwahlkonferenzen angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b467e-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="b467e-106">Sie sollten außerdem sicherstellen, dass die Website mit Einstellungen für die Einzelwahlkonferenz und die Zugriffsnummern korrekt funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b467e-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="b467e-107">So ermitteln Sie Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen, die von keiner Zugriffsnummer verwendet wird</span><span class="sxs-lookup"><span data-stu-id="b467e-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="b467e-108">Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.</span><span class="sxs-lookup"><span data-stu-id="b467e-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b467e-109">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b467e-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b467e-110">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="b467e-110">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="b467e-111">Dieses Cmdlet gibt alle Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen zurück, die von keiner Zugriffsnummer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b467e-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="b467e-112">Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b467e-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="b467e-113">So bestimmen Sie Zugriffsnummern ohne zugewiesene Regionen</span><span class="sxs-lookup"><span data-stu-id="b467e-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="b467e-114">Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.</span><span class="sxs-lookup"><span data-stu-id="b467e-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b467e-115">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b467e-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b467e-116">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="b467e-116">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="b467e-117">Dieses Cmdlet gibt alle Zugriffsnummern für Einwahlkonferenzen zurück, die keiner Region zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b467e-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="b467e-118">Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b467e-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="b467e-119">So testen Sie Websites und Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="b467e-119">Test webpage and access numbers</span></span>

<span data-ttu-id="b467e-120">Sie müssen die folgenden Aufgaben ausführen, um sicherzustellen, dass die Webseite mit den Einstellungen für Einwahlkonferenzen und die Zugriffsnummern für die Einwahl ordnungsgemäß funktionieren:</span><span class="sxs-lookup"><span data-stu-id="b467e-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="b467e-121">Testen Sie die Webseite mit Einstellungen für Einwahlkonferenzen, indem Sie sich über die einfache URL anmelden.</span><span class="sxs-lookup"><span data-stu-id="b467e-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="b467e-p102">Testen Sie die Zugriffsnummern für einen bestimmten Pool, indem Sie das weiter unten in diesem Thema gezeigte Skript ausführen. Dieses Skript simuliert Anrufe bei Zugriffsnummern. Sie benötigen zur Verwendung dieses Skripts die SIP-Adresse und Anmeldeinformationen für einen Unified Communications-Client (UC), der im angegebenen Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b467e-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="b467e-125">So testen Sie Zugriffsnummern für einen spezifischen Pool</span><span class="sxs-lookup"><span data-stu-id="b467e-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="b467e-126">Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.</span><span class="sxs-lookup"><span data-stu-id="b467e-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b467e-127">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b467e-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b467e-128">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="b467e-128">Run the following at the command prompt:</span></span>
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="b467e-129">In den Berichtergebnissen wird der Test entweder als erfolgreich oder mit Fehlern angezeigt, zusammen mit spezifischen Diagnoseinformationen.</span><span class="sxs-lookup"><span data-stu-id="b467e-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="b467e-130">Die - Verbose Flag enthält weitere detaillierte Informationen über wie viele Nummern gefunden und Details.</span><span class="sxs-lookup"><span data-stu-id="b467e-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="b467e-131">Weitere Informationen finden Sie unter [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b467e-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

