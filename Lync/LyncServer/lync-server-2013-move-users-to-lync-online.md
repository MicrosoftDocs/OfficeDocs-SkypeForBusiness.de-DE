---
title: 'Lync Server 2013: Verschieben von Benutzern nach lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="24b75-102">Verschieben von Benutzern nach lync Online in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b75-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24b75-103">_**Letztes Änderungsdatum des Themas:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="24b75-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="24b75-104">Bevor Sie mit der Migration von Benutzern zu lync Online beginnen, sollten Sie die Benutzerdaten sichern, die den zu verschiebenden Konten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="24b75-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="24b75-105">Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="24b75-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="24b75-106">Informationen finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Daten](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="24b75-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="24b75-107">Migrieren von Benutzereinstellungen zu lync Online</span><span class="sxs-lookup"><span data-stu-id="24b75-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="24b75-108">Benutzereinstellungen werden zusammen mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="24b75-108">User settings are moved with the user account.</span></span> <span data-ttu-id="24b75-109">Einige lokale Einstellungen werden jedoch nicht mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="24b75-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="24b75-110">Verschieben von Pilot Benutzern nach lync Online</span><span class="sxs-lookup"><span data-stu-id="24b75-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="24b75-111">Bevor Sie beginnen, Benutzer nach lync online zu verschieben, möchten Sie möglicherweise einige Pilotbenutzer verschieben, um zu bestätigen, dass Ihre Umgebung ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="24b75-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="24b75-112">Sie können dann überprüfen, ob die lync-Features und-Dienste wie erwartet funktionieren, bevor Sie versuchen, weitere Benutzer zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="24b75-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="24b75-113">Wenn Sie einen lokalen Benutzer in ihren lync Online-Mandanten verschieben möchten, führen Sie die folgenden Cmdlets in der lync Server-Verwaltungsshell aus, und verwenden Sie die Administratoranmeldeinformationen für Ihren Microsoft Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="24b75-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="24b75-114">Ersetzen Sie „benutzername@contoso.com“ mit den Informationen des zu verschiebenden Benutzers.</span><span class="sxs-lookup"><span data-stu-id="24b75-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="24b75-115">Das Format der für den **HostedMigrationOverrideUrl** -Parameter angegebenen URL muss die URL des Pools sein, in dem der gehostete Migrationsdienst ausgeführt wird, im folgenden Format:\<https://Pool\>FQDN/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="24b75-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="24b75-116">Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.</span><span class="sxs-lookup"><span data-stu-id="24b75-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="24b75-117">**So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten**</span><span class="sxs-lookup"><span data-stu-id="24b75-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="24b75-118">Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="24b75-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="24b75-119">Öffnen Sie das **lync Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="24b75-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="24b75-120">Wenn das **lync Admin Center** angezeigt wird, wählen Sie die URL in der Adressleiste bis zu **lync.com**aus, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="24b75-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="24b75-121">Eine Beispiel-URL sieht ähnlich wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="24b75-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="24b75-122">Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:</span><span class="sxs-lookup"><span data-stu-id="24b75-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="24b75-123">Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="24b75-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="24b75-124">Die daraus resultierende URL, die dem Wert der **HostedMigrationOverrideUrl** entspricht, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="24b75-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="24b75-125">Verschieben von Benutzern nach lync Online</span><span class="sxs-lookup"><span data-stu-id="24b75-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="24b75-126">Sie können mehrere Benutzer verschieben, indem Sie das Cmdlet " [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) " mit dem-Filter-Parameter verwenden, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen, die den Benutzerkonten zugewiesen ist, wie etwa RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="24b75-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="24b75-127">Sie können die zurückgegebenen Benutzer dann an das Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) übergeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="24b75-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="24b75-128">Sie können auch den Parameter „-OU“ verwenden, um alle Benutzer in der angegebenen Organisationseinheit (Organizational Unit, OU) abzurufen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="24b75-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="24b75-129">Überprüfen der lync Online-Benutzereinstellungen und-Features</span><span class="sxs-lookup"><span data-stu-id="24b75-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="24b75-130">Mit folgenden Methoden können Sie überprüfen, ob ein Benutzer erfolgreich verschoben wurde:</span><span class="sxs-lookup"><span data-stu-id="24b75-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="24b75-131">Anzeigen des Status des Benutzers in der lync Online-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="24b75-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="24b75-132">Für lokale und Onlinebenutzer werden unterschiedliche visuelle Indikatoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="24b75-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="24b75-133">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="24b75-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

