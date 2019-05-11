---
title: Aktivieren Sie oder deaktivieren Sie der Archivierung in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Zusammenfassung: Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server.'
ms.openlocfilehash: 27cb7aab08c6a85f21e058848963bb42de6e1635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885031"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="11463-103">Aktivieren Sie oder deaktivieren Sie der Archivierung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="11463-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="11463-104">**Zusammenfassung:** Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="11463-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="11463-105">Aktivieren oder Deaktivieren der Archivierung mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="11463-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="11463-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="11463-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="11463-107">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11463-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="11463-108">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="11463-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="11463-109">Wählen Sie in der Liste der Archivierungskonfigurationen die entsprechende globale Konfiguration, Standortkonfiguration oder Poolkonfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen** und führen Sie dann die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11463-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="11463-110">Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="11463-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="11463-111">Klicken Sie auf **IM- und Konferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="11463-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="11463-112">Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Konfiguration zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="11463-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="11463-113">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="11463-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="11463-114">Aktivieren oder Deaktivieren der Archivierung mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11463-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="11463-115">Sie können die Archivierung außerdem mithilfe des **Set-CsArchivingConfiguration**-Cmdlet aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="11463-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="11463-116">Mithilfe des folgenden Befehls werden beispielsweise alle Archivierungskonfigurationseinstellungen geändert, sodass nur Chatsitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="11463-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="11463-117">Der Befehl ruft das **Get-CsArchivingConfiguration**-Cmdlet ohne Parameter auf, um alle derzeit in der Organisation verwendeten Archivierungskonfigurationseinstellungen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="11463-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="11463-118">Diese Auflistung wird dann an das **Where-Object**-Cmdlet weitergeleitet, das nur die Einstellungen auswählt, bei denen die Eigenschaft „EnableArchiving“ den Wert „ImAndWebConf“ aufweist (der Vergleichsoperator „-eq“ steht für „equal to“).</span><span class="sxs-lookup"><span data-stu-id="11463-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="11463-119">Die Auflistung wird dann an das **Set-CsArchivingConfiguration**-Cmdlet weitergeleitet, das für jedes Element in der Auflistung die Eigenschaft „EnableArchiving“ auf „ImOnly“ festlegt:</span><span class="sxs-lookup"><span data-stu-id="11463-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
