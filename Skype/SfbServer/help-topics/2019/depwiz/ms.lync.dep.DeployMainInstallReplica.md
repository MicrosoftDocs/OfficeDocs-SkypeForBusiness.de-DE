---
title: Installieren des lokalen Konfigurationsspeichers
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Um die Installation von einer neuen Skype für Business Server Role Server beginnen, müssen Sie zuerst den lokalen SQL Server installieren, auf denen den lokale Konfigurationsspeicher gehostet wird. Der lokale Konfigurationsspeicher fungiert als ein Replikat der Skype für Business Server zentralen Verwaltungsspeicher (CMS) schreibgeschützt.
ms.openlocfilehash: 1aa0e033991c91edd0ff6eef225d357fd9ff0e95
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260685"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="4416f-104">Installieren des lokalen Konfigurationsspeichers</span><span class="sxs-lookup"><span data-stu-id="4416f-104">Install Local Configuration Store</span></span>

<span data-ttu-id="4416f-105">Um die Installation von einer neuen Skype für Business Server Role Server beginnen, müssen Sie zuerst den lokalen SQL Server installieren, auf denen den lokale Konfigurationsspeicher gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4416f-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="4416f-106">Der lokale Konfigurationsspeicher fungiert als ein Replikat der Skype für Business Server zentralen Verwaltungsspeicher (CMS) schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="4416f-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="4416f-107">Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein.</span><span class="sxs-lookup"><span data-stu-id="4416f-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="4416f-108">Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein.</span><span class="sxs-lookup"><span data-stu-id="4416f-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="4416f-109">Topologie-Generator Definition Dokument wird aus dem Dokument exportierten Definition statt aus dem zentralen Verwaltungsspeicher gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="4416f-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="4416f-110">Exportieren Sie das Dokument der Topologie-Generator-Definition und für den Edge-Servern verfügbar machen, finden im Thema[Your Topology exportieren und kopieren Sie es auf externe Medien zur Edgeinstallation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="4416f-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="4416f-111">So starten Sie die Installation:</span><span class="sxs-lookup"><span data-stu-id="4416f-111">To begin the installation:</span></span>

1. <span data-ttu-id="4416f-112">Klicken Sie auf die Skype für Business Server-Seite neben **Schritt 1: lokalen Konfigurationsspeicher installieren**, klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4416f-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="4416f-113">Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4416f-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="4416f-114">Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4416f-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="4416f-115">Die Installation von der lokalen SQL Server kann eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="4416f-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="4416f-116">Updates werden nicht auf Fortschritte bei der Installation im Fenster Zusammenfassung angezeigt werden, während SQL Server installiert wird.</span><span class="sxs-lookup"><span data-stu-id="4416f-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="4416f-117">Wenn Sie den Status der Installation überwachen möchten, verwenden Sie Task-Manager überwachen das SQL Server-Setup.</span><span class="sxs-lookup"><span data-stu-id="4416f-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


