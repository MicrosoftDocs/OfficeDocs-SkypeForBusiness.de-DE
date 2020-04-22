---
title: Konfigurieren der intelligenten Kontaktliste in Skype for Business Clients
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Feature "intelligente Kontaktliste" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776690"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="ca62e-103">Konfigurieren der intelligenten Kontaktliste in Skype for Business Clients</span><span class="sxs-lookup"><span data-stu-id="ca62e-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="ca62e-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie das Feature "intelligente Kontaktliste" im Skype for Business-Client aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ca62e-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="ca62e-105">Das Feature "intelligente Kontaktliste" ermöglicht die automatische Auffüllung von Kontaktlisten für die Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="ca62e-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="ca62e-106">Bei der ersten Verwendung von Skype for Business werden Ihre Benutzer automatisch Ihren Vorgesetzten und andere Personen in Ihrem Team sehen.</span><span class="sxs-lookup"><span data-stu-id="ca62e-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="ca62e-107">Dieses Feature ist für Microsoft 365 und Office 365 Benutzer standardmäßig aktiviert, Sie müssen dieses Feature jedoch explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinien Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ca62e-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="ca62e-108">Beachten Sie beim Konfigurieren dieses Features Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ca62e-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="ca62e-109">Benutzer, bis zu 13, werden automatisch der Liste der intelligenten Kontakte in der folgenden Reihenfolge hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="ca62e-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="ca62e-110">Manager</span><span class="sxs-lookup"><span data-stu-id="ca62e-110">Manager</span></span>

  2. <span data-ttu-id="ca62e-111">Leitet in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ca62e-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="ca62e-112">Peers in alphabetischer Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ca62e-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="ca62e-113">Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen "meine Gruppe" erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca62e-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="ca62e-114">Die Gruppe wird automatisch mit Personen in der AD-Gruppenbeziehung des Benutzers basierend auf dem im Feld Manager aufgefüllten Benutzer Alias aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ca62e-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="ca62e-115">Beachten Sie, dass Änderungen an der AD-Gruppenmitgliedschaft nicht dazu führen, dass meine Gruppe aktualisiert wird, nachdem Sie ursprünglich aufgefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca62e-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="ca62e-116">Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca62e-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="ca62e-117">Wenn die automatische Kennzeichnung aktiviert ist, werden Kontakte in der Liste für Anwesenheitsänderungen markiert.</span><span class="sxs-lookup"><span data-stu-id="ca62e-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="ca62e-118">Die automatische Kennzeichnung ist standardmäßig aktiviert, Sie können Sie jedoch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ca62e-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="ca62e-119">Alle neuen Benutzer in der Gruppe werden darüber informiert, dass Sie der Kontaktliste hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca62e-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="ca62e-120">Benutzer können manuell neue Mitglieder zu Ihrer Gruppe meine oder zu anderen Gruppen Ihrer Wahl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca62e-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="ca62e-121">Dieses Feature funktioniert nur für Benutzer, die sich zum ersten Mal anmelden.</span><span class="sxs-lookup"><span data-stu-id="ca62e-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="ca62e-122">Wenn ein Benutzer sich zuvor von einem beliebigen Gerät aus angemeldet hat, beispielsweise auf einem mobilen Gerät oder einem Mac, ist das Feature für diesen Benutzer nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca62e-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="ca62e-123">Konfigurieren der intelligenten Kontaktliste</span><span class="sxs-lookup"><span data-stu-id="ca62e-123">Configure Smart contacts list</span></span>

<span data-ttu-id="ca62e-124">Sie müssen die folgenden Schritte ausführen, um die Funktion "intelligente Kontaktliste" für Ihre Benutzer zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ca62e-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="ca62e-125">Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu.</span><span class="sxs-lookup"><span data-stu-id="ca62e-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="ca62e-126">Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ca62e-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="ca62e-127">Erstellen eines Richtlinien Eintrags zum Aktivieren der Smart Contacts-Liste</span><span class="sxs-lookup"><span data-stu-id="ca62e-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="ca62e-128">Verwenden Sie das [New-CsClientPolicyEntry-](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet mit der Option EnableClientAutoPopulateWithTeam wie folgt, um einen Richtlinieneintrag zum Aktivieren des Features für die intelligente Kontaktliste zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ca62e-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="ca62e-129">Verwenden Sie als nächstes das Cmdlet " [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ", um die Änderungen wie folgt in die globale Richtlinie zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="ca62e-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="ca62e-130">Sie können optional eine Richtlinie erstellen, um die automatische Kennzeichnung wie folgt zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="ca62e-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="ca62e-131">Sie müssen auch den AddressBookAvailability-Parameter für die entsprechende Richtlinie auf WebSearchOnly festlegen.</span><span class="sxs-lookup"><span data-stu-id="ca62e-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="ca62e-132">Weitere Informationen finden Sie unter [Sets-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ca62e-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="ca62e-133">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="ca62e-133">Troubleshoot</span></span>

<span data-ttu-id="ca62e-134">Wenn die Liste der intelligenten Kontakte nicht wie erwartet funktioniert, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ca62e-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="ca62e-135">Überprüfen Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ca62e-135">Validate the configuration.</span></span> 

- <span data-ttu-id="ca62e-136">Stellen Sie sicher, dass die Informationen zur AD-Organisation aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="ca62e-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="ca62e-137">Sammeln Sie Skype for Business Clientprotokolle für einen neuen Benutzer zur weiteren Analyse.</span><span class="sxs-lookup"><span data-stu-id="ca62e-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="ca62e-138">Vergewissern Sie sich, dass auf der Benutzeroberfläche des Skype for Business Clients keine Meldung angezeigt wird, dass keine Verbindung mit dem Adressbuch hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca62e-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="ca62e-139">Um die Adressbuch Konnektivität zu bestätigen, führen Sie in der Skype for Business-Client Suchleiste eine Suche nach einem Benutzer durch.</span><span class="sxs-lookup"><span data-stu-id="ca62e-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="ca62e-140">AD DS Replikationsprobleme können dazu führen, dass Kontakte nicht aufgelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet.</span><span class="sxs-lookup"><span data-stu-id="ca62e-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


