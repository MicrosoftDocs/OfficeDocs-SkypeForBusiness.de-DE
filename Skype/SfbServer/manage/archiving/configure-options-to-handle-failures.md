---
title: Konfigurieren von Archivierungsoptionen zur Behandlung von Fehlern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Chat-und Konferenzsitzungen blockieren, wenn ein Skype for Business Server-Fehler auftritt, der die Archivierung verhindert.'
ms.openlocfilehash: c1a6b9930d9f27e9d679710708141c0394c41dc4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818967"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="908cd-103">Konfigurieren von Archivierungsoptionen zur Behandlung von Fehlern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="908cd-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="908cd-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Chat-und Konferenzsitzungen blockieren, wenn ein Skype for Business Server-Fehler auftritt, der die Archivierung verhindert.</span><span class="sxs-lookup"><span data-stu-id="908cd-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="908cd-105">Wenn die Archivierung eine Voraussetzung für Ihre Organisation ist, können Sie im Fall eines Skype for Business Server-Fehlers Chat-und Konferenzsitzungen blockieren, die die Archivierung verhindern.</span><span class="sxs-lookup"><span data-stu-id="908cd-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="908cd-106">Dies wird manchmal auch als kritischer Modus bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="908cd-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="908cd-107">Wenn beispielsweise ein Problem mit einem Speicherdienst auftritt, würde Chat für Nutzer blockiert, die für die Archivierung aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="908cd-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="908cd-108">Nach der Fehlerkorrektur werden Chat und Konferenzen automatisch wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="908cd-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="908cd-109">Konfigurieren des kritischen Modus mit der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="908cd-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="908cd-110">So legen Sie fest, ob Kommunikationssitzungen bei einem Ausfall, der die Archivierung verhindern würde, erlaubt sein sollen:</span><span class="sxs-lookup"><span data-stu-id="908cd-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="908cd-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="908cd-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="908cd-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="908cd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="908cd-113">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="908cd-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="908cd-114">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="908cd-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="908cd-115">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.</span><span class="sxs-lookup"><span data-stu-id="908cd-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="908cd-116">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="908cd-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="908cd-117">Konfigurieren des kritischen Modus mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="908cd-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="908cd-118">Sie können auch angeben, ob Kommunikationssitzungen zulässig sein sollen, wenn ein Fehler auftritt, der das Archivieren mithilfe des Cmdlets "CsArchivingConfiguration" mit dem BlockOnArchiveFailure **-** Parameter verhindert.</span><span class="sxs-lookup"><span data-stu-id="908cd-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="908cd-119">Mit dem folgenden Befehl wird beispielsweise die Kommunikation im Fall eines Archivierungs Fehlers deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="908cd-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="908cd-120">Mit dem nächsten Befehl kann die Kommunikation bei einem Archivierungsfehler aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="908cd-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="908cd-121">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="908cd-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

