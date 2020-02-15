---
title: Erstellen einer Dateifreigabe in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe im Rahmen der Installation von Skype for Business Server erstellen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028296"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="e8ab8-104">Erstellen einer Dateifreigabe in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8ab8-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="e8ab8-105">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe im Rahmen der Installation von Skype for Business Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="e8ab8-106">Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)unter: herunter.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="e8ab8-107">Skype for Business Server erfordert eine Dateifreigabe, sodass Computer in der gesamten Topologie Dateien austauschen können.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="e8ab8-108">Das Erstellen einer Dateifreigabe ist der Schritt 2 von 8 im Installationsprozess für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="e8ab8-109">Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="e8ab8-110">Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge ausführen, und nach den Schritten 1 bis 5, wie im Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="e8ab8-111">Informationen zur Planung von Details zur Dateifreigabe finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ab8-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Übersicht Diagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="e8ab8-113">Erstellen einer einfachen Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="e8ab8-113">Create a basic file share</span></span>

<span data-ttu-id="e8ab8-114">In diesem Abschnitt erfahren Sie, wie Sie eine grundlegende Windows Server-Dateifreigabe erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="e8ab8-115">Eine grundlegende Windows Server-Dateifreigabe wird mit Skype for Business Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="e8ab8-116">Es bietet jedoch nicht explizit hohe Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="e8ab8-117">Für eine Umgebung mit hoher Verfügbarkeit wird eine DFS-Dateifreigabe (Distributed File System) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="e8ab8-118">Weitere Informationen zu einer Dateifreigabe mit hoher Verfügbarkeit und zu DFS finden Sie unter [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e8ab8-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8ab8-119">Windows Server 2012 R2 hat bei der Bereitstellung von San-basierten Dateifreigabe Lösungen (Storage Area Network) mit der Windows Server-Plattform große Fortschritte gemacht.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="e8ab8-120">Im Vergleich zu einer herkömmlichen SAN-basierten Appliance kann eine Windows Server 2012 R2-Speicherlösung die Kosten in der Hälfte reduzieren und die Leistung nur sehr geringfügig beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="e8ab8-121">Weitere Informationen zu Dateifreigabeoptionen in Windows Server 2012 R2 finden Sie im herunterladbaren Whitepaper [Windows Server 2012 R2-Speicher](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="e8ab8-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="e8ab8-122">Sehen Sie sich die Video Schritte zum **Erstellen einer Dateifreigabe**an:</span><span class="sxs-lookup"><span data-stu-id="e8ab8-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="e8ab8-123">Erstellen einer einfachen Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="e8ab8-123">Create a basic file share</span></span>

1. <span data-ttu-id="e8ab8-124">Melden Sie sich an dem Computer an, auf dem die Dateifreigabe gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="e8ab8-125">Klicken Sie mit der rechten Maustaste auf den Ordner, den Sie freigeben möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="e8ab8-126">Wählen Sie die Registerkarte **Freigabe** aus, und klicken Sie auf **Erweiterte Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="e8ab8-127">Klicken Sie auf **diesen Ordner freigeben**.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="e8ab8-128">Klicken Sie auf **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="e8ab8-129">Fügen Sie die lokale Gruppe **Administratoren** des Servers hinzu, der die Dateifreigabe hostet, Grant **Allow: Vollzugriff, Änderungen und Lese** Berechtigungen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="e8ab8-130">Klicken Sie erneut auf **OK** , und notieren Sie sich den Netzwerkpfad.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="e8ab8-131">Klicken Sie auf **Fertig** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-131">Click **Done** to close the wizard.</span></span>
    
     ![Registerkarte Freigabe für die Freigabe eines Ordners.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="e8ab8-133">Wenn der Dateispeicher in einer DFS-Freigabe gehostet wird, wird die folgende Warnung empfangen:</span><span class="sxs-lookup"><span data-stu-id="e8ab8-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="e8ab8-134">Warnung: auf Freigabeberechtigungen für "\\<domain>\<Share>" kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="e8ab8-135">Dies wird erwartet, wenn Sie kein Administrator auf dem Dateiserver sind oder wenn es sich um eine DFS-Freigabe (Distributed File System) handelt.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="e8ab8-136">Wenn die Freigabeberechtigungen bereits konfiguriert wurden, kann diese Warnung ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="e8ab8-137">Wenn es sich um eine neue Freigabe handelt, lesen Sie in der Dokumentation ausführliche Informationen zur manuellen Konfiguration von Freigabeberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="e8ab8-138">Aufgrund der Unfähigkeit, auf die Freigabeberechtigungen für eine DFS-Freigabe zuzugreifen, können Skype for Business Server Gruppen nicht explizit auf der Dateifreigabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="e8ab8-139">Um sicherzustellen, dass Skype for Business Server Komponenten mit den entsprechenden Berechtigungen auf die Dateifreigabe zugreifen können, stellen Sie sicher, dass die folgenden RTC-Gruppen zusätzlich zu den lokalen Administratoren mit der Vollzugriff-Freigabe mit Lese-und Änderungs Ebenen-Freigabeberechtigungen hinzugefügt werden. Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="e8ab8-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="e8ab8-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ab8-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="e8ab8-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e8ab8-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="e8ab8-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e8ab8-142">RTCUniversalServerAdmins</span></span>
