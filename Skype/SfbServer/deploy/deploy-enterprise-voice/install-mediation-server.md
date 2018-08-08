---
title: Installieren der Dateien für den Vermittlungsserver in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Zusammenfassung: Informationen Sie zum Installieren der Dateien für den Vermittlungsserver in Skype für Business Server.'
ms.openlocfilehash: b3314e5443a7aa881fa849fd3e3b5b639f72664e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002481"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="30c76-103">Installieren der Dateien für den Vermittlungsserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="30c76-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="30c76-104">**Zusammenfassung:** Informationen Sie zum Installieren der Dateien für den Vermittlungsserver in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="30c76-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="30c76-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe „RTCUniversalReadOnlyAdmins“ ist.</span><span class="sxs-lookup"><span data-stu-id="30c76-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="30c76-106">Verwenden Sie die Schritte in diesem Thema ausführen Skype für Business Server-Bereitstellungs-Assistenten zum Installieren der Dateien für den Vermittlungsserver auf einem Computer, die Sie in einen Pool Mediation Server hinzugefügt haben, nachdem Sie der Topologie-Generator zum Definieren und veröffentlichen den Pool verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="30c76-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="30c76-107">Bei der Installation von Dateien Mediation Server auch installieren und Zuweisen des Zertifikats von jedem Computer in einem Pool Mediation Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30c76-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="30c76-108">In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen vermittlungsserverpool in Ihrer Topologie veröffentlicht und definiert, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server](deploy-a-mediation-server.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30c76-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="30c76-109">So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool</span><span class="sxs-lookup"><span data-stu-id="30c76-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="30c76-110">Dem Installationsmedium mit der rechten Maustaste _ \<-Installationsmedium\> _ **\Setup\amd64\Setup.exe**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="30c76-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="30c76-111">Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="30c76-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="30c76-p102">Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** und klicken Sie anschließend auf **OK**. (Dieser Schritt ist erforderlich, um fortfahren zu können.)</span><span class="sxs-lookup"><span data-stu-id="30c76-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="30c76-114">Klicken Sie auf der Seite **Skype für Business Server-Bereitstellungs-Assistenten** auf **installieren oder aktualisieren Skype für Business Server-System**.</span><span class="sxs-lookup"><span data-stu-id="30c76-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="30c76-115">Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="30c76-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="30c76-116">Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="30c76-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="30c76-117">Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="30c76-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="30c76-118">Neben **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Ausführen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="30c76-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="30c76-119">Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="30c76-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="30c76-p103">Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm und übernehmen Sie die Standardeinstellungen. Da der Vermittlungsserver ein Zertifikat benötigt, müssen Sie **Schritt 3** zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="30c76-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="30c76-123">Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="30c76-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="30c76-124">Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu und melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ an.</span><span class="sxs-lookup"><span data-stu-id="30c76-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="30c76-125">Auf dem Computer, auf dem Sie Skype Business Server-Systemsteuerung ausführen, vergewissern Sie sich auf der Seite **Topologie** von Skype Business Server-Systemsteuerung, die der Status des Vermittlungsservers als ein grünes Häkchen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="30c76-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="30c76-126">Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus.</span><span class="sxs-lookup"><span data-stu-id="30c76-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="30c76-127">Klicken Sie im Menü **Aktion** auf **Alle Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="30c76-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="30c76-128">Wenn Sie mehrere Computer auf den Pool Mediation Server hinzugefügt haben, führen Sie die Schritte aus, in diesem Verfahren auf allen anderen Computern im Pool Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="30c76-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="30c76-129">Wenn Sie keine Dateien für den Vermittlungsserver für alle anderen Computern installieren müssen, führen Sie die Verfahren in [Configure-Trunks in Skype für Business Server](configure-trunks.md) konfigurieren Sie Einstellungen für die trunkverbindung zwischen diesen Mediation Server-Pool (oder alle Vermittlungsserver Server an einem Standort) und seinen Peer.</span><span class="sxs-lookup"><span data-stu-id="30c76-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

