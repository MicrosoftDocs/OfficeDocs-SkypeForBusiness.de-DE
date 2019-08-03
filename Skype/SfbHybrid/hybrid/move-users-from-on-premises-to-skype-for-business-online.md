---
title: Migrieren von Benutzern von lokal in Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Informationen zum Migrieren von Benutzern zu Skype for Business Online.
ms.openlocfilehash: 90d225eb725690566f23b73b3626cbcf1f42c8c7
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "36160591"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="e171e-103">Migrieren von Benutzern von lokal in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e171e-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="e171e-104">Nachdem Sie einen Benutzer von lokal in Skype for Business Online umgezogen haben, interagiert der Benutzer mit Skype for Business Online für seine Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="e171e-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="e171e-105">Alle Kontakte, die lokal vorhanden waren, werden in Skype for Business Online zur Verfügung stehen, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert hat, werden so aktualisiert, dass die Links auf Skype for Business Online verweisen.</span><span class="sxs-lookup"><span data-stu-id="e171e-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="e171e-106">Wenn der Benutzer für Audiokonferenzen aktiviert ist, enthalten die Besprechungen auch Einwahl Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="e171e-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="e171e-107">Um Benutzer aus einer lokalen Umgebung in Skype for Business Online zu migrieren, verwenden Sie entweder das Cmdlet "CsUser" oder die Skype for Business Server-Systemsteuerung, beide lokale Tools.</span><span class="sxs-lookup"><span data-stu-id="e171e-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="e171e-108">Lesen Sie vor dem Verschieben von Benutzern unbedingt die [voraus](move-users-between-on-premises-and-cloud.md#prerequisites) setzungen, um Benutzer in die Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e171e-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="e171e-109">Migrieren von Benutzern mit "CsUser"</span><span class="sxs-lookup"><span data-stu-id="e171e-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="e171e-110">CsUser ist in einem lokalen Skype for Business-Verwaltungsshell PowerShell-Fenster verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e171e-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="e171e-111">Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch im Office 365-Mandanten verfügen, wie unter [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e171e-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e171e-112">Sie können entweder ein einzelnes Konto verwenden, das über Berechtigungen in beiden Umgebungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den `-Credential` -Parameter verwenden, um Anmeldeinformationen für eine Office 365 anzugeben. Konto mit der erforderlichen Office 365 Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="e171e-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="e171e-113">So stellen Sie einen Benutzer mithilfe von "CsUser" in "Online" ein:</span><span class="sxs-lookup"><span data-stu-id="e171e-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="e171e-114">Geben Sie den zu verschiebenden Benutzer mit dem Parameter Identity an.</span><span class="sxs-lookup"><span data-stu-id="e171e-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="e171e-115">Geben Sie den-target-Parameter mit dem Wert "sipfed. online. lync" an. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="e171e-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e171e-116">Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch Office 365 verfügen, verwenden Sie den Parameter-Credential, um ein Konto mit ausreichenden Berechtigungen in Office 365 bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e171e-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="e171e-117">Wenn das Konto mit den Berechtigungen in Office 365 nicht in "on. Microsoft" endet. <span>com ", müssen Sie den-HostedMigrationOverrideUrl-Parameter mit dem korrekten Wert angeben, wie unter" [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)"beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e171e-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

 > [!NOTE]
 > <span data-ttu-id="e171e-118">Sie müssen den korrekten HostedMigrationOverrideUrl-Wert für Ihren Mandanten ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e171e-118">You must determine the correct HostedMigrationOverrideUrl value for your tenant.</span></span> <span data-ttu-id="e171e-119">Dies kann ganz einfach erfolgen, indem Sie zum Legacy Skype for Business Admin Center navigieren.</span><span class="sxs-lookup"><span data-stu-id="e171e-119">this can be easily done by navigating to the Legacy Skype for Business admin center.</span></span> <span data-ttu-id="e171e-120">Bestimmen des Präfix-xxxxxxx.online.lync.com und Anfügen von/HostedMigration/hostedmigrationservice.svc.</span><span class="sxs-lookup"><span data-stu-id="e171e-120">determine the prefix - XXXXXXX.online.lync.com and append /HostedMigration/hostedmigrationservice.svc.</span></span> <span data-ttu-id="e171e-121">Beispiel: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Wenn Sie den Wert identifiziert haben, verwenden Sie ihn für die $URL-Variable wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e171e-121">for example: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Once you identified the value, use it for the $url variable as shown below.</span></span>

<span data-ttu-id="e171e-122">Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer zu Skype for Business Online zu migrieren, und es wird davon ausgegangen, dass die Office 365 Credential ein separates Konto ist und als Eingabe für die Get-Credential-Eingabeaufforderung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e171e-122">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="e171e-123">Wenn das Administratorkonto MFA (Multi-Factor Authentication) aktiviert ist, geben Sie den Parameter-Credential nicht an.</span><span class="sxs-lookup"><span data-stu-id="e171e-123">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="e171e-124">Der Administrator wird zur Eingabe von Anmeldeinformationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e171e-124">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e171e-125">Benutzer mit Skype for Business Server-Systemsteuerung migrieren</span><span class="sxs-lookup"><span data-stu-id="e171e-125">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="e171e-126">Öffnen Sie die Skype for Business Server-Systemsteuerung-app.</span><span class="sxs-lookup"><span data-stu-id="e171e-126">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e171e-127">Wählen Sie im linken Navigationsbereich **Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="e171e-127">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e171e-128">Verwenden Sie **Suchen** , um die Benutzer zu finden, die Sie in Skype for Business Online verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="e171e-128">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="e171e-129">Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **Aktion** oberhalb der Liste die Option **ausgewählte Benutzer in Skype for Business Online**verlagern aus.</span><span class="sxs-lookup"><span data-stu-id="e171e-129">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="e171e-130">Klicken Sie im Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e171e-130">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e171e-131">Wenn Sie dazu aufgefordert werden, melden Sie sich bei Office 365 mit einem Konto an, das in. onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="e171e-131">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e171e-132">Klicken Sie auf **weiter**und dann auf **weiter** , um den Benutzer zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="e171e-132">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e171e-133">Beachten Sie, dass Statusmeldungen bezüglich Erfolg oder Fehler oben in der Hauptsystem Steuerung-APP, nicht im Assistenten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e171e-133">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="e171e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e171e-134">See also</span></span>

[<span data-ttu-id="e171e-135">CsUser</span><span class="sxs-lookup"><span data-stu-id="e171e-135">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
