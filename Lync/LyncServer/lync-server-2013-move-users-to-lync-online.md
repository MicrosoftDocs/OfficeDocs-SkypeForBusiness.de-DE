---
title: 'Lync Server 2013: Migrieren von Benutzern zu lync Online'
description: 'Lync Server 2013: Benutzer zu lync Online migrieren.'
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
ms.openlocfilehash: 501eda3a76cec3226831c0af3631317377cd82cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541991"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="5afee-103">Migrieren von Benutzern zu lync Online in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5afee-103">Move users to Lync Online in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5afee-104">_**Letztes Änderungsstand des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="5afee-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="5afee-105">Bevor Sie mit der Migration von Benutzern zu lync Online beginnen, sollten Sie die Benutzerdaten sichern, die den zu verschiebenden Konten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5afee-105">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="5afee-106">Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="5afee-106">Not all user data is moved with the user account.</span></span> <span data-ttu-id="5afee-107">Weitere Informationen finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="5afee-107">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="5afee-108">Migrieren von Benutzereinstellungen zu lync Online</span><span class="sxs-lookup"><span data-stu-id="5afee-108">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="5afee-109">Benutzereinstellungen werden mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="5afee-109">User settings are moved with the user account.</span></span> <span data-ttu-id="5afee-110">Einige lokale Einstellungen werden nicht mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="5afee-110">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="5afee-111">Verschieben von Pilot Benutzern nach lync Online</span><span class="sxs-lookup"><span data-stu-id="5afee-111">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="5afee-112">Bevor Sie mit dem Migrieren von Benutzern zu lync Online beginnen, sollten Sie einige Pilotbenutzer zur Bestätigung der ordnungsgemäßen Konfiguration Ihrer Umgebung migrieren.</span><span class="sxs-lookup"><span data-stu-id="5afee-112">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="5afee-113">Sie können dann überprüfen, ob lync-Features und-Dienste wie erwartet funktionieren, bevor Sie versuchen, zusätzliche Benutzer zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="5afee-113">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="5afee-114">Wenn Sie einen lokalen Benutzer zu Ihrem lync Online Mandanten migrieren möchten, führen Sie die folgenden Cmdlets im lync Server-Verwaltungsshell aus, wobei Sie die Administratoranmeldeinformationen für Ihre Microsoft 365-oder Office 365-Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="5afee-114">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="5afee-115">Ersetzen Sie "username@contoso.com" durch die Informationen für den Benutzer, den Sie wechseln möchten.</span><span class="sxs-lookup"><span data-stu-id="5afee-115">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="5afee-116">Das Format der URL, die für den **HostedMigrationOverrideUrl** -Parameter angegeben ist, muss die URL zum Pool sein, in dem der gehostete Migrationsdienst ausgeführt wird, im folgenden Format: https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="5afee-116">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="5afee-117">Sie können die URL des gehosteten Migrations Diensts ermitteln, indem Sie die URL für die lync Online-Systemsteuerung für Ihr Microsoft 365-oder Office 365-organisationskonto anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5afee-117">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="5afee-118">**So bestimmen Sie die URL des gehosteten Migrations Diensts für Ihre Organisation**</span><span class="sxs-lookup"><span data-stu-id="5afee-118">**To determine the Hosted Migration Service URL for your organization**</span></span>

1.  <span data-ttu-id="5afee-119">Melden Sie sich bei Ihrer Microsoft 365-oder Office 365-Organisation als Administrator an.</span><span class="sxs-lookup"><span data-stu-id="5afee-119">Login to your Microsoft 365 or Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="5afee-120">Öffnen Sie das **lync Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="5afee-120">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="5afee-121">Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis **lync.com**aus, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="5afee-121">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="5afee-122">Eine Beispiel-URL sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5afee-122">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="5afee-123">Ersetzen Sie **WebDir** in der URL durch den **Administrator**, was Folgendes ergibt:</span><span class="sxs-lookup"><span data-stu-id="5afee-123">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="5afee-124">Fügen Sie die folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="5afee-124">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="5afee-125">Die resultierende URL, die dem Wert des **HostedMigrationOverrideUrl**entspricht, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5afee-125">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="5afee-126">Verschieben von Benutzern nach lync Online</span><span class="sxs-lookup"><span data-stu-id="5afee-126">Moving Users to Lync Online</span></span>

<span data-ttu-id="5afee-127">Sie können mehrere Benutzer mithilfe des Cmdlets [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) mit dem Parameter – Filter migrieren, um die Benutzer auszuwählen, denen eine bestimmte Eigenschaft für die Benutzerkonten zugewiesen ist, beispielsweise RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="5afee-127">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="5afee-128">Sie können dann die zurückgegebenen Benutzer an das Cmdlet " [CsUser" weiter](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) leiten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5afee-128">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="5afee-129">Sie können auch den Parameter "– OU" verwenden, um alle Benutzer in der angegebenen Organisationseinheit abzurufen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5afee-129">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="5afee-130">Überprüfen lync Online Benutzereinstellungen und-Features</span><span class="sxs-lookup"><span data-stu-id="5afee-130">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="5afee-131">Sie können sicherstellen, dass der Benutzer auf folgende Weise erfolgreich verschoben wurde:</span><span class="sxs-lookup"><span data-stu-id="5afee-131">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="5afee-132">Zeigen Sie den Status des Benutzers in der lync Online-Systemsteuerung an.</span><span class="sxs-lookup"><span data-stu-id="5afee-132">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="5afee-133">Der visuelle Indikator für lokale Benutzer und Online Benutzer ist unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="5afee-133">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="5afee-134">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="5afee-134">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

