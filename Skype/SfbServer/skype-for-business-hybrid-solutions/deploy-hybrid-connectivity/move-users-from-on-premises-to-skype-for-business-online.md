---
title: Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Zusammenfassung: Informationen Sie zum Migrieren von benutzereinstellungen und Verschieben von Benutzern in Skype für Business Online.'
ms.openlocfilehash: dada94d1bc198a86a06c468dc959fa0684e706d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="416da-103">Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="416da-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="416da-104">**Zusammenfassung:** Informationen Sie zum Migrieren von benutzereinstellungen und Verschieben von Benutzern in Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="416da-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="416da-p101">Bevor Sie Nutzer tatsächlich nach Office 365 migrieren, müssen Sie zunächst sicherstellen, dass sie mit der Cloud synchronisiert sind, und Sie müssen ihnen eine Lizenz zuweisen. Dazu verwenden Sie die Office 365-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="416da-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="416da-107">Wie Sie sicherstellen, dass ein lokales Benutzerkonto mit Office 365 synchronisiert worden ist</span><span class="sxs-lookup"><span data-stu-id="416da-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="416da-108">Öffnen Sie [Office 365 Administrationscenter](https://portal.office.com/) mit einem Mandanten-Admin-Konto, für Ihre Mandanten.</span><span class="sxs-lookup"><span data-stu-id="416da-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>
    
2. <span data-ttu-id="416da-109">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und anschließend auf **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="416da-109">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="416da-110">Klicken Sie auf **Suche nach Benutzer** und geben Sie den Namen des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="416da-110">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="416da-111">Vergewissern Sie sich, dass der Benutzer angezeigt wird und dass sein Status **Synchronisiert mit Active Directory** ist.</span><span class="sxs-lookup"><span data-stu-id="416da-111">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="416da-112">Sofern der Benutzer noch nicht synchronisiert ist, sollte die nächste automatischen Synchronisierung innerhalb der nächsten drei Stunden stattfinden.</span><span class="sxs-lookup"><span data-stu-id="416da-112">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="416da-113">Sie können auch eine Synchronisierung früher erzwingen.</span><span class="sxs-lookup"><span data-stu-id="416da-113">You can also force a synchronization sooner.</span></span> <span data-ttu-id="416da-114">Weitere Informationen finden Sie unter [Verzeichnissynchronisierung erzwingen](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span><span class="sxs-lookup"><span data-stu-id="416da-114">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="416da-115">Zuweisen, indem Sie die Lizenz in Office 365 finden Sie unter [Zuweisen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="416da-115">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="416da-116">Migrieren von benutzereinstellungen zu Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="416da-116">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="416da-117">Bevor Sie die Migration von Benutzern zum Skype für Business Online beginnen, sollten Sie die Benutzerdaten zugeordnete Konten verschoben werden soll sichern.</span><span class="sxs-lookup"><span data-stu-id="416da-117">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="416da-118">Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="416da-118">Not all user data is moved with the user account.</span></span> <span data-ttu-id="416da-119">Informationen finden Sie unter [Sicherungs- und Wiederherstellungsanforderungen: Daten](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span><span class="sxs-lookup"><span data-stu-id="416da-119">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="416da-p104">Benutzereinstellungen werden zusammen mit dem Benutzerkonto verschoben. Einige lokale Einstellungen werden jedoch nicht mit dem Benutzerkonto verschoben.</span><span class="sxs-lookup"><span data-stu-id="416da-p104">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="416da-122">Verschieben von Pilotbenutzer in Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="416da-122">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="416da-123">Bevor Sie beginnen, um Benutzer nach Skype für Business Online verschieben, sollten Sie verschieben einige Pilotbenutzer zu bestätigen, dass Ihre Umgebung ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="416da-123">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="416da-124">Anschließend können Sie überprüfen, ob die Funktionen und Dienste erwartungsgemäß funktionieren, bevor Sie weitere Nutzer verschieben.</span><span class="sxs-lookup"><span data-stu-id="416da-124">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="416da-125">Um einen lokalen Benutzer in Ihrer Skype für Business Online-Mandanten zu verschieben, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell, verwenden die Administratoranmeldeinformationen für Ihre Microsoft Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="416da-125">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="416da-126">Ersetzen Sie „benutzername@contoso.com“ mit den Informationen des zu verschiebenden Benutzers.</span><span class="sxs-lookup"><span data-stu-id="416da-126">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="416da-127">Verschieben von Benutzern nach Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="416da-127">Move users to Skype for Business Online</span></span>

<span data-ttu-id="416da-128">Verschieben mehrerer Benutzer können mit dem Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) mit dem Parameter Filter auswählen die Benutzer mit einer bestimmten Eigenschaft, die Benutzerkonten, beispielsweise RegistrarPool zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="416da-128">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="416da-129">Sie können dann die zurückgegebenen Benutzer an das Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) reichen Sie wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="416da-129">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="416da-130">Sie können auch den OU - Parameter verwenden zum Abrufen von allen Benutzern in der angegebenen Organisationseinheit, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="416da-130">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="416da-131">Überprüfen von Online-Benutzereinstellungen und -Funktionen</span><span class="sxs-lookup"><span data-stu-id="416da-131">Verify online user settings and features</span></span>

<span data-ttu-id="416da-132">Mit folgenden Methoden können Sie überprüfen, ob ein Benutzer erfolgreich verschoben wurde:</span><span class="sxs-lookup"><span data-stu-id="416da-132">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="416da-p108">Zeigen Sie in der Systemsteuerung von Skype for Business Online den Status des Benutzers an. Für lokale und Onlinebenutzer werden unterschiedliche visuelle Indikatoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="416da-p108">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="416da-135">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="416da-135">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```


