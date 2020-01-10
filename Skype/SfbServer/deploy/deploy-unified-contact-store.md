---
title: 'Bereitstellen des einheitlichen Kontaktspeichers in Skype for Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Zusammenfassung: Aktivieren des Unified Contact Stores in Skype for Business Server.'
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003065"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="15a3f-103">Bereitstellen des einheitlichen Kontaktspeichers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="15a3f-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="15a3f-104">**Zusammenfassung:** Aktivieren Sie den einheitlichen Kontaktspeicher in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15a3f-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="15a3f-105">Für die Aktivierung des Unified Contact Stores in Skype for Business Server sind keine topologieeinstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="15a3f-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="15a3f-106">Zur Aktivierung des einheitlichen Kontaktspeichers für Benutzer müssen Sie die folgenden Punkte sicherstellen:</span><span class="sxs-lookup"><span data-stu-id="15a3f-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="15a3f-107">Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).</span><span class="sxs-lookup"><span data-stu-id="15a3f-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="15a3f-108">Benutzer melden sich mindestens einmal mit Skype for Business an.</span><span class="sxs-lookup"><span data-stu-id="15a3f-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="15a3f-109">Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer mit Skype for Business anmeldet, kann der Benutzer auf seine Skype for Business-Kontakte über Skype for Business, Outlook 2013 oder Outlook Web Access zugreifen und diese verwalten.</span><span class="sxs-lookup"><span data-stu-id="15a3f-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="15a3f-110">Der Benutzer muss nicht bei Skype for Business angemeldet sein, um seine Kontakte aus Outlook oder Outlook Web Access zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="15a3f-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="15a3f-111">Wenn ein Benutzer sich nach der Migration von Skype for Business anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (das heißt, Sie können diese Kontakte hinzufügen, löschen, verschieben, markieren, Markierung oder ändern).</span><span class="sxs-lookup"><span data-stu-id="15a3f-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="15a3f-112">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="15a3f-112">Enable users for unified contact store</span></span>

