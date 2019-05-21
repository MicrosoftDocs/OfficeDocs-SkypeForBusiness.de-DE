---
title: Installieren des lokalen Konfigurationsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Um mit der Installation eines neuen Skype for Business Server-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL Server installieren, der den lokalen Konfigurationsspeicher hosten soll. Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS).
ms.openlocfilehash: 699294889008f0d353e1ba727cbc078f9616f4ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303404"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="d31d5-104">Lokalen Konfigurationsspeicher installieren</span><span class="sxs-lookup"><span data-stu-id="d31d5-104">Install Local Configuration Store</span></span>

<span data-ttu-id="d31d5-105">Um mit der Installation eines neuen Skype for Business Server-Rollen Servers zu beginnen, müssen Sie zuerst den lokalen SQL Server installieren, der den lokalen Konfigurationsspeicher hosten soll.</span><span class="sxs-lookup"><span data-stu-id="d31d5-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="d31d5-106">Der lokale Konfigurationsspeicher fungiert als schreibgeschütztes Replikat des Skype for Business Server Central-Verwaltungsspeichers (CMS).</span><span class="sxs-lookup"><span data-stu-id="d31d5-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="d31d5-107">Sie müssen auf dem Server, auf dem Sie den Schritt **Lokalen Konfigurationsspeicher installieren** ausführen, als lokaler Administrator angemeldet sein und Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein.</span><span class="sxs-lookup"><span data-stu-id="d31d5-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="d31d5-108">Wenn Sie das Setup auf einem Edgeserver ausführen, müssen Sie kein Mitglied der Gruppe „RTCUniversalServerAdmins“ oder „RTCUniversalGlobalReadOnlyGroup“ sein.</span><span class="sxs-lookup"><span data-stu-id="d31d5-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="d31d5-109">Das Definitions Dokument für das Topologie-Builder wird aus dem exportierten Definitions Dokument anstatt aus dem zentralen Verwaltungsspeicher gelesen.</span><span class="sxs-lookup"><span data-stu-id="d31d5-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="d31d5-110">Informationen zum Exportieren des Definitions Dokuments für das Topologie-Builder und zur Bereitstellung für die Edgeserver finden Sie im Thema[Exportieren der Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="d31d5-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="d31d5-111">So starten Sie die Installation:</span><span class="sxs-lookup"><span data-stu-id="d31d5-111">To begin the installation:</span></span>

1. <span data-ttu-id="d31d5-112">Klicken Sie auf der Seite Skype for Business Server neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d31d5-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="d31d5-113">Vergewissern Sie sich auf der Seite **Lokale Serverkonfiguration**, dass die Option **Konfiguration automatisch aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d31d5-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="d31d5-114">Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d31d5-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="d31d5-115">Die Installation des lokalen SQL-Servers kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d31d5-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="d31d5-116">Auf dem Bildschirm "Installationszusammenfassung" werden keine Aktualisierungen des Status angezeigt, während SQL Server installiert wird.</span><span class="sxs-lookup"><span data-stu-id="d31d5-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="d31d5-117">Wenn Sie den Status der Installation überwachen möchten, verwenden Sie den Task-Manager, um das SQL Server-Setup zu sehen.</span><span class="sxs-lookup"><span data-stu-id="d31d5-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


