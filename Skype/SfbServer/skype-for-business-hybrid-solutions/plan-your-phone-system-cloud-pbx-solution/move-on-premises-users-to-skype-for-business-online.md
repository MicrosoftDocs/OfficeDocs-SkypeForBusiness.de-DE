---
title: Migrieren von lokalen Benutzern zu Skype für Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Zusammenfassung: Informationen zum Verschieben von lokalen Benutzern Skype für Business Online.'
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="97a5e-103">Migrieren von lokalen Benutzern zu Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="97a5e-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="97a5e-104">**Zusammenfassung:** Informationen zum Verschieben von lokalen Benutzern zu Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="97a5e-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="97a5e-105">Lync Phone Edition-Geräte MÜSSEN in Ihrer lokalen Umgebung auf die minimal erforderliche Firmware aktualisiert werden, BEVOR nach Skype for Business Online umgezogen wird.</span><span class="sxs-lookup"><span data-stu-id="97a5e-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="97a5e-106">Wenn Sie Ihre Benutzer vor einer Aktualisierung der Firma von der lokalen Verwendung zur Onlinebereitstellung übertragen, können diese Benutzer mit ihren Telefonen keine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="97a5e-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="97a5e-107">Um dieses Problem zu beheben, müssen die Benutzer zur lokalen Umgebung zurückübertragen werden, damit ihre Telefone dort auf die minimal erforderliche Firmware aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="97a5e-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="97a5e-108">VERSUCHEN SIE NICHT; VOR DEM ZURÜCKÜBERTRAGEN DER BENUTZER ZU IHRER LOKALEN UMGEBUNG AUF DIE MINIMAL ERFORDERLICHE FIRMWARE ZU AKTUALISIEREN ODER EIN HARDRESET DER TELEFONE DURCHZUFÜHREN.</span><span class="sxs-lookup"><span data-stu-id="97a5e-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="97a5e-109">Wenn ein Hardreset durchgeführt wird, während das Gerät nicht mit der minimal erforderlichen Firmware ausgestattet ist, nutzt das Telefon standardmäßig die PIN-Authentifizierung, die in Skype for Business Online nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="97a5e-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="97a5e-110">Weitere Informationen finden Sie unter [Abrufen von Telefonen für Skype für Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="97a5e-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="97a5e-111">Dies ist ein optionaler Schritt, der erforderlich ist, nur, wenn Sie lokale Benutzer auf Skype für Business Online verschieben.</span><span class="sxs-lookup"><span data-stu-id="97a5e-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="97a5e-112">Bevor Sie beginnen, um Benutzer zu Skype für Business Online zu verschieben, überprüfen Sie, dass die Skype für Business Online Connector (Windows PowerShell-Modul) auf Front-End-Servern bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="97a5e-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="97a5e-113">Wenn es nicht der Fall ist, können Sie es aus [dem Downloadcenter](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="97a5e-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="97a5e-114">Für die Vorbereitung Ihres AD müssen Sie Azure AD Connect konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="97a5e-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="97a5e-115">Die Version von AAD, die Sie verwenden, muss wenigstens Version 1.0.9125.0 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="97a5e-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="97a5e-116">Wenn Sie mit einer früheren Version der AAD Connect-Werkzeuge oder DirSync arbeiten, führen Sie ein Upgrade auf die unterstützte Version durch.</span><span class="sxs-lookup"><span data-stu-id="97a5e-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="97a5e-117">Sie können aber auch ein Upgrade Ihrer aktuellen Installation durchführen und alle benutzerdefinierten Regeln beibehalten, die Sie in Ihrer Umgebung definiert haben.</span><span class="sxs-lookup"><span data-stu-id="97a5e-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="97a5e-118">Verschieben von Benutzern, die entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell in der lokalen Bereitstellung verwenden, jedoch benötigen Sie Administratorberechtigungen für Ihre Office 365-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="97a5e-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="97a5e-119">Verschieben von Benutzern mithilfe von Skype für die Business-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="97a5e-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="97a5e-120">Zum Verschieben eines Benutzers zu Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="97a5e-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="97a5e-121">Von einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder der csadministrator zugewiesen ist, melden Sie sich an einem beliebigen Computer in Ihrer internen Bereitstellung mit Skype für Business Server oder auf mindestens Skype für die Business Server-Verwaltungstools installiert.</span><span class="sxs-lookup"><span data-stu-id="97a5e-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="97a5e-122">Öffnen Sie auf das Startmenü oder desktop-Verknüpfung die Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="97a5e-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="97a5e-123">Sie können auch die Skype Business Server-Systemsteuerung zugreifen, indem die Admin-URL verwenden, wenn Sie eine konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="97a5e-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="97a5e-124">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="97a5e-125">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="97a5e-126">Klicken Sie auf den Benutzer, auf das **Aktionsmenü** und anschließend auf **Ausgewählte Benutzer zu Skype for Business Online verschieben**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="97a5e-127">Lesen Sie die Informationen auf der Seite **Verschieben von Benutzern zu Skype for Business Online** und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="97a5e-128">Auf der nächsten Seite Wenn Sie nicht noch zu Office 365 angemeldet sind, klicken Sie auf **Anmelden bei Office 365**, Anmeldeinformationen Sie Ihre, und klicken Sie auf **OK** und **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="97a5e-129">Vergewissern Sie sich, dass die Anzahl der zu verschiebenden Benutzer richtig ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="97a5e-130">Lesen Sie auf der nächsten Seite die Ergebnisse durch und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="97a5e-131">Verschieben von Benutzern mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="97a5e-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="97a5e-132">Um einen lokalen Benutzer in Ihrer Skype für Business Online-Mandanten zu verschieben, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell, verwenden die Administratoranmeldeinformationen für Ihre Microsoft Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="97a5e-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="97a5e-133">Ersetzen Sie „benutzername@contoso.com“ mit den Informationen des zu verschiebenden Benutzers.</span><span class="sxs-lookup"><span data-stu-id="97a5e-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="97a5e-134">Das Format der URL für der **HostedMigrationOverrideUrl** -Parameter die URL auf den Pool sein muss, auf dem der Migration gehosteten Dienst wird, im folgenden Format ausgeführt, angegeben: _Https://\<Pool-FQDN\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="97a5e-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="97a5e-135">Die URL der Migration gehosteter Dienst können Sie bestimmen, indem Sie die URL für die Skype für Business Online Admin Center für Ihre Office 365-mandantenkontos anzeigen.</span><span class="sxs-lookup"><span data-stu-id="97a5e-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97a5e-136">Bei der URL muss die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="97a5e-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="97a5e-137">So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="97a5e-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="97a5e-138">Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="97a5e-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="97a5e-139">Öffnen Sie das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="97a5e-140">Wenn das **Skype for Business Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:</span><span class="sxs-lookup"><span data-stu-id="97a5e-140">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="97a5e-141">Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten:</span><span class="sxs-lookup"><span data-stu-id="97a5e-141">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="97a5e-142">Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationService.svc**.</span><span class="sxs-lookup"><span data-stu-id="97a5e-142">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="97a5e-143">Ergebnis-URL, die den Wert der **HostedMigrationOverrideUrl**ist, sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="97a5e-143">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

