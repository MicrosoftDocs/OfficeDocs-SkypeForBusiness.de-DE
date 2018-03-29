---
title: Konfigurieren von Archivierungsoptionen zum Beheben von Fehlern in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Zusammenfassung: Erfahren Sie, wie im- und konferenzsitzungen im Fall einer Skype für Business Server 2015 Fehler zu blockieren, die Archivierung verhindern würden.'
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a><span data-ttu-id="f2374-103">Konfigurieren von Archivierungsoptionen zum Beheben von Fehlern in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f2374-103">Configure archiving options to handle failures in Skype for Business Server 2015</span></span>

<span data-ttu-id="f2374-104">**Zusammenfassung:** Erfahren Sie, wie im- und konferenzsitzungen im Fall einer Skype für Business Server 2015 Fehler zu blockieren, die Archivierung verhindern würden.</span><span class="sxs-lookup"><span data-stu-id="f2374-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server 2015 failure that would prevent archiving.</span></span>
  
<span data-ttu-id="f2374-105">Wenn die Archivierung für Ihre Organisation erforderlich ist, können Sie im- und konferenzsitzungen im Fall einer Skype für Business Serverausfall blockieren, die Archivierung verhindern würden.</span><span class="sxs-lookup"><span data-stu-id="f2374-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="f2374-106">Dies wird manchmal auch als kritischer Modus bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f2374-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="f2374-107">Wenn beispielsweise ein Problem mit einem Speicherdienst auftritt, würde Chat für Nutzer blockiert, die für die Archivierung aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f2374-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="f2374-108">Nach der Fehlerkorrektur werden Chat und Konferenzen automatisch wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f2374-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="f2374-109">Konfigurieren des kritischen Modus mit der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f2374-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="f2374-110">So legen Sie fest, ob Kommunikationssitzungen bei einem Ausfall, der die Archivierung verhindern würde, erlaubt sein sollen:</span><span class="sxs-lookup"><span data-stu-id="f2374-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="f2374-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f2374-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f2374-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2374-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f2374-113">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f2374-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f2374-114">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f2374-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f2374-115">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f2374-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="f2374-116">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f2374-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="f2374-117">Konfigurieren des kritischen Modus mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2374-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="f2374-118">Sie können auch angeben, ob kommunikationssitzungen bei einem Ausfall zugelassen werden soll, die mit dem **Set-CsArchivingConfiguration** -Cmdlet mit dem Parameter BlockOnArchiveFailure Archivierung verhindern würden.</span><span class="sxs-lookup"><span data-stu-id="f2374-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="f2374-119">Beispielsweise wird mit der folgende Befehl Communications im Fall eines Fehlers Archivierung deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="f2374-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="f2374-120">Mit dem nächsten Befehl kann die Kommunikation bei einem Archivierungsfehler aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="f2374-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="f2374-121">Weitere Informationen finden Sie im Hilfethema zum [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f2374-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

