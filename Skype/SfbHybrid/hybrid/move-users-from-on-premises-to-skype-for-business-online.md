---
title: Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
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
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221115"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="c33b7-103">Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c33b7-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="c33b7-104">Nachdem Sie einen Benutzer von lokal in Skype for Business Online umgezogen haben, interagiert der Benutzer mit Skype for Business Online für seine Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="c33b7-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="c33b7-105">Alle Kontakte, die lokal vorhanden waren, werden in Skype for Business Online zur Verfügung stehen, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert hat, werden so aktualisiert, dass die Links auf Skype for Business Online verweisen.</span><span class="sxs-lookup"><span data-stu-id="c33b7-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="c33b7-106">Wenn der Benutzer für Audiokonferenzen aktiviert ist, enthalten die Besprechungen auch Einwahl Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="c33b7-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="c33b7-107">Um Benutzer aus einer lokalen Umgebung in Skype for Business Online zu migrieren, verwenden Sie entweder das Cmdlet "CsUser" oder die Skype for Business Server-Systemsteuerung, beide lokale Tools.</span><span class="sxs-lookup"><span data-stu-id="c33b7-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="c33b7-108">Lesen Sie vor dem Verschieben von Benutzern unbedingt die [Voraussetzungen](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in die Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="c33b7-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="c33b7-109">Migrieren von Benutzern mit "CsUser"</span><span class="sxs-lookup"><span data-stu-id="c33b7-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="c33b7-110">CsUser ist in einem lokalen Skype for Business-Verwaltungsshell PowerShell-Fenster verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c33b7-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="c33b7-111">Sie müssen sowohl in der lokalen Umgebung als auch in der Microsoft 365/Office 365-Organisation über ausreichende Berechtigungen verfügen, wie unter [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c33b7-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="c33b7-112">Sie können entweder ein einzelnes Konto verwenden, das über Berechtigungen in beiden Umgebungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, `-Credential` um Anmeldeinformationen für ein Microsoft 365-oder Office 365-Konto mit der erforderlichen Administratorrolle anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c33b7-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="c33b7-113">So stellen Sie einen Benutzer mithilfe von "CsUser" in "Online" ein:</span><span class="sxs-lookup"><span data-stu-id="c33b7-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="c33b7-114">Geben Sie den zu verschiebenden Benutzer mit dem Parameter Identity an.</span><span class="sxs-lookup"><span data-stu-id="c33b7-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="c33b7-115">Geben Sie den-target-Parameter mit dem Wert "sipfed. online. lync" an. <span> com ".</span><span class="sxs-lookup"><span data-stu-id="c33b7-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="c33b7-116">Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch Office 365 verfügen, verwenden Sie den Parameter-Credential, um ein Konto mit ausreichenden Berechtigungen in Office 365 bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c33b7-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="c33b7-117">Wenn das Konto mit den Berechtigungen in Office 365 nicht in ". onmicrosoft <span> " endet. com ", müssen Sie den-HostedMigrationOverrideUrl-Parameter mit dem korrekten Wert angeben, wie unter" [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)"beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c33b7-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="c33b7-118">Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer in Skype for Business Online zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="c33b7-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="c33b7-119">Es wird davon ausgegangen, dass die Anmeldeinformationen von Microsoft 365 oder Office 365 ein separates Konto sind und als Eingabe für die Eingabeaufforderung Get-Credential angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c33b7-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="c33b7-120">Wenn das Administratorkonto MFA (Multi-Factor Authentication) aktiviert ist, geben Sie den Parameter-Credential nicht an.</span><span class="sxs-lookup"><span data-stu-id="c33b7-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="c33b7-121">Der Administrator wird zur Eingabe von Anmeldeinformationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c33b7-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="c33b7-122">Benutzer mit Skype for Business Server-Systemsteuerung migrieren</span><span class="sxs-lookup"><span data-stu-id="c33b7-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="c33b7-123">Öffnen Sie die Skype for Business Server-Systemsteuerung-app.</span><span class="sxs-lookup"><span data-stu-id="c33b7-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="c33b7-124">Wählen Sie im linken Navigationsbereich **Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="c33b7-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="c33b7-125">Verwenden Sie **Suchen** , um die Benutzer zu finden, die Sie in Skype for Business Online verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="c33b7-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="c33b7-126">Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **Aktion** oberhalb der Liste die Option **ausgewählte Benutzer in Skype for Business Online verlagern**aus.</span><span class="sxs-lookup"><span data-stu-id="c33b7-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="c33b7-127">Klicken Sie im Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c33b7-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="c33b7-128">Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 oder Office 365 mit einem Konto an, das in. onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="c33b7-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="c33b7-129">Klicken Sie auf **weiter**und dann auf **weiter** , um den Benutzer zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="c33b7-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="c33b7-130">Beachten Sie, dass Statusmeldungen bezüglich Erfolg oder Fehler oben in der Hauptsystem Steuerung-APP, nicht im Assistenten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c33b7-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="c33b7-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c33b7-131">See also</span></span>

[<span data-ttu-id="c33b7-132">CsUser</span><span class="sxs-lookup"><span data-stu-id="c33b7-132">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
