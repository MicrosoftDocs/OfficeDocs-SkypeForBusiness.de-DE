---
title: 'Lync Server 2013: Verwalten von Benutzern in einer hybridbereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="e8391-102">Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="e8391-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8391-103">_**Letztes Änderungsdatum des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="e8391-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="e8391-104">Sie können Benutzereinstellungen und Richtlinien für Benutzer verwalten, die nach lync Online migriert wurden, indem Sie die Benutzer Verwaltungsfeatures verwenden, die im Microsoft Office 365 Online-Portal zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e8391-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="e8391-105">Zum Ausführen von Verwaltungsaufgaben müssen Sie sich mit Ihrem Mandantenadministratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="e8391-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="e8391-106">Verschieben von Benutzern zurück in den lokalen Standort</span><span class="sxs-lookup"><span data-stu-id="e8391-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="e8391-107">Dieser Abschnitt gilt nur für Benutzer, die für lync lokal erstellt und aktiviert wurden und dann von einer lokalen Bereitstellung zu lync Online verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="e8391-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="e8391-108">Wenn Sie Benutzer verschieben möchten, die in lync online erstellt wurden (und in einer lokalen Bereitstellung nicht immer für lync aktiviert wurden), lesen Sie verschieben <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">von Benutzern aus lync Online in lync lokal in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e8391-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="e8391-109">Führen Sie die folgenden Cmdlets aus, um einen Benutzer aus lync Online zurück in lync lokal zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="e8391-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="e8391-110">Das Format der für den Parameter **HostedMigrationOverrideUrl** angegebenen URL muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, und muss folgendes Format haben:</span><span class="sxs-lookup"><span data-stu-id="e8391-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="e8391-111">Https://\<-Pool\>-FQDN-/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="e8391-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="e8391-112">Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e8391-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="e8391-113">**So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten**</span><span class="sxs-lookup"><span data-stu-id="e8391-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="e8391-114">Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="e8391-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="e8391-115">Öffnen Sie das **lync Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="e8391-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="e8391-116">Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis zu **lync.com**aus, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="e8391-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="e8391-117">Eine Beispiel-URL sieht ähnlich wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="e8391-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="e8391-118">Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:</span><span class="sxs-lookup"><span data-stu-id="e8391-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="e8391-119">Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="e8391-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="e8391-120">Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="e8391-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

