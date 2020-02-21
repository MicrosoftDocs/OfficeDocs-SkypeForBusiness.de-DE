---
title: 'Lync Server 2013: Migrieren von Benutzern zu lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f490a50ade6c10d37a478729c46a5545970afb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="f1d65-102">Migrieren von Benutzern zu lync Online in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1d65-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1d65-103">_**Letztes Änderungsstand des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="f1d65-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="f1d65-104">Bevor Sie mit der Migration von Benutzern zu lync Online beginnen, sollten Sie die Benutzerdaten sichern, die den zu verschiebenden Konten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f1d65-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="f1d65-105">Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="f1d65-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="f1d65-106">Weitere Informationen finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="f1d65-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="f1d65-107">Migrieren von Benutzereinstellungen zu lync Online</span><span class="sxs-lookup"><span data-stu-id="f1d65-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="f1d65-108">Benutzereinstellungen werden mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="f1d65-108">User settings are moved with the user account.</span></span> <span data-ttu-id="f1d65-109">Einige lokale Einstellungen werden nicht mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="f1d65-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="f1d65-110">Verschieben von Pilot Benutzern nach lync Online</span><span class="sxs-lookup"><span data-stu-id="f1d65-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="f1d65-111">Bevor Sie mit dem Migrieren von Benutzern zu lync Online beginnen, sollten Sie einige Pilotbenutzer zur Bestätigung der ordnungsgemäßen Konfiguration Ihrer Umgebung migrieren.</span><span class="sxs-lookup"><span data-stu-id="f1d65-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="f1d65-112">Sie können dann überprüfen, ob lync-Features und-Dienste wie erwartet funktionieren, bevor Sie versuchen, zusätzliche Benutzer zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f1d65-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="f1d65-113">Wenn Sie einen lokalen Benutzer zu Ihrem lync Online Mandanten migrieren möchten, führen Sie die folgenden Cmdlets im lync Server-Verwaltungsshell aus, wobei Sie die Administratoranmeldeinformationen für Ihren Microsoft Office 365-Mandanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1d65-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="f1d65-114">Ersetzen Sie "username@contoso.com" durch die Informationen für den Benutzer, den Sie wechseln möchten.</span><span class="sxs-lookup"><span data-stu-id="f1d65-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="f1d65-115">Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird,\<im folgenden\>Format: https://Pool FQDN/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="f1d65-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="f1d65-116">Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1d65-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="f1d65-117">**So bestimmen Sie die URL des gehosteten Migrations Diensts für den Office 365 Mandanten**</span><span class="sxs-lookup"><span data-stu-id="f1d65-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="f1d65-118">Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="f1d65-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="f1d65-119">Öffnen Sie das **lync Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="f1d65-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="f1d65-120">Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="f1d65-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="f1d65-121">Eine Beispiel-URL sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f1d65-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="f1d65-122">Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:</span><span class="sxs-lookup"><span data-stu-id="f1d65-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="f1d65-123">Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="f1d65-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="f1d65-124">Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f1d65-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="f1d65-125">Verschieben von Benutzern nach lync Online</span><span class="sxs-lookup"><span data-stu-id="f1d65-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="f1d65-126">Sie können mehrere Benutzer mithilfe des Cmdlets [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) mit dem Parameter – Filter migrieren, um die Benutzer auszuwählen, denen eine bestimmte Eigenschaft für die Benutzerkonten zugewiesen ist, beispielsweise RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="f1d65-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="f1d65-127">Sie können dann die zurückgegebenen Benutzer an das Cmdlet " [CsUser" weiter](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) leiten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1d65-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="f1d65-128">Sie können auch den Parameter "– OU" verwenden, um alle Benutzer in der angegebenen Organisationseinheit abzurufen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f1d65-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="f1d65-129">Überprüfen lync Online Benutzereinstellungen und-Features</span><span class="sxs-lookup"><span data-stu-id="f1d65-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="f1d65-130">Sie können sicherstellen, dass der Benutzer auf folgende Weise erfolgreich verschoben wurde:</span><span class="sxs-lookup"><span data-stu-id="f1d65-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="f1d65-131">Zeigen Sie den Status des Benutzers in der lync Online-Systemsteuerung an.</span><span class="sxs-lookup"><span data-stu-id="f1d65-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="f1d65-132">Der visuelle Indikator für lokale Benutzer und Online Benutzer ist unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="f1d65-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="f1d65-133">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f1d65-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

