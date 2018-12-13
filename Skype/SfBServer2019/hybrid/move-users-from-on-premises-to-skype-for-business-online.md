---
title: Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Erfahren Sie, wie Benutzer in Skype für Business Online zu verschieben.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243997"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="a9d53-103">Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a9d53-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="a9d53-104">Nachdem Sie einen Benutzer aus der lokalen in Skype für Business Online verschieben, interagiert der Benutzer mit Skype für Business Online für seine Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="a9d53-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="a9d53-105">Alle Kontakte, die lokalen vorhanden war, werden in Skype für Business Online verfügbar sein, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert werden so zeigen Sie die Links zu Skype für Business Online auf aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a9d53-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="a9d53-106">Wenn der Benutzer für Audiokonferenzen aktiviert ist, werden die Besprechungen auch Zugriffsnummer für Einwahl Koordinaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9d53-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="a9d53-107">Um Benutzer aus einer lokalen Umgebung zu Skype für Business Online zu verschieben, verwenden Sie das Cmdlet Move-CsUser oder die Skype für beide lokalen Tools sind Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a9d53-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="a9d53-108">Werden Sie vor dem Verschieben alle Benutzer, überprüfen Sie die [erforderlichen Komponenten](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in der Cloud zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a9d53-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="a9d53-109">Verschieben von Benutzern mit der Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="a9d53-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="a9d53-110">Move-CsUser ist von einem lokalen Skype für Business Management Shell PowerShell-Fenster zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a9d53-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="a9d53-111">Wie beschrieben in [Administratorrechte erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials), benötigen Sie ausreichende Berechtigungen in beiden der lokalen Umgebung sowie wie in der Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a9d53-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="a9d53-112">Sie können entweder ein einzelnes Konto mit Berechtigungen in beiden Umgebungen verwenden oder Sie können eine lokale Skype für Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und Verwenden der `-Credential` Parameter zum Angeben von Anmeldeinformationen für ein Office 365 Konto mit den erforderlichen Office 365-Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="a9d53-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="a9d53-113">Zum Verschieben eines Benutzers zu online mit der Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="a9d53-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="a9d53-114">Geben Sie den Benutzer mit dem Parameter Identity verschieben.</span><span class="sxs-lookup"><span data-stu-id="a9d53-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="a9d53-115">Geben Sie die - Target-Parameter mit dem Wert "sipfed.online.lync. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="a9d53-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="a9d53-116">Wenn Sie in beiden auf lokalen und Office 365 nicht über ein Konto mit ausreichenden Berechtigungen verfügen, verwenden Sie den - Credential-Parameter zum Angeben eines Kontos mit ausreichenden Berechtigungen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9d53-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="a9d53-117">Wenn das Konto mit Berechtigungen in Office 365 nicht in "on.microsoft. endet <span>com ", und klicken Sie dann HostedMigrationOverrideUrl - Angabe des Parameters, mit dem richtigen Wert müssen wie unter [administrative Anmeldeinformationen erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="a9d53-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="a9d53-118">Die folgende Sequenz Cmdlet zum Verschieben eines Benutzers in Skype für Business Online verwendet werden, und geht davon aus, die Office 365-Anmeldeinformationen ist ein separates Konto und als Eingabe für die Aufforderung Get-Credential angegeben.</span><span class="sxs-lookup"><span data-stu-id="a9d53-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="a9d53-119">Verschieben von Benutzern mit Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a9d53-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="a9d53-120">Öffnen Sie die Skype für Business-Serversteuerelement Systemsteuerung app.</span><span class="sxs-lookup"><span data-stu-id="a9d53-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="a9d53-121">Wählen Sie im linken Navigationsbereich **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="a9d53-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="a9d53-122">Verwenden Sie **Suchen** , um die Benutzer zu suchen, die Sie in Skype für Business Online verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="a9d53-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="a9d53-123">Wählen Sie die Benutzer, und wählen Sie dann aus der Dropdownliste **Aktion** über der Liste **ausgewählte Benutzer in Skype für Business Online zu verschieben**.</span><span class="sxs-lookup"><span data-stu-id="a9d53-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="a9d53-124">Klicken Sie im Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9d53-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="a9d53-125">Wenn Sie aufgefordert werden, melden Sie sich bei Office 365, mit einem Konto an, die in endet. onmicrosoft.com und über ausreichende Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="a9d53-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="a9d53-126">Klicken Sie auf **Weiter**, und klicken Sie dann **Weiter** noch einmal den Benutzer zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a9d53-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="a9d53-127">Beachten Sie, dass Statusnachrichten bezüglich Erfolg oder Fehler am oberen Rand der wichtigsten Systemsteuerung app nicht im Assistenten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a9d53-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9d53-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9d53-128">See also</span></span>

[<span data-ttu-id="a9d53-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="a9d53-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)