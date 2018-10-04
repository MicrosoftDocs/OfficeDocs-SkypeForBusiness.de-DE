---
title: Konfigurieren von Smart Kontaktliste in Skype für die Business-clients
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Erfahren Sie, wie das Listenfeature Smart Kontakte in die Skype für Business-Client zu aktivieren.'
ms.openlocfilehash: 1aba122df313384fe1680296551ff7689b237d54
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374484"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="63620-103">Konfigurieren von Smart Kontaktliste in Skype für die Business-clients</span><span class="sxs-lookup"><span data-stu-id="63620-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="63620-104">**Zusammenfassung:** Erfahren Sie, wie das Listenfeature Smart Kontakte in die Skype für Business-Client zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63620-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="63620-105">Das Listenfeature Smart Kontakte ermöglicht automatische Auffüllung von Kontaktlisten für die Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="63620-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="63620-106">Bei der ersten Verwendung von Skype für Unternehmen, Ihre Benutzer werden automatisch finden Sie unter ihren Manager und andere Personen in ihrem Team.</span><span class="sxs-lookup"><span data-stu-id="63620-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="63620-107">Dieses Feature ist standardmäßig für Office 365-Benutzer aktiviert, aber Sie müssen dieses Feature explizit durch Konfigurieren der Einstellung für die Richtlinie für Ihre lokalen Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63620-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="63620-108">Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="63620-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="63620-109">Benutzer, bis zu 13, werden automatisch der Liste Smart Kontakte in der folgenden Reihenfolge hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="63620-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="63620-110">Manager</span><span class="sxs-lookup"><span data-stu-id="63620-110">Manager</span></span>

  2. <span data-ttu-id="63620-111">Directors in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="63620-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="63620-112">Peers in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="63620-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="63620-113">Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen „My Group“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="63620-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="63620-114">Mit Personen in der Beziehung des Benutzers AD Gruppe basierend auf den Alias des Benutzers im Feld Manager aufgefüllt wird automatisch die Gruppe aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="63620-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="63620-115">Beachten Sie, dass Änderungen in Bezug auf die AD-Gruppenmitgliedschaft keine Aktualisierung der Gruppe „My Group“ zur Folge hat, nachdem diese einmal mit Benutzern gefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="63620-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="63620-116">Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="63620-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="63620-117">Falls die automatische Tag-Kennzeichnung aktiviert ist, werden Kontakte in der Liste markiert, sobald sich deren Anwesenheitsstatus ändert.</span><span class="sxs-lookup"><span data-stu-id="63620-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="63620-118">Die automatische Kennzeichnung ist standardmäßig aktiviert, kann jedoch bei Bedarf deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="63620-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="63620-119">Alle neuen Benutzer in der Gruppe erhalten eine Nachricht, dass sie zur Kontaktliste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="63620-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="63620-120">Benutzer haben die Möglichkeit, neue Mitglieder manuell zur Gruppe „My Group“ oder zu anderen Gruppen ihrer Wahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="63620-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="63620-121">Diese Funktion steht Benutzern nur bei der erstmaligen Anmeldung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="63620-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="63620-122">Falls sich ein Benutzer zuvor bereits von einem anderen Gerät jeglicher Art aus angemeldet hat, z. B. von einem mobilen Gerät oder von einem Mac aus, ist die Funktion für diesen Benutzer nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="63620-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="63620-123">Intelligente Kontaktlisten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="63620-123">Configure Smart contacts list</span></span>

<span data-ttu-id="63620-124">Um die Funktion „Intelligente Kontaktliste“ für Ihre Benutzer zu aktivieren, müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="63620-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="63620-125">Erstellen Sie einen neuen Eintrag CsClientPolicy und globale Clientrichtlinie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63620-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="63620-126">Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="63620-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="63620-127">Einen Richtlinieneintrag zur Aktivierung der intelligenten Kontaktliste erstellen</span><span class="sxs-lookup"><span data-stu-id="63620-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="63620-128">So erstellen Sie einen Richtlinieneintrag, um das Listenfeature Smart Kontakte aktivieren, verwenden Sie das Cmdlet " [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) " mit der Option EnableClientAutoPopulateWithTeam wie folgt:</span><span class="sxs-lookup"><span data-stu-id="63620-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="63620-129">Im nächsten Schritt verwenden Sie das Cmdlet " [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ", um die Änderungen an der globalen Richtlinie wie folgt schreiben:</span><span class="sxs-lookup"><span data-stu-id="63620-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="63620-130">Optional können Sie eine Richtlinie erstellen, um die automatische Kennzeichnung zu deaktivieren, wie im Folgenden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="63620-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="63620-131">Außerdem müssen Sie den Parameter „AddressBookAvailability“ für die entsprechende Richtlinie auf „WebSearchOnly“ einstellen.</span><span class="sxs-lookup"><span data-stu-id="63620-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="63620-132">Weitere Informationen finden Sie unter [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="63620-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="63620-133">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="63620-133">Troubleshoot</span></span>

<span data-ttu-id="63620-134">Sollte die intelligente Kontaktliste nicht wie erwartet funktionieren, nehmen Sie folgende Überprüfung vor:</span><span class="sxs-lookup"><span data-stu-id="63620-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="63620-135">Überprüfen Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="63620-135">Validate the configuration.</span></span> 

- <span data-ttu-id="63620-136">Stellen Sie sicher, dass die AD-Organisationsinformationen ausgefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="63620-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="63620-137">Sammeln von Skype für Clientprotokolle Business auf einen neuen Benutzer zur weiteren Analyse.</span><span class="sxs-lookup"><span data-stu-id="63620-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="63620-138">Vergewissern Sie sich, dass die Skype für Business Clientbenutzeroberfläche keine Meldung anzeigt, die zum Adressbuch keine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="63620-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="63620-139">Adressbuch-Konnektivität zu bestätigen, führen Sie eine Suche für einen Benutzer in der Skype für Business Client Suchleiste.</span><span class="sxs-lookup"><span data-stu-id="63620-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="63620-140">AD DS-Replikationsprobleme verursachen Kontakte nicht aufgelöst werden, wenn ein Benutzer zuerst bei Skype für Unternehmen anmeldet.</span><span class="sxs-lookup"><span data-stu-id="63620-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


