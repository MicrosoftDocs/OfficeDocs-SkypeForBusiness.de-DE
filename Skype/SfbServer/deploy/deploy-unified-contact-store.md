---
title: 'Bereitstellen des einheitlichen Kontaktspeicher in Skype für Business Server '
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Zusammenfassung: Den einheitlichen Kontaktspeicher in Skype für Business Server zu aktivieren.'
ms.openlocfilehash: 36515e9542a18d422254292b0cf2a2b4ef937178
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978221"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="8cc23-103">Bereitstellen des einheitlichen Kontaktspeicher in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8cc23-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="8cc23-104">**Zusammenfassung:** Aktivieren Sie den einheitlichen Kontaktspeicher in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cc23-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="8cc23-105">Aktivieren des einheitlichen Kontaktspeicher in Skype für Business Server erfordert keine Einstellungen Topologie.</span><span class="sxs-lookup"><span data-stu-id="8cc23-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="8cc23-106">Zur Aktivierung des einheitlichen Kontaktspeichers für Benutzer müssen Sie die folgenden Punkte sicherstellen:</span><span class="sxs-lookup"><span data-stu-id="8cc23-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="8cc23-107">Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).</span><span class="sxs-lookup"><span data-stu-id="8cc23-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="8cc23-108">Benutzer melden Sie sich mit Skype für Unternehmen mindestens einmal.</span><span class="sxs-lookup"><span data-stu-id="8cc23-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="8cc23-109">Nachdem die Kontakte eines Benutzers migriert wurden die automatisch geschieht, wenn ein Benutzer sich mit Skype für Unternehmen anmeldet, kann der Benutzer zugreifen und ihre Skype für Geschäftskontakte von Skype für Geschäftskunden, Outlook 2013 und Outlook Web Access verwalten.</span><span class="sxs-lookup"><span data-stu-id="8cc23-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="8cc23-110">Der Benutzer hat keinen Skype für Unternehmen zum Verwalten ihrer Kontakte aus Outlook oder Outlook Web Access angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="8cc23-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cc23-111">Wenn ein Benutzer von Skype für Unternehmen nach der Migration anmeldet, Kontakte und Gruppen verfügbar sind und auf dem neuesten Stand, aber der Benutzer ist nicht möglich (, die hinzugefügt wird, löschen, verschieben, markieren, Aufheben der Markierung von oder zu ändern,) verwalten die Kontakte.</span><span class="sxs-lookup"><span data-stu-id="8cc23-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="8cc23-112">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="8cc23-112">Enable users for unified contact store</span></span>

