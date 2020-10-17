---
title: 'Lync Server 2013: Zurücksetzen von migrierten Benutzern'
description: 'Lync Server 2013: Zurücksetzen migrierter Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5993bfd530c84307d3ee5be627b3ed33814be73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559541"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="b100c-103">Wiederherstellen migrierter Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b100c-103">Roll back migrated users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b100c-104">_**Letztes Änderungsstand des Themas:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="b100c-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="b100c-105">Wenn Sie ein Rollback für die Funktion des einheitlichen Kontaktspeichers ausführen müssen, führen Sie die Kontakte nur zurück, wenn Sie den Benutzer zurück in Exchange 2010 oder lync Server 2010 bewegen.</span><span class="sxs-lookup"><span data-stu-id="b100c-105">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="b100c-106">Wenn Sie ein Rollback ausführen möchten, deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus.</span><span class="sxs-lookup"><span data-stu-id="b100c-106">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="b100c-107">Das Ausführen von **Invoke-CsUcsRollback** alleine reicht nicht aus, um ein dauerhaftes Rollback sicherzustellen, da die Migration des einheitlichen Kontaktspeichers erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b100c-107">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="b100c-108">Wenn beispielsweise ein Rollback für einen Benutzer durchgeführt wird, da Exchange 2013 auf Exchange 2010 zurückgesetzt wird und das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Migration des einheitlichen Kontaktspeichers sieben Tage nach dem Rollback erneut initiiert, solange der einheitliche Kontaktspeicher für den Benutzer in der Benutzer Dienste-Richtlinie weiterhin aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b100c-108">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b100c-109">Das Cmdlet " <STRONG>CsUser</STRONG> " rollt den Kontaktspeicher des Benutzers in den folgenden Situationen automatisch von Exchange 2013 auf lync Server 2013 zurück:</span><span class="sxs-lookup"><span data-stu-id="b100c-109">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b100c-110">Wenn Benutzer von lync Server 2013 zu lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b100c-110">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="b100c-111">Wenn Benutzer über lokale Migrationen migriert werden, beispielsweise wenn ein Benutzer von lync online zu lync Server 2013 lokal verschoben wird oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="b100c-111">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b100c-p102">Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b100c-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b100c-114">Wenn Sie Kontaktlisten exportieren, bevor die Benutzer Kontakte zu Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, sind die Daten des einheitlichen Kontaktspeichers und die Kontaktlisten beschädigt.</span><span class="sxs-lookup"><span data-stu-id="b100c-114">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="b100c-115">Wenn Sie Benutzerinformationen nach dem Migrieren von Benutzern zu Exchange 2013 exportieren, die Migration zurücksetzen und dann aus irgendeinem Grund die Daten nach der Migration importieren, werden die Daten und Kontaktlisten für den einheitlichen Kontaktspeicher beschädigt.</span><span class="sxs-lookup"><span data-stu-id="b100c-115">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b100c-116">Bevor Sie ein Exchange-Postfach von Exchange 2013 in Exchange 2010 migrieren, muss der Exchange-Administrator sicherstellen, dass der lync Server Administrator zunächst die lync Server Benutzer Kontakte von Exchange 2013 auf lync Server zurückgesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="b100c-116">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="b100c-117">Informationen zum Zurücksetzen von Kontakten für den einheitlichen Kontaktspeicher auf lync Server finden Sie unter procedure to Rollback Unified Contact Store Contacts from Exchange 2013 to lync Server 2013 "weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b100c-117">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="b100c-118">Im folgenden Verfahren wird beschrieben, wie Sie ein Rollback für Benutzerkontakte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b100c-118">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="b100c-119">Wenn Sie das **Move-CsUser-** Cmdlet verwenden, um Benutzer zwischen lync Server 2013 und lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das Cmdlet **Move-CsUser** automatisch unifed Kontaktspeicher zurücksetzt, wenn Benutzer von lync Server 2013 in lync Server 2010 verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b100c-119">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="b100c-120">Mit **Move-CsUser** wird die Richtlinie für den einheitlichen Kontaktspeicher nicht deaktiviert, sodass die Migration zu einem einheitlichen Kontaktspeicher wiederholt wird, wenn der Benutzer zurück in lync Server 2013 verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="b100c-120">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="b100c-121">So führen Sie ein Rollback für Benutzer Kontakte von lync Server 2013 auf lync Server 2010 aus</span><span class="sxs-lookup"><span data-stu-id="b100c-121">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="b100c-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b100c-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b100c-p105">Deaktivieren Sie den einheitlichen Kontaktspeicher für die Benutzer, für die ein Rollback ausgeführt werden soll, damit sie nach dem Rollback nicht erneut migriert werden. (Führen Sie diesen Schritt nur aus, wenn Sie sicherstellen möchten, dass die Benutzer in Zukunft nicht erneut migriert werden.) Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher für einzelne Benutzer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="b100c-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="b100c-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b100c-125">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="b100c-126">Bevor Sie einen Benutzer aus lync Server 2013 in lync Server 2010 verschieben, führen Sie ein Rollback der Buddyliste für die angegebenen Benutzer in lync Server aus.</span><span class="sxs-lookup"><span data-stu-id="b100c-126">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b100c-127">Wenn dieser Schritt ausgelassen wird, geht die Buddy-Liste verloren.</span><span class="sxs-lookup"><span data-stu-id="b100c-127">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="b100c-p106">Führen Sie ein Rollback für die angegebenen Benutzer aus. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b100c-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="b100c-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b100c-130">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b100c-p107">Es wird davon abgeraten, mit der Option –Force das Rollback zu erzwingen. Falls Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.</span><span class="sxs-lookup"><span data-stu-id="b100c-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="b100c-133">So setzen Sie die Kontakte für den einheitlichen Kontaktspeicher von Exchange 2013 auf lync Server 2013 zurück</span><span class="sxs-lookup"><span data-stu-id="b100c-133">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="b100c-134">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b100c-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b100c-p108">Deaktivieren Sie den einheitlichen Kontaktspeicher für die Benutzer, für die ein Rollback ausgeführt werden soll, damit sie nach dem Rollback nicht erneut migriert werden. Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher für einzelne Benutzer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="b100c-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="b100c-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b100c-137">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="b100c-p109">Führen Sie ein Rollback für die angegebenen Benutzer aus. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b100c-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="b100c-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b100c-140">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b100c-141">Sie müssen zuerst den lync Server Benutzer zurücksetzen und dann das Exchange 2013 Postfach bewegen.</span><span class="sxs-lookup"><span data-stu-id="b100c-141">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="b100c-142">Dem Exchange-Administrator wird das Zurücksetzen von Exchange bis zum Abschluss des lync Server Rollbacks blockiert.</span><span class="sxs-lookup"><span data-stu-id="b100c-142">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="b100c-143">Es wird davon abgeraten, mit der Option –Force das Rollback zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b100c-143">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="b100c-144">Falls Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.</span><span class="sxs-lookup"><span data-stu-id="b100c-144">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="b100c-145">Nachdem Sie den Benutzer auf lync Server zurückgesetzt haben, kann der Exchange-Administrator den Exchange-Benutzer von Exchange 2013 auf Exchange 2010 zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="b100c-145">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

