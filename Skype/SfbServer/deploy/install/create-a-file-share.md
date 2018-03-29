---
title: Erstellen einer Dateifreigabe in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Zusammenfassung: Erfahren Sie, wie eine Windows Server-Dateifreigabe als Teil der Installation von Skype für Business Server 2015 zu erstellen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 697325cbe7616ca82734895e1af4922aeb580068
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a><span data-ttu-id="04b86-104">Erstellen einer Dateifreigabe in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="04b86-104">Create a file share in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="04b86-105">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Windows Server-Dateifreigabe als Teil der Installation von Skype für Business Server 2015 erstellen.</span><span class="sxs-lookup"><span data-stu-id="04b86-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="04b86-106">Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="04b86-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="04b86-107">Skype für Business Server erfordert eine Dateifreigabe, damit Computer in der Topologie, Dateien austauschen können.</span><span class="sxs-lookup"><span data-stu-id="04b86-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="04b86-108">Erstellen einer Dateifreigabe ist Schritt 2 von 8 in den Installationsvorgang für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="04b86-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span></span> <span data-ttu-id="04b86-109">Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="04b86-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="04b86-110">Sie müssen jedoch die Schritte 6, 7 und 8 der Reihe nach ausführen, und zwar nach den Schritten 1 bis 5, wie im Diagramm beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04b86-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="04b86-111">Planen von Details zu Dateifreigabe, finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04b86-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![Übersichtsdiagramm](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="04b86-113">Erstellen einer grundlegenden Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="04b86-113">Create a basic file share</span></span>

<span data-ttu-id="04b86-114">In diesem Abschnitt werden die Schritte zur Erstellung einer Standarddateifreigabe für Windows Server erläutert.</span><span class="sxs-lookup"><span data-stu-id="04b86-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="04b86-115">Eine grundlegende Windows Server-Dateifreigabe wird mit Skype für Business Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="04b86-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="04b86-116">Allerdings bietet nicht explizit hohen Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="04b86-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="04b86-117">Für eine solche Umgebung wird eine Dateifreigabe mithilfe von DFS (Distributed File System) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="04b86-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="04b86-118">Weitere Informationen über eine Dateifreigabe für hohe Verfügbarkeit und DFS finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="04b86-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="04b86-119">Windows Server 2012 R2 hat große Fortschritte bei der Bereitstellung Storage Area Network (SAN)-artiger Dateifreigabelösungen auf der Windows Server-Plattform erzielt.</span><span class="sxs-lookup"><span data-stu-id="04b86-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="04b86-120">Im Vergleich zu einem herkömmlichen System auf SAN-Basis kann eine Windows Server 2012 R2-Speicherlösung die Kosten bei kaum spürbaren Leistungseinbußen auf die Hälfte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="04b86-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="04b86-121">Weitere Informationen zu den Optionen für Freigabe in Windows Server 2012 R2 finden Sie unter einem herunterladbaren Whitepaper [Windows Server 2012 R2-Speicher](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="04b86-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="04b86-122">Sehen Sie sich im Video die Schritte zum **Erstellen einer Dateifreigabe** an:</span><span class="sxs-lookup"><span data-stu-id="04b86-122">Watch the video steps for **create a file share**:</span></span>
  
![Ihr Browser unterstützt kein Video. Installieren von Microsoft Silverlight, Adobe Flash Player oder Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="04b86-125">Erstellen einer grundlegenden Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="04b86-125">Create a basic file share</span></span>

1. <span data-ttu-id="04b86-126">Melden Sie sich bei dem Computer an, der die Dateifreigabe hosten soll.</span><span class="sxs-lookup"><span data-stu-id="04b86-126">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="04b86-127">Klicken Sie mit der rechten Maustaste auf den Ordner, den Sie freigegeben möchten, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="04b86-127">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="04b86-128">Wählen Sie die Registerkarte **Freigabe** aus und klicken Sie auf **Erweiterte Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="04b86-128">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="04b86-129">Klicken Sie auf **Diesen Ordner freigeben**.</span><span class="sxs-lookup"><span data-stu-id="04b86-129">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="04b86-130">Klicken Sie auf **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="04b86-130">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="04b86-131">Fügen Sie die Gruppe lokaler **Administratoren** des Servers hinzu, der die Dateifreigabe hostet, erteilen Sie die Berechtigungen **Einräumen: Vollzugriff, Ändern und Lesen** und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="04b86-131">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="04b86-132">Klicken Sie erneut auf **OK** und notieren Sie sich den Netzwerkpfad.</span><span class="sxs-lookup"><span data-stu-id="04b86-132">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="04b86-133">Klicken Sie auf **Fertig**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="04b86-133">Click **Done** to close the wizard.</span></span>
    
     ![Registerkarte „Freigabe“ zur Ordnerfreigabe.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

