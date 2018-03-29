---
title: Anwenden einer Richtlinie auf Benutzer in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Archivierungsrichtlinie für Benutzer in Skype für Business Server 2015 zuweisen.'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a><span data-ttu-id="a4020-103">Anwenden einer Richtlinie auf Benutzer in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4020-103">Apply an archiving policy to users in Skype for Business Server 2015</span></span>

<span data-ttu-id="a4020-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Benutzer in Skype für Business Server 2015 zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a4020-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a4020-105">Wenn Sie eine erstellt haben oder weitere Benutzerrichtlinien für die Archivierung für Benutzer, die unter Skype für Business Server 2015 verwaltet, können Sie die archivierungsunterstützung für bestimmte Benutzer durch Anwenden geeigneten Richtlinien auf die Benutzer oder Benutzergruppen implementieren.</span><span class="sxs-lookup"><span data-stu-id="a4020-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server 2015, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="a4020-106">Wenn Sie eine Richtlinie zur Unterstützung der Archivierung der internen Kommunikation erstellen, können Sie es beispielsweise auf mindestens einen Benutzer oder eine Benutzergruppe zur Unterstützung der Archivierung von Skype für Business Server 2015 Kommunikation der Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="a4020-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server 2015 communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4020-107">Wenn Sie Microsoft Exchange-Integration für die Bereitstellung, Exchange In-Place Hold Policies Steuerelement aktiviert, ob Archivierung aktiviert ist, für die Benutzer, die sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren.</span><span class="sxs-lookup"><span data-stu-id="a4020-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a4020-108">Weitere Informationen hierzu finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../plan-your-deployment/archiving/archiving.md) und [Integration mit Exchange-Speicher für Skype für Business Server 2015 konfigurieren](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="a4020-108">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="a4020-109">Anwenden einer Benutzerrichtlinie mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a4020-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="a4020-110">So wenden Sie eine Benutzerrichtlinie mithilfe der Systemsteuerung an:</span><span class="sxs-lookup"><span data-stu-id="a4020-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="a4020-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a4020-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a4020-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a4020-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a4020-113">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a4020-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="a4020-114">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a4020-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a4020-115">Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Benutzerrichtlinie, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a4020-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a4020-116">Die ** \<automatische\> ** Einstellungen gelten die Standardeinstellungen für Server-Installation.</span><span class="sxs-lookup"><span data-stu-id="a4020-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="a4020-117">Diese Einstellungen werden automatisch vom Server angewendet.</span><span class="sxs-lookup"><span data-stu-id="a4020-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="a4020-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a4020-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="a4020-119">Anwenden einer Benutzerrichtlinie mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4020-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="a4020-120">Sie können auch eine Benutzerrichtlinie anzuwenden, mit dem Windows PowerShell **Grant-CsArchivingPolicy** -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4020-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a4020-121">Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a4020-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="a4020-122">Dieser Befehl weist die benutzerbasierte Archivierungsrichtlinie "redmondarchivingpolicy" für alle Benutzer, die haben Konten, die sich in der Registrierung Pool Atl-Cs-001.contoso.com. Ausführliche Informationen zu den Parameter "Filter", die in dieser Befehl verwendet finden Sie unter der [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) -Cmdlet-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a4020-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com. For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

<span data-ttu-id="a4020-p104">Mithilfe des folgenden Befehls wird die Zuordnung aller benutzerbezogenen Archivierungsrichtlinien aufgehoben, die zuvor Jonas Baar zugeordnet wurden. Nach dem Aufheben der Zuordnung der benutzerbezogenen Richtlinie wird Jonas Baar automatisch mithilfe der globalen Richtlinie oder, sofern vorhanden, mithilfe seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a4020-p104">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="a4020-126">Weitere Informationen hierzu finden Sie unter [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) -Cmdlet-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a4020-126">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

