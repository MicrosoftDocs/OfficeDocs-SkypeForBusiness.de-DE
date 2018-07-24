---
title: Aktivieren Sie oder deaktivieren Sie der Archivierung in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Zusammenfassung: Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server.'
ms.openlocfilehash: a0d32a3bacb604c326db13034bf5315c7f3d4d99
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965891"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="8429e-103">Aktivieren Sie oder deaktivieren Sie der Archivierung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8429e-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="8429e-104">**Zusammenfassung:** Informationen Sie zum Aktivieren oder Deaktivieren der Archivierung in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="8429e-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="8429e-105">Aktivieren oder Deaktivieren der Archivierung mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="8429e-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="8429e-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8429e-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8429e-107">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8429e-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8429e-108">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8429e-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="8429e-109">Wählen Sie in der Liste der Archivierungskonfigurationen die entsprechende globale Konfiguration, Standortkonfiguration oder Poolkonfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen** und führen Sie dann die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8429e-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="8429e-110">Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8429e-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="8429e-111">Klicken Sie auf **IM- und Konferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="8429e-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="8429e-112">Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Konfiguration zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8429e-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="8429e-113">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8429e-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="8429e-114">Aktivieren oder Deaktivieren der Archivierung mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8429e-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="8429e-115">Sie können die Archivierung außerdem mithilfe des **Set-CsArchivingConfiguration**-Cmdlet aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8429e-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="8429e-116">Mithilfe des folgenden Befehls werden beispielsweise alle Archivierungskonfigurationseinstellungen geändert, sodass nur Chatsitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8429e-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="8429e-117">Der Befehl ruft das Cmdlet **Get-CsArchivingConfiguration** ohne Parameter, um alle archivierungskonfigurationseinstellungen, die derzeit in der Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8429e-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="8429e-118">Diese Auflistung wird dann an das Cmdlet **Where-Object** -Cmdlet, die nur diese Einstellungen auswählt, in dem die EnableArchiving-Eigenschaft gleich ist (-Eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="8429e-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="8429e-119">Gefilterte Auflistung wird dann an das Cmdlet **Set-CsArchivingConfiguration** weitergeleitet das nimmt jedes Element in der Auflistung und den Wert der EnableArchiving in "ImOnly" geändert:</span><span class="sxs-lookup"><span data-stu-id="8429e-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```