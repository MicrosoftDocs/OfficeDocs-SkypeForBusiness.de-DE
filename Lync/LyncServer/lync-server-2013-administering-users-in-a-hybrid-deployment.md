---
title: 'Lync Server 2013: Verwalten von Benutzern in einer hybridbereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b09ca3c5a80215c0a2d63a018150361671df6859
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="a014c-102">Verwalten von Benutzern in einer hybriden lync Server 2013-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a014c-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a014c-103">_**Letztes Änderungsstand des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="a014c-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="a014c-104">Sie können Benutzereinstellungen und Richtlinien für Benutzer, die zu lync Online migriert wurden, mithilfe der im Microsoft Office 365 Online-Portal verfügbaren Benutzerverwaltungsfunktionen verwalten.</span><span class="sxs-lookup"><span data-stu-id="a014c-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="a014c-105">Sie müssen sich mit Ihrem mandantenadministrator Konto anmelden, um Verwaltungsaufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a014c-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="a014c-106">Verschieben von Benutzern zurück zu lokal</span><span class="sxs-lookup"><span data-stu-id="a014c-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="a014c-107">Dieser Abschnitt gilt nur für Benutzer, die lokal erstellt und für lync aktiviert und dann von einer lokalen Bereitstellung in lync Online verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="a014c-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="a014c-108">Wenn Sie Benutzer verschieben möchten, die in lync online erstellt wurden (und nicht immer für lync in einer lokalen Bereitstellung aktiviert wurden), sehen Sie, wie Sie <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Benutzer von lync Online in lync lokal in lync Server 2013 verschieben</A>.</span><span class="sxs-lookup"><span data-stu-id="a014c-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="a014c-109">Führen Sie die folgenden Cmdlets aus, um einen Benutzer von lync Online zurück zu lokal in lync zu migrieren:</span><span class="sxs-lookup"><span data-stu-id="a014c-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="a014c-110">Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, in folgendem Format:</span><span class="sxs-lookup"><span data-stu-id="a014c-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="a014c-111">Https://\<-Pool\>-FQDN/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="a014c-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="a014c-112">Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Office 365 organisationskonto anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a014c-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 organization account.</span></span>

<span data-ttu-id="a014c-113">**So bestimmen Sie die URL des gehosteten Migrations Diensts für Ihre Office 365 Organisation**</span><span class="sxs-lookup"><span data-stu-id="a014c-113">**To determine the Hosted Migration Service URL for your Office 365 organization**</span></span>

1.  <span data-ttu-id="a014c-114">Melden Sie sich als Administrator bei Ihrer Office 365 Organisation an.</span><span class="sxs-lookup"><span data-stu-id="a014c-114">Login to your Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="a014c-115">Öffnen Sie das **lync Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="a014c-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="a014c-116">Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="a014c-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="a014c-117">Eine Beispiel-URL sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="a014c-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="a014c-118">Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:</span><span class="sxs-lookup"><span data-stu-id="a014c-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="a014c-119">Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="a014c-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="a014c-120">Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="a014c-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