<span data-ttu-id="15a3f-113">Wenn Sie Skype for Business Server bereitstellen und die Topologie veröffentlichen, ist der Unified Contact Store standardmäßig für alle Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="15a3f-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="15a3f-114">Sie müssen keine weiteren Schritte Unternehmen, um den Unified Contact Store nach der Bereitstellung von Skype for Business Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="15a3f-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="15a3f-115">Sie können jedoch das Cmdlet " **festlegen-CsUserServicesPolicy** " verwenden, um die verfügbaren Unified Contact Store-Benutzer anzupassen.</span><span class="sxs-lookup"><span data-stu-id="15a3f-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="15a3f-116">Sie können dieses Feature Global, nach Website, nach Mandanten oder nach Einzelpersonen oder Gruppen von Personen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="15a3f-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="15a3f-117">So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="15a3f-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="15a3f-118">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="15a3f-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="15a3f-119">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="15a3f-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="15a3f-120">Wenn Sie den Unified Contact Store Global für alle Skype for Business Server-Benutzer aktivieren möchten, unter dem folgenden Cmdlet auf der Windows PowerShell-Befehlszeilenschnittstelle:</span><span class="sxs-lookup"><span data-stu-id="15a3f-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="15a3f-121">Wenn Sie den einheitlichen Kontaktspeicher für die Benutzer an einem bestimmten Standort aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="15a3f-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="15a3f-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15a3f-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="15a3f-123">Wenn Sie den einheitlichen Kontaktspeicher nach Mandant aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="15a3f-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="15a3f-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15a3f-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="15a3f-125">Wenn Sie den einheitlichen Kontaktspeicher für bestimmte Benutzer aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="15a3f-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="15a3f-126">Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="15a3f-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="15a3f-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15a3f-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="15a3f-128">Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen UCS Enabled Users erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="15a3f-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="15a3f-129">Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d. h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.</span><span class="sxs-lookup"><span data-stu-id="15a3f-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="15a3f-130">Migrieren von Benutzern zum einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="15a3f-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="15a3f-131">Die Kontakte eines Benutzers werden automatisch auf den Exchange 2013-Server migriert, wenn der Benutzer:</span><span class="sxs-lookup"><span data-stu-id="15a3f-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="15a3f-132">Dem Benutzer muss eine Benutzerdienstrichtlinie zugewiesen worden sein, für die die Option „UcsAllowed“ auf „True“ gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="15a3f-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="15a3f-133">Wurde mit einem Exchange 2013-Postfach bereitgestellt und hat sich mindestens einmal beim Postfach angemeldet.</span><span class="sxs-lookup"><span data-stu-id="15a3f-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="15a3f-134">Melden Sie sich mit einem Rich-Client für Skype for Business an.</span><span class="sxs-lookup"><span data-stu-id="15a3f-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="15a3f-135">Wenn sich der Benutzer mit einem lync-oder früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, wird die Richtlinie für Benutzer Dienste ignoriert, und die Kontakte des Benutzers verbleiben in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15a3f-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="15a3f-136">Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:</span><span class="sxs-lookup"><span data-stu-id="15a3f-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="15a3f-137">Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:</span><span class="sxs-lookup"><span data-stu-id="15a3f-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="15a3f-138">HKEY_CURRENT_USER \software\microsoft\office\15.0\lync\\<SIP-\>URL \UCS</span><span class="sxs-lookup"><span data-stu-id="15a3f-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="15a3f-139">Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.</span><span class="sxs-lookup"><span data-stu-id="15a3f-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="15a3f-140">Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus.</span><span class="sxs-lookup"><span data-stu-id="15a3f-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="15a3f-141">Geben Sie in der Befehlszeile der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="15a3f-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="15a3f-142">Wenn**Test-CsUnifiedContactStore** erfolgreich ist, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.</span><span class="sxs-lookup"><span data-stu-id="15a3f-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="15a3f-143">Zurücksetzen von migrierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="15a3f-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="15a3f-144">Wenn Sie die Unified Contact Store-Funktion zurücksetzen müssen, setzen Sie die Kontakte nur zurück, wenn Sie den Benutzer wieder in Exchange 2010 oder lync Server 2010 zurück bewegen.</span><span class="sxs-lookup"><span data-stu-id="15a3f-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="15a3f-145">Zum Zurücksetzen des Rollbacks deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus.</span><span class="sxs-lookup"><span data-stu-id="15a3f-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="15a3f-146">Nur die Ausführung von **Invoke-CsUcsRollback** allein reicht nicht aus, um einen dauerhaften Rollback zu gewährleisten, da die Migration von Unified Contact Store erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="15a3f-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="15a3f-147">Wenn ein Benutzer beispielsweise zurückgesetzt wird, weil Exchange 2013 auf Exchange 2010 zurückgesetzt wird und dann das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Unified Contact Store-Migration sieben Tage nach dem Rollback erneut initiiert, solange der Unified Contact Store ist in der Richtlinie für Benutzer Dienste weiterhin für den Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="15a3f-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="15a3f-148">Mit dem Cmdlet **Move-CsUser** wird in den folgenden Situationen automatisch der Kontaktspeicher des Benutzers von Exchange 2013 auf Skype for Business Server zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="15a3f-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="15a3f-149">Wenn Benutzer von Skype for Business Server zu Microsoft lync Server 2013 oder lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="15a3f-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="15a3f-150">Wenn Benutzer über einen Standort migriert werden, beispielsweise wenn ein Benutzer von Skype for Business Online zu Skype for Business Server lokal oder umgekehrt verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="15a3f-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="15a3f-p107">Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15a3f-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="15a3f-153">Wenn Sie Kontaktlisten exportieren, bevor die Kontakte der Benutzer nach Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, werden die Unified Contact Store-Daten und Kontaktlisten beschädigt.</span><span class="sxs-lookup"><span data-stu-id="15a3f-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="15a3f-154">Wenn Sie Benutzerdaten exportieren, nachdem Sie Benutzer zu Exchange 2013 migriert haben, führen Sie die Migration zurück, und aus einem bestimmten Grund importieren Sie die Daten nach der Migration, und die Unified Contact Store-Daten und Kontaktlisten sind beschädigt.</span><span class="sxs-lookup"><span data-stu-id="15a3f-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="15a3f-155">Bevor Sie ein Exchange-Postfach von Exchange 2013 auf Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass der Skype for Business Server-Administrator zuerst die Skype for Business Server-Benutzer Kontakte von Exchange 2013 auf Skype für zurückgesetzt hat. Business Server.</span><span class="sxs-lookup"><span data-stu-id="15a3f-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="15a3f-156">Informationen zum Rollback von Unified Contact Store-Kontakten in Skype for Business Server finden Sie unter Verfahren "So führen Sie einen Rollback für Unified Contact Store-Kontakte von Exchange 2013 zu Skype for Business Server" weiter unten in diesem Abschnitt durch.</span><span class="sxs-lookup"><span data-stu-id="15a3f-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="15a3f-157">**Wiederherstellen von Benutzerkontakten:** Wenn Sie das Cmdlet **Move-CsUser** verwenden, um Benutzer zwischen Skype for Business Server 2015 und lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das Cmdlet **Move-CsUser** den Unified Contact Store automatisch zurücksetzt, wenn Benutzer von Skype for Business Server 2015 nach lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="15a3f-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="15a3f-158">**Verschieben-CsUser** deaktiviert die Unified Contact Store-Richtlinie nicht, sodass die Migration in den Unified Contact Store wiederholt wird, wenn der Benutzer zurück zu Skype for Business Server 2015 verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="15a3f-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

