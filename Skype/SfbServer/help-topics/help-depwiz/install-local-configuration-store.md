---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Um mit der Installation eines neuen Skype for Business Server 2015-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL-Server installieren, der den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS). Sie müssen auf dem Server, auf dem Sie den Schritt Lokalen Konfigurationsspeicher installieren ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein. Das Definitions Dokument für das Topologie-Builder wird aus dem exportierten Definitions Dokument anstatt aus dem zentralen Verwaltungsspeicher gelesen. Informationen zum Exportieren des Definitions Dokuments für das Topologie-Builder und zur Bereitstellung für die Edgeserver finden Sie im Thema Exportieren der Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation.
ms.openlocfilehash: 7908a862a01871988d6afe6ae1b0cf9c752e9d30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823619"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="af3ef-108">Lokalen Konfigurationsspeicher installieren</span><span class="sxs-lookup"><span data-stu-id="af3ef-108">Install Local Configuration Store</span></span>

<span data-ttu-id="af3ef-109">Um mit der Installation eines neuen Skype for Business Server 2015-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL-Server installieren, der den lokalen Konfigurationsspeicher hosten soll.</span><span class="sxs-lookup"><span data-stu-id="af3ef-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="af3ef-110">Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS).</span><span class="sxs-lookup"><span data-stu-id="af3ef-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="af3ef-111">Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein.</span><span class="sxs-lookup"><span data-stu-id="af3ef-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="af3ef-112">Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein.</span><span class="sxs-lookup"><span data-stu-id="af3ef-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="af3ef-113">Das Definitions Dokument für das Topologie-Builder wird aus dem exportierten Definitions Dokument anstatt aus dem zentralen Verwaltungsspeicher gelesen.</span><span class="sxs-lookup"><span data-stu-id="af3ef-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="af3ef-114">Informationen zum Exportieren des Definitions Dokuments für das Topologie-Builder und zur Bereitstellung für die Edgeserver finden Sie im Thema [Exportieren der Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="af3ef-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="af3ef-115">So starten Sie die Installation:</span><span class="sxs-lookup"><span data-stu-id="af3ef-115">To begin the installation:</span></span>

1. <span data-ttu-id="af3ef-116">Klicken Sie auf der Seite Skype for Business Server 2015 neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="af3ef-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="af3ef-117">Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af3ef-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="af3ef-118">Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="af3ef-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="af3ef-119">Die Installation des lokalen SQL-Servers kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="af3ef-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="af3ef-120">Auf dem Bildschirm "Installationszusammenfassung" werden keine Aktualisierungen des Status angezeigt, während SQL Server installiert wird.</span><span class="sxs-lookup"><span data-stu-id="af3ef-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="af3ef-121">Wenn Sie den Status der Installation überwachen möchten, verwenden Sie den Task-Manager, um das SQL Server-Setup zu sehen.</span><span class="sxs-lookup"><span data-stu-id="af3ef-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