<span data-ttu-id="8cc23-113">Wenn Sie Skype für Business Server bereitstellen und veröffentlichen Sie die Topologie, ist einheitlichen Kontaktspeicher für alle Benutzer in der Standardeinstellung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8cc23-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="8cc23-114">Sie müssen nicht keine weitere Aktion zum einheitlichen Kontaktspeicher nach der Bereitstellung von Skype für Business Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8cc23-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="8cc23-115">Das Cmdlet **"Set-csuserservicespolicy"** können Sie jedoch anpassen, welche Benutzer verfügbaren Kontaktspeicher unified haben.</span><span class="sxs-lookup"><span data-stu-id="8cc23-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="8cc23-116">Sie können dieses Feature Global, von der Website, von Mandanten oder nach Personen oder Gruppen einzelner Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8cc23-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="8cc23-117">So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="8cc23-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="8cc23-118">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Unternehmen**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8cc23-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8cc23-119">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8cc23-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="8cc23-120">Inter Sie zum einheitlichen Kontaktspeicher global für alle Skype für Business Server-Benutzer zu aktivieren, an der Windows PowerShell-Befehlszeilenschnittstelle das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="8cc23-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="8cc23-121">Wenn Sie den einheitlichen Kontaktspeicher für die Benutzer an einem bestimmten Standort aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8cc23-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="8cc23-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cc23-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="8cc23-123">Wenn Sie den einheitlichen Kontaktspeicher nach Mandant aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8cc23-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="8cc23-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cc23-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="8cc23-125">Wenn Sie den einheitlichen Kontaktspeicher für bestimmte Benutzer aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8cc23-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="8cc23-126">Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cc23-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="8cc23-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cc23-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="8cc23-p104">Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen UCS Enabled Users erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist. Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d. h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8cc23-p104">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="8cc23-130">Migrieren von Benutzern zum einheitlichen Kontaktspeicher</span><span class="sxs-lookup"><span data-stu-id="8cc23-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="8cc23-131">Kontakte eines Benutzers werden automatisch auf den Exchange 2013-Server migriert, wenn der Benutzer:</span><span class="sxs-lookup"><span data-stu-id="8cc23-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="8cc23-132">Dem Benutzer muss eine Benutzerdienstrichtlinie zugewiesen worden sein, für die die Option „UcsAllowed“ auf „True“ gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="8cc23-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="8cc23-133">Mit einem Exchange 2013-Postfach bereitgestellt und mindestens einmal in das Postfach angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="8cc23-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="8cc23-134">Protokolle in mithilfe einer Skype für Business-rich-Client.</span><span class="sxs-lookup"><span data-stu-id="8cc23-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="8cc23-135">Wenn der Benutzer sich mit einem Lync oder einem früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, der benutzerdiensterichtlinie ignoriert, und die Kontakte des Benutzers verbleiben in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="8cc23-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="8cc23-136">Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden:</span><span class="sxs-lookup"><span data-stu-id="8cc23-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="8cc23-137">Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:</span><span class="sxs-lookup"><span data-stu-id="8cc23-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="8cc23-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< SIP-URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="8cc23-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="8cc23-139">Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel einen Wert von InUCSMode mit einem Wert 2165.</span><span class="sxs-lookup"><span data-stu-id="8cc23-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="8cc23-140">Führen Sie das **Test-CsUnifiedContactStore** -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8cc23-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="8cc23-141">Geben Sie bei der Skype für Business Server-Verwaltungsshell Befehlszeile aus Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8cc23-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="8cc23-142">Wenn der **Test-CsUnifiedContactStore** erfolgreich, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.</span><span class="sxs-lookup"><span data-stu-id="8cc23-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="8cc23-143">Zurücksetzen von migrierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="8cc23-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="8cc23-144">Wenn Sie einen Rollback müssen der Kontakt unified Feature speichern, Rollback für die Kontakte aus, nur, wenn Sie den Benutzer wieder zurück in Exchange 2010 oder Lync Server 2010 verschieben.</span><span class="sxs-lookup"><span data-stu-id="8cc23-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="8cc23-145">Wenn Sie ein Rollback, deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie das Cmdlet " **Invoke-CsUcsRollback** ".</span><span class="sxs-lookup"><span data-stu-id="8cc23-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="8cc23-146">Nur ausführen **Invoke-CsUcsRollback** allein ist nicht genug sind, um permanente Rollback, stellen Sie sicher, da einheitlichen Kontaktspeicher Migration wird erneut gestartet werden, wenn die Richtlinie nicht deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8cc23-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="8cc23-147">Beispielsweise wenn ein Benutzer rückgängig gemacht werden, da Exchange 2013 ein auf Exchange 2010 Rollback wird, und klicken Sie dann das Postfach des Benutzers in Exchange 2013 verschoben wird die einheitlichen Kontaktspeicher Migration erneut sieben Tage nach der Rollback initiiert werden, solange unified Contact speichern ist für den Benutzer in der Benutzerrichtlinie Services noch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8cc23-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="8cc23-148">Das Cmdlet **Move-CsUser** automatisch ein Rollback Kontaktspeicher des Benutzers von Exchange 2013 um Skype für Business Server in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="8cc23-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="8cc23-149">Wenn Benutzer von Skype für Business Server auf Microsoft Lync Server 2013 oder Lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="8cc23-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="8cc23-150">Wenn Benutzer firewallübergreifenden vor Ort, beispielsweise wenn ein Benutzer von Skype für Business Online auf Skype für Business Server lokal, verschoben wird migriert werden oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="8cc23-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="8cc23-p107">Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cc23-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="8cc23-153">Wenn Sie Kontaktlisten exportieren, bevor Kontakte des Benutzers in Exchange 2013 migriert werden und anschließend, nach der Migration die gleichen Daten importieren werden den einheitlichen Kontaktspeicher Daten und Kontaktlisten beschädigt.</span><span class="sxs-lookup"><span data-stu-id="8cc23-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="8cc23-154">Wenn Sie nach dem Migrieren von Benutzern zu Exchange 2013 Benutzerdaten exportieren, Rollbacks der Migration und dann aus irgendeinem Grund, dass Sie nach der Migration die Daten importieren die unified Contact Daten zu speichern und Kontaktlisten beschädigt.</span><span class="sxs-lookup"><span data-stu-id="8cc23-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="8cc23-155">Bevor Sie ein Exchange-Postfach von Exchange 2013 in Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass die Skype für Business Server-Administrator zuerst die Skype für Business Server Benutzerkontakte von Exchange 2013 Skype für ein Rollback auf hat Business-Server.</span><span class="sxs-lookup"><span data-stu-id="8cc23-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="8cc23-156">Zum einheitlichen Kontaktspeicher Kontakte Skype für Business Server wiederherstellen, finden Sie Verfahren "so Rollback für Kontakte des einheitlichen Kontaktspeicher von Exchange 2013 an Skype For Business Server" weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="8cc23-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="8cc23-157">**Wie Rollback für Benutzerkontakte:** Wenn Sie das Cmdlet **Move-CsUser** zum Verschieben von Benutzern zwischen Skype für Business Server 2015 und Lync Server 2010 verwenden, können Sie diese Schritte überspringen, da das **Move-CsUser** -Cmdlet automatisch einheitlichen Kontaktspeicher Rollback ausführt, wenn es von Skype für Benutzer wechselt Business Server 2015 zu Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8cc23-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="8cc23-158">**Move-CsUser** wird nicht einheitlichen Kontaktspeicher-Richtlinie deaktiviert, damit die Migration zu einheitlichen Kontaktspeicher wiederholt werden soll, wenn der Benutzer wieder in Skype für Business Server 2015 verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="8cc23-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

