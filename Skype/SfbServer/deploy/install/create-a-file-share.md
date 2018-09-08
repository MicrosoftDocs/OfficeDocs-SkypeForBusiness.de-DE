---
title: Erstellen Sie eine Dateifreigabe in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Windows Server-Dateifreigabe als Teil der Installation von Skype für Business Server erstellen. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a6a040c60d3c5a41df8dfa24abd5948d85180f2e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884621"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="a795b-104">Erstellen Sie eine Dateifreigabe in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a795b-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="a795b-105">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe als Teil der Installation von Skype für Business Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="a795b-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="a795b-106">Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="a795b-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a795b-107">Skype für Business Server erfordert eine Dateifreigabe, damit Computer in der Topologie, Dateien austauschen können.</span><span class="sxs-lookup"><span data-stu-id="a795b-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="a795b-108">Erstellen einer Dateifreigabe ist Schritt 2 von 8 in den Installationsvorgang für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="a795b-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="a795b-109">Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="a795b-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="a795b-110">Sie müssen jedoch die Schritte 6, 7 und 8 der Reihe nach ausführen, und zwar nach den Schritten 1 bis 5, wie im Diagramm beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a795b-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="a795b-111">Planen von Details zu Dateifreigabe, finden Sie unter [umgebungsanforderungen für Skype für Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server-Anforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a795b-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Übersichtsdiagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="a795b-113">Erstellen einer grundlegenden Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="a795b-113">Create a basic file share</span></span>

<span data-ttu-id="a795b-114">In diesem Abschnitt werden die Schritte zur Erstellung einer Standarddateifreigabe für Windows Server erläutert.</span><span class="sxs-lookup"><span data-stu-id="a795b-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="a795b-115">Eine grundlegende Windows Server-Dateifreigabe wird mit Skype für Business Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a795b-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="a795b-116">Allerdings bietet nicht explizit hohen Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="a795b-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="a795b-117">Für eine solche Umgebung wird eine Dateifreigabe mithilfe von DFS (Distributed File System) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a795b-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="a795b-118">Weitere Informationen über eine Dateifreigabe für hohe Verfügbarkeit und DFS finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a795b-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a795b-119">Windows Server 2012 R2 hat große Fortschritte bei der Bereitstellung Storage Area Network (SAN)-artiger Dateifreigabelösungen auf der Windows Server-Plattform erzielt.</span><span class="sxs-lookup"><span data-stu-id="a795b-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="a795b-120">Im Vergleich zu einem herkömmlichen System auf SAN-Basis kann eine Windows Server 2012 R2-Speicherlösung die Kosten bei kaum spürbaren Leistungseinbußen auf die Hälfte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="a795b-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="a795b-121">Weitere Informationen zu den Optionen für Freigabe in Windows Server 2012 R2 finden Sie unter einem herunterladbaren Whitepaper [Windows Server 2012 R2-Speicher](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="a795b-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="a795b-122">Sehen Sie sich im Video die Schritte zum **Erstellen einer Dateifreigabe** an:</span><span class="sxs-lookup"><span data-stu-id="a795b-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="a795b-123">Erstellen einer grundlegenden Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="a795b-123">Create a basic file share</span></span>

1. <span data-ttu-id="a795b-124">Melden Sie sich bei dem Computer an, der die Dateifreigabe hosten soll.</span><span class="sxs-lookup"><span data-stu-id="a795b-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="a795b-125">Klicken Sie mit der rechten Maustaste auf den Ordner, den Sie freigegeben möchten, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a795b-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="a795b-126">Wählen Sie die Registerkarte **Freigabe** aus und klicken Sie auf **Erweiterte Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="a795b-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="a795b-127">Klicken Sie auf **Diesen Ordner freigeben**.</span><span class="sxs-lookup"><span data-stu-id="a795b-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="a795b-128">Klicken Sie auf **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="a795b-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="a795b-129">Fügen Sie die Gruppe lokaler **Administratoren** des Servers hinzu, der die Dateifreigabe hostet, erteilen Sie die Berechtigungen **Einräumen: Vollzugriff, Ändern und Lesen** und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a795b-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="a795b-130">Klicken Sie erneut auf **OK** und notieren Sie sich den Netzwerkpfad.</span><span class="sxs-lookup"><span data-stu-id="a795b-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="a795b-131">Klicken Sie auf **Fertig**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a795b-131">Click **Done** to close the wizard.</span></span>
    
     ![Registerkarte „Freigabe“ zur Ordnerfreigabe.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

