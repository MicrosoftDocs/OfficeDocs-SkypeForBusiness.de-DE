---
title: Konfigurieren der intelligenten Kontaktliste in Skype for Business-Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Feature "Smart Contacts List" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768868"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="bf05c-103">Konfigurieren der intelligenten Kontaktliste in Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="bf05c-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="bf05c-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie das Feature "Smart Contacts List" im Skype for Business-Client aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bf05c-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="bf05c-105">Das Feature "Smart Contacts List" ermöglicht die automatische Auffüllung von Kontaktlisten für Ihre Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="bf05c-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="bf05c-106">Bei der ersten Verwendung von Skype for Business werden Ihre Benutzer automatisch Ihren Manager und andere Personen in Ihrem Team sehen.</span><span class="sxs-lookup"><span data-stu-id="bf05c-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="bf05c-107">Dieses Feature ist standardmäßig für Office 365-Benutzer aktiviert, Sie müssen dieses Feature aber explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinien Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf05c-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="bf05c-108">Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="bf05c-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="bf05c-109">Benutzer, bis zu 13, werden der Liste der intelligenten Kontakte automatisch in der folgenden Reihenfolge hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="bf05c-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="bf05c-110">Manager</span><span class="sxs-lookup"><span data-stu-id="bf05c-110">Manager</span></span>

  2. <span data-ttu-id="bf05c-111">Directors in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="bf05c-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="bf05c-112">Peers in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="bf05c-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="bf05c-113">Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen „My Group“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="bf05c-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="bf05c-114">Die Gruppe wird automatisch mit Personen in der Anzeigengruppen Beziehung des Benutzers ausgefüllt, basierend auf dem im Feld Manager aufgefüllten Benutzer-Alias.</span><span class="sxs-lookup"><span data-stu-id="bf05c-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="bf05c-115">Beachten Sie, dass Änderungen in Bezug auf die AD-Gruppenmitgliedschaft keine Aktualisierung der Gruppe „My Group“ zur Folge hat, nachdem diese einmal mit Benutzern gefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="bf05c-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="bf05c-116">Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="bf05c-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="bf05c-117">Falls die automatische Tag-Kennzeichnung aktiviert ist, werden Kontakte in der Liste markiert, sobald sich deren Anwesenheitsstatus ändert.</span><span class="sxs-lookup"><span data-stu-id="bf05c-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="bf05c-118">Die automatische Kennzeichnung ist standardmäßig aktiviert, kann jedoch bei Bedarf deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bf05c-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="bf05c-119">Alle neuen Benutzer in der Gruppe erhalten eine Nachricht, dass sie zur Kontaktliste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="bf05c-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="bf05c-120">Benutzer haben die Möglichkeit, neue Mitglieder manuell zur Gruppe „My Group“ oder zu anderen Gruppen ihrer Wahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf05c-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="bf05c-121">Diese Funktion steht Benutzern nur bei der erstmaligen Anmeldung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bf05c-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="bf05c-122">Falls sich ein Benutzer zuvor bereits von einem anderen Gerät jeglicher Art aus angemeldet hat, z. B. von einem mobilen Gerät oder von einem Mac aus, ist die Funktion für diesen Benutzer nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bf05c-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="bf05c-123">Intelligente Kontaktlisten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bf05c-123">Configure Smart contacts list</span></span>

<span data-ttu-id="bf05c-124">Um die Funktion „Intelligente Kontaktliste“ für Ihre Benutzer zu aktivieren, müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="bf05c-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="bf05c-125">Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf05c-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="bf05c-126">Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bf05c-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="bf05c-127">Einen Richtlinieneintrag zur Aktivierung der intelligenten Kontaktliste erstellen</span><span class="sxs-lookup"><span data-stu-id="bf05c-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="bf05c-128">Verwenden Sie zum Erstellen eines Richtlinien Eintrags zum Aktivieren des Features "Smart Contacts List" das Cmdlet " [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) " mit der Option "EnableClientAutoPopulateWithTeam" wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bf05c-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="bf05c-129">Verwenden Sie als nächstes das Cmdlet " [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ", um die Änderungen an der globalen Richtlinie wie folgt zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="bf05c-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="bf05c-130">Optional können Sie eine Richtlinie erstellen, um die automatische Kennzeichnung zu deaktivieren, wie im Folgenden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="bf05c-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="bf05c-131">Außerdem müssen Sie den Parameter „AddressBookAvailability“ für die entsprechende Richtlinie auf „WebSearchOnly“ einstellen.</span><span class="sxs-lookup"><span data-stu-id="bf05c-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="bf05c-132">Weitere Informationen finden Sie unter [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bf05c-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="bf05c-133">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="bf05c-133">Troubleshoot</span></span>

<span data-ttu-id="bf05c-134">Sollte die intelligente Kontaktliste nicht wie erwartet funktionieren, nehmen Sie folgende Überprüfung vor:</span><span class="sxs-lookup"><span data-stu-id="bf05c-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="bf05c-135">Überprüfen Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bf05c-135">Validate the configuration.</span></span> 

- <span data-ttu-id="bf05c-136">Stellen Sie sicher, dass die AD-Organisationsinformationen ausgefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="bf05c-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="bf05c-137">Sammeln Sie Skype for Business-Client-Logs für einen neuen Benutzer zur weiteren Analyse.</span><span class="sxs-lookup"><span data-stu-id="bf05c-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="bf05c-138">Vergewissern Sie sich, dass auf der Skype for Business-Client-Benutzeroberfläche keine Meldung angezeigt wird, dass keine Verbindung mit dem Adressbuch hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bf05c-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="bf05c-139">Um die Adressbuch Konnektivität zu bestätigen, führen Sie in der Skype for Business-Client Suchleiste eine Suche nach einem Benutzer durch.</span><span class="sxs-lookup"><span data-stu-id="bf05c-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="bf05c-140">Probleme mit der AD DS-Replikation können dazu führen, dass Kontakte nicht aufgelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet.</span><span class="sxs-lookup"><span data-stu-id="bf05c-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


